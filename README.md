<img width="502" height="603" alt="NOMBRES" src="https://github.com/user-attachments/assets/906d8fd9-cb65-4f57-ba5b-7ca8fa17e592" />



# LABORATORIO-FORENSE-CEM-2026
Este ejercicio incluye tutorial en youtube
https://www.youtube.com/watch?v=uwM_Olu2zB4
[README_FORENSE.md](https://github.com/user-attachments/files/26908487/README_FORENSE.md)
TALLER FORENSE


 

https://github.com/user-attachments/assets/f9feca92-4c70-4ead-bccf-55c343db6eb0


# DESARROLLO DE EJERCICIO DE FORENSE

## Carga de evidencia en Autopsy
<img width="1907" height="1007" alt="1" src="https://github.com/user-attachments/assets/7fcc38f3-722a-4a44-af71-7cdc0d19914c" />

En el desarrollo del ejercicio se realizó el intento de incorporación de una nueva fuente de datos dentro de **Autopsy 4.22.1**, siguiendo el flujo de carga de una imagen de espacio no asignado para su posterior análisis forense.

---

## 1. Selección del tipo de fuente de datos

En esta fase se eligió la opción **Unallocated Space Image File**, la cual permite trabajar con imágenes forenses orientadas al análisis de espacio no asignado dentro del medio digital.

<img width="1918" height="1018" alt="2" src="https://github.com/user-attachments/assets/b085eae8-0159-4ea8-a89a-568b81cd8b37" />


---

## 2. Selección de la fuente de datos

Posteriormente, se avanzó al apartado de selección de la fuente de datos, donde se configuró la ruta de entrada, la zona horaria correspondiente a **America/Bogota** y la opción de fragmentación de la imagen en bloques de **2 GB**.

<img width="1917" height="1012" alt="3" src="https://github.com/user-attachments/assets/bb876322-ef27-451b-9699-a11ea8e01dee" />


---

## 3. Configuración de los módulos de ingestión

Luego se habilitaron distintos módulos de ingestión para apoyar el procesamiento automático de la evidencia digital, entre ellos:

- Recent Activity
- Hash Lookup
- File Type Identification
- Extension Mismatch Detector
- Embedded File Extractor
- Picture Analyzer
- Keyword Search
- Email Parser
- Encryption Detection
- Interesting Files Identifier
- Central Repository
- PhotoRec Carver
- Virtual Machine Extractor

Esta fase es importante porque define las tareas automáticas que Autopsy ejecutará sobre la evidencia cargada.




---

## 4. Resultado del proceso

Al finalizar el procedimiento, la herramienta presentó un mensaje de error indicando que **no fue posible agregar la fuente de datos**, debido a errores críticos detectados durante la carga.

<img width="1918" height="1078" alt="Resultados" src="https://github.com/user-attachments/assets/ac90f26b-9371-4d11-8535-410cccebb97e" />

---

## Análisis del incidente

Con base en la secuencia observada, el fallo puede estar relacionado con una o varias de las siguientes causas:

1. La ruta seleccionada no corresponde directamente a un archivo de imagen válido, sino únicamente a una carpeta.
2. El tipo de fuente de datos escogido podría no coincidir con el formato real de la evidencia.
3. El archivo de entrada puede estar incompleto, corrupto o no ser compatible con la opción elegida.
4. Puede existir un problema de permisos de lectura sobre la ruta seleccionada.
5. Algún módulo de ingestión pudo generar conflicto durante el proceso inicial de carga.
<img width="1918" height="1078" alt="Resultados2" src="https://github.com/user-attachments/assets/bc0bc4d2-3e72-4613-aa13-d956b8273e68" />

---


•	¿Quién es el proveedor de marihuana de Joe Jacobs y cuál es su dirección?
626 Jungle Ave Apt 2
Jungle, NY 11111 
•	¿Qué dato clave está disponible dentro del archivo coverpage.jpg?

Metadatos que permite entender la trazabilidad en esa línea de tiempo de la investigación.

•	¿Qué otras escuelas secundarios (si hay) adicionales a Smith Hill, frecuenta Joe Jacobs?

•	Key High School (B)
•	Leetch High School (C)
•	Birard High School (D)
•	Richter High School (E)
•	Hull High School (F)

Patrones identificados:
1.	Patrón temporal: los días siguen una estructura fija de Monday a Friday. 
2.	Patrón secuencial: los colegios aparecen en una rotación cíclica: A, B, C, D, E, F. 
3.	Patrón de codificación: cada colegio tiene una letra asociada entre paréntesis, lo que indica clasificación o identificación abreviada. 
4.	Patrón de repetición: después de llegar a Hull High School (F), la secuencia vuelve a comenzar en Smith Hill High School (A). 
5.	Patrón organizacional: el archivo parece construido con una lógica de agenda programada, no aleatoria. 
6.	Patrón de consistencia: el mes queda fijo en April 2002, mientras las filas siguientes omiten repetirlo, lo que indica herencia de contexto en la tabla.


•	Para cada archivo recuperado, ¿qué proceso fue adelantado por el sospechoso para ocultarlo en el disco?
El archivo ya no aparecía como activo en el sistema, debido a que sus bloques habían sido marcados como Unallocated. En Autopsy, este archivo se identificó dentro de la carpeta Deleted Files con una X roja, lo cual indica que fue eliminado lógicamente, pero no sobrescrito. Esto significa que, aunque el sistema operativo lo consideraba borrado, su contenido aún permanecía físicamente en el disco, permitiendo así su recuperación mediante el análisis forense.

Con base en esa evidencia, el proceso adelantado por el sospechoso para ocultar Jimmy Jungle.doc fue la eliminación lógica del archivo del sistema de archivos.
1. Tipo de archivo
Content-Type: application/msword
Indica que el archivo era un documento de Microsoft Word en formato clásico .doc, no un .txt ni un PDF.

2. Programa usado
extended-properties:Application: Microsoft Word 10.0
Esto apunta a que fue creado o editado con Microsoft Word 10. En términos prácticos, corresponde a una versión antigua de Word, asociada a la generación de Office/Word 2002.

3. Título interno del documento
dc:title: Jimmy Jungle
El título embebido en el archivo es “Jimmy Jungle”. Eso no siempre coincide con el nombre del archivo, pero sí muestra cómo fue etiquetado internamente.

4. Fechas relevantes
dcterms:created: 2002-04-15T20:30:00Z
dcterms:modified: 2002-04-15T21:42:00Z

El documento fue creado el 15 de abril de 2002, y fue modificado ese mismo día, aproximadamente 1 hora y 12 minutos después

•	¿Qué proceso realizó Ud. como investigador para examinar con éxito el contenido completo de cada archivo?

Como investigador, para examinar con éxito el contenido completo de cada archivo realicé un análisis forense lógico y de contenido dentro de Autopsy. Primero identifiqué los archivos recuperados en las categorías de documentos eliminados y verifiqué su estado dentro del sistema de archivos. Luego revisé cada evidencia en las vistas de texto, metadatos y hexadecimal para confirmar su tipo real, sus fechas, su tamaño y posibles alteraciones. En el caso del archivo Jimmy Jungle.doc, examiné el texto extraído y los metadatos del documento para reconstruir su contenido. Para los archivos gráficos y comprimidos, verifiqué la firma del archivo, analicé el contenido residual y revisé si existían datos ocultos o extensiones alteradas. Finalmente, cuando fue necesario, procedí a la recuperación completa mediante extracción/carving del contenido válido y a su posterior apertura con la herramienta adecuada, lo que permitió acceder íntegramente a la información de cada archivo.

•	¿Puede decir qué programa fue usado para crear el archivo coverpage.jpg? ¿Cómo lo puede probar?
El valor application/octet-stream indica únicamente que el archivo fue reconocido como un contenido binario genérico, pero no permite identificar el programa con el que fue creado. Por lo tanto, con los metadatos aportados no existe evidencia técnica suficiente para demostrar qué software originó el archivo coverpage.jpg, ya que no aparecen campos específicos como Software, EXIF o Creator Tool.




## Conclusión

El procedimiento permitió documentar de manera ordenada el proceso de incorporación de evidencia digital en Autopsy. Aunque la fuente de datos no logró ser agregada exitosamente, las capturas evidencian cada una de las etapas ejecutadas y permiten sustentar técnicamente el punto exacto en el que se presentó el error. Esto facilita la trazabilidad del ejercicio y aporta insumos para corregir la selección de la evidencia o ajustar la configuración del análisis forense.
