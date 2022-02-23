# 베이그런트(Vagrant)

베이그런트(Vagrant) : 코드로 인프라 생성하는 것을 지원하는 소프트웨어임. 사용자의 요구에 맞게 시스템 자원을 할당, 배치, 배포해 두었다가 필요할 때 시스템을 사용할 수 있는 상태로 만들어 줌

자주 쓰는 베이그런트 명령

| 베이그런트 명령   | 설명                                                 |
| ----------------- | ---------------------------------------------------- |
| vagrant init      | 프로비저닝을 위한 기초 파일 생성                     |
| vagrant up        | Vagrantfile을 읽어 들여 프로비저닝을 진행            |
| vagrant halt      | 베이그런트에서 다루는 가상 머신 종료                 |
| vagrant destroy   | 베이그런트에서 관리하는 가상 머신 삭제               |
| vagrant ssh       | 베이그런트에서 관리하는 가상 머신에 ssh 접속         |
| vagrant provision | 베이그런트에서 관리하는 가상 머신에 변경된 설정 적용 |

<br/>

**베이그런트 클라우드에서 sysnet4admin/CentOS-k8s 이미지 내려 받기**

1. Vagrantfile을 열어 config.vm.box = "base" 를 config.vm.box = "sysnet4admin/CentOS-k8s" 로 변경하고 저장
2. 명령 프롬프트에서 vagrant up 실행하고 해당 가상 머신 이미지를 내려받는지 확인

<br/>

**SuperPuTTY로 다수의 가상 머신 접속해서 쿠버네티스 클러스터 구성하기**

노드 구성

- 마스터 노드(m-k8s), 워커 노드(w1-k8s, w2-k8s, w3-k8s)를 로컬 환경에서 구성

\* 가상 머신에 접속할 때 보안 경고 창이 나오는건 known_hosts(알려진 호스트)가 없어서 발생하는 경고로 Accept 누르면 known_hosts를 등록



컨테이너 실행 중 vagrant provision 명령어를 실행했더니 

`w1-k8s: [preflight] Running pre-flight checks
    w1-k8s: error execution phase preflight: [preflight] Some fatal errors occurred:
    w1-k8s:     [ERROR FileAvailable--etc-kubernetes-kubelet.conf]: /etc/kubernetes/kubelet.conf already exists
    w1-k8s:     [ERROR Port-10250]: Port 10250 is in use
    w1-k8s:     [ERROR FileAvailable--etc-kubernetes-pki-ca.crt]: /etc/kubernetes/pki/ca.crt already exists
    w1-k8s: [preflight] If you know what you are doing, you can make a check non-fatal with `--ignore-preflight-errors=...``

라는 이미 사용중인 포트라는 에러 메시지가 떴음