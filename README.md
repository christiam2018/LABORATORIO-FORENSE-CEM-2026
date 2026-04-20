# LABORATORIO-FORENSE-CEM-2026
Este ejercicio incluye tutorial en youtube
https://www.youtube.com/watch?v=uwM_Olu2zB4
[README_FORENSE.md](https://github.com/user-attachments/files/26908487/README_FORENSE.md)
TALLER FORENSE
 

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
