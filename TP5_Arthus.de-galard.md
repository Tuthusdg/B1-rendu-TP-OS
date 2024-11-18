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

```bash
unuser@TPOS:~/Documents/work$ arm-linux-gnueabi-gcc -o hello4 hello3.c
```