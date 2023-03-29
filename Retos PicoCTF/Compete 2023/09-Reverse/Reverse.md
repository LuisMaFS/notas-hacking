## Descripción
Try reversing this file? Can ya? I forgot the password to this [file](https://artifacts.picoctf.net/c/365/ret). Please find it for me?

## Hints



## Solución
``` bash
┌─[ramdark@parrot]─[~/Documents/Hacking_Notes_RFC/PicoCTF2023/Reverse]
└──╼ $ls
ret  Reverse.md
┌─[ramdark@parrot]─[~/Documents/Hacking_Notes_RFC/PicoCTF2023/Reverse]
└──╼ $file ret
ret: ELF 64-bit LSB pie executable, x86-64, version 1 (SYSV), dynamically linked, interpreter /lib64/ld-linux-x86-64.so.2, BuildID[sha1]=3617cc143df7171b9d44f553bfcf367b1feca8a0, for GNU/Linux 3.2.0, not stripped
┌─[ramdark@parrot]─[~/Documents/Hacking_Notes_RFC/PicoCTF2023/Reverse]
└──╼ $strings ret
/lib64/ld-linux-x86-64.so.2
libc.so.6
__isoc99_scanf
puts
__stack_chk_fail
printf
__cxa_finalize
strcmp
__libc_start_main
GLIBC_2.7
GLIBC_2.4
GLIBC_2.2.5
_ITM_deregisterTMCloneTable
__gmon_start__
_ITM_registerTMCloneTable
u+UH
picoCTF{H
3lf_r3v3H
r5ing_suH
cce55fulH
_f7abcc2H
[]A\A]A^A_
Enter the password to unlock this file: 
You entered: %s
Password correct, please see flag: picoCTF{3lf_r3v3r5ing_succe55ful_f7abcc2f}
Access denied
:*3$"
GCC: (Ubuntu 9.4.0-1ubuntu1~20.04.1) 9.4.0
crtstuff.c
deregister_tm_clones
__do_global_dtors_aux
completed.8061
__do_global_dtors_aux_fini_array_entry
frame_dummy
__frame_dummy_init_array_entry
ret.c
__FRAME_END__
__init_array_end
_DYNAMIC
__init_array_start
__GNU_EH_FRAME_HDR
_GLOBAL_OFFSET_TABLE_
__libc_csu_fini
_ITM_deregisterTMCloneTable
puts@@GLIBC_2.2.5
_edata
__stack_chk_fail@@GLIBC_2.4
printf@@GLIBC_2.2.5
__libc_start_main@@GLIBC_2.2.5
__data_start
strcmp@@GLIBC_2.2.5
__gmon_start__
__dso_handle
_IO_stdin_used
__libc_csu_init
__bss_start
main
__isoc99_scanf@@GLIBC_2.7
__TMC_END__
_ITM_registerTMCloneTable
__cxa_finalize@@GLIBC_2.2.5
.symtab
.strtab
.shstrtab
.interp
.note.gnu.property
.note.gnu.build-id
.note.ABI-tag
.gnu.hash
.dynsym
.dynstr
.gnu.version
.gnu.version_r
.rela.dyn
.rela.plt
.init
.plt.got
.plt.sec
.text
.fini
.rodata
.eh_frame_hdr
.eh_frame
.init_array
.fini_array
.dynamic
.data
.bss
.comment
┌─[ramdark@parrot]─[~/Documents/Hacking_Notes_RFC/PicoCTF2023/Reverse]
└──╼ $strings ret | grep 'pico'
picoCTF{H
Password correct, please see flag: picoCTF{3lf_r3v3r5ing_succe55ful_f7abcc2f}
┌─[ramdark@parrot]─[~/Documents/Hacking_Notes_RFC/PicoCTF2023/Reverse]
└──╼ $


```


## Flag

``` picoCTF{3lf_r3v3r5ing_succe55ful_f7abcc2f} ```


## Notas adicionales

|Comando | Descripcion |
|------------ | ------------|
| strings | comando que permite leer cadenas en el binario |


## Referencias
+ [strings](https://www.javatpoint.com/linux-strings-command)
