# SVN
중앙 집중형 버전관리 도구인 SVN(Subversion:서브버전) Studying

## 버전관리 도구

버전관리 시스템(Version Control System)은 형상관리(Software Configuration Management)의 한 분류이다.   
따라서 형상관리 도구 혹은 버전관리 도구라고 불러도 무방하다.  
버전관리는 여러 명이 작업할 때 뛰어난 효과를 얻을 수 있다. 심지어 혼자 작업할 경우도 상당히 유용하다.

## 중앙집중형 버전관리 도구 Subversion(SVN)와 분산 버전관리 시스템인 Git

중앙 집중형 버전관리 도구(CVCS : Centralized Version Control System)은 내가 작업하고자 하는 파일 또는 프로젝트 버전만 서버에서 받아오지만   
분산 버전관리 시스템(DVCS : Distributed Version Control System)은 네트워크 없어도 저장소 전체를 클라이언트에 다운로드하여 관리하는 차이점이 있다.

## SVN(Subversion)의 이해

중앙 집중형 버전관리 도구인 SVN(Subversion)의 주요 기능은 다음과 같다.   

1. 디렉터리의 버전관리 : 시간과 함께 디렉터리 트리 전체 변경을 확인할 수 있다.
2. 버전 이력 기능 강화 : 파일과 디렉터리의 모두에 대해 추가, 삭제, 복사, 명칭 변경을 할 수 있다.
3. Atomic Commit : 변경 사항 전체가 저장소에 완전하게 반영 되어지거나, 전혀 반영되지 않을 수 있다.
4. 메타 데이터 버전관리 : 파일과 디렉터리는 각각 관련한 속성키와 값의 조합이며 임의의 조합을 생성해 보존할 수 있다.
5. 네트워크층의 선택 : http 서버의 확장 모듈로서 플러그인될 수 있고 기존의 서버가 제공하는 기능을 곧바로 이용할 수 있다.
6. 데이터 처리의 일관성 : 동일한 알고리즘을 사용해 파일의 변경 부분을 표현한다.
7. 효율적인 브랜치, 태그의 작성 : 프로젝트를 복사하는 것으로 브랜치와 태그를 만든다.
8. 확장하기 쉬움 : 잘 설계된 api로 완성된 c의 공유 라이브러리의 모임이며 유지보수나 다른 애플리케이션, 언어와 연동하여 사용하기 쉽다.

## svn 명령어와 svn 작업 사이클

1. init : 프로젝트 매니저나 리드 개발자가 svn 서버에 프로젝트 저장소를 만든다.
2. import : 개발자 한 명이 초기 버전에 대한 문서나 파일을 서버에 올린다.
3. checkout : 서버에 저장되어 있는 것을 자신의 로컬 작업환경에 가져온다.
4. add/remove : 개발자는 새로운 소스나 파일 등을 추가하거나 삭제한다.
5. Update : 서버에 저장되어 있는 최근의 소스를 로컬로 가져온다.
6. Conflict : 한 파일의 일부 행을 두 명 이상의 사용자가 변경했을 때 또는 갱신할 때 충돌이 발생한다. 즉 타인에 의해 수정되고 커밋된 상태이다.
7. commit : 체크인이라고도 하며, 로컬에 체크아웃한 소스를 수정, 추가, 삭제한 후 저장소에 저장하여 갱신한다.
8. export : 체크아웃과는 달리 버전관리 파일들을 뺀 순수한 소스 파일을 가져온다.
9. trunk : 프로젝트의 중심 디렉터리로 모든 개발은 trunk 디렉터리에서 이루어진다.
10. branches : trunk 디렉터리에서 개발하다보면 큰 프로젝트에서 작은 분류로 빼서 따로 개발해야 할 때 브랜치 디렉터리 안에 또 다른 디렉터리를 두어 그 안에서 개발한다.
11. tag : 태그 디렉터리는 프로그램을 개발하면서 정기적으로 릴리즈를 할 때 그때그때 발표한 소스를 따로 저장하는 공간이다.
12. hook : 새로운 개정판의 생성이나 버전관리가 되지 않은 속성의 수정과 같은 저장소 이벤트에 의해 실행되는 프로그램을 의미한다. hook는 그 이벤트가 무엇인지, 어떤 목표로 작동하는지, 이벤트를 실행한 사람의 사용자 이름을 알려준다.
13. lock : 사용자가 작업 사본 파일을 수정할 독점적 권리를 요구하는 장치이다.
14. merge : 병합은 하나의 브랜치에 대한 변경 사항을 다른 브랜치와 합쳐서 트렁크로 반영하는 것을 의미한다.

특정 소스와 관련된 과거 모든 리비전의 내역을 보고자 한다면 이클립스의 기본 카테고리인 team -> history 뷰를 통해 조회할 수 있다.

## TortoiseSVN, Subversive 

### TortoiseSVN 사용

