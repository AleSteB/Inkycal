# Welcome to inkycal v2.0.3!

<p align="center">
        <img src="https://raw.githubusercontent.com/aceisace/Inkycal/assets/Repo/logo.png" width="900" alt="aceinnolab logo">
</p>
<p align="center">
        <img src="https://github.com/aceinnolab/Inkycal/blob/c1c274878ba81ddaee6186561e6ea892da54cd6a/Repo/inkycal-featured-gif.gif" width="900" alt="featured-image">
</p>

<p align="center">
        <a href="https://github.com/aceinnolab/Inkycal/actions/workflows/test-on-rpi.yml"><img src="https://github.com/aceinnolab/Inkycal/actions/workflows/test-on-rpi.yml/badge.svg"></a>
    <a href="https://github.com/aceinnolab/Inkycal/actions/workflows/update-docs.yml"><img src="https://github.com/aceinnolab/Inkycal/actions/workflows/update-docs.yml/badge.svg"></a>
    <a href="https://github.com/aceinnolab/Inkycal/releases"><img alt="Version" src="https://img.shields.io/github/release/aceisace/Inkycal.svg"/></a>
   <a href="https://github.com/aceinnolab/Inkycal/blob/main/LICENSE"><img alt="Licence" src="https://img.shields.io/github/license/aceisace/Inkycal.svg" /></a>
   <a href="https://github.com/aceinnolab/Inkycal/stargazers"><img alt="GitHub stars" src="https://img.shields.io/github/stars/aceisace/Inkycal?color=yellow"></a>
   <a href="https://github.com/aceinnolab/Inkycal"><img alt="python" src="https://img.shields.io/badge/python-3.11-lightorange"></a>
</p>

Inkycal is a software written in python for selected E-Paper displays. It converts these displays into useful
information dashboards. It's open-source, free for personal use, fully modular and user-friendly. Despite all this,
Inkycal can run well even on the Raspberry Pi Zero. Oh, and it's open for third-party modules! Hooray!

## ⚠️ Warning: long installation time expected!

