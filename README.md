# [Leanote](http://leanote.org/) Dockerfile

This is yet another Dockerfile to run Leanote. Heavily inspired by the version from [furiousgeorge](https://github.com/hannah98/docker-leanote).  

This Dockerfile runs Leanote only, MongoDB should be already running or launched from a different container.  

## Usage

The easiest way to set this up is to clone this Github repository and build it locally. This way you already have your config file and shared directories set up for you:
```
git clone https://github.com/klazutin/leanote-docker
cd leanote-docker
```
Next, change the included `app.conf` file to match your MongoDB configuration. Now you can run the build:
```
docker build -t leanote:latest .
```
Finally, start the container as follows:
```
docker run -p 9000:9000 -v `pwd`/files/:/leanote/files -v `pwd`/public/upload/:/leanote/public/upload leanote:latest
```
This exposes Leanote's default port 9000 and mounts local directories ./files and ./public/upload to store non-ephemeral data.
