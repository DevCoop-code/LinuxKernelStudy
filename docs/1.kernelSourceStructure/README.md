# 리눅스 커널 소스의 구조

- linux
    - arch
        - arm
            - kernel
            - mm
            - lib
        - arm64
            - kernel
            - mm
            - lib
        - x86
            - kernel
            - mm
            - lib
    - include
    - Documentation
    - kernel
        - irq
        - sched
        - power
        - locking
        - printk
        - trace
    - mm
    - drivers
    - fs
    - lib

### arch
arch의 하부 디렉터리에는 architecture별 동작 커널 코드가 존재 

ex] arm: 32bit 계열 ARM 아키텍쳐 코드가 존재

### include
커널 코드 빌드에 필요한 헤더 파일이 존재

### Documentation
커널 기술 문서가 있는 폴더, 커널 시스템에 대한 기본 동작을 설명하는 문서가 존재

### kernel
커널의 핵심 코드가 있는 directory

- irq : 인터럽트 관련 코드
- sched : 스케줄링 코드
- power : 커널 파워 Management 코드
- locking : 커널 동기화 관련 코드
- printk : 커널 콘솔 관련 코드
- trace : frace 관련 코드

kernel directory는 cpu architecture와는 무관한 공통 코드들이 있으며 각 cpu architecture별로 동작하는 커널 코드는 arch/*/kernel/에 존재

### mm
가상 메모리 및 페이징 관련 코드가 존재

cpu architecture별로 존재하는 코드는 arch/*/mm/ 아래에 존재

### drivers
모든 시스템의 디바이스 드라이버 코드가 존재

### fs
모든 파일 시스템 코드가 존재

### lib
커널에서 제공하는 라이브러리 코드가 존재, cpu architecture에 종속적인 라이브러리 코드는 arch/*/lib/에 존재