Starting october 2023, Raspberry Pi OS is now based on Debian bookworm and uses python 3.11 instead of 3.9 as the
default version. Inkycal has been updated to work with python3.11, but the installation of numpy can take a very long
time, in some cases even hours. If you do not want to wait this long to install Inkycal, you can also get a
ready-to-flash version of Inkycal called InkycalOS-Lite with everything pre-installed for you by sponsoring
via [Github Sponsors](https://github.com/sponsors/aceisace). This helps keep up maintenance costs, implement new
features and fixing bugs. Please choose the one-time sponsor option and select the one with the plug-and-play version of
Inkycal. Then, send your email-address to which InkycalOS-Lite should be sent.
Alternatively, you can also use the paypal.me link and send the same amount as Github sponsors to get access to InkycalOS-Lite!

## Main features

Inkycal is fully modular, you can mix and match any modules you like and configure them on the web-ui. For now, these
following built-in modules are supported:

* Calendar - Monthly Calendar with option to sync events from iCalendars, e.g. Google.
* Agenda - Agenda showing upcoming events from given iCalendar URLs.
* Image - Display an Image from URL or local file path.
* Slideshow - Cycle through images in a given folder and show them on the E-Paper.
* Feeds - Synchronise RSS/ATOM feeds from your favorite providers.
* Stocks - Display stocks using Tickers from Yahoo! Finance.
* Weather - Show current weather, daily or hourly weather forecasts from openweathermap.
* Todoist - Synchronise with Todoist app or website to show todos.
* iCanHazDad - Display a random joke from [iCanHazDad.com](iCanhazdad.com).

## Quickstart

Watch the one-minute video on getting started with Inkycal:

[![Inkycal quickstart](https://img.youtube.com/vi/IiIv_nWE5KI/0.jpg)](https://www.youtube.com/watch?v=IiIv_nWE5KI)

## Hardware guide

Before you can start, please ensure you have one of the supported displays and of the supported Raspberry
Pi: `|4|3A|3B|3B+|2B|0W|0WH|02W|`. We personally recommend the Raspberry Pi Zero W as this is relatively cheaper, uses
less power and is perfect to fit in a small photo frame once you have assembled everything.

**Serial** displays are usually cheaper, but slower. Their main advantage is ease of use, like being able to communicate
via SPI. A single update will cause flickering (fully normal on e-paper displays) ranging from a few seconds to half an
minute. We recommend these for users who want to get started quickly and for more compact setups, e.g. fitting inside a
photo frame. The resolution of these displays ranges from low to medium. Usually, these displays support 2-3 colours,
but no colours in between, e.g. fully black, fully red/yellow and fully-white.

**Parallel** displays on the other hand do not understand SPI and require their own dedicated driver boards individually
configured for these displays. Flickering also takes place here, but an update only takes about one to a few seconds.
The resolution is much better than serial e-paper displays, but the cost is also higher. These also have 16 different
grayscale levels, which does not compare to the 256 grayscales of LCDs, but far better than serial displays.

**❗️Important note: e-paper displays cannot be simply connected to the Raspberry Pi, but require a driver board. The
links below may or may not contain the required driver board. Please ensure you get the correct driver board for the
display!**

| type                                      | vendor                  | Where to buy                                                              |
|-------------------------------------------|-------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 7.5" Inkycal (plug-and-play)              | Aceinnolab (author)       |  [Buy on Tindie](https://www.tindie.com/products/aceisace4444/inkycal-build-v1/)  Pre-configured version of Inkycal with custom frame and a web-ui. You do not need to buy anything extra. Includes Raspberry Pi Zero W, 7.5" e-paper, microSD card, driver board, custom packaging and 1m of cable. Comes pre-assembled for plug-and-play. |
| Inkycal frame (kit -> requires wires, 7.5" Display and Zero W with microSD card | Aceinnolab (author)       |  [Buy on Tindie](https://www.tindie.com/products/aceinnolab/inkycal-frame-custom-driver-board-only/) Ultraslim frame with custom-made front and backcover inkl. ultraslim driver board). You will need a Raspberry Pi, microSD card and a 7.5" e-paper display |
| `[serial]`  12.48" (1304×984px) display   | waveshare / gooddisplay |  Search for `Waveshare 12.48" E-Paper 1304×984` on amazon or similar |
| `[serial]` 7.5" (640x384px) -> v1 display (2/3-colour) | waveshare / gooddisplay |  Search for `Waveshare 7.5" E-Paper 640x384` on amazon or similar |
| `[serial]` 7.5" (800x480px) -> v2 display (2/3-colour) | waveshare / gooddisplay |  Search for `Waveshare 7.5" E-Paper 800x480` on amazon or similar |
| `[serial]` 7.5" (880x528px) -> v3 display (2/3-colour) | waveshare / gooddisplay |  Search for `Waveshare 7.5" E-Paper 800x528` on amazon or similar |
| `[serial]`  5.83" (400x300px) display     | waveshare / gooddisplay | Search for `Waveshare 5.83" E-Paper 400x300` on amazon or similar |
| `[serial]`  4.2" (400x300px)display       | waveshare / gooddisplay | Search for `Waveshare 4.2" E-Paper 400x300` on amazon or similar |                                                                                         |
| `[parallel]` 10.3" (1872×1404px) display  | waveshare / gooddisplay |  Search for `Waveshare 10.3" E-Paper 1872×1404` on amazon or similar |
| `[parallel]` 9.7" (1200×825px) display    | waveshare / gooddisplay | Search for `Waveshare 9.7" E-Paper 1200×825` on amazon or similar |
| `[parallel]` 7.8" (1872×1404px) display   | waveshare / gooddisplay |  Search for `Waveshare 7.8" E-Paper 1872×1404` on amazon or similar |
| Raspberry Pi Zero W                       | Raspberry Pi            |  Search for `Raspberry Pi Zero W` on amazon or similar |
| MicroSD card                              | Sandisk                 |  Search for `MicroSD card 8GB` on amazon or similar |

## Configuring the Raspberry Pi

Flash Raspberry Pi OS on your microSD card (min. 4GB) with [Raspberry Pi Imager](https://rptl.io/imager). Use the
following settings:

| option                    |            value            |
|:--------------------------|:---------------------------:|
| hostname                  |           inkycal           |
| enable ssh                |             yes             |
| set username and password |             yes             |
| username                  |     a username you like     |
| password                  | a password you can remember |
| set Wi-Fi                 |             yes             |
| Wi-Fi SSID                |       your Wi-Fi name       |
| Wi-Fi password            |     your Wi-Fi password     |
| set timezone              |     your local timezone     |

1. Create and download `settings.json` file for Inkycal from
   the [WEB-UI](https://aceinnolab.com/inkycal/ui). Add the modules you want with the add
   module button.
2. Copy the `settings.json` to the flashed microSD card.
3. Eject the microSD card from your computer now, insert it in the Raspberry Pi and power the Raspberry Pi.
4. Once the green LED has stopped blinking after ~3 minutes, you can connect to your Raspberry Pi via SSH using a SSH
   Client. We suggest [Termius](https://termius.com/download/windows)
   on your smartphone. Use the address: `inkycal.local` with the username and password you set earlier. For more
   detailed instructions, check out the page from
   the [Raspberry Pi website](https://www.raspberrypi.org/documentation/remote-access/ssh/)
5. After connecting via SSH, run the following commands, line by line:

```bash
sudo raspi-config --expand-rootfs
sudo sed -i s/#dtparam=spi=on/dtparam=spi=on/ /boot/config.txt
sudo dpkg-reconfigure tzdata

# If you have the 12.48" display, these steps are also required:
wget http://www.airspayce.com/mikem/bcm2835/bcm2835-1.71.tar.gz
tar zxvf bcm2835-1.71.tar.gz 
cd bcm2835-1.71/
sudo ./configure && sudo make && sudo make check && sudo make install
wget https://project-downloads.drogon.net/wiringpi-latest.deb
sudo dpkg -i wiringpi-latest.deb

# If you are using the Raspberry Pi Zero models, you may need to increase the swapfile size to be able to install Inkycal:
sudo dphys-swapfile swapoff
sudo sed -i -E '/^CONF_SWAPSIZE=/s/=.*/=512/' /etc/dphys-swapfile
sudo dphys-swapfile setup
sudo dphys-swapfile swapon
```

These commands expand the filesystem, enable SPI and set up the correct timezone on the Raspberry Pi. When running the
last command, please select the continent you live in, press enter and then select the capital of the country you live
in. Lastly, press enter.

7. Follow the steps in `Installation` (see below) on how to install Inkycal.

## Installing Inkycal

⚠️ Please note that although the developers try to keep the installation as simple as possible, the full installation
can sometimes take hours on the Raspberry Pi Zero W and is not guaranteed to go smoothly each time. This is because
installing dependencies on the zero w takes a long time and is prone to copy-paste-, permission- and configuration
errors.

ℹ️ **Looking for a shortcut to safe a few hours?** We know about this problem and have spent a signifcant amount of time
to prepare a pre-configured image with the latest version of Inkycal for the Raspberry Pi Zero. It comes with the latest
version of Inkycal, is fully tested and uses the Raspberry Pi OS Lite as it's base image. You only need to copy your
settings.json file, we already took care of the rest, including auto-start at boot, enabling spi and installing all
dependencies in advance. Pretty neat right? Check the [sponsor button](https://github.com/sponsors/aceisace) at the very
top of the repo to get access to Inkycal-OS-Lite. Alternatively, you can also use the paypal.me link and send the same amount as Github sponsors to get access to InkycalOS-Lite! 
This will help keep this project growing and cover the ongoing expenses too! Win-win for everyone! 🎊 

### Manual installation

Run the following steps to install Inkycal. Do **not** use sudo for this, except where explicitly specified.

```bash
# the next line is for the Raspberry Pi only
sudo apt-get install zlib1g libjpeg-dev libatlas-base-dev rustc libopenjp2-7 python3-dev scons libssl-dev python3-venv python3-pip git libfreetype6-dev wkhtmltopdf
cd $HOME
git clone --branch main --single-branch https://github.com/aceinnolab/Inkycal
cd Inkycal
python3 -m venv venv
source venv/bin/activate
python -m pip install --upgrade pip
pip install wheel
pip install -e ./

# If you are running on the Raspberry Pi, please install the following too to allow rendering on the display
pip install RPi.GPIO==0.7.1 spidev==3.5
```

## Running Inkycal

To run Inkycal, type in the following command in the terminal:

```bash
cd $HOME/Inkycal
source venv/bin/activate
python3 inky_run.py
```

## Running on each boot

To make inkycal run on each boot automatically, you can use crontab. Do not use sudo for this

```bash
(crontab -l ; echo "@reboot sleep 60 && cd $HOME/Inkycal && venv/bin/python inky_run.py &")| crontab -
```

## Updating Inkycal

To update Inkycal to the latest version, navigate to the Inkycal folder, then run:

```bash
git pull
```

Yep. It's actually that simple!
But, if you have made changes to Inkycal, those will be overwritten.
If that is the case, backup your modified files somewhere else if you need them. Then run:

```bash
git reset --hard
git pull
```

## Uninstalling Inkycal

We'll miss you, but we don't want to make it hard for you to leave.
Just delete the Inkycal folder, and you're good to go!

Additionally, if you want to reset your crontab file, which runs inkycal at boot, run:

```bash
crontab -r
```

https://rahulmahale.com/blogs/running-cronjob-at-reboot-on-raspberry-pi/

## Modifying Inkycal

Inkycal now runs in a virtual environment to support more devices than just the Raspberry Pi. Therefore, to make changes
to Inkycal, navigate to Inkycal, then run:

```bash
cd $HOME/Inkycal && source venv/bin/activate
```

Then modify the files as needed and experiment with Inkycal.
To deactivate the virtual environment, simply run:

```bash
deactivate
```

## 3D printed frames

With your setup being complete at this stage, you may want to 3d-print a case. The following files were shared by our
friendly community:
[3D-printable case](https://github.com/aceinnolab/Inkycal/wiki/3D-printable-files)

## Contributing

All sorts of contributions are most welcome and appreciated. To start contributing, please follow
the [Contribution Guidelines](https://github.com/aceisace/Inkycal/blob/main/.github/CONTRIBUTING.md)

The average response time for issues, PRs and emails is usually 24 hours. In some cases, it might be longer. If you want
to have some faster responses, please use Discord (link below)

**P.S:** Don't forget to star and/or watch the repo. For those who have done so already, thank you very much!

## Join us on Discord!

We're happy to help, to beginners and developers alike. In fact, you are more likely to get faster support on Discord
than on Github.

<a href="https://discord.gg/sHYKeSM">
        <img src="https://github.com/aceisace/Inkycal/blob/assets/Repo/discord-logo.png?raw=true" alt="Inkycal chatroom Discord" width=200>
</a>

## Sponsoring

Inkycal relies on sponsors to keep up maintainance, development and bug-fixing. Please consider sponsoring Inkycal via
the sponsor button if you are happy with Inkycal.

We now offer perks depending on the amount contributed for sponsoring, ranging from pre-configured OS images for
plug-and-play to development of user-suggested modules. Check out the sponsor page to find out more.
If you have been a previous sponsor, please let us know on our Dicord server or by sending an email. We'll send you the
perks after confirming 💯

## As featured on

* [raspberrypi.com](https://www.raspberrypi.com/news/ashleys-top-five-projects-for-raspberry-pi-first-timers/)
* [hackster.io](https://www.hackster.io/news/ace-innovation-lab-s-inkycal-v3-puts-a-raspberry-pi-powered-modular-epaper-dashboard-on-your-desk-b55a83cc0f46)
* [makeuseof - fantastic projects using an eink display](http://makeuseof.com/fantastic-projects-using-an-e-ink-display/)
* [magpi.de](https://www.magpi.de/news/maginkcal-ein-kalender-mit-epaper-display-und-raspberry-pi)
* [goodreader.com](https://goodereader.com/blog/e-paper/five-of-the-most-innovative-e-ink-display-projects?doing_wp_cron=1701869793.2312469482421875000000)
* [reddit - Inkycal](https://www.reddit.com/r/InkyCal/)
* [schuemann.it](https://schuemann.it/2019/09/11/e-ink-calendar-with-a-raspberry-pi/)
* [huernerfuerst.de](https://www.huenerfuerst.de/archives/e-ink-kalender-mit-einem-raspberry-pi-zero-teil-1-was-wird-benoetigt)
* [canox.net](https://canox.net/2019/06/raspberry-pi-als-e-ink-kalender/)
