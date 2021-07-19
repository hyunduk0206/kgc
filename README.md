<h1 align="center">
  <img src="icon.png"><br/>kgc
  (https://hshin.ddns.net:20443)
</h1>

## Requirements
### SSL problem
<img src="ssl.jpg"><br/>

### Demo devices
<!-- 1. Smartphone or laptop -->
1. Laptop

2. Raspberry Pi 3/4 or PC
    - Peripherals needed
        - Video/audio input devices (e.g. webcam)
        - Display/audio output device (e.g. touch display/speaker)

    - Raspberry Pi OS settings
        - Set up WIFI with on-screen keyboard
        - Go to the main menu and open the Raspberry Pi Configuration tool. Select the Interfaces tab and ensure that the camera is enabled. Reboot your Raspberry Pi.
        - Adjust audio volume
        - Screen resolution of 800 x 480 pixels
        - Auto-hide taskbar
            - Right-click on the taskbar and select "Panel Settings". Click on the "Advanced" tab, and check "Minimize panel when not in use".
        - Install Korean language
            ```bash
            sudo apt-get install fonts-unfonts-core
            sudo apt-get install ibus ibus-hangul
            sudo reboot
            ```
        - How to start Chromium on Raspberry boot?
            ```bash
            sudo nano /etc/xdg/lxsession/LXDE-pi/autostart
            ```
            - Add this to what is already there:
            ```bash
            @chromium-browser --start-fullscreen --kiosk https://YourServerURL.com
            ```
            - Next press CTRL+X and type Y for saving the file

        - How to disable SSH password warning?
            ```bash
            sudo rm /etc/xdg/lxsession/LXDE-pi/sshpwd.sh
            ```
        - Optional settings
            - Enable VNC/SSH
            - https://blog.r0b.io/post/minimal-rpi-kiosk/ 

### SW
- Chromium based browser
- Node.js
- Python

#### keti server
- FFmpeg install (https://www.gyan.dev/ffmpeg/builds/)
    - For Ubuntu, 
        ```bash
        sudo apt install ffmpeg
        ```
    - For Windows, add FFmpeg to Windows path using Environment variables

## API settings
### Talk endpoints
- Replace the API endpoints in gnict/public/config.js with your API endpoints

### Kakao OpenAPI for STT/TTS
- Create a .env file at the keti directory and add your {API_KEY} to it (e.g. API_KEY=*************************)
- https://speech-api.kakao.com/
- https://developers.kakao.com/docs/latest/ko/voice/rest-api
- https://docs.kakaoi.ai/skill/ssml_guide/
- https://ai-creator.tistory.com/70


# WebRTC references

- Python WebRTC basics with aiortc, https://dev.to/whitphx/python-webrtc-basics-with-aiortc-48id
<!-- - Building a WebRTC video broadcast using Javascript, https://gabrieltanner.org/blog/webrtc-video-broadcast
- WebRTC tutorial, https://www.youtube.com/watch?v=QJMM758oCYk&list=PLayYqdnyegt0qX8EfEGExxZF3DxkyA1Dj -->
