# Brautomat

[![de](https://img.shields.io/badge/lang-de-green.svg)](https://github.com/InnuendoPi/Brautomat/blob/main/README.md)

Brautomat is a brewing controller for GGM IDS induction hobs with an ESP8266 Wemos D1 mini. Brautomat is used in the brewery by hobby brewers and offers intuitive, easy-to-use controls. During mashing, rest temperatures are reached automatically and the rest times are adhered too. Brautomat also supports the the boiling process of the wort and adding hops. In an ascending infusion mash process, the brautomat can fully automate the mashing process.

 _Note: induction hobs from other manufacturers than GGM IDS are not supported._

Brautomat is a stand alone brewing device and offers :

* induction hob controller GGM IDS
* integrated PID-Controller
* PID-AutoTune
* Mash plan management
* Mash plans with up to 20 steps
* Hot liquid tank controller (HLT)
* Controlling actors like agitator, pumps etc.
* PWM for heating elements
* Temperature progression in the mashing process (line chart)
* MP3 alerts
* Toasts messages
* Recipe import kleinen Brauhelfer2
* Recipe import Maische Malz und Mehr
* Recipe import BrewFather
* Recipe export
* Nextion 3,5" HMI Touchdisplay (optional)

## 📚 Documentation

Manual: [https://innuendopi.gitbook.io/brautomat\_de/](https://innuendopi.gitbook.io/brautomat\_de/)

Discussion: [https://hobbybrauer.de/forum/viewtopic.php?p=486504#p486504](https://hobbybrauer.de/forum/viewtopic.php?p=486504#p486504)

Changelog: [https://github.com/InnuendoPi/Brautomat/blob/main/CHANGELOG.md](CHANGELOG.md)

## 📰 WebInterface

The Brautomat is controlled via a web browser. A browser with support for CSS3, HTML5, Javascript and Server Sent Events (SSE) is required.\

Compatible browser list [Browser](https://developer.mozilla.org/en-US/docs/Web/API/Server-sent_events/Using_server-sent_events#browser_compatibility)

![Startseite](/docs/img/brautomat.jpg)

![Startseite](/docs/img/IDS-AutoTune-Ziel.jpg)

![Startseite](/docs/img/brautomat-2.jpg)

## 💻 Nextion HMI Touchdisplay

Note: the display is an optional extension. Only Nextion ITEAD HMI 3.5" Touchdisplays are supported.

* Overview
* Mash tun
* Manual control cooking

![Overview](/docs/img/kettlepage-sm.jpg) ![Mash tun](/docs/img/brewpage-sm.jpg) ![Manual control](/docs/img/induction-mode-sm.jpg)

## ▶️ Installation

Hardware driver CP210x USB to UART Bridge Virtual COM Port (VCP): [Silicon Labs](https://www.silabs.com/developers/usb-to-uart-bridge-vcp-drivers?tab=downloads)

* Download [Firmeware.zip](https://github.com/InnuendoPi/Brautomat/releases/download/Release/Firmware.zip)
* unzip Firmware.zip
* edit Flashen.cmd:
* change "COM3" in line 6 und line 8 "esptool.exe -p COM3" as you need
* open command line (cmd.exe) and change into firmware.zip directory
* start script "flashen.cmd"

Script flashen.cmd use [esptool](https://github.com/espressif/esptool).

_"Boxing Bell" (info), "Short School Bell" (error), "Ding sound effect" (warning) and "Success sound effect" (success) mp3 from Free Sounds Library [http://www.freesoundslibrary.com](http://www.freesoundslibrary.com) Licence: Attribution 4.0 International (CC BY 4.0). You are allowed to use sound effects free of charge and royalty free in your multimedia projects for commercial or non-commercial purposes._
