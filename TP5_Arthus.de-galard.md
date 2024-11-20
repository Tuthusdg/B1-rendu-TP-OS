# TP5: le compilateur ton pire meilleur ami 

## 0.prérequis
```bash
unuser@TPOS:~/Documents/work$
```


## I.Programme minimal

### 1.Compilation

### 2.Analyse du programme compilé


```bash
unuser@TPOS:~/Documents/work$ readelf -h hello1
ELF Header:
  Magic:   7f 45 4c 46 01 01 01 00 00 00 00 00 00 00 00 00
  Class:                             ELF32
  Data:                              2's complement, little endian
  Version:                           1 (current)
  OS/ABI:                            UNIX - System V
  ABI Version:                       0
  Type:                              DYN (Position-Independent Executable file)
  Machine:                           Intel 80386
  Version:                           0x1
  Entry point address:               0x1000
  Start of program headers:          52 (bytes into file)
  Start of section headers:          13316 (bytes into file)
  Flags:                             0x0
  Size of this header:               52 (bytes)
  Size of program headers:           32 (bytes)
  Number of program headers:         11
  Size of section headers:           40 (bytes)
  Number of section headers:         21
  Section header string table index: 20
  ```

  ```bash
unuser@TPOS:~/Documents/work$ readelf -S hello1
There are 21 section headers, starting at offset 0x3404:

Section Headers:
  [Nr] Name              Type            Addr     Off    Size   ES Flg Lk Inf Al
  [ 0]                   NULL            00000000 000000 000000 00      0   0  0
  [ 1] .interp           PROGBITS        00000194 000194 000013 00   A  0   0  1
  [ 2] .note.gnu.bu[...] NOTE            000001a8 0001a8 000024 00   A  0   0  4
  [ 3] .gnu.hash         GNU_HASH        000001cc 0001cc 000018 04   A  4   0  4
  [ 4] .dynsym           DYNSYM          000001e4 0001e4 000010 10   A  5   1  4
  [ 5] .dynstr           STRTAB          000001f4 0001f4 000001 00   A  0   0  1
  [ 6] .text             PROGBITS        00001000 001000 00005d 00  AX  0   0  1
  [ 7] .eh_frame_hdr     PROGBITS        00002000 002000 00001c 00   A  0   0  4
  [ 8] .eh_frame         PROGBITS        0000201c 00201c 000058 00   A  0   0  4
  [ 9] .dynamic          DYNAMIC         00003f8c 002f8c 000068 08  WA  5   0  4
  [10] .got.plt          PROGBITS        00003ff4 002ff4 00000c 04  WA  0   0  4
  [11] .comment          PROGBITS        00000000 003000 00001f 01  MS  0   0  1
  [12] .debug_aranges    PROGBITS        00000000 00301f 000020 00      0   0  1
  [13] .debug_info       PROGBITS        00000000 00303f 000070 00      0   0  1
  [14] .debug_abbrev     PROGBITS        00000000 0030af 000062 00      0   0  1
  [15] .debug_line       PROGBITS        00000000 003111 000054 00      0   0  1
  [16] .debug_str        PROGBITS        00000000 003165 000085 01  MS  0   0  1
  [17] .debug_line_str   PROGBITS        00000000 0031ea 000025 01  MS  0   0  1
  [18] .symtab           SYMTAB          00000000 003210 0000b0 10     19   6  4
  [19] .strtab           STRTAB          00000000 0032c0 00006a 00      0   0  1
  [20] .shstrtab         STRTAB          00000000 00332a 0000d9 00      0   0  1
Key to Flags:
  W (write), A (alloc), X (execute), M (merge), S (strings), I (info),
  L (link order), O (extra OS processing required), G (group), T (TLS),
  C (compressed), x (unknown), o (OS specific), E (exclude),
  D (mbind), p (processor specific)
  ```

  ```bash
unuser@TPOS:~/Documents/work$ objdump -M intel -j .text -d hello1

hello1:     file format elf32-i386


Disassembly of section .text:

00001000 <_start>:
    1000:       55                      push   ebp
    1001:       89 e5                   mov    ebp,esp
    1003:       57                      push   edi
    1004:       56                      push   esi
    1005:       53                      push   ebx
    1006:       83 ec 10                sub    esp,0x10
    1009:       e8 4b 00 00 00          call   1059 <__x86.get_pc_thunk.ax>
    100e:       05 e6 2f 00 00          add    eax,0x2fe6
    1013:       c7 45 e5 48 65 6c 6c    mov    DWORD PTR [ebp-0x1b],0x6c6c6548
    101a:       c7 45 e9 6f 2c 20 57    mov    DWORD PTR [ebp-0x17],0x57202c6f
    1021:       c7 45 ed 6f 72 6c 64    mov    DWORD PTR [ebp-0x13],0x646c726f
    1028:       c7 45 f0 64 21 0a 00    mov    DWORD PTR [ebp-0x10],0xa2164
    102f:       8d 75 e5                lea    esi,[ebp-0x1b]
    1032:       bf 0e 00 00 00          mov    edi,0xe
    1037:       b8 04 00 00 00          mov    eax,0x4
    103c:       bb 01 00 00 00          mov    ebx,0x1
    1041:       89 f1                   mov    ecx,esi
    1043:       89 fa                   mov    edx,edi
    1045:       cd 80                   int    0x80
    1047:       b8 01 00 00 00          mov    eax,0x1
    104c:       31 db                   xor    ebx,ebx
    104e:       cd 80                   int    0x80
    1050:       90                      nop
    1051:       83 c4 10                add    esp,0x10
    1054:       5b                      pop    ebx
    1055:       5e                      pop    esi
    1056:       5f                      pop    edi
    1057:       5d                      pop    ebp
    1058:       c3                      ret

00001059 <__x86.get_pc_thunk.ax>:
    1059:       8b 04 24                mov    eax,DWORD PTR [esp]
    105c:       c3                      ret
  ```


