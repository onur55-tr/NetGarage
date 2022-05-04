# NetGarage

## Netgarage Level01

    level1@io:/levels$: cd /levels/


    level1@io:/levels$: cat level01


Level01.asm-> asm’ye ait olduğunu görüyoruz. Debuga geçelim.

    level1@io:/levels$: gdb level01:

Exec’in sökmenin iki yol var.


1.

    (gdb)  disasemble main


Output: 
    
    Dump of assembler code for function main:
    
    0x08048080 <+0>:     push   $0x8049128
    0x08048085 <+5>:     call   0x804810f
    0x0804808a <+10>:    call   0x804809f
    0x0804808f <+15>:    cmp    $0x10f,%eax
    0x08048094 <+20>:    je     0x80480dc
    0x0804809a <+26>:    call   0x8048103æ
    
    End of assembler dump.


2.

    (gdb) objdump -d level01

Output:
      
    Disassembly of section .text:

    08048080 <_start>:
    8048080:       68 28 91 04 08          push   $0x8049128
    8048085:       e8 85 00 00 00          call   804810f <puts>
    804808a:       e8 10 00 00 00          call   804809f <fscanf>
    804808f:       3d 0f 01 00 00          cmp    $0x10f,%eax
    8048094:       0f 84 42 00 00 00       je     80480dc <YouWin>
    804809a:       e8 64 00 00 00          call   8048103 <exit>



İlk çağrı push tarafından gönderilir. Bizden girdi istenen %eax’dir. 
%eax’in içinde ne olduğunu görmek için onaltılık tabanda çıktı göstermektir.


Onaltılık tabanda outputu görme komutu:

    (gdb) p 0x10f

Output:
      
    $1 = 271

Cevap 271 olduğunu görüyoruz. Çıkmak için q tuşuna basabilirsiniz.

Level02’nin ssh şifresi öğrenme:

    sh-4.3$ cat /home/level2/.pass

<h3>XNWFtWKWHhaaXoKI</h3>
