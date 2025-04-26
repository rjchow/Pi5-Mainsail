Pi5-Mainsail

Simple Guide to setting up Mainsail OS on a Raspberry Pi 5 using RPI and Kiauh via SSH
1. Flash SD with Raspberry Pi OS Lite
a. Install and open official Raspberry Pi Imager

    Raspberry Pi Imager

b. Select:

    Device: Raspberry Pi 5
    OS: Raspberry Pi OS (other) > Raspberry Pi OS Lite (64-bit)
    Storage: [YOUR_SD_CARD_NAME]

c. Customize settings and flash firmware

    Click "Next" on RPI Imager
    Click "Edit Settings"
    Enable "Set hostname" and change hostname as desired
    Set Username and password
    If using WiFi: Enable and set SSID and Password for your network, then select correct country
    Enable and set locale settings
    Navigate to "Services" tab and enable SSH with password authentication (or pub-key authentication)
    Click "Save" at the bottom
    Click "yes" to apply OS customization settings
    Click "yes" to erase all data on SD if prompted
    Wait for OS to write and verify
    Safely remove SD and install on Pi 5

d. SSH into the Pi 5

    Open your terminal of choice:
    - Mac/Linux: use built-in Terminal
    - Windows: use PuTTY or Windows Terminal

    If using Terminal (Mac/Linux):
    ssh <username>@<hostname>.local

    Example:
    ssh pi@pi5mainsail.local

    Accept any SSH key prompt by typing `yes`.

    Enter your password when prompted.

e. Update your Raspberry Pi OS

    Once logged in, immediately update the system by running:

    sudo apt update && sudo apt upgrade -y
    sudo reboot

    After reboot, SSH back in the same way.

f. Install Klipper Installation And Update Helper (KIAUH)

    Install required packages:
    sudo apt install git curl -y

    Download and run KIAUH:
    
    cd ~
    git clone https://github.com/dw-0/kiauh.git
    cd kiauh
    ./kiauh.sh


g. Use KIAUH Menu to Install Klipper, Moonraker, and Mainsail:
    - Choose:
      - Install Klipper
      - Install Moonraker
      - Install Mainsail (or Fluidd if you prefer)
    Follow on-screen prompts

h. Done!

Once installed, you can access your Mainsail dashboard from your web browser at:

```bash
http://<hostname>.local
```
or
```bash
http://<raspberrypi_ip_address>
```
