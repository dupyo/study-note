# 도커 이미지

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

