# [Leanote](http://leanote.org/) Dockerfile

This is yet another Dockerfile to run Leanote. Heavily inspired by the version from [furiousgeorge](https://github.com/hannah98/docker-leanote).  

This Dockerfile runs Leanote only, MongoDB should be already running or launched from a different container.  

## Usage

To run, adjust the attached app.conf file and be sure to set a reachable MongoDB instance.  
Start the container as follows:
```
docker run -p 9000:9000 -v `pwd`/files/:/leanote/files -v `pwd`/public/upload/:/leanote/public/upload leanote:latest
```
This exposes Leanote's default port 9000 and mounts local directories ./files and ./public/upload to store non-ephemeral data.
