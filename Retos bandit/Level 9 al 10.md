# Level 9 al 10

## Objetivo.

La contaseña para el siguiente nivel, está almacenada en el archivo **data.txt** en una de las pocas cadenas legibles por humanos, precedida por varios caracteres '='.

## Datos de acceso al nivel.

bandit9
EN632PlfYiZbn3PhVK3XOGSlNInNE00t

## Solución.

bandit9@bandit:~$ ls
data.txt
bandit9@bandit:~$ strings data.txt | grep ===
c========== the
h;========== password
========== isT
n.E========== G7w8LIi6J3kTb8A7j9LgrywtEUlyyp6s

## Notas opcionales.

Primero, debemos distinguir las cadenas legibles por humanos en 'data.txt'. Usamos el comando strings.

A continuación, queremos filtrar esa salida observando las líneas que incluyen más de un signo igual. - Asumiendo que los signos de igual y la contraseña están en la misma línea, podemos usar grep.


## Referencias.

https://overthewire.org/wargames/bandit/bandit10.html
https://mayadevbe.me/posts/overthewire/bandit/level10/