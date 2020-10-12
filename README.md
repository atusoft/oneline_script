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

* delete all docker containers
```
docker rm $(docker ps -aq)
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

## Video/Audio
* Extract mp3 from video file

```bash
ffmpeg -i sample.avi -f mp3 -ab 192000 -vn sample.mp3
```

* Cut mp3 
```bash
 ffmpeg -i source.mp3 -ss 00:01:12 -t 00:01:42 -acodec copy target.mp3
```
