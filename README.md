# PyTorch GStreamer Video Pipeline

https://paulbridger.com/posts/video-analytics-pytorch-pipeline/


## Docker
```bash
docker build docker/ -t pytorch-gst
docker run -it -v $PWD:/app --device /dev/snd --entrypoint=/bin/bash pytorch-gst
```

## Validate Environment
```bash
# Running this will show the video file being read (by the filesrc element), decoded (decodebin element) and sent to the Gstreamer equivalent of /dev/null (fakesink element).
gst-launch-1.0 filesrc location=media/in.mp4 ! decodebin ! progressreport update-freq=1 ! fakesink sync=true

# or to test audio
gst-launch-1.0 audiotestsrc ! alsasink
```
