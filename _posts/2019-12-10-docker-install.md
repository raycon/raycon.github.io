---
layout: post
date: 2019-12-10 11:00:00 +0900
categories: til
tags: ["docker"]
---

# Install Docker on Ubuntu

## 도커 저장소 추가

apt 패키지를 업데이트 한다.

    $ sudo apt-get update

도커 공식 GPG 키를 추가한다.

    $ curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
    OK

x86_64 / amd64 용 저장소를 추가한다.

    $ sudo add-apt-repository \
      "deb [arch=amd64] https://download.docker.com/linux/ubuntu \
      $(lsb_release -cs) \
      stable"

## 도커 CE 설치

apt 패키지를 업데이트 한다.

    $ sudo apt-get update

도커 최신 버전을 설치한다.

    $ sudo apt-get install docker-ce

`hello-world` 이미지로 설치를 확인한다.

    $ sudo docker run hello-world

설치가 완료 되면 `docker` 그룹이 생성되지만 유저는 추가되지 않는다. 따라서 도커 명령어를 사용하려면 `sudo` 를 사용해야 한다. 유저를 추가하거나 다른 설정을 변경하려면 [Linux postinstall](https://docs.docker.com/install/linux/linux-postinstall/) 문서를 참고한다.

## 일반 사용자에 권한 추가

`docker` 그룹을 생성하고 유저를 추가한다.

    $ sudo groupadd docker
    $ sudo usermod -aG docker USER_NAME

로그아웃하고 다시 접속해서 `sudo` 명령어 없이 도커를 실행해서 권한을 확인한다.

    $ docker run hello-world

