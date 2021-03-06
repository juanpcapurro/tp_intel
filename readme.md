# TP intel
Enunciado 101

### Instrucciones para obtener el ejecutable
#### Ensamblado:
Se debe correr nasm, lo testeé sobre Ubuntu 16.04LTS de 64 bits
```
nasm -fOBJ tp.asm
```
#### Linkeo
Desde DOSbox (probé la versión 0.74 bajo Ubuntu 16.04LTS de 64 bits), se debe
montar este directorio, iniciar un DPMI y linkear con ALINK, cuyos archivos
están incluidos en este repositorio
```
mount c ~/Documents/GitHub/organizacion_del_computador/TP_intel/
c:
cwsdpmi.exe -p
alink.exe -oEXE -o tp.exe tp.obj
```
Para poder enviar el comprimido por Gmail, tuve que quitarle la extensión `.exe` a los ejecutables.
Al volver a agregársela deberían funcionar sin problemas, basta con ejecutar `mv ALINK ALINK.EXE && mv cwsdpmi cwsdpmi.exe && mv RSX RSX.EXE`

### Supuestos:
El enunciado es ambiguo en qué método de ordenamiento usar, ya que indica usar un burbujeo optimizado, pero el código se corresponde con un ordenamiento por selección.
Opto por implementar este último, por considerar el código propuesto como instrucciones más claras que un simple nombre.

Por otra parte, interpreto que el programa debe mostrar los contenidos del archivo ordenado, en el sentido de que lee el archivo y ordena el contenido del mismo pero no guarda dicho contenido ordenado sobreescribiendo el archivo, ni guardándolo en otro.

### Sobre la generacion de archivos de prueba
Para generar los archivos con los cuales probar el programa, creé un programa en C que puede ser compilado con:
```
gcc -std=c99 -Wall -Wconversion generador_numeros.c -o generador_numeros
```
No recibe argumentos, y el largo del archivo está como una constante dentro del código.
Genera un archivo con la cantidad indicada de bpfs de 16 bits, elegidos aleatoriamente, y tambien los muestra por pantalla.

---
Realizado por Juan Pablo Capurro

Padrón 98194
