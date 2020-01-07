# embeddedOS 개발 프로젝트

## 삽질 모음

[p.17 어셈블리어 소스 파일 컴파일 warning](https://852completed.tistory.com/92)

[p.21 arm-none-eabi-gdb 설치 에러](https://852completed.tistory.com/93)

[p.53 main.c 빌드 error](https://852completed.tistory.com/95)

## 명령어 모음

* 17 Page (코드 3.2)
---
boot 폴더에서 실행
```bash
$ arm-none-eabi-as -march=armv7-a -mcpu=cortex-a8 -o Entry.o ./Entry.S
$ arm-none-eabi-objcopy -O binary Entry.o Entry.bin
$ hexdump Entry.bin
```


* 20 Page (코드 3.4)
---
root 폴더에서 실행
```bash
$ arm-none-eabi-ld -n -T ./navilos.ld -nostdlib -o navilos.axf boot/Entry.o
$ arm-none-eabi-objdump -D navilos.axf
```


* 21 Page (코드 3.5)
---
root 폴더에서 실행
```bash
$ qemu-system-arm -M realview-pb-a8 -kernel navilos.axf -S -gdb tcp::1234,ipv4
```

* QEMU와 gdb 연동
---
```bash
$ make gdb
(gdb) target remote:1234
(gdb) file build/navilos.axf
```