# ch2. system structures

>운영체제를 완전히 잊기 전에 다시금 공부하여 간략하게나마 내용들을 정리해보려 한다.
공룡책을 기준으로 중요한 내용들만 정리한 것이니 다시 살펴봐야 할 부분들은 구글링이 필요하다.
>> 

ch1 에서 운영체제가 어떠한 역할을 하는 지에 대한 내용이었다면,

ch2. system structures(시스템 구조)에서는 운영체제가 어떤 구조를 가지고 있는 지에 관한 내용을 담고 있다. 

운영체제가 제공하는 서비스에 대한 구조는
1.  UI(user interface) - CLI, GUI 등
2. program execution - 프로그램을 메모리에 적재하여 실행
3. i/o operation
4. file system manipulation - 프로그램이 파일을 읽고 쓰고, 생성, 삭제, 검색, 권한 관리 등
5. communication - 프로세스 간 정보 교환    a) 동일한 컴퓨터 내에서  b) 네트워크 상의 컴퓨터의 프로세스간  (message passing, shared memory 기법을 이용)
6. error detection
7. resource allocation : cpu cycle, main memory, i/o device 등
8. accounting
9. protecting and security


## system call

운영체제는 커널모드와 유저모드로 나뉘어져 동작한다. 최초 부팅 시 커널 모드에서 운영체제가 올라오고 그 위에 유저 모드가 시작된다. interrupt, trap 발생 시 운영체제는 커널 모드로 바꾸어 처리한다.  유저 모드에서는 프로세스들은 다른 메모리 영역에 간섭이 불가능하지만 커널모드에서는 모든 메모리로의 접근이 가능하다. 커널 모드에서는 시스템 콜을 이용한다.
두 모드가 나뉘는 이유는 시스템과 사용자들을 보호하기 위해서다. 

시스템 콜은 커녈 모드의 기능을 유저 모드에서 사용가능하게끔 한다. 프로세스는 이를 이용하여 하드웨어에 접근하여 필요한 작업을 할 수 있다. 각 시스템 콜은 번호가 할당되고 시스템 콜 인터페이스는 이 번호에 따라 인덱스되는 테이블을 가지고 있다. 

시스템 콜의 유형은 - process control, file manipulation, device management, information maintenance, communication 등이 있다.