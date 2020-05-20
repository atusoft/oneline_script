# oneline_script
A collection of one line script

## Developer
Create github repository

```bash
curl -u 'USER' https://api.github.com/user/repos -d '{"name":"REPO"}'
```

## Video/Audio
Extract mp3 from video file
```bash
ffmpeg -i sample.avi -f mp3 -ab 192000 -vn sample.mp3
```
