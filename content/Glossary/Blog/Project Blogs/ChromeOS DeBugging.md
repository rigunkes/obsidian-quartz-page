
# Session 1: Underestimation

The story starts with my friend asking me about what laptop he should buy and that he was looking at chromebooks because they are a good budget option. I said, "Hell Yeah! buy it and ill put Linux on it for ya, *It shouldn't be too hard*".

So he bought it and he came over to my place and the work had begun..

We started with understanding the ChromeOS firmware. The laptop Chromebook that we worked on was called "Acer Chromebook Plus 514". Since the Chromebook has a unique keyboard layout we learned a few hotkeys for debugging. mainly "esc + refresh" while powering on to enter the pre-boot environment. It had a total of three options, all being useless. This is when we learned about another hotkey "ctrl + D" this hotkey combo enable developer mode. 5 minutes later of waiting for it to load developer mode, we were in. I entered the terminal with the hotkey "ctrl + alt + refresh" with root access and enabled external USB booting(the terminal has a short blurb on how to do this when you open it). Then I restarted the device and used the hotkey "ctrl + u" to boot from my USB flash tool with an ubuntu image. It did not work. "No valid image detected" this was a screen that I would be seeing quite often.

Around this time is when I found out about [Mr.Chromebox](https://docs.mrchromebox.tech/) . Mr. Chromebox is a documentation site for how to remove write protection on Chromebook firmware. It took me around 2 or 3 hours to learn that the Chromebook is write protected. Mr. Chromebox has scripts to check the write protection, so I tried to use that and enable RW_LEGACY which allows dual booting. But that didn't work and even if it did, it's not the solution we were looking for. I searched up our device in the list of [Supported Devices](https://docs.mrchromebox.tech/docs/supported-devices.html). The device we used had a model code (CB514-4H). We need to have a UEFI full ROM to be able to install ubuntu. This device has that capability. BUT we need to disable write protection with a SuzyQ to overwrite the Ti50 chip since it is one of the newer models.

What's SuzyQ?
It is a debug USB tool that is plugged into the Chromebook to enable certain debugging software tools that won't work without it(It costs $6 on eBay). I bought mine from [chocolateloverraj](https://github.com/ChocolateLoverRaj/gsc-debug-board) , who also provides documentation on their [github](https://github.com/ChocolateLoverRaj/gsc-debug-board).

What is Ti50?
It is a write protection firmware chip provided on Chromebooks from the year 2023 and newer. Older Chromebooks have different ways to write protect their firmware on the board(such as a screw or jumper connectors). The Ti50 requires the use of CCD

What is CCD?
it is Closed Case Debugging. Using the SuzyQ to enable software tools to disable WP(write protection). Essentially being able to disable WP without *opening the case*.

At this point in the day I did not have a SuzyQ cable, I had been troubleshooting for about 5 hours and I was *tired*. So I ordered the tool and scheduled to meet my friend with his laptop about a week later when it arrived.


# Session 2: Terminal Hell

Beginning again, fresh mind and optimism. "All I needed was the cable and now I can do it easy peasy". I got the SuzyQ plugged it in, and.... it didn't work. I check Mr. Chromebox, no help. I check chocolateloverraj's GitHub, and there is a command that you can run in the terminal to check for new external devices every second. I run the command and it displays nothing even though the device is plugged in. raj says that I may need to try different ports or flip the connector. So I do and eventually I find the right orientation and it works.

Now I go back to Mr. Chromebox and begin CCD. First I must [Enable CCD](https://docs.mrchromebox.tech/docs/firmware/wp/disabling.html#step-1-enabling-closed-case-debugging-ccd) then run all the [commands](https://docs.mrchromebox.tech/docs/firmware/wp/disabling.html#step-2-disabling-write-protection). I do so and I verify if WP is disabled. The verification failed and it did not work. I retried 3-5 times before coming to the conclusion that I am missing something. 

I read through Mr. Chromebox's documentation, online forums and reddit posts trying methods such as disconnecting the battery and re-enabling CCD, I try special commands and a multitude of things. I got so lost in band-aid solutions that I ignored the *real problem*. I need to understand how the debug works.

I plug the battery in, plug in the charger, plug in the SuzyQ into the USB-C port and attach the other end of the cable to the USB-A port. I start from scratch, enable CCD. Re-enter Developer mode, enter the terminal, enable external boot with usb, run the debug commands to disable write protect, verify the write protect, it verifies, and then [enter the flashrom commands](https://docs.mrchromebox.tech/docs/firmware/wp/disabling.html#disabling-software-write-protection). Now all the changes were successful and the write-protect is disabled, even after restarting the device. Now it is time to write the UEFI firmware onto the Chromebook.

I was able to curl the [Utility Script](https://docs.mrchromebox.tech/docs/fwscript.html#firmware-utility-script) from Mr. Chromebox. This is the actual script that you will run to install UEFI firmware on your Chromebook. UEFI is the boot environment that lets you boot from external USB and non-ChromeOS images(Such as Ubuntu). Run the script and install UEFI following the directions from Mr. Chromebox. Once this completes, you can restart and boot from your USB flash of Linux. At this point, my installation of Ubuntu kept failing when trying to install system files. While running the lite version of Ubuntu, I opened gparted and noticed that the drive had a LVM of the previous OS. I removed the LVM partition and was able to complete the install successfully.

## MISSION ACCOMPLISHED!