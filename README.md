# oneline_script
A collection of one line script

## Developer
* Create github repository

```bash
curl -u 'USER' https://api.github.com/user/repos -d '{"name":"REPO"}'
```

* Find process using port (windows)
```bash
netstat -aon|findstr <port>
```

## DevOps
* Start ec2 instance, need awscli and run `aws config` first

```bash
aws ec2 start-instance --instance-ids  <instance id>
```

* Delet old files
```
tmpwatch 100d /var/log
```
or 
```
tmpreaper 100d /var/log
```

Test network
* server 
```
iperf3 -s
```

* client 
```
iperf -c 192.168.1.1  -P 30 -t 60
```

* find big folder and files
```
du -a /var | sort -n -r | head -n 10
```

`find / -type f -size +1024k`

* sort APT package by size
`dpkg-query -W --showformat='${Installed-Size} ${Package}\n' | sort -nr | less`

* delete all docker containers
```
docker rm $(docker ps -aq)
```

* attch container
```
docker exec -i -t 665b4a1e17b6 /bin/bash #by ID
```

## OS
* Mount Samba/Windows Share to local
```
mount -t cifs //192.168.1.2/temp ~/temp -o username=someone,password=someone,rw,dir_mode=0777,file_mode=0777```
```
* Delete duplicated file those big than 100M 
```
jdupes -dr --xsize=100M .
```
* Delete empty folder
```
find . -type d -empty -delete
```
* Rename files
```
rename <pattern> <replacement> <file-list>
```
## Video/Audio
* Extract mp3 from video file

```bash
ffmpeg -i sample.avi -f mp3 -ab 192000 -vn sample.mp3
```

* Cut mp3 
```bash
 ffmpeg -i source.mp3 -ss 00:01:12 -t 00:01:42 -acodec copy target.mp3
```
* Get video encode format
```bash
ffprobe -v error -select_streams v:0 -show_entries stream=codec_name -of default=nokey=1:noprint_wrappers=1 sample.mp4
```
* Cut by time
```bash
ffmpeg -i file.mkv -ss 20 -to 40 -c copy file-2.mkv
```

* convert to h265
```bash
 ffmpeg -i input.mp4 -vcodec libx265 -crf 28 output.mp4
 ```
