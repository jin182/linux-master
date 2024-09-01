# 리눅스 명령어 요약 정리

## 파일 소유권 변경 (`chown`)
- **명령어**: `chown 소유자:그룹 파일명`
- **예시**: `chown ihduser:kait lin.txt`
- **설명**: 파일 `lin.txt`의 소유자를 `ihduser`로, 그룹 소유권을 `kait`로 설정합니다.

## 디스크 사용량 확인 명령어
- **디렉토리 사용량**: `du`
- **디스크 전체 사용량**: `df`
- **파티션 확인/편집**: `fdisk`

## 파일 시스템 관련 파일
- **/etc/fstab**: 부팅 시 시스템이 마운트해야 하는 파일 시스템 정의.
- **/etc/mtab**: 현재 시스템에 마운트된 파일 시스템 정보.
- **/etc/mounts**: /etc/mtab에 기록된 파일 시스템 목록을 관리.

## XFS 파일 시스템 생성
- **명령어**: `mkfs.xfs /dev/sdb1`
- **설명**: `/dev/sdb1` 파티션을 XFS 파일 시스템으로 포맷합니다.

## Nano 편집기 종료
- **단축키**: `[Ctrl] + [x]`
- **설명**: 나노 편집기 종료 시 변경사항 저장 여부를 묻습니다.

## Bourne Shell 계열
- **Bourne Shell**: 기본 유닉스 셸(`sh`).
- **Dash**: Debian Almquist Shell, Debian 시스템에서 `sh` 대체.
- **Bash**: GNU 프로젝트의 Bourne Again Shell.

## FTP 설치 확인 (vsftpd)
- **명령어**: `rpm -qa 패키지명`
- **설명**: 특정 패키지(`vsftpd`)가 설치되었는지 확인.

## 특수 허가권
1. **Sticky-Bit를 파일에 부여**:
   - **설명**: Sticky-Bit는 주로 디렉토리에서 사용되며, 해당 디렉토리 내의 파일을 삭제할 때 특정 권한을 가진 사용자만 삭제할 수 있도록 합니다. 파일에 Sticky-Bit를 부여하는 것은 흔치 않습니다.
   - **기타**: Sticky-Bit는 일반적으로 파일에 부여되지 않으며, 이 사용 방법은 흔치 않기 때문에 다른 옵션들과 비교했을 때 가장 거리가 먼 것으로 판단됩니다.

2. **Set-UID를 실행 파일에 부여**:
   - **설명**: Set-UID는 실행 파일에 주로 사용되며, 해당 파일을 실행하는 동안 프로세스는 파일 소유자의 권한을 얻습니다. 이는 특정 작업을 수행하기 위해 일시적으로 루트(superuser) 권한이 필요한 경우에 사용됩니다.

3. **Set-GID를 실행 파일에 부여**:
   - **설명**: Set-GID는 실행 파일에 사용되며, 해당 파일을 실행하는 동안 프로세스는 파일의 그룹 권한을 얻습니다. 이는 그룹이 특정 작업을 수행하는 데 필요한 권한이 있는 경우에 유용합니다.

4. **Set-GID를 디렉터리에 부여**:
   - **설명**: Set-GID는 디렉토리에도 부여될 수 있습니다. 디렉터리에 Set-GID를 부여하면, 해당 디렉토리에 생성된 새로운 파일의 그룹은 디렉터리의 그룹으로 설정됩니다.

## 리눅스 데스크톱 환경
- **GDM**: GNOME 디스플레이 매니저.
- **GNOME**: GNU 프로젝트의 데스크탑 환경.
- **Mutter**: GNOME 3의 윈도우 매니저.

## FTP 포트
- **데이터 전송**: 20번 포트
- **제어**: 21번 포트

## 컨테이너 기술
- **Kubernetes**: 컨테이너화된 애플리케이션의 자동 배포 및 관리 플랫폼.
- **Docker**: 컨테이너화된 애플리케이션의 개발 및 실행 플랫폼.

## 압축률 순서
- **순서**: `xz > bz2 > gz > compress`
- **명령어**
  - **.xz**: `tar -Jxvf`
  - **.bz2**: `tar -jxvf`
  - **.gz**: `tar -zxvf`
  - **compress**: `tar -Zxvf`

## Tar 옵션 정리
- **-x**: tar 파일을 풉니다.
- **-z**: gzip 파일로 압축 해제.
- **-c**: 파일/디렉터리를 아카이브(tar)로 묶음.
- **-f**: 아카이브 파일명 지정.
- **-v**: 작업 파일 처리과정을 화면에 출력.
- **-t**: tar 안의 파일 목록 출력.
- **-P**: 절대 경로 정보 출력.
- **-r**: 기존 tar 파일에 파일 추가.
- **-j**: tar.bz2 압축 파일에 사용.
- **-J**: xz 압축 파일에 사용.
- **-C**: 디렉터리 변경.

## Signal 코드
- **SIGINT**: 2
- **SIGQUIT**: 3
- **SIGTSTP**: 20
- **SIGCONT**: 18