프로젝트를 github에서 다운받아서 오른쪽 마우스 클릭 후 TortoiseSVN -> import 메뉴를 선택한다.   
![image](https://user-images.githubusercontent.com/58906858/180745835-96d13d46-00d7-494b-ba3a-ec4b6b33707c.png)

url 입력창이 나오는데 VisualSVN Sever Manager에서 SVNRepository를 선택하고 오른쪽 마우스 클릭 후 Copy URL to Clipboard를 선택하여 저장소의 URL을 복사한다.   
![image](https://user-images.githubusercontent.com/58906858/180746004-2ecd008a-1ce6-4789-9c18-a8f911a75e39.png)   
![image](https://user-images.githubusercontent.com/58906858/180746264-52f4963b-6a18-4c2d-8544-f98ed8f0c99b.png)

복사한 url 뒤에 프로젝트 이름을 붙여준다.   
import Message에는 적당한 메시지를 입력한다. 안 적어도 무방하지만 추후 파일을 비교하거나 찾을 때 메시지가 있으면 편하다.   
프로젝트를 import 하면 다음과 같이 revision이 1 증가된다.   
![image](https://user-images.githubusercontent.com/58906858/180746806-066a3f25-9c95-474c-9fd5-bb82651c316e.png)

서버에 올라간 프로젝트를 자신의 로컬 작업 환경으로 가져올 때는 디렉터리를 생성하고 오른쪽 마우스 클릭 후 SVN Checkout메뉴를 선택한다.   
URL of repository에는 아까 생성한 url을 넣어주고 checkout directory에는 서버의 프로젝트를 넣을 디렉터리의 주소를 넣는다.   

다음과 같이 서버의 프로젝트를 checkout한 것을 확인할 수 있다.   
![image](https://user-images.githubusercontent.com/58906858/180747667-7a86a7d1-481b-49f3-b48a-3106be35073f.png)

## 이클립스 Subversive 플러그인 사용

서버 저장소에 있는 프로젝트를 이클립스에서 체크아웃을 해본다. SVN Repository Exploring Perspective를 열어주고 오른쪽 마우스 클릭 후 New -> Repository Location을 선택한다.   
![image](https://user-images.githubusercontent.com/58906858/180748454-53d90bce-4bd7-4662-ba8e-1673065d72d0.png)

url은 VisualSVN Repository의 url주소를 넣고 밑에 user와 password를 입력하여 저장소를 생성한다.   
생성 후 SVN Repository의 프로젝트를 오른쪽 마우스 클릭 후 check out 메뉴를 선택한다.   
   
이제는 프로젝트를 서버에 올려본다. 프로젝트 오른쪽 마우스 클릭 후 Team -> Share Project 메뉴를 선택하고 svn을 선택한다.   
기존에 등록했떤 저장소를 선택하고 commit 창에서 Resource가 모두 선택된 채로 ok 버튼을 클릭한다.   
![image](https://user-images.githubusercontent.com/58906858/180750101-f7fe08ed-78a7-421e-8fe9-097a10a147d8.png)

새로고침(F5)를 누르면 해당 프로젝트가 올라간 것을 확인할 수 있고 VisualSVNServer 서버 저장소에서도 새로고침을 눌러 확인할 수 있다.
![image](https://user-images.githubusercontent.com/58906858/180750333-091e003f-e76a-4c0f-9169-27b036c68dcd.png)

## SVN 사용

이클립스에서 올린 프로젝트를 TortoiseSVN을 통해서 체크아웃한다.   
서버의 프로젝트를 checkout 하기위해 디렉터리 오른쪽 마우스 클릭 후 SVN Checkout을 클릭한다.   
![image](https://user-images.githubusercontent.com/58906858/180751322-53b90f04-81f9-488c-89e4-80253da5e964.png)
이제 프로젝트의 일부를 변경하여 커밋을 하고 다른 클라이언트에서 변경된 사항만을 가져오는 update를 수행할 수 있다.   
프로젝트안의 pom.xml에 주석문을 넣는다.   
![image](https://user-images.githubusercontent.com/58906858/180752269-eabca0cc-5f2e-46ab-987f-2053b345c8b7.png)
변경사항이 있는데 서버에 커밋되지않는다면 다음과 같이 빨간색 느낌표로 알려준다.   
pom.xml 오른쪽 마우스 클릭 후 SVN Commit을 수행한다.
서버에 변경사항이 반영되고 이 변경사항을 다른 개발자가 자신의 공간으로 가져오려면 이클립스에서 프로젝트 오른쪽 마우스 클릭 후 Team -> Update를 수행하면 서버의 최신사항 즉 변경사항이 반영되어진 프로젝트를 가져올 수 있다.   

Team -> Show History를 수행하면 어떤 파일이 누구에 의해 변경되었는지 리비전 번호는 어떻게 달라졌는 지 등을 알 수 있다.
![image](https://user-images.githubusercontent.com/58906858/180752893-16386b33-4000-410d-926e-ff953ff4666a.png)

이 외에도 리소스의 이름변경과 이동, 삭제, 브랜치, 태그 등 다양한 기능을 사용할 수 있다.


