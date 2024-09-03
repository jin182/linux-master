
# 리눅스 명령어 요약 정리

## 별칭(`alias`)
alias [별명=명령어]
그 외 옵션 없습니다.

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
  
- Set-UID와 Set-GID는 보안에 매우 취약한 설정입니다. 이러한 권한 설정은 잘못 사용될 경우 시스템 보안에 심각한 위험을 초래할 수 있습니다. 특히, 루트 권한을 필요로 하는 프로그램에서 Set-UID를 사용하는 경우, 악의적인 사용자가 이를 악용하여 시스템 전체에 대한 제어권을 획득할 수 있습니다.


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
- **SIGINT**: 2 (Ctrl + C)
- **SIGQUIT**: 3  (Ctrl + `\`)
- **SIGTSTP**: 20  (Ctrl + Z)
- **SIGCONT**: 18

# 리눅스 파일 시스템 관리 명령어

리눅스에서 파일 시스템을 관리할 때 자주 사용하는 명령어들을 정리했습니다.

- **`umount`**: 
  - **설명**: `umount`는 리눅스에서 파일 시스템을 마운트 해제하는 명령어입니다. 
  - **사용 예시**: 
    ```bash
    umount /mnt/mydisk
    ```
  - **참고 사항**: 마운트된 파일 시스템을 안전하게 해제하려면 이 명령어를 사용해야 합니다.

- **`unmount`**: 
  - **설명**: `unmount`는 존재하지 않는 명령어입니다. 리눅스에서 파일 시스템을 마운트 해제할 때는 `umount` 명령어를 사용해야 합니다.
  - **참고 사항**: 오타에 주의해야 하며, `umount`가 올바른 명령어입니다.

- **`eject`**: 
  - **설명**: `eject`는 주로 CD-ROM과 같은 이동식 매체의 마운트를 해제하고 장치를 제거하는 리눅스 명령어입니다. 
  - **사용 예시**: 
    ```bash
    eject /dev/cdrom
    ```
  - **기타 정보**: CD-ROM 드라이브의 트레이를 열거나 장치를 안전하게 제거할 때 사용됩니다.

- **`fsck`**: 
  - **설명**: `fsck`는 리눅스 파일 시스템을 검사하고 수리하는 명령어입니다. 파일 시스템에 문제가 발생했을 때, 이를 확인하고 복구할 수 있습니다. 
  - **사용 예시**:
    ```bash
    fsck /dev/sda1
    ```
  - **기타 정보**: 시스템 부팅 시 파일 시스템 무결성을 확인하고 복구할 때도 사용됩니다. `fsck`를 실행하기 전에 해당 파일 시스템이 마운트 해제되었는지 확인하는 것이 좋습니다.

# LINUX 하드디스크 관리 및 구성

## LVM (Logical Volume Manager)
- **설명**: LVM은 하나의 디스크를 여러 파티션으로 분할하여 유연하게 관리할 수 있도록 해주는 시스템입니다. 물리적 볼륨(PV)을 묶어 볼륨 그룹(VG)을 생성하고, 이 그룹에서 논리적 볼륨(LV)을 생성하여 사용할 수 있습니다.
- **예시**: 
  - 500GB 크기의 디스크 2개를 VG로 묶어 1TB 볼륨 그룹을 생성하고, 이 그룹에서 필요한 크기의 LV를 생성하여 사용할 수 있습니다.
- **장점**: 디스크 공간을 효율적으로 관리할 수 있으며, 볼륨 크기를 동적으로 조정할 수 있습니다.
- **단점**: 디스크 장애나 OS 재설치 시 데이터 유지에 불리할 수 있습니다. 특히 LVM 구성 시 마운트가 풀릴 위험이 있어 데이터 손실 가능성이 있습니다.
- **주의 사항**: VM 서버나 가상 디스크를 사용하는 경우 LVM이 적합할 수 있으나, 물리 디스크에서는 신중한 선택이 필요합니다.

## RAID (Redundant Array of Independent Disks)
- **설명**: RAID는 동일한 데이터를 여러 디스크에 중복 저장하여 데이터 손실을 방지하는 기술입니다. 여러 형태의 RAID 구성이 가능하며, 각 구성마다 데이터 보호와 성능 향상 정도가 다릅니다.
- **RAID-0 예시**: 
  - 500GB 크기의 디스크 2개를 RAID-0으로 묶어 1TB 디스크로 인식시킨 후 LVM을 생성할 수 있습니다.
- **장점**: RAID-1 이상의 구성에서는 디스크 장애 발생 시에도 데이터 손실을 방지할 수 있습니다. RAID-0의 경우 성능을 향상시키지만, 데이터 보호는 보장되지 않습니다.
- **단점**: RAID-0의 경우 데이터 중복이 없으므로 디스크 장애 시 데이터 복구가 불가능합니다. 또한, 하드웨어 RAID의 경우 BIOS에서 설정이 필요하며, 시스템 복구 시 추가적인 작업이 요구될 수 있습니다.
- **주의 사항**: 물리 디스크 환경에서는 RAID 구성을 우선시할 수 있습니다. 특히 데이터 보호가 중요한 경우 RAID-1 또는 그 이상의 구성을 고려해야 합니다.

## 문제 해설
LVM과 RAID 모두 500GB 디스크 2개를 이용해 1TB의 저장 공간을 구성할 수 있지만, 환경에 따라 최적의 선택이 달라질 수 있습니다.

- **LVM을 사용하는 경우**: 가상 디스크나 VM 서버에서 유연한 디스크 관리가 필요할 때 LVM을 사용하는 것이 적합합니다. 그러나 물리 디스크 환경에서는 데이터 손실 위험이 있으므로 신중해야 합니다.
- **RAID를 사용하는 경우**: 물리 디스크에서 RAID 구성을 통해 데이터 보호와 성능을 동시에 고려할 수 있습니다. 특히, RAID-0은 성능을 중시하지만 데이터 보호가 없다는 점에서 단점이 있습니다.

따라서, 특정 상황에 따라 LVM이나 RAID 중 어느 것을 사용할지 결정하는 것이 중요하며, 일반적으로 물리 디스크 환경에서는 RAID 구성을 우선시하는 것이 더 적합할 수 있습니다.

## 환경변수 VS 셸 변수

- 환경변수 = env 셸 변수 = set

## 소스 설치 방법으로 cmake

- 소스 설치 방법 cmake 선택 프로젝트 - MySQL, KDE, LMMS

## 디스플레이 매니저
사용자 로그인 및 세션 관리
[ XDM ] [ GDM ] [ KDM ] 


# X 윈도 시스템

## 개요
X 윈도 시스템은 IBM, MIT, DEC의 공동 프로젝트인 아데나 프로젝트를 통해 1984년에 Bob Scheifler와 Jim Gettys에 의해 처음 개발되었습니다. 이 시스템은 유닉스와 리눅스 환경에서 널리 사용되는 그래픽 사용자 인터페이스를 제공하는 윈도 시스템입니다.

## 역사
- **1984년**: IBM, MIT, DEC 공동의 아데나 프로젝트를 통해 X 윈도 시스템이 처음 개발되었습니다.
- **1988년**: 여러 컴퓨터 제조업체들이 모여 X컨소시엄이 조직되었습니다. X컨소시엄에 의해 X11 버전이 처음으로 개정되어 **X11R2**가 발표되었습니다.
- **1996년**: X컨소시엄이 X 윈도 시스템의 최종 개정판인 **X11R6**을 발표하였으며, **X11R6.3** 버전을 마지막으로 X컨소시엄은 해체되었습니다.

## 주요 버전
- **X11R2**: 1988년, X컨소시엄에 의해 최초로 개정된 X11 버전.
- **X11R6**: 1996년, X컨소시엄이 발표한 최종 개정판.
- **X11R6.3**: X컨소시엄 해체 전 마지막으로 발표된 버전.

## X컨소시엄
X 윈도 시스템의 개발 및 관리 조직으로, 여러 컴퓨터 제조업체들이 참여하여 X11 버전을 발전시켰습니다. 1996년에 해체되었습니다.

# 문제 해설: LAN 케이블 별 최대 전송 속도

LAN 케이블은 각 카테고리에 따라 지원하는 최대 전송 속도가 다릅니다. 아래는 주요 LAN 케이블의 카테고리와 해당하는 최대 전송 속도를 정리한 내용입니다.

## LAN 케이블 카테고리 및 최대 전송 속도
- **CAT.5**: 최대 100Mbps
- **CAT.5e**: 최대 1Gbps
- **CAT.6**: 최대 1Gbps
- **CAT.6A**: 최대 10Gbps
- **CAT.7**: 최대 10Gbps

## 해설
- **CAT.5**: 초당 100Mbps의 전송 속도를 지원하며, 기본적인 네트워크 환경에서 사용됩니다.
- **CAT.5e**: CAT.5의 업그레이드 버전으로, 최대 1Gbps의 전송 속도를 지원합니다. 오늘날 많은 네트워크 환경에서 사용됩니다.
- **CAT.6**: CAT.5e와 마찬가지로 1Gbps의 속도를 지원하지만, 더 나은 성능과 신호 품질을 제공합니다.
- **CAT.6A**: CAT.6의 업그레이드 버전으로, 최대 10Gbps의 전송 속도를 지원합니다. 고속 네트워크 환경에 적합합니다.
- **CAT.7**: 최대 10Gbps의 속도를 지원하며, 최고 수준의 성능과 차폐 기능을 제공합니다. 고성능 네트워크에서 사용됩니다.

- # 옵션 설명: 텔넷 명령어

텔넷(Telnet) 명령어는 원격 서버에 접속하기 위해 사용되는 명령어입니다. 텔넷 명령어의 주요 옵션에 대해 설명합니다.

## 옵션
- **-l 사용자 ID**: 
  - **설명**: 텔넷 서버에 접속할 때 사용할 사용자 ID를 지정하는 옵션입니다.
  - **예시**: 
    ```bash
    telnet -l username server_address
    ```
  - **기타 정보**: 이 옵션을 사용하면 미리 지정된 사용자 ID로 텔넷 서버에 로그인할 수 있습니다.

- **-a**: 
  - **설명**: 현재 로그인된 사용자의 ID를 그대로 사용하여 텔넷 서버에 접속하는 옵션입니다.
  - **예시**: 
    ```bash
    telnet -a server_address
    ```
  - **기타 정보**: 현재 로그인된 사용자 ID로 자동 로그인을 시도합니다.
 
  # 리눅스 디스크 관련 명령어 설명

리눅스에서 스토리지 디바이스와 관련된 작업을 수행할 때 유용한 명령어들에 대해 설명합니다.

## 명령어 설명
- **lsblk**: 
  - **설명**: 리눅스 시스템에서 스토리지 디바이스의 정보를 출력하는 명령어입니다. 디바이스의 이름, 크기, 유형, 마운트된 지점 등을 확인할 수 있습니다.
  - **예시**: 
    ```bash
    lsblk
    ```

- **blkid**: 
  - **설명**: 리눅스 블록 디바이스의 UUID를 출력하는 명령어입니다. 각 디스크나 파티션의 고유 식별자인 UUID를 확인하는 데 사용됩니다.
  - **예시**: 
    ```bash
    blkid
    ```

- **fdisk**: 
  - **설명**: 디스크 파티션을 생성, 삭제, 수정할 때 사용하는 명령어입니다. 주로 MBR 파티션 테이블을 관리하는 데 사용되며, 디스크를 초기화하거나 재구성할 때 유용합니다.
  - **예시**: 
    ```bash
    fdisk /dev/sda
    ```

- **df**: 
  - **설명**: 파일 시스템의 마운트된 디스크 사용량과 여유 공간을 보여주는 명령어입니다. 각 파일 시스템의 전체 크기, 사용된 공간, 남은 공간 등을 확인할 수 있습니다.
  - **예시**: 
    ```bash
    df -h
    ```

## LVM (Logical Volume Manager)

LVM은 논리적 볼륨을 효율적이고 유연하게 관리하기 위한 커널 모듈로, 가상의 블록 장치를 생성합니다. 주요 구성 요소는 다음과 같습니다:

- **PV (Physical Volume)**  
  LVM에서 블록 장치를 사용하려면 PV로 초기화해야 합니다. 블록 장치의 파티션들을 LVM에서 사용할 수 있게 변환합니다.

- **PE (Physical Extent)**  
  PV를 구성하는 일정한 크기의 블록으로, LV의 LE (Logical Extent)와 1:1로 대응됩니다. 각 PV는 동일한 PE로 구성됩니다.

- **VG (Volume Group)**  
  PV들의 집합으로, LV를 할당할 수 있는 공간을 제공합니다. PV로 초기화된 장치는 VG로 통합됩니다.

- **LV (Logical Volume)**  
  사용자가 최종적으로 다루게 되는 논리 스토리지입니다. 물리적 볼륨(PV)에서 논리적 볼륨(LV)으로 데이터를 할당합니다.

## XSANE

- **XSANE**  
  XSANE은 SANE 스캐너 인터페이스를 X-Window 기반으로 만든 프로그램으로, GTK+ 라이브러리를 사용하여 개발되었습니다.

## UTP 케이블링

- **T568A**  
  흰녹, 녹, 흰주, 파, 흰파, 주, 흰갈, 갈

- **T568B**  
  흰주, 주, 흰녹, 파, 흰파, 녹, 흰갈, 갈

  실제로 사용되는 선은 주, 흰주, 녹, 흰녹입니다.

## 쉘 프롬프트 설정 가이드

쉘 프롬프트는 사용자가 명령을 입력하는 곳으로, 다양한 정보를 표시하여 작업 효율을 높일 수 있습니다.

### 주요 환경 변수

* **PS1:** 주 프롬프트 (예: 사용자 이름, 호스트 이름, 현재 디렉토리)
* **PS2:** 보조 프롬프트 (명령어가 다음 줄로 이어질 때 표시)
* **PROMPT:** C 셸에서 사용되는 프롬프트 설정 변수

### 예시 (Bash)


```bash
# PS1 설정 예시
PS1='\[\033[01;32m\]\u@\h\[\033[00m\]:\[\033[01;34m\]\w\[\033[00m\]\$ '

# 패키지 'vim'이 설치한 파일 목록 보기
rpm -ql vim

# 시스템에 설치된 모든 패키지 목록 보기
rpm -qa

# 설치되지 않은 패키지 파일 'vim-enhanced-8.0.0-1.el7.x86_64.rpm' 정보 보기
rpm -qip vim-enhanced-8.0.0-1.el7.x86_64.rpm

# 패키지 'bash' 검증
rpm -qV bash

```

### Xlib의 기능을 포함하는 고수준의 라이브러리


- 고수준 : Xt, Xaw, Motif, FLTK, CTK+, Qt, TK, SDL
- 저수준 : Xlib, XCB 이것도
  
### XCB
- XCB는 컴퓨팅에서 X 윈도 시스템을 위한 C언어 결합이고, Xlib 대체가 목적입니다
  참고로 Xlib은 C언어로 구현된 클라이언트 라이브러리이며 X서버와 대화해주는 역할이라고 합니다

### 프로토콜
- /etc/services 모든 프로토콜, 포트번호
- /etc/protocols '사용 가능한' 프로토콜들

### 웰노운포트 정리
- 20: FTP 데이터 전송 - TCP
- 21: FTP 제어 (명령) - TCP
- 22: SSH (Secure Shell) - TCP
- 23: Telnet - TCP
- 25: SMTP (Simple Mail Transfer Protocol) - TCP
- 53: DNS (Domain Name System) - TCP/UDP 모두 사용. 주로 UDP 사용.
- 80: HTTP (Hypertext Transfer Protocol) - TCP
- 110: POP3 (Post Office Protocol version 3) - TCP
- 143: IMAP (Internet Message Access Protocol) - TCP
- 443: HTTPS (HTTP Secure) - TCP
- 161: SNMP는 일반적으로 UDP
- 162: SNMP의 알림 메시지를 수신하기 위해
- 993: IMAPS (IMAP over SSL) - TCP
- 995: POP3S (POP3 over SSL) - TCP
