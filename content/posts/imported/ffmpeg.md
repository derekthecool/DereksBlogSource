---
title: "ffmpeg"
date: 2024-07-17T13:25:55
image: https://trac.ffmpeg.org/ffmpeg-logo.png
categories:
  - ffmpeg
  - terminal
draft: true
---

# ffmpeg Video & Audio Tool

{{< featuredImage alt="ffmpeg image" >}}

## Basics

### Get File Information

#### Get basic video information

```sh
ffmpeg -i .\20240313_133247.mp4
ffmpeg version 6.0-full_build-www.gyan.dev Copyright (c) 2000-2023 the FFmpeg developers
  built with gcc 12.2.0 (Rev10, Built by MSYS2 project)
  configuration: --enable-gpl --enable-version3 --enable-static --disable-w32threads --disable-autodetect --enable-fontconfig --enable-iconv --enable-gnutls --enable-libxml2
--enable-gmp --enable-bzlib --enable-lzma --enable-libsnappy --enable-zlib --enable-librist --enable-libsrt --enable-libssh --enable-libzmq --enable-avisynth --enable-libbluray --enable-libcaca --enable-sdl2 --enable-libaribb24 --enable-libdav1d --enable-libdavs2 --enable-libuavs3d --enable-libzvbi --enable-librav1e --enable-libsvtav1 --enable-libwebp --enable-libx264 --enable-libx265 --enable-libxavs2 --enable-libxvid --enable-libaom --enable-libjxl --enable-libopenjpeg --enable-libvpx --enable-mediafoundation --enable-libass --enable-frei0r --enable-libfreetype --enable-libfribidi --enable-liblensfun --enable-libvidstab --enable-libvmaf --enable-libzimg --enable-amf --enable-cuda-llvm
--enable-cuvid --enable-ffnvcodec --enable-nvdec --enable-nvenc --enable-d3d11va --enable-dxva2 --enable-libvpl --enable-libshaderc --enable-vulkan --enable-libplacebo --enable-opencl --enable-libcdio --enable-libgme --enable-libmodplug --enable-libopenmpt --enable-libopencore-amrwb --enable-libmp3lame --enable-libshine --enable-libtheora --enable-libtwolame --enable-libvo-amrwbenc --enable-libilbc --enable-libgsm --enable-libopencore-amrnb --enable-libopus --enable-libspeex --enable-libvorbis --enable-ladspa --enable-libbs2b --enable-libflite --enable-libmysofa --enable-librubberband --enable-libsoxr --enable-chromaprint
  libavutil      58.  2.100 / 58.  2.100
  libavcodec     60.  3.100 / 60.  3.100
  libavformat    60.  3.100 / 60.  3.100
  libavdevice    60.  1.100 / 60.  1.100
  libavfilter     9.  3.100 /  9.  3.100
  libswscale      7.  1.100 /  7.  1.100
  libswresample   4. 10.100 /  4. 10.100
  libpostproc    57.  1.100 / 57.  1.100
Input #0, mov,mp4,m4a,3gp,3g2,mj2, from '.\20240313_133247.mp4':
  Metadata:
    major_brand     : mp42
    minor_version   : 0
    compatible_brands: isommp42
    creation_time   : 2024-03-13T19:35:00.000000Z
    com.android.version: 13
    com.android.capture.fps: 30.000000
  Duration: 00:02:11.39, start: 0.000000, bitrate: 17094 kb/s
  Stream #0:0[0x1](eng): Video: h264 (High) (avc1 / 0x31637661), yuv420p(tv, bt709, progressive), 1920x1080, 16838 kb/s, 30 fps, 30 tbr, 90k tbn (default)
    Metadata:
      creation_time   : 2024-03-13T19:35:00.000000Z
      handler_name    : VideoHandle
      vendor_id       : [0][0][0][0]
    Side data:
      displaymatrix: rotation of -90.00 degrees
  Stream #0:1[0x2](eng): Audio: aac (LC) (mp4a / 0x6134706D), 48000 Hz, stereo, fltp, 256 kb/s (default)
    Metadata:
      creation_time   : 2024-03-13T19:35:00.000000Z
      handler_name    : SoundHandle
      vendor_id       : [0][0][0][0]
At least one output file must be specified
```

#### Get basic image information

