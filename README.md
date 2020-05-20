# oneline_script
A collection of one line script

## Developer
create github repository

```bash
curl -u 'USER' https://api.github.com/user/repos -d '{"name":"REPO"}'
```

## Video/Audio
```bash
ffmpeg -i sample.avi -f mp3 -ab 192000 -vn sample.mp3
```
