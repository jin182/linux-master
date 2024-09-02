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
- **SIGQUIT**: 3  (Ctrl + \)
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
