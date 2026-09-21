# 9/14/2026 Wired some of the pins for the wireless module!! (1 hr)

Today, I worked on wiring the WiFI+BT chip pins to the CPU. I focused on the data pins for today. I started off with looking at the datasheet for both the chip and the wireless chip. The wireless chip's datasheet was fairly simple, and I understood its clear pin descriptions, but I wish that the same could be said for the processor's. I looked at the processor's datasheet, and it did mention the SDIO interface being supported, but there were no pin descriptions to be found for that. After doing a lot of digging, I decided to ask AI to help me find the pins and it gave me the pin PG0. Now, I went back to the datasheet and looked that pin up, and in the section that listed all the different uses that a GPIO pin could use, saw that the pins were there. Rather than being called SDIO, they were called SDC which is why I could not find them easily. But, after wiring the wireless chip up to the processor, I also wired up the 4 Bluetooth UART pins to the CPU. I had to use UART1 instead of UART0 because I needed a UART that supported a 4-wire interface. Also, while I was looking at the datasheet for the CPU when I was looking for the SDIO data pins, I read something unrelated to those pins, but that turned out to be important, our CPU did not support natively booting from USB and supported booting things from things like SD cards, eMMC, etc.

Lapse: https://lapse.hackclub.com/timelapse/PKg6cDWvifzt

<img width="1257" height="754" alt="image" src="https://github.com/user-attachments/assets/d1e3f85d-c93e-416b-ac2a-47be9ecca212" />

<img width="430" height="635" alt="image" src="https://github.com/user-attachments/assets/f9178fd5-8bd4-4b8b-88be-f5d6c04376a6" />

# 9/15/2026 Added some USB ports + did some more research!! (1 hr)

Today, I did some more research on the USB and also added 2 USB ports to the schematic! I started off with reading over some parts of the datasheet for the H616 and the way that it will boot, and we still do not know how we will get the chip to boot from a USB line which carries the SATA chip. I also added 2 USB ports on the schematic to make use of the 2 unused USB lines on the CPU. I wired them up and then I discussed on a huddle on what we should do, but we got no ideas. I did move the data pins for the SATA SSD from the USB 0 line to the USB1 line since the USB 0 port was USB OTG, where the device would not be the USB host, but the peripheral. We still do not know how to implement USB boot with this, and I hope that we can get this figured out soon! I think that I might focus on finding a way to get the thing to boot from the SSD the next time that I work on this!

Lapse: https://lapse.hackclub.com/timelapse/pt8ENm7_3Prb

<img width="1522" height="609" alt="image" src="https://github.com/user-attachments/assets/6f796cbc-56fc-494d-b2c0-0955a7be2e1f" />

# 9/16/2026 Did a lot more research on booting the H616!! (50 mins)

Today, I could not get too much work as I stressed on finding out a way to get the H616 to boot. There is nothing much to journal about today. All I have currently done for today is a lot of research on a thing called U-Boot which should allow out TV box to be able to boot from USB. We also discussed connecting USB0 to the USB-C power port to allow for data access to the board and be able to program the bootloader via a thing called FEL, which is on our processor. I am going to find a small and cheap SPI flash chip that support our CPU booting from it so that we can have that hold the bootloader that handles booting from USB can boot and then handle booting from USB the next time that I work on this. Hopefully I can get some actual work done on the schematic the next time that I work on this.

Lapse: https://lapse.hackclub.com/timelapse/mCIKFbrVOwVY

<img width="1353" height="517" alt="image" src="https://github.com/user-attachments/assets/4180f8ae-0b35-466a-925a-427b082064d3" />
