# Creators Toolkit

Welcome to the Wisdome Creators Toolkit!

## Table of Contents

-   Introduction
-   Getting started
-   [Video](#video)
-   [Audio](#audio)
-   [Light](#light)
-   [Links](#links)
-   [FAQ](#faq)
-   [FAQ](#faq)

## Introduction

During fall 2023 a new stage for audiovisual experiences is unveiled at Tekniska Muséet! The Wisdome Project revolves around five leading Swedish science centers joining forces in order to establish innovative visualization dome theaters. A group of artists and technologists, known to some as the Wisdome Wizards, have come together to build the **Creators Toolkit**! A mythical index of knowledge which is said to help bring fantasy to reality…

## Getting started

This document relies on you having direct access to the Wisdome control room.

## Video

The dome is set up with 6 projectors, stitched together. The aspect ratio is 1:1 and it is possible to play 8k video (7680 × 7680 px) but 4K is fine (4096 x 4096 px). If you want to save time rendering 1920 x 1920 px is OK.

Render your video as a PNG sequence on your own machine (must be prefixed with a leading zero). If possible, save as a zip file in the cloud. It’s then easy to download on the master computer controlling the projectors.

On the master you can prepare your files for the 6 computers controlling each projector. This can be done by using a piece of software called Splitter. The output of your 1:1 video will automatically be adjusted for the dome with added "fish eye" effect as well as correct edge blending. Your video is automatically divided into six video files, one for each projector.

### Split video using Splitter

1. On "Master"
2. Locate: `D:\Splitter2020\bin`
3. Open "Splitter_GUI.exe"
4. Set config file
5. Locate: `D:\SGCT\V2`

    [tekniska_mono_split.xml](https://prod-files-secure.s3.us-west-2.amazonaws.com/bff47d75-b622-4565-b186-e6c0c433fca8/c163186e-ec4e-4ef2-94e8-ed44c41cdff3/tekniska_mono_split.xml)

    [tekniska_stereo_split.xml](https://prod-files-secure.s3.us-west-2.amazonaws.com/bff47d75-b622-4565-b186-e6c0c433fca8/0ff3c59d-4da5-45e4-8f04-d8f1440d4403/tekniska_stereo_split.xml)

6. Locate folder with PNG sequence

> [!IMPORTANT]
> The PNG sequence must be prefixed with a leading zero

7. Settings

    1. Output path: [custom]
    2. Project title: [custom]
    3. Preset: **Veryfast**

### Change video output on Crestron touch monitor

1. On Crestron
2. Locate "Videomonitor"
3. Select "Ingång" and a "Planetarie" option

### Sending/Receiving Video Stream

1. In Terminal, go to: `D:\Splitter2020\bin` or where your ffmpeg binaries are and run:
   `ffmpeg -f gdigrab -video_size 1024x1024 -offset_x 100 -offset_y 300 -show_region 1 -framerate 16 -i "desktop" -preset ultrafast -vcodec mpeg4 -crf 0 -f mpegts "udp://192.168.204.255:12345?pkt_size=1316"`
2. Open `C-Troll.exe`
3. Select **Filmvisning**
4. In C-Play; Choose Open URL, enter `udp://192.168.204.101:12345?pkt_size=1316`

> [!IMPORTANT]
> If C-Play complains that **youtube-dl** doesn’t exist, copy `youtube-dl.exe` to `C:\Windows\System32`

## Audio

### Channel Schematic

1. Focus
2. Center
3. Left
4. Right
5. Side Left Front
6. Side Left Rear
7. Rear Left
8. Side Right Front
9. Side Right Rear
10. Rear right
11. LFE (Sub)

### Trähallen

5 zones + 1 outside.

## Light

> [!IMPORTANT]
> 🔥 **Temporary solution**. Connect your computer directly to the DMX transmitter via Ethernet.

1. Set Ethernet interface set:
   1. IP Address: `2.1.1.1`
   2. Subnet Mask: `255.0.0.0`
   3. Router/Gateway: `2.1.1.1`
2. In ArtNet sending software:
   1. Target IP: `2.255.255.255`

## Links

-   [SGCT - Simple Graphics Cluster Toolkit](https://github.com/sgct/sgct)

## Contributing

We welcome contributions to the Wisdome Creators Toolkit from anyone, regardless of experience level. If you are interested in contributing, please reach out in the [Wisdome Discord](https://discord.gg/r53hh4pw6y) for more information.

## Participation

The best way to participate is to join the [Wisdome Discord](https://discord.gg/r53hh4pw6y), or any of the public hack events announced on Discord.