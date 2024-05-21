# top 명령어
top 명령어는 Linux와 Unix 시스템에서 실시간으로 시스템 성능과 프로세스 상태를 모니터링 하는데 사용되는 강력한 명령어입니다.
- 사용자가 현재 시스템의 리소스 사용 현황을 한 눈에 알아볼 수 있도록 정보를 제공, 시스템 관리와 성능 최적화에 도움을 줌

## top 명령어 출력 화면 구성
1. 시스템 정보 라인 (Header)
  - top 실행 시간 및 시스템 업타임
  - 현재 로그인한 사용자 수
  - 평균 부하 (load average) - 1분, 5분, 15분 동안의 평균 부하

2. 작업 요약 (Tasks)
  - 전체 태스크 수
  - 실행 중인 태스크 수
  - 멈춘 태스크 수
  - 대기 중인 태스크 수

3. CPU 상태 (CPU States)
  - 사용자 모드에서의 CPU 사용률
  - 시스템 모드에서의 CPU 사용률
  - 낮은 우선 순위에서의 CPU 사용률
  - 대기 중인 CPU 사용률
  - 하드웨어 인터럽트 처리에서의 CPU 사용률
  - 소프트웨어 인터럽트 처리에서의 CPU 사용률
  - 유휴 상태에서의 CPU 사용률

4. 메모리 사용량 (Memory Usage)
  - 총 스왑 공간
  - 사용 중인 스왑 공간
  - 사용 가능한 스왑 공간
  - 캐시된 스왑 공간

5. 스왑 사용량 (Swap Usage)
  - 총 스왑 공간
  - 사용 중인 스왑 공간
  - 사용 가능한 스왑 공간
  - 캐시된 스왑 공간

6. 프로세스 목록 (Process List)
  - `PID`: 프로세스 ID
  - `USER`: 프로세스를 실행하는 사용자
  - `PR`: 프로세스 우선 순위
  - `NI`: Nice 값 (프로세스 우선 순위 조정 값)
  - `VIRT`: 가상 메모리 사용량
  - `RES`: 실제 메모리 사용량
  - `SHR`: 공유 메모리 사용량
  - `S`: 프로세스 상태 (R: 실행 중, S: 대기 중, T: 멈춤, Z: 좀비)
  - `%CPU`: CPU 사용률
  - `%MEM`: 메모리 사용률
  - `TIME+`: 프로세스가 사용한 총 CPU 시간
  - `COMMAND`: 실행 중인 명령어

7. 키보드 단축키
: top 명령어는 실행 중 다양한 키보드 입력으로 동작을 조작할 수 있습니다.

  - `h`: 도움말 표시
  - `k`: 프로세스 종료 (PID 입력 필요)
  - `n` 또는 `#`: 표시할 프로세스 수 변경
  - `q`: `top` 종료
  - `s`: 업데이트 주기 변경 (초 단위)
  - `P`: CPU 사용률 기준으로 정렬
  - `M`: 메모리 사용률 기준으로 정렬
  - `T`: 실행 시간 기준으로 정렬

8. 명령어 옵션
: top 명령어는 다양한 옵션을 제공하여 초기 실행 환경을 설정할 수 있습니다.
  - `-d`: 갱신 주기 설정 (초 단위)

    ```ex
    top -d 5
    ```
  - `-p`: 특정 PID를 모니터링

    ```ex
    top -p 1234
    ```
  - `-u`: 특정 사용자의 프로세스만 표시

    ```ex
    top -u username
    ```

# ps 명령어
Linux 및 Unix 시스템에서 현재 실행 중인 프로세스의 상태를 확인하는 데 사용됩니다.
- 다양한 옵션을 제공해 프로세스에 대한 상세 정보를 출력할 수 있으며, 시스템 모니터링과 관리에 매우 유용한 도구

## ps 명령어 출력 예시
   ```ex 
   PID   TTY       TIME   CMD
   1234 pts/0    00:00:01 bash
   5678 pts/0    00:00:00 ps
  ```

## 주요 옵션
: `ps` 명령어는 다양한 옵션을 제공하여 프로세스 정보를 더욱 상세히 확인할 수 있습니다.

1. 모든 프로세스 보기
- `-e` 또는 `-A` 옵션을 사용해 시스템의 모든 프로세스 보기
   ```ex
   ps -e  또는 ps -A
   ```

2. 포맷 지정
- `-f` 옵션을 사용해 전체 포맷으로 프로세스 정보 보기
   ```ex
   ps -f
   ```

3. 특정 사용자 프로세스 보기
- `-u` 옵션을 사용해 특정 사용자의 프로세스 보기
     예를 들어, `username` 사용자의 프로세스를 보려면 다음과 같이 입력
   ```ex
   ps -u username
   ```
   
4. 프로세스 트리 보기
- `-e` 옵션과 `--forest` 옵션을 함께 사용해 프로세스 트리 형태 출력 가능
   ```ex
   ps -e --forest
   ```

5. 프로세스 상태(STAT)
 - `-l` 옵션을 사용해 장황한 포맷으로 프로세스 상태 확인 가능
   ```ex
   ps -l
   ```

6. 결합 가능
- `ps` 명령어는 여러 옵션을 결합하여 사용 가능
   예를 들어, 특정 사용자(username)의 모든 프로세스를 전체 포맷으로 보려면 다음과 같이 입
   ```ex
   ps -u username -f
   ```

7. 주요 필드
: `ps` 명령어의 출력에는 다양한 필드가 포함될 수 있음
   - `PID`: 프로세스 ID
   - `TTY`: 프로세스가 연결된 터미널
   - `TIME`: 프로세스가 사용한 총 CPU 시간
   - `CMD`: 실행된 명령어
   - `USER`: 프로세스를 실행한 사용자
   - `%CPU`: CPU 사용률
   - `%MEM`: 메모리 사용률
   - `VSZ`: 가상 메모리 사용량 (KB)
   - `RSS`: 실제 메모리 사용량 (KB)
   - `STAT`: 프로세스 상태 (S: 대기 중, R: 실행 중, Z: 좀비, T: 멈춤)


# jobs 명령어
# kill 명령


