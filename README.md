# LABORATORIO-FORENSE-CEM-2026
Este ejercicio incluye tutorial en youtube
https://www.youtube.com/watch?v=uwM_Olu2zB4
[README_FORENSE.md](https://github.com/user-attachments/files/26908487/README_FORENSE.md)
TALLER FORENSE
 
# DESARROLLO DE EJERCICIO DE FORENSE

## Carga de evidencia en Autopsy
<img width="1907" height="1007" alt="1" src="https://github.com/user-attachments/assets/7fcc38f3-722a-4a44-af71-7cdc0d19914c" />

En el desarrollo del ejercicio se realizó el intento de incorporación de una nueva fuente de datos dentro de **Autopsy 4.22.1**, siguiendo el flujo de carga de una imagen de espacio no asignado para su posterior análisis forense.

---

## 1. Selección del tipo de fuente de datos

En esta fase se eligió la opción **Unallocated Space Image File**, la cual permite trabajar con imágenes forenses orientadas al análisis de espacio no asignado dentro del medio digital.

![Selección del tipo de fuente de datos](./img/01_tipo_fuente.png)

---

## 2. Selección de la fuente de datos

Posteriormente, se avanzó al apartado de selección de la fuente de datos, donde se configuró la ruta de entrada, la zona horaria correspondiente a **America/Bogota** y la opción de fragmentación de la imagen en bloques de **2 GB**.

![Selección de la fuente de datos](./img/02_seleccion_archivo.png)

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

![Configuración de ingestión](./img/03_configure_ingest.png)

---

## 4. Resultado del proceso

Al finalizar el procedimiento, la herramienta presentó un mensaje de error indicando que **no fue posible agregar la fuente de datos**, debido a errores críticos detectados durante la carga.

![Error al agregar la fuente de datos](./img/04_error_carga.png)

---

## Análisis del incidente

Con base en la secuencia observada, el fallo puede estar relacionado con una o varias de las siguientes causas:

1. La ruta seleccionada no corresponde directamente a un archivo de imagen válido, sino únicamente a una carpeta.
2. El tipo de fuente de datos escogido podría no coincidir con el formato real de la evidencia.
3. El archivo de entrada puede estar incompleto, corrupto o no ser compatible con la opción elegida.
4. Puede existir un problema de permisos de lectura sobre la ruta seleccionada.
5. Algún módulo de ingestión pudo generar conflicto durante el proceso inicial de carga.

---

## Conclusión

El procedimiento permitió documentar de manera ordenada el proceso de incorporación de evidencia digital en Autopsy. Aunque la fuente de datos no logró ser agregada exitosamente, las capturas evidencian cada una de las etapas ejecutadas y permiten sustentar técnicamente el punto exacto en el que se presentó el error. Esto facilita la trazabilidad del ejercicio y aporta insumos para corregir la selección de la evidencia o ajustar la configuración del análisis forense.
