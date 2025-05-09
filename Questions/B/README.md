
## Question B: Funny Cat Slideshow

-----

Ellie has a long bus journey in the countryside. To pass the time, she tries watching a funny cat compilation on her phone. Having only a weak connection during the journey, the video playback is frequently interrupted.

Ellie's favourite content platform 'DougaBeam' uses the following logic for streaming video:
- Each video frame has an associated frame ID, indicating its position in the overall video
- Any video stream is treated as a series of 'buffer blocks' containing 12 consecutive frames each, though the final 'block' within a video may contain fewer frames.
- A buffer block is considered 'unhealthy' until all anticipated frames have arrived, at which point the block becomes 'healthy'.
- Video frames are played at a rate of 20 frames per second.
- If the video is playing and would enter an 'unhealthy' block of video frames, playback instead stops after playing the last frame from the previous healthy block.
- When the video isn't playing, the application waits until either of the following conditions are met before resuming (or starting) playback:
	- A) The next three un-played blocks of the video are healthy
	- B) All remaining blocks of the video are healthy
- DougaBeam evaluates whether to begin or resume playing at 200ms intervals using an internal timer system. Importantly, this check ignores any video frames that arrive at the same time as the check is being performed.

After a series of interruptions, Ellie's video finally finishes playing after over 16 minutes.
Given ```FunnyCatStream.csv```, which details the arrival of video frames relative to DougaBeam's internal timer, how many times did playback stop to wait for more video frames to arrive? 

Enter your answer as an integer (e.g. 10) into the hex-grid tool under **Question B** and generate a pattern to present for validation.

