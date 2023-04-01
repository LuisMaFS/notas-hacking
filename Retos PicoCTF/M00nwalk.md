# M00nwalk

## Objetivo.

Decode this [message](https://jupiter.challenges.picoctf.org/static/fc1edf07742e98a480c6aff7d2546107/message.wav) from the moon.

## Solución.

**Clonaremos un repositorio de github e instalaremos, el decodificador SSTV, Scottie 1, 2, DX

┌──(kali㉿kali)-[~/opt]

└─$ git clone https://github.com/colaclanth/sstv.git

┌──(kali㉿kali)-[~/opt/sstv]

└─$ sudo python3 setup.py install

**Regresamos a la carpeta, donde descargamos el archivo para el reto y convertimos el audio a imagen**

┌──(kali㉿kali)-[~/picoctf/forense/m00nwalk]

└─$ sstv -d message.wav -o result.png

**Abrimos la imagen y obtenemos la bandera**

picoCTF{beep_boop_im_in_space}

## Notas opcionales.

Las cintas que faltan del Apolo 11 fueron aquellas que se grabaron de la transmisión de televisión de exploración lenta (SSTV) del Apolo 11 en su formato sin formato en cinta de datos de telemetría en el momento del primer aterrizaje en la Luna en 1969 y posteriormente se perdieron. Las cintas de datos se utilizaron para registrar todos los datos transmitidos (video y telemetría) como respaldo.

## Referencias.

**Decodificador SSTV**

https://github.com/colaclanth/sstv

https://en.wikipedia.org/wiki/Apollo_11_missing_tapes