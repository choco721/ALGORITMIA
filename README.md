# Algorítmica y lógica computacional 
Departamento de informatica UCA 
Practica 2 - Descriptores estadísticos

La finalidad de esta practica es trabajar con series temporales aplicando descriptores estadísticos para encontrar informacion valiosa de las señales. La idea es ponerse en contexto en un nuevo tema para resolverlo en un tiempo corto.
Se trabajará con la base de datos CHBMIT Scalp EEG Database de physionet.Lea bien las
instrucciones de las anotaciones de los archivos.

1. Cada archivo tiene la extension .edf ∴ es necesario convertirlo a una lista o matriz
para poder analizarlo → ver como funciona la librer´ıa pyedflib, junto con import
highlevel.

2. Para cada archivo se tiene una crisis epileptica anotada i.e. inicio y fin de la crisis,
e.g. el archivo "chb01-summary.txt” tiene toda la informacioon necesaria para la carpeta chb01, e.g. frecuencia de muestreo, los canales usados y las crisis: File
Name: chb01 03.edf
File Start Time: 13:43:04
File End Time: 14:43:04
Number of Seizures in File: 1
Seizure Start Time: 2996 seconds
Seizure End Time: 3036 seconds
Note que todo está en segundos, así que se tiene que trabajar correctamente de acuerdo a la frecuencia de muestreo.
Para convertir de muestras a segundos, basta con hacer una regla de 3.
Si 1 Hz equivale a 1 segundo, cuantos segundos equivalen a la frecuencia de muestreo en Hz.
Moverse a traves de un ciclo for en pasos de 1, corresponde a moverse en pasos de una muestra o en pasos de la frecuencia de muestreo.

3. Segmente las senales de tal manera que el total de la señal a analizar esté compuesta por 2 minutos antes de la crisis, crisis y 2 minutos despues de la crisis, e.g. si la crisis dura un minuto, la duracion de la señal para trabajar será de 5 minutos: 2 min antes + 1 min crisis + 2 min despues. Nota: Restarle la media a cada segmento por canal, hace que se centre todas las senales. 

5. Se analizaran dos escenarios, note que es un ejemplo para 5 minutos. Escenario 1 Por Bloques: Para analizar cada bloque del paso anterior, i.e.
Before = segmento de 2m de duracion antes de crisis.
Crisis = segmento de 1m de duracion de la crisis.
After = segmento de 2 m de duracion después de la crisis.

Escenario 2 Bloque total: para analizar la senal moviendose en pasos de frecuencia de muestreo o en segundos, i.e.
Se tiene la senal completa compuesta por [Before Crisis After]. Observe que los bloques están seguidos, no están divididos.

Para cada paciente se pide: Usar el analisis y la caracterización del Escenario 1 para ser aplicado en el Escenario 2. Hacer el analisis de todos los canales, mínimo para
un paciente.

1. Analizar descriptores estadísticos, como: varianza, desviacioon estándar, prome- ´
dio de variacion absoluta 
PN−1
i=0 |x(i)|/N, covarianza, coeficiente de correlacion de Pearson, correlacion cruzada, autocorrelación, autocovarianza, covarianza cruzada, etc. Determine cuales análisis pueden llegar a servir para caracterizar y determinar: el comienzo y fin de la crisis y la crisis como tal.

3. Grafique los resultados del punto anterior. Determine un posible umbral de identificacion y el tiempo de retardo de detección de la crisis para todos los canales.
El umbral (rango) puede ser determinado por [min,max] de algun descriptor estadístico.

4. Histograma y un diagrama de cajas de los escenarios.
Determine, cual densidad de probabilidad (PDF) se ajusta mejor a los datos.
Una vez determinada la PDF a usar, grafique sus parametros de la distribución elegida por medio de un scaterplot.
Use los diagramas de caja y explique los resultados.

6. Para cada rutina, determine su precondicion, postcondición, invarianza y complejidad. Analice, si usar una función ramdom, mejora la complejidad.

Tener en cuenta:
Esta práctica se defenderá en clase por todo el grupo. Cualquier persona puede hacer preguntas de la exposición. 
Debe entregar una Notebook con los códigos junto con todas las librerías que se
instalaron comentadas, e.g. # pip install pyedflib from pyedflib import highlevel.
Se debe poder correr el programa en cualquier maquina. 
Cabe resaltar que todo el código debe estar debidamente explicado.
Debe entregar un informe, completo y detallado, de todo lo desarrollado, explicando muy bien y claro, todos los resultados obtenidos.
Si desea trabajar en latex, puede hacer un usuario en overleaf y copiar el siguiente código overleaf.
Una presentación con la información más relevante, siempre ayuda a una mejor comprensión.
comprension. ´
Consultas: no duden en escribirme al correo uca.