### 3.Librairie et compilation dynamique

#### C.Tracer les appels de librairies
  ```bash

unuser@TPOS:~/Documents/work$ ldd hello2
        linux-gate.so.1 (0xf7ef3000)
        libc.so.6 => /lib32/libc.so.6 (0xf7caf000)
        /lib/ld-linux.so.2 (0xf7ef5000)
  ```
  
  ```bash

  unuser@TPOS:~/Documents/work$ ldd hello1
        statically linked
```

```bash
unuser@TPOS:~$ ldd /usr/bin/firefox
        not a dynamic executable
```


```bash
unuser@TPOS:~/Documents/work$ file /lib32/libc.so.6
/lib32/libc.so.6: ELF 32-bit LSB shared object, Intel 80386, version 1 (GNU/Linux), dynamically linked, interpreter /lib/ld-linux.so.2, BuildID[sha1]=b3f5646d25dc90cc34d2507f197561065c7e630c, for GNU/Linux 3.2.0, stripped
```


### 4.compilation statique

```bash
unuser@TPOS:~/Documents/work$ file hello2
hello2: ELF 32-bit LSB pie executable, Intel 80386, version 1 (SYSV), dynamically linked, interpreter /lib/ld-linux.so.2, BuildID[sha1]=93b7fcdc82b3b20a19d73c98dcacb33201d16340, for GNU/Linux 3.2.0, with debug_info, not stripped
unuser@TPOS:~/Documents/work$ file hello3
hello3: ELF 32-bit LSB executable, Intel 80386, version 1 (GNU/Linux), statically linked, BuildID[sha1]=147ba66c973f28c6f1c69afc8136fb091829d9dc, for GNU/Linux 3.2.0, with debug_info, not stripped
```


```bash
unuser@TPOS:~/Documents/work$ du -ah
16K     ./hello2
4.0K    ./hello2.c
4.0K    ./hello1.c
16K     ./hello1
728K    ./hello3
4.0K    ./hello3.c
776K    .
```


### 5. compilation cross-plateforme

```bash
unuser@TPOS:~$ cat /proc/cpuinfo
processor       : 0
vendor_id       : GenuineIntel
cpu family      : 6
model           : 140
model name      : 11th Gen Intel(R) Core(TM) i7-1165G7 @ 2.80GHz
stepping        : 1
microcode       : 0xffffffff
cpu MHz         : 2803.210
cache size      : 12288 KB
physical id     : 0
siblings        : 1
core id         : 0
cpu cores       : 1
apicid          : 0
initial apicid  : 0
fpu             : yes
fpu_exception   : yes
cpuid level     : 22
wp              : yes
flags           : fpu vme de pse tsc msr pae mce cx8 apic sep mtrr pge mca cmov pat pse36 clflush mmx fxsr sse sse2 ht syscall nx rdtscp lm constant_tsc rep_good nopl xtopology nonstop_tsc cpuid tsc_known_freq pni pclmulqdq ssse3 cx16 pcid sse4_1 sse4_2 movbe popcnt aes rdrand hypervisor lahf_lm abm 3dnowprefetch invpcid_single ibrs_enhanced fsgsbase bmi1 bmi2 invpcid rdseed clflushopt arat md_clear flush_l1d arch_capabilities
bugs            : spectre_v1 spectre_v2 spec_store_bypass swapgs retbleed eibrs_pbrsb bhi
bogomips        : 5606.42
clflush size    : 64
cache_alignment : 64
address sizes   : 39 bits physical, 48 bits virtual
power management:
```


