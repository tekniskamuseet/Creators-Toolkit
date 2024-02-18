# Creators Toolkit

Welcome to the Wisdome Creators Toolkit!

![Wisdome](/media/wisdome-03.jpg)

## Table of Contents

-   [Introduction](#introduction)
-   [Video](#video)
-   [Audio](#audio)
-   [Light](#light)
-   [Other](#other)
-   [Links](#links)
-   [FAQ](#faq)
-   [Contributing](#contributing)

## Introduction

Fall 2023 marked the unveiling of a new stage for audiovisual experiences at Tekniska Muséet! The Wisdome Project, a collaboration among five leading Swedish science centers, introduces innovative visualization dome theaters. The Wisdome Wizards, a group of artists and technologists, have assembled the **Creators Toolkit**—a legendary compendium rumored to bring fantasy to reality.

## Video

The dome features 6 projectors stitched together, supporting 8k (7680 × 7680 px) or 4K (4096 x 4096 px) video. For quicker rendering, 1920 x 1920 px suffices.

Render your video as a PNG sequence, preferably in a cloud-stored zip file for easy download to the master computer controlling projectors. Utilize Splitter software to prepare files for the 6 projector-controlling computers, automatically adjusting aspect ratio and applying edge blending.

![Splitter](/media/wisdome-04.jpg)

### Split video using Splitter

1. On **Master**
2. Launch `Splitter_GUI.exe` from `D:\Splitter2020\bin`
3. Configure using `tekniska_split.xml`
4. Navigate to folder with PNG sequence, ensuring files are prefixed with a leading zero
5. Adjust settings:
    - Output path: []
    - Project title: []
    - Preset: **Veryfast**

### Change video output on Crestron touch monitor

1. **On Crestron**
2. Access **Videomonitor**
3. Choose **Ingång** and a **Planetarie** option

### Sending/Receiving Video Stream

1. In Terminal, navigate to `D:\Splitter2020\bin` or relevant ffmpeg directory
2. Run:
   `ffmpeg -f gdigrab -video_size 1024x1024 -offset_x 100 -offset_y 300 -show_region 1 -framerate 16 -i "desktop" -preset ultrafast -vcodec mpeg4 -crf 0 -f mpegts "udp://192.168.204.255:12345?pkt_size=1316"`
3. Open `C-Troll.exe`
4. Choose **Filmvisning**
5. In C-Play, select Open URL and enter: `udp://192.168.204.101:12345?pkt_size=1316`

## Audio

### Audio Setup in DAW on the **Master Computer**

1. Choose ASIO Driver : ASIOMadiface USB in your preferred DAW
2. Enable Dante Outputs 1-16

### Channel Schematic 

1. Left
2. Right
3. Center
4. LFE
5. Left Surround Front
6. Right Surround Front
7. Left Surround Rear
8. Right Surround Rear
9. Left Surround Back
10. Right Surround Back
16. Focus Center (Height center is on channel *16!*)

![Wisdome](/media/wisdome-audio-01.jpg)

## Audio Setup with your *Laptop and External Audio Sources* - For example for live performances from the scene of the dome.

To connect your laptop and external audio sources to the dome speakers you need to connect to the external Allen Heath SQ5 mixer, located behind the dome screen.

1. Download and install the [SQ USB Audio driver](https://www.allen-heath.com/hardware/sq/sq-5/resources/) *only a requirement for PC*
2. Connect your computer to the mixers internal digital interface via the USB cable connected to the mixer.
3. Use the stagebox connected to the mixer for your External Audio Sources. (Bring DI box for line level signals, there are XLR and Shure Beta 58 mics available).
4. Patch your relevant inputs sockets to the Dante output channels.

Your audio outputs from your DAW are "USB INPUTS" on the SQ5. If you want to connect external audio sources you can connect it to the stagebox, to patch these you refer to "S-LINK INPUTS".

> [!CAUTION]
> Make sure to switch from "Domkälla" to "Extern mixer" in the audio tab in the Crestron computer to enable sound from the mixer.
  Don't forget to switch back to "Domkälla" to enable sound from the master computer.

![Wisdome](/media/wisdome-audio-02.jpg)

### Trähallen (Still under development)

5 zones + 1 outside.

## Light

Ensure direct connection of your computer to the DMX transmitter via Ethernet.

1. Configure Ethernet interface:
    - IP Address: `2.1.1.1`
    - Subnet Mask: `255.0.0.0`
    - Router/Gateway: `2.1.1.1`
2. In ArtNet sending software, set target IP to `2.255.255.255`.

## Other

### 3D assets of dome

[Tekniska_Wisdome_V01.fbx](files/Tekniska_Wisdome_V01.fbx)

### Stream Audio/Video using VDO.ninja (OBS)

1. Sender: Open [VDO.ninja room](https://vdo.ninja/v16/?room=Wisdome2023&hash=a3b1&view=)
2. Receiver (director): Open [VDO.ninja director's view](https://vdo.ninja/v16/?director=Wisdome2023&password=Wisdome2023)

### Web Visualiser

-   [Visualization 1](https://lab.possan.codes/wizdome/vis/1/index.html)
-   [Visualization 2](https://lab.possan.codes/wizdome/vis/2/index.html)
-   [Visualization 3](https://lab.possan.codes/wizdome/vis/3/index.html)

## Links

-   [SGCT - Simple Graphics Cluster Toolkit](https://github.com/sgct/sgct)

## FAQ

### Is it possible to have one output for the whole dome?

No. The current setup involves a video cluster with a master computer and 6 slaves for each projector. While the computers are not physically accessible, remote access is available in the control room via a monitor with mouse and keyboard.

> [!CAUTION]
> Direct connections such as USB sticks, SD cards, HDMI, DP, or DVI are not feasible without access to the server room.

### Will it be possible to have one output for the whole dome?

Theoretically, yes, but this functionality is not yet implemented.

## Contributing

We welcome contributions to the Wisdome Creators Toolkit from all experience levels. For more information, please join the [Wisdome Discord](https://discord.gg/r53hh4pw6y).

![Wisdome](/media/wisdome-01.jpg)
