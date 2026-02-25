Generación Procedural de Entorno Dinámico en Blender con Python
Descripción General
Este proyecto implementa la generación automática de un entorno tridimensional en Blender mediante scripting en Python. Se construye un pasillo compuesto por segmentos rectos y curvos, incluyendo suelo, muros laterales con materiales alternados y una cámara animada que recorre la trayectoria completa.
El desarrollo utiliza la API de Blender y modelado procedural basado en cálculos geométricos.
Software utilizado: Blender

Objetivo
El objetivo de la práctica es:
•	Generar un entorno 3D de manera procedural.
•	Aplicar materiales con y sin emisión.
•	Construir geometría mediante código.
•	Implementar una animación automatizada de cámara siguiendo una curva.

Estructura del Programa
El sistema está organizado mediante una clase llamada:
Entorno Dinámico
Esta clase encapsula toda la lógica de:
•	Configuración de parámetros.
•	Creación de materiales.
•	Generación de coordenadas.
•	Construcción del suelo.
•	Construcción de muros.
•	Animación de la cámara.
El método principal es:
escena = EntornoDinamico()
escena.construir()

Parámetros Principales
Dentro del constructor se definen los siguientes parámetros:
•	Ancho del pasillo: 3.0 unidades
•	Largo de cada segmento: 2.0 unidades
•	Altura del techo: 3.0 unidades
•	Segmentos rectos: 10
•	Segmentos curvos: 20
•	Giro por segmento curvo: 7.5 grados
Estos valores controlan completamente la forma del entorno generado.

Lógica de Generación Geométrica
1. Cálculo de Trayectoria
Se calculan tres listas principales de puntos:
•	Puntos del borde izquierdo
•	Puntos del borde derecho
•	Puntos de la trayectoria de la cámara
El sistema utiliza funciones trigonométricas como:
•	sin()
•	cos()
•	radians()
Primero se generan segmentos rectos. Posteriormente se incrementa progresivamente el ángulo de rotación para generar la sección curva del pasillo.
También se calcula un vector perpendicular para determinar los bordes laterales del pasillo.

Construcción de Geometría
Creación del Suelo
•	Se combinan los puntos izquierdos y derechos.
•	Se genera una cara cerrada mediante mes.
•	Se asigna el material del pavimento.
El suelo se crea como un único polígono continuo.
Creación de Muros Laterales
Para cada lado:
•	Se generan vértices inferiores.
•	Se generan vértices superiores según la altura del techo.
•	Se crean caras verticales entre segmentos consecutivos.
•	Se alternan materiales para generar un patrón visual.
Esto produce un efecto dinámico en las paredes.

Animación de la Cámara
El sistema crea automáticamente:
1.	Una curva 3D que representa la ruta.
2.	Una cámara.
3.	Una restricción FOLLOW_PATH.
4.	Keyframes desde el cuadro 1 hasta el 200.
La propiedad offset_factor pasa de 0.0 a 1.0, permitiendo que la cámara recorra completamente el entorno.
 
Conceptos Aplicados
•	Modelado procedural
•	Programación orientada a objetos
•	Geometría analítica
•	Uso de la API bpy
•	Uso de bmesh
•	Materiales con emisión
•	Animación programática con keyframes
•	Restricciones de trayectoria

Resultados
Al ejecutar el script:
•	Se limpia la escena.
•	Se genera el pasillo con sección recta y curva.
•	Se construyen suelo y muros.
•	Se aplican materiales alternados.
•	Se crea una cámara animada recorriendo la escena.
El entorno se construye completamente por medio de código, sin intervención manual en el modelado.

Conclusiones
La práctica demuestra que Blender permite la generación automatizada de entornos tridimensionales mediante scripting.
El uso de programación para modelado y animación:
•	Reduce trabajo manual.
•	Permite crear estructuras parametrizadas.
•	Facilita la reutilización del código.
•	Es útil en desarrollo de videojuegos, simulaciones y visualización arquitectónica.

