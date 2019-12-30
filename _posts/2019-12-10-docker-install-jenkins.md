---
layout: post
date: 2019-12-10 11:00:00 +0900
categories: til
tags: ["docker"]
---

# Install Jenkins on Docker

## 최신 버전 실행

도커 허브에서 젠킨스 이미지를 확인한다.

    https://hub.docker.com/_/jenkins

다음 명령어로 젠킨스를 실행한다.

    docker run -p 8080:8080 -p 50000:50000 jenkins

8080 포트로 접속하면 젠킨스가 실행된 것을 확인할 수 있다. 이때 저장된 데이터는 컨테이너가 중지되면 모두 사라지게 된다.

## 데이터 경로 지정해서 실행

`-v` 명령어를 사용해서 `/var/jenkins_home` 값을 지정해준다.

    docker run -p 8080:8080 -p 50000:50000 -v /your/home:/var/jenkins_home jenkins

`/your/home` 경로에 젠킨스 데이터가 저장된다.

## 권한 문제가 발생할 경우

`jenkins` 이미지에서 사용하는 uid 를 확인한다.

    $ sudo docker run -p 8080:8080 -p 50000:50000 -it jenkins bin/bash
    $ id
    uid=1000(jenkins) gid=1000(jenkins) groups=1000(jenkins)

`jenkins` 폴더를 생성하고, uid `1000`에 권한을 부여한 뒤 실행한다.

    mkdir jenkins
    chown 1000 jenkins
    docker run -p 8080:8080 -p 50000:50000 -v $PWD/jenkins:/var/jenkins_home -t jenkins

## Jenkins 도커 bash 접속

    $ docker logs jenkins

## 백그라운드 실행

`-d` 옵션을 추가한다.

    $ docker run -d -p 8080:8080 -p 50000:50000 -v $PWD/jenkins:/var/jenkins_home -t jenkins
