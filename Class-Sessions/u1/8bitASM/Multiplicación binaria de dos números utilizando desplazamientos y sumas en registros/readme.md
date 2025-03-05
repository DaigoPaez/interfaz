![image](https://github.com/user-attachments/assets/e1707545-fc0c-413d-bc64-5e53624fdf77)
**TECNOLÓGICO NACIONAL DE MÉXICO**  
**INSTITUTO TECNOLÓGICO DE TIJUANA**  

**SUBDIRECCIÓN ACADÉMICA**  
**DEPARTAMENTO DE SISTEMAS Y COMPUTACIÓN**  

**SEMESTRE:**  
Enero - Junio 2025  

**CARRERA:**  
Ingeniería en Sistemas Computacionales  

**MATERIA:**  
Lenguajes de interfaz

**TÍTULO ACTIVIDAD:**  
Ensamblador 8 bits

**PARCIAL A EVALUAR:**  
1  

**NOMBRES Y NÚMEROS DE CONTROL:**  
Páez Beltrán Diego Alonso - 22211630

**NOMBRE DEL MAESTRO (A):**  
René Solis Reyes

#Código documentado
```
.begin:	; Inicio del programa
	clra ; Pone en 0 el valor del registro A
  ; Multiplicaré 4 x 6
	num1 = 4	; Defino la variable num1 con el valor 4, este es el multiplicando
	num2 = 6	; Defino la variable num2 con el valor 6, este es el multiplicador
	data Ra, num1	; Carga num1 en Ra
	data Rc, num2	; Carga num2 en Rc
	dec Rc	; Decrementa Rc en 1
	mvb Ra	; Mueve el valor de Ra a Rb

.loop:	; Bucle principal	
	add Ra	; Suma Rb al registro Ra
	dec Rc	; Decrementa Rc en 1
	mvd Ra	; Mueve el valor de Ra a Rd
	jnz .loop	; Si el contador Rc no llega a 0, se repite el ciclo
	jmp 00000000	; Salta a 0 una vez termina el ciclo
```
# Lógica que sigue el programa
A lo que entendí, debía multiplicar los números de mi elección mediante sumas, yo elegí los números 4 y 6. Y sobre el desplazamiento, entiendo que se refiere a desplazar los números entre registros.

Cargué el 4 y el 6, el 4 lo cargué en el registro A, y el 6 en el registro C. El 6 se trata de un contador que define la cantidad de veces que se repetirá el bucle,
pero como en este caso Ra empieza con 4, al sumarse seis veces más daría el resultado de 4 x 7, así que le resté 1 al 6, pues para que no haga una iteración de más.
Moví Ra a Rb porque Rb es el registro que se usa para hacer las operaciones aritméticas, si no hubiera nada en Rb no se le sumaría nada a Ra.

El bucle empieza sumando lo que hay en Rb a Ra. Luego se le decrementa 1 a Rc (el contador), de ahí se mueve el valor de Ra a Rd para que el resultado se muestre en la pantalla LED. Así hasta que Rc llegue a 0
Ya para acabar pongo las condiciones del bucle, si el indicador no es 0 entonces el bucle puede repetirse. Esto causa que cuando el contador Rc llegue a 0, las iteraciones paran.
jmp 00000000 hace que se repita todo el código desde el inicio.

En resúmen, Ra sirve como acumulador de 4, Rb le añade 4 a Ra en cada iteración, Rc es el número de iteraciones y Rd muestra el resultado.
Siguiendo las 6 iteraciones, este es el resultado: 4 + 4 + 4 + 4 + 4 + 4 = 24. Es 4 x 6 pero con sumas.

![image](https://github.com/user-attachments/assets/b1b7b169-8ea6-4181-821f-0407f285f337)
