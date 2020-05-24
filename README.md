# oneline_script
A collection of one line script

## Developer
Create github repository

```bash
curl -u 'USER' https://api.github.com/user/repos -d '{"name":"REPO"}'
```

## DevOps
Start ec2 instance, need awscli and run `aws config` first

```bash
aws ec2 start-instance --instance-ids  <instance id>
```

## OS
Mount Samba/Windows Share to local
```sudo mount -t cifs //nas/folder local_folder```

## Video/Audio
Extract mp3 from video file

```bash
ffmpeg -i sample.avi -f mp3 -ab 192000 -vn sample.mp3
```
