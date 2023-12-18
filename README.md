## Video

### Split video using Splitter

1. On “Master”
2. Locate: `D:\Splitter2020\bin`
3. Open “Splitter_GUI.exe”
4. Set config file
5. Locate: `D:\SGCT\V2`

   [tekniska_mono_split.xml](https://prod-files-secure.s3.us-west-2.amazonaws.com/bff47d75-b622-4565-b186-e6c0c433fca8/c163186e-ec4e-4ef2-94e8-ed44c41cdff3/tekniska_mono_split.xml)

   [tekniska_stereo_split.xml](https://prod-files-secure.s3.us-west-2.amazonaws.com/bff47d75-b622-4565-b186-e6c0c433fca8/0ff3c59d-4da5-45e4-8f04-d8f1440d4403/tekniska_stereo_split.xml)

6. Locate folder with PNG sequence

   **\*\***\*\*\*\***\*\***PNG SEQUENCE MUST HAVE INDEX WITH LEADING ZERO**\*\***\*\*\*\***\*\***

7. Settings

   1. Output path: [custom]

      **OUTPUT TO TEST_X_VIDEO** (can’t remember the correct path…)

   2. Project title: [custom]
   3. Preset: **Veryfast**

### Change video output on Crestron monitor

1. On Crestron
2. Locate “Videomonitor”
3. Touch “Ingång”
4. Select a “Planetarie” option

### Sending/Receiving Video Stream

1. In Terminal, go to: `D:\Splitter2020\bin` or where your ffmpeg binaries are and run:
   `ffmpeg -f gdigrab -video_size 1024x1024 -offset_x 100 -offset_y 300 -show_region 1 -framerate 16 -i "desktop" -preset ultrafast -vcodec mpeg4 -crf 0 -f mpegts "udp://192.168.204.255:12345?pkt_size=1316"`
2. Open `C-Troll.exe`
3. Select **Filmvisning**
4. In C-Play; Choose Open URL, enter `udp://192.168.204.101:12345?pkt_size=1316`

> [!IMPORTANT]
> If C-Play complains that \***\*youtube-dl\*\*** doesn’t exist, copy `youtube-dl.exe` to `C:\Windows\System32`

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

### Servando PureData Speaker Test

[serv_spkrtest.pd](https://wisdome-creators-toolkit.tekniskamuseet.github.io/files//serv_spkrtest.pd)

## Light

> [!IMPORTANT]
> 🔥 **Temporary solution**. Connect your computer directly to the DMX transmitter via Ethernet.

1. Set Ethernet interface set:
   1. IP Address: `2.1.1.1`
   2. Subnet Mask: `255.0.0.0`
   3. Router/Gateway: `2.1.1.1`
2. In Resolume:
   1. Target IP: `2.255.255.255`

