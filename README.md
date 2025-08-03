📌 강의 노트 요약 – Part 1: 개발 환경 및 어셈블리 구조 이해

🔧 개발 환경 설정
사용 툴: SASM

코드 편집 + 빌드(컴파일) + 실행 기능이 통합된 툴

문서 편집기처럼 보이지만 실제 번역기(컴파일러) 역할도 함

🧩 어셈블러 종류

NASM (Netwide Assembler)

GAS (GNU Assembler)

FASM (Flat Assembler)

MASM (Microsoft Assembler)

📦 어셈블러 종류 4개 요약

NASM	Netwide Assembler	<ul><li>가장 많이 쓰이는 오픈소스 어셈블러</li><li>문법이 깔끔하고 구조화됨</li><li>Windows/Linux 둘 다 사용 가능</li></ul>
GAS	GNU Assembler	<ul><li>리눅스/유닉스 환경에서 기본으로 제공됨</li><li>GCC와 함께 쓰임</li><li>문법이 NASM보다 살짝 복잡</li></ul>
FASM	Flat Assembler	<ul><li>고속 컴파일로 유명</li><li>작고 가볍고, 자체적으로 실행 파일 생성 가능</li><li>문법이 NASM과 비슷</li></ul>
MASM	Microsoft Assembler	<ul><li>Windows 전용 어셈블러</li><li>Visual Studio에서도 사용 가능</li><li>윈도우 API 연동에 강함</li></ul>


<img width="1532" height="994" alt="image" src="https://github.com/user-attachments/assets/8b3fa71f-3f80-4fd0-a5b9-a72ba970181b" />


🧪 Hello World 출력 (어셈블리 예제)

#include "io64.inc"

section .text
global main
main:
    PRINT_STRING msg
    xor rax, rax
    ret

section .data
    msg db 'Hello World', 0x00
PRINT_STRING: 문자열 출력

xor rax, rax: rax 레지스터 값을 0으로 초기화

ret: 함수 종료

✅ 실행 결과: "Hello World" 출력

🧠 메모리 구조 이해

실행 파일은 내부적으로 .text, .data, .rsrc 등의 섹션으로 나뉨

.text: 우리가 작성한 실행 코드

.data: 고정된 데이터 (예: Hello World 문자열)

각 섹션은 디스크에 저장될 때와 메모리에 로드될 때 주소 배치가 다름

해당 구조를 이해하는 것이 언리얼/C++ 메모리 구조 이해에 매우 중요

💬 느낀 점
어셈블리 언어는 컴퓨터가 이해하기 쉬운 언어이다.
하지만 사람이 보기엔 어렵고, 메모리 구조를 시각적으로 이해하는 게 중요하다.
메모리 구조를 이해하면 C++로 넘어가서 포인터나 메모리 제어 로직 이해가 훨씬 수월할 것 같음.
