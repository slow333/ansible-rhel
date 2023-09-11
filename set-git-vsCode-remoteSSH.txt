### 원격 리눅스에 vs code로 원격접속해서 작업하는 방법

1. remote ssh extension 설치
   메인 아이콘에 Remote explorer 가 생김

2. 여기에서 ssh 항목에서 + 누름
3. ssh remote_server_id@SERVER_IP
   해당 암호 입력
   접속하면 원격 서버에 접속해서 서버의 폴더에서 작업 가능

### intellij remote server ssh 접속 작업하기
1. tool > deployment > configuration >
2. 이름 지정 > connection
  type : sftp
  ssh configuration : kal@IP_address

  Root path : /home/kal/ansible-rhel # 원격서버 작업 위치
  Use sudo to run ... : check
  Mappings >
  local path : C:\ansible\ansible-rhel
  Deployment path : / # 이렇게 해야 root path로 올라감

3. 파일 올리기
   파일을 끌어서 폴더로 옮기거나,
   파일 우클릭 => deployment > upload to ...

### git 설정
git에 repository 생성 => 서버에서 key 생성 => git에 key.pub 등록

작업 폴더에서 
git init
git remote add origin git@github.com:slow333/[name.git]   => ssh로 해야함 그래야 암호 안물어봄
git branch -M main
git add [file]
git commit -m "원하는 comment"
git push -u origin main