```bash
unuser@TPOS:~$ which x86_64-linux-gnu-gcc
/usr/bin/x86_64-linux-gnu-gcc
```
#### compil cross-plateforme
```bash
unuser@TPOS:~/Documents/work$ arm-linux-gnueabi-gcc -o hello4 hello3.c
```

```bash
objdump -M intel -j .text -d hello3
```

Il est looooooooooooooooooooooooooooooong 

```bash
unuser@TPOS:~/Documents/work$ objdump -M intel -j .text -d hello4

hello4:     file format elf32-littlearm


Disassembly of section .text:

00000400 <_start>:
 400:   objdump: unrecognised disassembler option: intel
e3a0b000        mov     fp, #0
 404:   e3a0e000        mov     lr, #0
 408:   e49d1004        pop     {r1}            @ (ldr r1, [sp], #4)
 40c:   e1a0200d        mov     r2, sp
 410:   e52d2004        push    {r2}            @ (str r2, [sp, #-4]!)
 414:   e52d0004        push    {r0}            @ (str r0, [sp, #-4]!)
 418:   e59fa01c        ldr     sl, [pc, #28]   @ 43c <_start+0x3c>
 41c:   e28f3018        add     r3, pc, #24
 420:   e08aa003        add     sl, sl, r3
 424:   e3a03000        mov     r3, #0
 428:   e52d3004        push    {r3}            @ (str r3, [sp, #-4]!)
 42c:   e59f000c        ldr     r0, [pc, #12]   @ 440 <_start+0x40>
 430:   e79a0000        ldr     r0, [sl, r0]
 434:   ebffffe2        bl      3c4 <__libc_start_main@plt>
 438:   ebffffed        bl      3f4 <abort@plt>
 43c:   00001bc4        .word   0x00001bc4
 440:   0000002c        .word   0x0000002c

00000444 <call_weak_fn>:
 444:   e59f3014        ldr     r3, [pc, #20]   @ 460 <call_weak_fn+0x1c>
 448:   e59f2014        ldr     r2, [pc, #20]   @ 464 <call_weak_fn+0x20>
 44c:   e08f3003        add     r3, pc, r3
 450:   e7932002        ldr     r2, [r3, r2]
 454:   e3520000        cmp     r2, #0
 458:   012fff1e        bxeq    lr
 45c:   eaffffe1        b       3e8 <__gmon_start__@plt>
 460:   00001bac        .word   0x00001bac
 464:   00000028        .word   0x00000028

00000468 <deregister_tm_clones>:
 468:   e59f002c        ldr     r0, [pc, #44]   @ 49c <deregister_tm_clones+0x34>
 46c:   e59f302c        ldr     r3, [pc, #44]   @ 4a0 <deregister_tm_clones+0x38>
 470:   e08f0000        add     r0, pc, r0
 474:   e08f3003        add     r3, pc, r3
 478:   e1530000        cmp     r3, r0
 47c:   e59f3020        ldr     r3, [pc, #32]   @ 4a4 <deregister_tm_clones+0x3c>
 480:   e08f3003        add     r3, pc, r3
 484:   012fff1e        bxeq    lr
 488:   e59f2018        ldr     r2, [pc, #24]   @ 4a8 <deregister_tm_clones+0x40>
 48c:   e7933002        ldr     r3, [r3, r2]
 490:   e3530000        cmp     r3, #0
 494:   012fff1e        bxeq    lr
 498:   e12fff13        bx      r3
 49c:   00001bc4        .word   0x00001bc4
 4a0:   00001bc0        .word   0x00001bc0
 4a4:   00001b78        .word   0x00001b78
 4a8:   00000024        .word   0x00000024

000004ac <register_tm_clones>:
 4ac:   e59f0038        ldr     r0, [pc, #56]   @ 4ec <register_tm_clones+0x40>
 4b0:   e59f3038        ldr     r3, [pc, #56]   @ 4f0 <register_tm_clones+0x44>
 4b4:   e08f0000        add     r0, pc, r0
 4b8:   e08f3003        add     r3, pc, r3
 4bc:   e0433000        sub     r3, r3, r0
 4c0:   e1a01fa3        lsr     r1, r3, #31
 4c4:   e0811143        add     r1, r1, r3, asr #2
 4c8:   e59f3024        ldr     r3, [pc, #36]   @ 4f4 <register_tm_clones+0x48>
 4cc:   e1b010c1        asrs    r1, r1, #1
 4d0:   e08f3003        add     r3, pc, r3
 4d4:   012fff1e        bxeq    lr
 4d8:   e59f2018        ldr     r2, [pc, #24]   @ 4f8 <register_tm_clones+0x4c>
 4dc:   e7933002        ldr     r3, [r3, r2]
 4e0:   e3530000        cmp     r3, #0
 4e4:   012fff1e        bxeq    lr
 4e8:   e12fff13        bx      r3
 4ec:   00001b80        .word   0x00001b80
 4f0:   00001b7c        .word   0x00001b7c
 4f4:   00001b28        .word   0x00001b28
 4f8:   00000030        .word   0x00000030

000004fc <__do_global_dtors_aux>:
 4fc:   e59f304c        ldr     r3, [pc, #76]   @ 550 <__do_global_dtors_aux+0x54>
 500:   e59f204c        ldr     r2, [pc, #76]   @ 554 <__do_global_dtors_aux+0x58>
 504:   e08f3003        add     r3, pc, r3
 508:   e5d33000        ldrb    r3, [r3]
 50c:   e08f2002        add     r2, pc, r2
 510:   e3530000        cmp     r3, #0
 514:   112fff1e        bxne    lr
 518:   e59f3038        ldr     r3, [pc, #56]   @ 558 <__do_global_dtors_aux+0x5c>
 51c:   e92d4010        push    {r4, lr}
 520:   e7923003        ldr     r3, [r2, r3]
 524:   e3530000        cmp     r3, #0
 528:   0a000002        beq     538 <__do_global_dtors_aux+0x3c>
 52c:   e59f3028        ldr     r3, [pc, #40]   @ 55c <__do_global_dtors_aux+0x60>
 530:   e79f0003        ldr     r0, [pc, r3]
 534:   ebffffa5        bl      3d0 <__cxa_finalize@plt>
 538:   ebffffca        bl      468 <deregister_tm_clones>
 53c:   e59f301c        ldr     r3, [pc, #28]   @ 560 <__do_global_dtors_aux+0x64>
 540:   e3a02001        mov     r2, #1
 544:   e08f3003        add     r3, pc, r3
 548:   e5c32000        strb    r2, [r3]
 54c:   e8bd8010        pop     {r4, pc}
 550:   00001b30        .word   0x00001b30
 554:   00001aec        .word   0x00001aec
 558:   00000020        .word   0x00000020
 55c:   00001b00        .word   0x00001b00
 560:   00001af0        .word   0x00001af0

00000564 <frame_dummy>:
 564:   eaffffd0        b       4ac <register_tm_clones>

00000568 <main>:
 568:   e92d4800        push    {fp, lr}
 56c:   e28db004        add     fp, sp, #4
 570:   e59f3014        ldr     r3, [pc, #20]   @ 58c <main+0x24>
 574:   e08f3003        add     r3, pc, r3
 578:   e1a00003        mov     r0, r3
 57c:   ebffff96        bl      3dc <puts@plt>
 580:   e3a03000        mov     r3, #0
 584:   e1a00003        mov     r0, r3
 588:   e8bd8800        pop     {fp, pc}
 58c:   000000b0        .word   0x000000b0
```

```bash
unuser@TPOS:~/Documents/work$ ./hello4
-bash: ./hello4: cannot execute binary file: Exec format error
```

compilation de password_2

```bash
unuser@TPOS:~/Documents/work$ gcc password_2.c -o password_2 -lssl -lcrypto -Wno-deprecated-declarations
```


```bash
unuser@TPOS:~/Documents/work$ ./password_2 1
Access granted! Spawning shell...
```
kaddate chall

```bash
b1-os{PetitB1deviendraGrandPetitB1}
```