```sh
ffmpeg -i C:\Users\dlomax\.dotnet\tools\.store\dotnet-ef\7.0.13\dotnet-ef\7.0.13\Icon.png
ffmpeg version 6.0-full_build-www.gyan.dev Copyright (c) 2000-2023 the FFmpeg developers
  built with gcc 12.2.0 (Rev10, Built by MSYS2 project)
  configuration: --enable-gpl --enable-version3 --enable-static --disable-w32threads --disable-autodetect --enable-fontconfig --enable-iconv --enable-gnutls --enable-libxml2
--enable-gmp --enable-bzlib --enable-lzma --enable-libsnappy --enable-zlib --enable-librist --enable-libsrt --enable-libssh --enable-libzmq --enable-avisynth --enable-libbluray --enable-libcaca --enable-sdl2 --enable-libaribb24 --enable-libdav1d --enable-libdavs2 --enable-libuavs3d --enable-libzvbi --enable-librav1e --enable-libsvtav1 --enable-libwebp --enable-libx264 --enable-libx265 --enable-libxavs2 --enable-libxvid --enable-libaom --enable-libjxl --enable-libopenjpeg --enable-libvpx --enable-mediafoundation --enable-libass --enable-frei0r --enable-libfreetype --enable-libfribidi --enable-liblensfun --enable-libvidstab --enable-libvmaf --enable-libzimg --enable-amf --enable-cuda-llvm
--enable-cuvid --enable-ffnvcodec --enable-nvdec --enable-nvenc --enable-d3d11va --enable-dxva2 --enable-libvpl --enable-libshaderc --enable-vulkan --enable-libplacebo --enable-opencl --enable-libcdio --enable-libgme --enable-libmodplug --enable-libopenmpt --enable-libopencore-amrwb --enable-libmp3lame --enable-libshine --enable-libtheora --enable-libtwolame --enable-libvo-amrwbenc --enable-libilbc --enable-libgsm --enable-libopencore-amrnb --enable-libopus --enable-libspeex --enable-libvorbis --enable-ladspa --enable-libbs2b --enable-libflite --enable-libmysofa --enable-librubberband --enable-libsoxr --enable-chromaprint
  libavutil      58.  2.100 / 58.  2.100
  libavcodec     60.  3.100 / 60.  3.100
  libavformat    60.  3.100 / 60.  3.100
  libavdevice    60.  1.100 / 60.  1.100
  libavfilter     9.  3.100 /  9.  3.100
  libswscale      7.  1.100 /  7.  1.100
  libswresample   4. 10.100 /  4. 10.100
  libpostproc    57.  1.100 / 57.  1.100
Input #0, png_pipe, from 'C:\Users\dlomax\.dotnet\tools\.store\dotnet-ef\7.0.13\dotnet-ef\7.0.13\Icon.png':
  Duration: N/A, bitrate: N/A
  Stream #0:0: Video: png, rgba(pc), 512x512 [SAR 3780:3780 DAR 1:1], 25 fps, 25 tbr, 25 tbn
At least one output file must be specified

```

## Video editing with ffmpeg

### Compression

Calculate bitrate to use for compression to get a 5 MB output file
5^6 bytes \* 8 (bits in a byte) / 30 seconds = 1333333 or 133k

```sh
ffmpeg -i input.mp4 -b 133k output.mp4
```

## Join 2 or more videos

1. Prep files by creating a file list like this

```sh
for f in ./*.mp4; do echo "file '$f'" >> mylist.txt; done
```

2. Finally run the command

```sh
ffmpeg -f concat -safe 0 -i mylist.txt -c copy output.mp4
```

## Screen Capturing

### Screenshot Capture

#### On Windows

```powershell
# Capture a 100x100 square block on monitor 2 (assuming first monitor is
# 1920x1080)
ffmpeg.exe -f gdigrab -framerate ntsc -offset_x 1920 -video_size 100x100 -show_region 1 -i desktop snip.jpg

# Capture a screensmot from the app with the name shown in title
ffmpeg.exe -f gdigrab -framerate 25 -i title="Power Tool --ZUMZ2H_FS04_Normal.pt5--" power.jpg

# Better version of the specific window screenshow
# Use powershell to get the window name
# Prompt user for output filename
ffmpeg.exe -f gdigrab -framerate 25 -i title="$((Get-Process PowerTool | Select-Object MainWindowTitle).MainWindowTitle)" "$(Read-Host -Prompt 'Image info').jpg"

# Capture a portion of the image
# you can also adjust offsets
ffmpeg.exe -f gdigrab -framerate ntsc -video_size 1920x810 -i desktop asht.jpg
```

### Video Capture

#### On Windows

Find video and audio devices
https://how-to.fandom.com/wiki/Record_desktop

http://underpop.online.fr/f/ffmpeg/help/gdigrab.htm.gz

```powershell
 ffmpeg -list_devices true -f dshow -i dummy

# Records all desktops until you press <C-c>
 ffmpeg.exe -f gdigrab -i desktop -framerate 15 -video_size 1920x1080 -vcodec libx264 -pix_fmt yuv420p -preset ultrafast 1.mkv
```
