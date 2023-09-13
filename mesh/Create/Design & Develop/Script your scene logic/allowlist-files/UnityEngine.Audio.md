# UnityEngine\.Audio

## Scene

### UnityEngine\.AudioSource

A representation of audio sources in 3D\.

Supports additional properties and methods from UnityEngine\.Behaviour, UnityEngine\.Component, and UnityEngine\.Object.

| Property | Type | Description | Read? | Write? | Share? | Script |
|----------|------|-------------|:-----:|:------:|:------:|--------|
|`clip`|UnityEngine\.AudioClip|The default AudioClip to play\.|yes|yes|no|Audio Source \| Get Clip<br>Audio Source \| Set Clip
|`isPlaying`|bool|Is the clip playing right now \(Read Only\)?|yes|no|no|Audio Source \| Is Playing
|`loop`|bool|Is the audio clip looping?|yes|yes|yes|Audio Source \| Get Loop<br>Audio Source \| Set Loop
|`mute`|bool|Un\- / Mutes the AudioSource\. Mute sets the volume=0, Un\-Mute restore the original volume\.|yes|yes|yes|Audio Source \| Get Mute<br>Audio Source \| Set Mute
|`panStereo`|float|Pans a playing sound in a stereo way \(left or right\)\. This only applies to sounds that are Mono or Stereo\.|yes|yes|yes|Audio Source \| Get Pan Stereo<br>Audio Source \| Set Pan Stereo
|`pitch`|float|The pitch of the audio source\.|yes|yes|yes|Audio Source \| Get Pitch<br>Audio Source \| Set Pitch
|`time`|float|Playback position in seconds\.|yes|yes|yes|Audio Source \| Get Time<br>Audio Source \| Set Time
|`timeSamples`|int|Playback position in PCM samples\.|yes|yes|yes|Audio Source \| Get Time Samples<br>Audio Source \| Set Time Samples
|`volume`|float|The volume of the audio source \(0\.0 to 1\.0\)\.|yes|yes|yes|Audio Source \| Get Volume<br>Audio Source \| Set Volume

| Method | Parameters | Returns | Description | Script |
|--------|------------|---------|-------------|--------|
|`Pause`||void|Pauses playing the clip\.|Audio Source \| Pause
|`Play`||void||Audio Source \| Play
|`PlayClipAtPoint`|`clip` UnityEngine\.AudioClip<br>`position` UnityEngine\.Vector3|void|Plays an AudioClip at a given position in world space\.|Audio Source \| Play Clip At Point
|`PlayClipAtPoint`|`clip` UnityEngine\.AudioClip<br>`position` UnityEngine\.Vector3<br>`volume` float|void|Plays an AudioClip at a given position in world space\.|Audio Source \| Play Clip At Point
|`PlayDelayed`|`delay` float|void|Plays the clip with a delay specified in seconds\. Users are advised to use this function instead of the old Play\(delay\) function that took a delay specified in samples relative to a reference rate of 44\.1 kHz as an argument\.|Audio Source \| Play Delayed
|`PlayOneShot`|`clip` UnityEngine\.AudioClip|void|Plays an AudioClip, and scales the AudioSource volume by volumeScale\.|Audio Source \| Play One Shot
|`PlayOneShot`|`clip` UnityEngine\.AudioClip<br>`volumeScale` float|void|Plays an AudioClip, and scales the AudioSource volume by volumeScale\.|Audio Source \| Play One Shot
|`Stop`||void|Stops playing the clip\.|Audio Source \| Stop
|`UnPause`||void|Unpause the paused playback of this AudioSource\.|Audio Source \| Un Pause

## Other

### UnityEngine\.AudioClip

A container for audio data\.

Supports additional properties and methods from UnityEngine\.Object.

| Property | Type | Description | Read? | Write? | Script |
|----------|------|-------------|:-----:|:------:|--------|
|`channels`|int|The number of channels in the audio clip\. \(Read Only\)|yes|no|Audio Clip \| Get Channels
|`frequency`|int|The sample frequency of the clip in Hertz\. \(Read Only\)|yes|no|Audio Clip \| Get Frequency
|`length`|float|The length of the audio clip in seconds\. \(Read Only\)|yes|no|Audio Clip \| Get Length
|`samples`|int|The length of the audio clip in samples\. \(Read Only\)|yes|no|Audio Clip \| Get Samples

