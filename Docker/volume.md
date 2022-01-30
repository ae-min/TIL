# Docker Volume

1. Docker container에 쓰여진 데이터는 기본적으로 컨테이너 삭제 시 함께 사라지는데,  
컨테이너의 생명 주기와 관계 없이 데이터를 영속적으로 저장할 수 있도록 하는 방법 중 하나가 docker volume

2. 컨테이너들 끼리 데이터 공유 시 사용 (nginx 내부의 static 파일들과 django의 static 파일들을 동기화 시키기 위해서 docker volume을 사용 가능)

---
## 1. bind volume 
- host server(vps서버)와 nginx컨테이너간의 각 파일들을 연동, 동기화 시킴

## 2. named volume
- 도커 안에서 이름이 있는 새로운 볼륨을 만들고, 이 새로운 볼륨을 django컨테이너나 nginx같은 컨테이너들과 붙여서 동기화 가능
- 네임드 볼륨은 도커가 알아서 관리
- 만약 네임드볼륨과 연결된 컨테이너들이 사라지더라도, 네임드 볼륨은 사라지지 않고 데이터를 유지시킴
