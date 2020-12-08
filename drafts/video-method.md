# Configure OBS
OBS (Open Broadcast Studio) is a free tool that provides professional grade control of live video sources, such as screen recording and webcams. 

I use it to record my HD (1080p) logitech webcam, and both monitors (1080p mode). 

First, make a 4K canvas. Add each video source (1 webcam, 2 monitors, 3 total) to quadrants of the 4K canvas.

Double check you have audio recording from the proper device selected, such as a headset. 

Start recording. 

After you finish recording, use the "remux" menu option to prepare the files for importing into adobe premiere. 

# Adobe Media Encoder

Adobe Media Encoder reformats the video clips as preferred by Premiere, and it seperates out the 3 different video streams from the 4K canvas. 

1. Add video
2. Select ProRes 422
3. Configure crop settings
4. Set save location
5. add another encoding for the same video clip
6. add encodings for each video stream
6. add the other video clips, and repeat
7. export, using paralell encoding 💪 

# import 

Create new premiere project. 

Create new folder for project, and check all settings are set to "use project folder"

Navigate to "Ingest Settings" and use "Copy and Create Proxies"

Choose medium res proxy. 

Ingest all your video clips (should have 3x number of recording sessions). This will automatically create proxies. 

# multicam
- select multiple clips
- create multicam from selection
- all exactly same lenght, perfectly aligned already
- accept
- basics of multicam editing link

# edit
- basics of timeline
- multiple timelines
- keyframe
- screenshots
- ultrakey 
- effects

# export
- youtube settings
- transcription software?

- use adobe tools for checking if everything in project folder
- 7z, copy to cold storage

# other
- ppt template
- amazon? services template?
- putty large font?
