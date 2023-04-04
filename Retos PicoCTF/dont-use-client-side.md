# Dont-use-client-side

## Objetivo.

Can you break into this super secure portal? `https://jupiter.challenges.picoctf.org/problem/17682`

## Solución.

Nos dirigimos al link, click derecho, inspeccionar, source, dentro de source selecciinamos en archivo index, en el panel izquierdo.
Este archivo contine una sección parecida a esto:

  function verify() {
    checkpass = document.getElementById("pass").value;
    split = 4;
    if (checkpass.substring(0, split) == 'pico') {
      if (checkpass.substring(split*6, split*7) == '706c') {
        if (checkpass.substring(split, split*2) == 'CTF{') {
         if (checkpass.substring(split*4, split*5) == 'ts_p') {
          if (checkpass.substring(split*3, split*4) == 'lien') {
            if (checkpass.substring(split*5, split*6) == 'lz_b') {
              if (checkpass.substring(split*2, split*3) == 'no_c') {
                if (checkpass.substring(split*7, split*8) == '5}') {
                  alert("Password Verified")
                  }
                }
              }
      
            }
          }
        }
      }
    }
    else {
      alert("Incorrect password");
    }
    
  }
  
Podemos ver que en la función verify, se encuentra la bandera. Pero esta partida en varias partes, hay que acomodarla conforme lo indiquen las particiones.

organizada la bandera quedaría así:
picoCTF{no_clients_plz_b706c5}

## Notas opcionales.

## Referencias.

https://www.youtube.com/watch?v=TFlDRCODq2A&ab_channel=MikeOnTech