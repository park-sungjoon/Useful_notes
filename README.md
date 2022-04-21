# Useful_notes
CLI환경에서 NAS mount 하는 방법 테스트하여 공유 드립니다.
/etc/fstab 파일 마지막 줄에 다음과 같이 추가
//192.168.1.105/Shared_research SHARED_FOLDER_PATH cifs credentials=HOME_FOLDER_PATH/.smbid 0 0
SHARED_FOLDER_PATH는 NAS의 Shared-research폴더를 마운트시킬 위치입니다. (e.g., 저의 경우는 /mnt/NAS로 했습니다.)
HOME_FOLDER_PATH는 홈폴더 위치입니다. (e.g., /home/taeyoung)
2. 홈폴더 아래에 다음과 같이 .smbid생성
username=USERNAME
password=PASSWORD
3. 마운트 시킬 폴더 생성
위에서 지정한 마운트 시킬 폴더를 미리 생성합니다. (저의 경우는 /mnt/NAS 폴더)
4. 다음과 같은 명령어로 마운트합니다.
sudo mount -a
** 만약 뭔가 오류가 난다면 cifs 유틸이 설치가 안되어있는 것이니 sudo apt install cifs-utils로 설치하시면 됩니다. 
