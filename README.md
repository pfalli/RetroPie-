# RetroPie Installation Guide

This guide provides step-by-step instructions to install and configure RetroPie on your Raspberry Pi 5, allowing you to emulate retro games from various consoles.

## Requirements

- Raspberry Pi (any model, but Raspberry Pi 3 or 4 recommended for best performance)
- MicroSD card (at least 16 GB, 32 GB recommended)
- USB game controller (recommended for easy navigation)
- USB keyboard (for initial setup)
- Power supply for Raspberry Pi
- HDMI cable (for connecting to a TV or monitor)
- USB stick (for transferring ROMs)
- A computer with internet access (to prepare the SD card and transfer ROMs)

---

## Step 1: Prepare the SD Card

1. **Download the RetroPie Image**  
   Visit the official [RetroPie website](https://retropie.org.uk/download/) and download the correct image for your Raspberry Pi model.

2. **Flash the Image to the SD Card**  
   Use a tool like [Raspberry Pi Imager](https://www.raspberrypi.com/software/) or [Balena Etcher](https://www.balena.io/etcher/) to write the RetroPie image to your microSD card:
   - Insert the SD card into your computer.
   - Open the Imager tool and select the RetroPie image you downloaded.
   - Select your SD card as the target and write the image to the card.

3. **Insert the SD Card into the Raspberry Pi**  
   Once the image has been successfully flashed, eject the SD card and insert it into your Raspberry Pi.

Here a nice step by step instruction to git install RetroPie on the SD Card: https://github.com/danielfreer/raspberrypi5-retropie-setup/tree/main?tab=readme-ov-file

---

## Step 2: Boot the Raspberry Pi

1. **Connect the Raspberry Pi to a Monitor/TV**  
   Use the HDMI cable to connect your Raspberry Pi to your display.
   
2. **Plug in Power and Peripherals**  
   Connect the USB keyboard, game controller, and power supply to your Raspberry Pi. The system will automatically power on and boot into RetroPie.

3. **First-Time Setup**  
   On first boot, you’ll see the EmulationStation setup screen. You can configure your USB game controller by following the on-screen instructions.


## Step 3: Transfer ROMs

### Option A: USB Stick Method (***it didn'twork***) i suggest option B

1. **Prepare the USB Stick**
   - Format a USB stick to FAT32 or exFAT.
   - Create a folder called `retropie` on the USB stick.

2. **Transfer the USB Stick to the Raspberry Pi**
   - Insert the USB stick into the Raspberry Pi while RetroPie is running.
   - Wait for a few minutes (until the USB stick's activity light stops blinking or after a few minutes if no light).
   - Remove the USB stick.

3. **Transfer ROMs from PC to USB**
   - Insert the USB stick into your computer.
   - Inside the `retropie` folder, you will now see additional folders like `roms`.
   - Add your ROM files to the respective console folders (e.g., `roms/snes` for SNES games).

4. **Transfer ROMs to Raspberry Pi**
   - Insert the USB stick back into the Raspberry Pi.
   - Wait for the ROMs to automatically transfer to the SD card.
   - After the transfer is complete, remove the USB stick.

5. **Refresh the Game List**
   - Press `F4` to restart EmulationStation or go to **Start > Quit > Restart EmulationStation** to see your new games.
  
### Option B: Connection with SSH

1.Go on Terminal of your laptop and write: ping "IP address of the rasperrypi"

2.Right-click your “roms” folder and choose “copy as path”

3.Copy over your ROMs with the command:   scp -r <roms folder path>\\* <username>@<pi ip address>:~/RetroPie/roms/

***add the game exactly in the right Console folder (ex: Mario64 inside n64, GodofWar inside playstation1)

---

## Step 5: Play Games

1. **Launch EmulationStation**  
   After transferring the ROMs, restart EmulationStation (press `F4` or reboot the Raspberry Pi).

2. **Select Your Console and Game**  
   Use your game controller to navigate through the EmulationStation menu, select the console, and choose the game you want to play.

---

## Troubleshooting

- If the games don’t appear after transferring the ROMs, ensure that:
  - The ROM files are in the correct folder.
  - The file types are supported by the emulator.
  - You restart EmulationStation after adding new ROMs.
  
- To install additional emulator packages, access the setup script using:
  ```bash
  sudo ./retropie_setup.sh
