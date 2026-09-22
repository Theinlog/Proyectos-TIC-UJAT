# Universidad Juárez Autónoma de Tabasco
**División Académica de Ciencias y Tecnologías de la Información**  
**Asignatura:** Tecnologías de la Información y la Comunicación  
**Proyecto:** Análisis de Datos Estadísticos y Generación de Gráficos  
**Alumno:** Angel Nahum Castro Ruiz  
**Matrícula:** 242H17030  

---

## 1. Presentación del Caso Práctico
El presente informe documenta el análisis estadístico realizado al dataset de rendimiento del **Centro de Soporte y Gestión de Bases de Datos**, evaluando un total de 30 incidentes/tickets registrados. El objetivo es identificar cuellos de botella en los tiempos de respuesta e insatisfacción de los usuarios en los diferentes SGBD (PostgreSQL, MongoDB, MySQL, SQL Server, Oracle).

---

## 2. Resumen Estadístico y Fórmulas Utilizadas

| Métrica / Indicador | Función en Excel Utilizada | Resultado Obtenido |
| :--- | :--- | :--- |
| **Total de Incidencias** | `=CONTAR(D2:D31)` | 30 tickets |
| **Incidencias Resueltas** | `=CONTAR.SI(F2:F31, "Cerrado")` | 27 tickets |
| **Incidencias Críticas** | `=CONTAR.SI(C2:C31, "Critica")` | 6 tickets |
| **Tiempo Promedio de Atención** | `=PROMEDIO(D2:D31)` | 112.83 minutos |
| **Mediana del Tiempo de Atención**| `=MEDIANA(D2:D31)` | 90.00 minutos |
| **Tiempo Máximo registrado** | `=MAX(D2:D31)` | 300.00 minutos (5 hrs) |
| **Satisfacción Promedio** | `=PROMEDIO(E2:E31)` | 3.53 / 5.00 |

---

## 3. Interpretación de los Hallazgos

1. **Relación entre Prioridad y Tiempo de Resolución:**  
   Los datos muestran una correlación directa entre el nivel de prioridad y el tiempo de atención. Los tickets categorizados como *Críticos* promedian **238 minutos** de resolución, en comparación con los de prioridad *Baja*, que se resuelven en un promedio de **26.6 minutos**.

2. **Evaluación de la Satisfacción del Cliente:**  
   Existe una penalización severa en la satisfacción del usuario cuando el tiempo de atención supera los 180 minutos. Las incidencias críticas obtuvieron una calificación promedio de **1.33/5**, mientras que los tickets con atención menor a 45 minutos alcanzaron el valor máximo de **5/5**.

3. **Plataforma con Mayor Incidencia:**  
   Las bases de datos relacionales tradicionales (**PostgreSQL** y **SQL Server**) concentran el 53.3% del total de incidencias registradas, principalmente vinculadas a bloqueos de transacciones y optimización de consultas SQL.

---

## 4. Recomendaciones de Mejora

* **Implementación de SLAs (Acuerdos de Nivel de Servicio):** Establecer un límite máximo de 120 minutos para la atención de incidentes críticos en SGBD.
* **Capacitación en Optimización SQL:** Automatizar el monitoreo de consultas lentas en PostgreSQL para reducir la generación de tickets de prioridad alta.
* **Escalamiento Automatizado:** Configurar alertas inmediatas a los administradores de bases de datos (DBA) cuando un ticket crítico permanezca sin atención durante más de 30 minutos.

---

## 5. Evidencia del Archivo Excel
El archivo fuente estructurado con las tablas dinámicas y gráficos correspondientes se encuentra alojado en este mismo repositorio:
<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/b333acc7-83df-46af-a5c3-4cd2b3896d17" />
<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/e90149ea-d72b-4c44-a9d5-233b53ba3fa1" />
