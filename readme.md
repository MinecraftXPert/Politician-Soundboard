# Politician Soundboard
View the soundboard at [https://minecraftxpert.github.io/Politician-Soundboard/](https://minecraftxpert.github.io/Politician-Soundboard/)

## Compression Self Notes
We want to keep file sizes as small as possible without losing significant quality from the original.

#### audio codecs (in order of worst to best compression)
1) mp3 (supported by everything)
2) vorbis (supported by everything but IE)
3) opus (supported by everything but IE and Safari)

Since opus gives best compression I chose to go with it. womp womp IE and Apple IE (Safari) users.

#### video codecs (in order of worst to best compression)
1) VP8 (supported by everything but IE)
2) H264 (supported by everything)
3) VP9 (supported by everything but IE and Safari)
4) H265 (only supported by Safari and Firefox)
5) AV1 (supported by everything but IE and Safari)

It should also be noted that the WEBM container is smaller and has better support for progressive playback compared to MP4. However, WEBM only supports VP8, VP9, and AV1.

Since AV1 gives best compression along with WEBM I have gone with those. Dear IE and Safari users, get gud lol.

#### ffmpeg command
We could play with the crf value, but 40 compresses the original to about 1/4th of the size.
```
ffmpeg -i you-aint-black-original.mp4 -c:v libsvtav1 -crf 40 -c:a libopus output.webm
```