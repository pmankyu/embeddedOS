# embeddedOS 개발 프로젝트

## 명령어 모음

* 17 Page
---
```bash
$ arm-none-eabi-as -march=armv7-a -mcpu=cortex-a8 -o Entry.o ./Entry.S
$ arm-none-eabi-objcopy -O binary Entry.o Entry.bin
$ hexdump Entry.bin
```

