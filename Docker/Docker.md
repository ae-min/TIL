# Docker

## 1. 도커란
- 가상화 기반 : 기존의 방식은 OS위에 가상머신(vm)을 나눠서 만드는 방식이었다면,  
도커는 OS위에 컨테이너를 만드는 방식으로, 언제 어느 곳에서 어떤 os를 쓰던 간에 
규격화되고 표준화된 같은 환경의 컨테이너를 사용 가능함
- 일반 OS를 사용하는 것과 비슷한 빠른 속도로 사용가능. VM에 비해 도커는 성능하락이 거의 없음
- 개발 배포 빌드 유지보수 모두 다 빠름

## 2. 도커의 장점
- 도커를 사용하지 않고 배포할 경우 : 개발환경과 OS환경의 호환성, 개발 시 사용한 것과 의존된 프로그램 설치, 파이썬 설치, 관련 라이브러리 설치, 환경변수 설정, 테스트가 어떻게 되는지 확인 등 해야할 것이 많고 번거로움.
- 도커를 사용한다면 : 최초 한번은 (호환성, 관련 설치, 테스트 등)을 해야하지만, 한 번 만들어 뒀으면 추후에 발생되는 추가적인 일들은 없음.
- 최초 한번 만들어둔 것을 이미지 형태로 저장을 해둔 뒤, 이 이미지를 원할때마다 실제 서버에 구축하는 형태 (컨테이너를 사용하여 구축)

## 3. 도커의 필요성
- 만약 서버를 한번 빌려 배포 후, 어떠한 유지보수도 이루어지지 않는 경우라면 도커를 사용하지 않아도 되겠지만, 실제로 배포를 하다보면 서버다운, 서버이동, 유지보수 등의 여러 애로사항이 발생하기때문에 도커가 유용함. 
이미지를 계속 복제해서 컨테이너 형식으로 구축하면 되므로 매우 편리해짐.
- [이미지 = 클래스] , [컨테이너 = 인스턴스]의 관계라고 이해 가능 => 이미지를 상속받아 새로운 이미지를 만들 수 있고, 이미지를 상속받아 새로운 객체를 만들 수도 있고