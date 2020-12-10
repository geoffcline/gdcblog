---
title: "Edit Recording of Dual Monitors in Premiere "
date: 2020-12-08
draft: false
---

# Hardware
- Green Screen 
    - https://www.amazon.com/Neewer-Collapsible-Reversible-Chromakey-Background/dp/B00E89Q5OY
- Webcam
    - logitech C920
    - 1080p USB
    - https://www.amazon.com/Logitech-Webcam-Calling-Recording-Stereo/dp/B08DRQ66WP/ref=sr_1_5?dchild=1&keywords=logitech+webcam+c920&qid=1607544410&s=electronics&sr=1-5


# Configure OBS
[OBS (Open Broadcast Studio)](https://obsproject.com/) is a free tool that provides professional grade control of live video sources, such as screen recording and webcams. 

I use it to record my HD (1080p) logitech webcam, and both monitors (1080p mode). 

## Configure Canvas
First, make a 4K canvas. 

- Settings > Video > Base (Canvas) Resolution
- 3840x1260

[![Image from Gyazo](https://i.gyazo.com/40bee9775e5235d9e120535390daf75f.png)](https://gyazo.com/40bee9775e5235d9e120535390daf75f)

- Same value for Output Resolution

## Add Webcam Source
I use a logitech webcam to record in 1080p HD. HD must be manually enabled. 

- ➕ icon for sources
- Video Capture Device
- Resolution - Custom
- Resolution 1980x1080

## Add Display Capture Source
Add a source for each screen. 

Double check your monitor is set to 1920x1080 in the control panel or settings. 

## Arrange Sources

Drag each video source (1 webcam, 2 monitors, 3 total) to quadrants of the 4K canvas.

[![Image from Gyazo](https://i.gyazo.com/04e630904bb9d369ccbf9d9b9a89c41f.png)](https://gyazo.com/04e630904bb9d369ccbf9d9b9a89c41f)

Look at the audio mixer, and disable (drag to zero) any audio sources you don't want recorded. You may need to add your microphone manually as an audio source. 

Start recording. 

After you finish recording, use the "remux" menu option to finalize the files for playback. 


# Transcode Recordings for Adobe

Adobe Media Encoder reformats the video clips as preferred by Premiere, and it seperates out the 3 different video streams from the 4K canvas. 

Each input video file is a canvas including multiple source streams. A video file will be generated for each video stream. 


- Add the first video file by dragging it into `Queue`
- Use the dropdown menu to select the preset, as shown below:

[![Image from Gyazo](https://i.gyazo.com/ac752488d32d0b75c1c9f621042e72f4.png)](https://gyazo.com/ac752488d32d0b75c1c9f621042e72f4)

- `Apple ProRes...` , `Apple ProRes 422`

- Click on the video file header, then sliders icon to add another output for the first video file. 
- Repeat until you have three total outputs for the one input video file. 

[![Image from Gyazo](https://i.gyazo.com/6bb6502423ebe568e6030c4e0b36752d.gif)](https://gyazo.com/6bb6502423ebe568e6030c4e0b36752d)

- Open the first output by double clicking on it, in the row below the header for the video file input
- Switch to the source tab in the top left, and click on the crop symbol
- Set the crop values to 1920x1080 (as shown below)
- Drag the crop area to the first video source

[![Image from Gyazo](https://i.gyazo.com/0606159bfce6b66501ed11eaf60969eb.gif)](https://gyazo.com/0606159bfce6b66501ed11eaf60969eb)

- Configure the crop for the 2nd and 3rd outputs

- Repeat with any additional video files. 

- Start the encoding process, and note the paralell encoding of each partion of the canvas. 

[![Image from Gyazo](https://i.gyazo.com/c607a6bfa663a7ca953ad2d735fb98f3.png)](https://gyazo.com/c607a6bfa663a7ca953ad2d735fb98f3)

# Setup Adobe Premiere Project 

Create a new folder for project.

Open Premiere and create a new project. Use your new project folder.

Enable proxies for faster editing. 
-  "Ingest Settings" > "Copy and Create Proxies"
-  ProRes Medium Resolution Proxy

[![Image from Gyazo](https://i.gyazo.com/0b5320f57e06cb4cb456811328a8fdff.png)](https://gyazo.com/0b5320f57e06cb4cb456811328a8fdff)

Finish creating the project, then go to premiere settings and enable using the proxies. 
- File > Preferences > Media > Enable Proxies

Ingest all your video clips (should have 3x number of recording sessions). This will automatically create proxies. 

- File > Import...

Rename your video clips. For example, I use "s1-face", "s1-screen", "s2-face", and "s2-screen". The S# indicates the recording session, and then the portion of the video. 

# Add Green Screen Effect
- Right click on webcam recording
- "New Sequence from Clip"
- Choose "Effects" display configuration at top of window

You can learn more from [Adobe about Ultra Key](https://helpx.adobe.com/premiere-pro/how-to/ultra-key-effect.html#:~:text=The%20Ultra%20Key%20effect%20can%20be%20used%20to,or%20contract%20the%20selected%20color%20range%20for%20transparency%3A).

Here is the basics
- Select key color in effects settings, then click on greenscreen (not in shadow or highlight)
- Try the presets (especially `agressive`)
- Try adjusting the sliders, including `shadows`

# MultiCam Editing

MultiCam editing is a technique for editing together multiple video sources that were reocrded at the same time. It was created for multiple camera angles of a set, but it works well for computer screens also. 

- Select the matching clips in the browsers on the left, such as the webcam sequence, and both screen recordings.
- Be careful to select the sequence with the green screen effect applied, and not the raw webcam footage. 
- right click > create multicam from selection
- Accept defaults

[![Image from Gyazo](https://i.gyazo.com/b6726621ff37c304123934289a2bca9a.png)](https://gyazo.com/b6726621ff37c304123934289a2bca9a)


- Note the 3 previous clips were moved to "processed clips" folder
- Just one super clip remains 

- Now, learn the [basics of multicam editing.](https://blog.pond5.com/13182-5-simple-steps-to-multi-camera-editing-in-adobe-premiere-pro/)
- It's a natural extension of regular video editing in premiere

# Edit Video

Review one of the many great tutorials for Adobe Premiere. Adobe has a [focused set of videos](https://helpx.adobe.com/premiere-pro/how-to/create-edit-sequence.html).

- Review all of the timeline tools, and each keyboard shortcut. What are the variants of the blade tool? 
- Practice using keyframes for simple video properties, such as occupacity and position. 

# Export

## Upload to YouTube
- File > Export
- Choose YouTube 1080p as the preset, under `web video`

## Archive project
- Project settings dictate that media is coped to project folder. 
- Apply 7z to entire folder, and move to backup location.

- Before deleting the origional folder, test expanding the archive and ensure premiere properly locates all it's dependencies. 

# other
- ppt template
- amazon? services template?
- putty large font?
- transcription software?
