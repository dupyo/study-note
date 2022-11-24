# 도커 활용하기

도커 이미지는 일반적으로 docker hub와 같은 도커 레지스트리에서 공유함

하지만 도커 레지스트리를 사용할 수 없는 경우 도커 이미지를 tar 파일로 만들어 공유 가능

## 도커 이미지를 tar 압축 파일로 저장

docker save 명령어로 도커 이미지를 tar 압축 파일로 추출 가능

```docker
docker save [option : --output, -o] [tar filename] [image name]
```

### docker save & load

 - docker save (docker image → tar)

 - docker load (tar → docker image)

### docker export & import 

 - docker export (docker container → tar)

 - docker import (tar → docker image)

## 사용 명령어 모음

```docker
# dockerhub로부터 tomcat 이미지를 pull 받기
docker pull tomcat:9.0.68-jdk8

# pull 받은 tomcat 이미지로 컨테이너 생성
docker run -it --name tomcat-test -p 9091:8080 tomcat:9.0.68-jdk8

# 컨테이너 생성 여부 확인
docker ps -a

# tomcat 컨테이너에 접속
docker exec -it tomcat-test /usr/bin/bash

# 컨테이너에 접속 후 /usr/local/tomcat# 기본 경로에서 시작
# tomcat 컨테이너는 실행 후 기본 페이지를 요청해도 바로 화면에 띄울 수 없음.
# 그 이유는 Apache tomcat에서 tomcat/webapps 경로에 ROOT 폴더를 포함한 어떤 파일도 존재하기 않도록 설계하였기 때문임.
# 고양이 그림이 있는 페이지를 띄우기 위해서는 아래와 같이 폴더 경로를 수정해야 함.
mv webapps webapps2
mv webapps.dist/ webapps

# => 기본 페이지 띄우기 성공

# 현재 호스트에서 컨테이너로 파일 복사하기
docker cp ./ROOT.war tomcat-test:/usr/local/tomcat/webapps/

# tomcat은 HTTP/1.1 통신하기 위해 사용하는 기본 포트가 8080임.
# 따라서 필요에 따라 tomcat/conf/server.xml 파일에서 HTTP/1.1 통신 포트 번호를 변경해줘야 함.

```

## 도커 컨테이너 내부에서 호스트에 접근하는 방법

```docker
curl host.docker.internal:{port}
```

## 미니쿠베(minikube)로 웹 애플리케이션 배포

관련 블로그 참고

[[쿠버네티스] docker 이미지 빌드 부터 helm 배포까지 [1부]](https://jay-ji.tistory.com/97)
