### 우분투에 깃 설치하고 기초 설정
https://git-scm.com/downloads 홈페이지에서 우분투 설치를 들어가면 설치방법이 있다.
```
apt-get install git
```
라고 하라고 되어있는데 저대로 치면 할수없다고 나와서
```
sudo apt-get install git
```
라고 해줘야 한다

```
git --version
```
버전 확인
```
git config --global user.name '내 깃허브 이름'
git config --global user.email '깃허브 연결된 이메일'
```
을 쳐서 내 정보를 등록 해준다
```
git config --list
```
로 등록된것 확인
```
gir clone 깃허브 레퍼지토리 복사 붙여넣기
```
완료되면 내 컴퓨터에 깃허브 폴더가 추가된것을 확인 할 수 있다
