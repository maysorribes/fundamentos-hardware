<p style="font-size: 1.3em;"><strong>CFGS Administración de Sistemas Informáticos y en Red (1º curso)</strong></p>

Material elaborado para el módulo **0371. Fonaments de Maquinari / Fundamentos de Hardware**

# Respaldo y creación de imágenes

## Programación de Aula

### Resultados de Aprendizaje

Esta unidad trabaja el **Resultado de Aprendizaje 3 (RA3)** del módulo, según el **Real Decreto 1629/2009** (Anexo I, módulo *Fundamentos de Hardware*):

3. **RA3.** Ejecuta procedimientos para recuperar el software base de un equipo, analizándolos y utilizando imágenes almacenadas en memoria auxiliar.

Los criterios de evaluación literales de este RA3 son:

a) Se han identificado los soportes de memoria auxiliar adecuados para el almacenaje y restauración de imágenes de software.

b) Se ha reconocido la diferencia entre una instalación estándar y una preinstalación o imagen de software.

c) Se han identificado y probado las distintas secuencias de arranque configurables en un equipo.

d) Se han utilizado herramientas para el particionado de discos.

e) Se han empleado distintas utilidades y soportes para realizar imágenes.

f) Se han restaurado imágenes desde distintas ubicaciones.

!!! info "Nota"
    En la numeración de tu programación (DECRET 114/2025), estos criterios corresponden previsiblemente a CE29-CE34 (continuando la numeración correlativa tras los de RA1 y RA2). Verifica la correspondencia exacta con tu programación.

### Ponderación de esta unidad

Según el cuadro de ponderaciones de la programación del módulo, **UT6 (Respaldo y creación de imágenes)** aporta un **20%** de la nota final del módulo, correspondiente al 100% del RA3.

### Planificación Temporal (6 sesiones / 12 horas)

| Sesión | Contenido |
| ------ | --------- |
| 1 | Copias de seguridad: conceptos, tipos y estrategia 3-2-1 |
| 2 | Soportes de almacenamiento para copias e imágenes |
| 3 | Instalación estándar frente a imagen preinstalada. Particionado de discos |
| 4 | Secuencias y medios de arranque de un equipo |
| 5 | Creación de imágenes de disco con herramientas específicas |
| 6 | Restauración de imágenes desde distintas ubicaciones. Práctica y repaso |

## 1. Copias de seguridad

Una **copia de seguridad** (o *backup*) es una copia de la información de un sistema, guardada en un soporte independiente, que permite recuperar los datos en caso de pérdida (por avería, borrado accidental, ciberataque...).

### 1.1 Tipos de copia de seguridad

| Tipo | Qué copia | Ventaja | Inconveniente |
| ----- | --------- | ------- | --------------- |
| Completa | Todos los datos seleccionados, cada vez | Restauración simple y rápida (un solo archivo de copia) | Ocupa mucho espacio y tarda más en realizarse |
| Incremental | Solo lo que ha cambiado desde la **última copia** (de cualquier tipo) | Muy rápida y ocupa poco espacio | Para restaurar, hace falta la última completa + todas las incrementales posteriores, en orden |
| Diferencial | Solo lo que ha cambiado desde la **última copia completa** | Restauración más simple que la incremental (solo hace falta la completa + la última diferencial) | Ocupa más espacio que la incremental, ya que va creciendo hasta la siguiente completa |

!!! example "Ejemplo práctico"
    Si el lunes se hace una copia completa, y de martes a viernes se hacen copias **incrementales**, para restaurar el viernes hace falta: la copia del lunes + las de martes, miércoles, jueves y viernes, en ese orden. Si en cambio fueran copias **diferenciales**, solo haría falta: la copia del lunes + la del viernes (que ya incluye todos los cambios acumulados desde el lunes).

### 1.2 La estrategia 3-2-1

Una recomendación clásica y muy extendida en la gestión de copias de seguridad es la **regla 3-2-1**:

- **3** copias de la información (el original + 2 copias de seguridad).
- **2** soportes de almacenamiento distintos (por ejemplo, un disco externo y una nube).
- **1** copia fuera de las instalaciones (*offsite*), para sobrevivir a un desastre físico (incendio, robo, inundación) que afecte al lugar original.

### 1.3 Planificación y automatización

Las copias de seguridad casi nunca se hacen manualmente cada vez: se **programan** para ejecutarse automáticamente (por ejemplo, cada noche), utilizando el programador de tareas del sistema operativo o un software específico de backup, que además suele permitir definir cuánto tiempo se conservan las copias antiguas (política de retención) antes de eliminarlas y liberar espacio.

## 2. Soportes de almacenamiento para copias e imágenes

<img src="/assets/img/cinta-backup.jpg" alt="Unidad de cinta magnética LTO para copias de seguridad" style="max-width:420px; width:100%; display:block; margin:16px auto;">
<p style="text-align:center; font-size:0.85em; color:#666;"><em>Las cintas magnéticas LTO siguen siendo muy utilizadas en entornos empresariales para copias de seguridad a largo plazo.</em></p>

No todos los soportes de memoria auxiliar son igual de adecuados para guardar copias de seguridad o imágenes de sistema. Cada uno tiene sus ventajas e inconvenientes:

| Soporte | Ventajas | Inconvenientes | Uso típico |
| -------- | --------- | ---------------- | ----------- |
| Disco duro externo / SSD externo | Rápido, fácil de usar, reutilizable | Puede fallar mecánicamente (HDD), riesgo si está siempre conectado | Copias personales o de pequeñas empresas |
| NAS | Accesible desde toda la red, puede tener su propio RAID | Requiere red y mantenimiento | Copias centralizadas de varios equipos |
| Cinta magnética (LTO) | Muy económica por GB almacenado, gran durabilidad si se conserva bien, fácil de transportar fuera de las instalaciones | Acceso secuencial (lento para restaurar un archivo suelto), requiere unidad lectora específica | Copias empresariales de gran volumen y archivo a largo plazo |
| Almacenamiento en la nube | Automáticamente fuera de las instalaciones (offsite), accesible desde cualquier lugar | Depende de la conexión a internet, coste recurrente | Copia adicional de la regla 3-2-1, recuperación ante desastres |
| DVD/Blu-ray | Muy económico, resistente a campos magnéticos | Capacidad limitada, lento, cada vez más en desuso | Archivo puntual de poca información |

!!! note "Recuerda"
    Aunque hoy es menos habitual que hace años, la cinta magnética **sigue viva** en el mundo empresarial precisamente por su bajísimo coste por GB y su gran fiabilidad a largo plazo cuando se almacena correctamente, lo que la hace ideal para el archivo histórico de grandes volúmenes de datos que rara vez se necesitan recuperar con urgencia.

## 3. Instalación estándar frente a imagen preinstalada

Es importante distinguir dos formas muy distintas de dejar un sistema operativo funcionando en un equipo:

- **Instalación estándar**: se ejecuta el proceso de instalación completo del sistema operativo desde cero (o desde un archivo de respuestas, como vimos en la UT5), configurando cada equipo de forma individual.
- **Preinstalación o imagen de software**: se copia, tal cual, una **imagen exacta** de un disco ya preparado (con el sistema operativo, controladores y programas ya instalados y configurados) a otro equipo. El proceso es mucho más rápido que una instalación completa, ya que no hay que repetir todos los pasos de configuración en cada máquina.

!!! example "Cuándo usar cada una"
    Una instalación estándar tiene sentido para un único equipo con una configuración muy particular. Una imagen preinstalada es la opción lógica cuando hay que dejar **muchos equipos idénticos** listos para usar (por ejemplo, todos los ordenadores de un aula o de un departamento), como ya se planteó al hablar de despliegue masivo en la UT5.

## 4. Particionado de discos

Como ya se vio en la UT5, un disco puede dividirse en varias **particiones** independientes. En el contexto de las imágenes y copias de seguridad, el particionado es especialmente relevante porque:

- Permite crear una **imagen de una única partición** (por ejemplo, solo la del sistema operativo) sin necesidad de copiar todo el disco.
- Facilita mantener **separados el sistema operativo y los datos del usuario** en particiones distintas, de forma que se pueda restaurar (o incluso reinstalar) el sistema operativo sin afectar a los datos personales guardados en la otra partición.
- Existen herramientas específicas de particionado (tanto integradas en el propio sistema operativo como independientes, como GParted) que permiten crear, redimensionar, mover o eliminar particiones, incluso en muchos casos sin perder los datos que ya contienen.

## 5. Secuencias de arranque de un equipo

Para poder crear o restaurar una imagen, normalmente hace falta arrancar el equipo desde un medio distinto al disco duro habitual (ya que, mientras el sistema operativo está en marcha, algunos de sus propios archivos están "en uso" y no se pueden copiar de forma fiable).

### 5.1 Configuración de la secuencia de arranque

En la BIOS/UEFI se puede configurar el **orden de arranque** (*boot order*): la lista de dispositivos en los que el equipo buscará, por orden, un sistema desde el que iniciar. Es habitual tener que modificar temporalmente este orden (o usar un menú de arranque rápido, accesible con una tecla concreta al encender el equipo) para arrancar desde un USB o DVD en lugar de hacerlo desde el disco duro interno.

### 5.2 Medios de arranque habituales

| Medio de arranque | Uso típico |
| ------------------ | ----------- |
| USB de arranque (live USB) | Contiene una herramienta de creación/restauración de imágenes, o un sistema operativo completo para tareas de mantenimiento, sin necesidad de instalarlo |
| DVD de arranque | Similar al USB, en soporte óptico; cada vez menos habitual |
| Arranque por red (PXE) | El equipo descarga el sistema de arranque desde un servidor de la red, sin necesidad de ningún soporte físico; muy usado en despliegues masivos |
| Partición de recuperación | Una partición oculta en el propio disco del equipo, con herramientas básicas de reparación, sin necesidad de ningún soporte externo |

## 6. Creación de imágenes de disco

<img src="/assets/img/clonacion-disco.jpg" alt="Proceso de clonación de un disco duro" style="max-width:420px; width:100%; display:block; margin:16px auto;">
<p style="text-align:center; font-size:0.85em; color:#666;"><em>Clonar un disco copia su contenido bit a bit en otro soporte o en un archivo de imagen.</em></p>

Una **imagen de disco** es una copia exacta, bit a bit, del contenido de un disco o de una partición, guardada normalmente como uno o varios archivos.

### 6.1 Herramientas habituales de creación de imágenes

| Herramienta | Tipo | Características |
| ------------ | ---- | ----------------- |
| Clonezilla | Software libre | Arranca desde USB/DVD, muy usada para clonar e implantar imágenes en despliegues masivos |
| Acronis True Image | Comercial | Interfaz gráfica sencilla, orientada tanto a copias de seguridad como a clonación de discos |
| dd (Linux) | Comando integrado | Copia bit a bit a bajo nivel, muy flexible pero sin protección ante errores del usuario |
| Herramientas integradas del sistema operativo | Incluidas en el propio SO | Suelen permitir crear una imagen del disco del sistema de forma sencilla, aunque con menos opciones avanzadas |

### 6.2 Imagen completa frente a clonación directa

- **Crear una imagen**: el contenido del disco de origen se guarda como uno o varios **archivos** en otro soporte (disco externo, NAS...), que después se pueden restaurar cuando haga falta, en el mismo equipo o en otro.
- **Clonar directamente**: el contenido de un disco se copia **directamente** a otro disco físico, sin pasar por un archivo intermedio; el disco de destino queda funcionando como una copia exacta del de origen, lista para usarse inmediatamente.

### 6.3 Consideraciones al crear una imagen

- El disco o partición de destino debe tener **capacidad suficiente** para almacenar la imagen (aunque muchas herramientas comprimen el contenido, reduciendo el tamaño final).
- Es recomendable **verificar la integridad** de la imagen tras crearla (muchas herramientas incluyen una opción de verificación), para asegurarse de que se podrá restaurar correctamente cuando se necesite.
- Si el disco de origen tiene errores (sectores dañados), algunas herramientas permiten continuar el proceso omitiendo esas zonas y avisando de qué se ha perdido, en lugar de detener todo el proceso.

## 7. Restauración de imágenes

La restauración es el proceso inverso: volcar el contenido de una imagen guardada de vuelta a un disco, dejándolo en el mismo estado que tenía en el momento de crear la imagen.

### 7.1 Restauración desde distintas ubicaciones

Una imagen puede restaurarse desde diferentes orígenes, según dónde se haya guardado:

- **Desde un soporte local** (disco externo, USB) conectado directamente al equipo.
- **Desde la red** (un recurso compartido, un NAS, un servidor de imágenes), especialmente útil en despliegues masivos donde muchos equipos restauran la misma imagen simultáneamente por red (por ejemplo, mediante PXE + Clonezilla server edition).
- **Desde la nube**, descargando la imagen desde un servicio de almacenamiento remoto antes de aplicarla, o en algunos casos restaurando directamente desde ahí.

!!! warning "Atención"
    Antes de restaurar una imagen sobre un disco, hay que asegurarse de que el disco de destino **no contiene datos que se quieran conservar**, ya que la restauración sobrescribe completamente su contenido anterior.

### 7.2 Comprobación tras la restauración

Después de restaurar una imagen, conviene verificar que el equipo arranca correctamente y que el software y los datos esperados están presentes, antes de dar por completado el proceso y, en su caso, retirar el medio de recuperación utilizado.

## Ejercicios prácticos

!!! task "Tarea"
    **Ejercicio 1**. Explica la diferencia entre una copia de seguridad completa, una incremental y una diferencial. Si se hace una copia completa el lunes y copias diferenciales el resto de la semana, ¿qué archivos se necesitan para restaurar el estado del jueves?

    **Ejercicio 2**. Explica con tus propias palabras en qué consiste la estrategia 3-2-1 de copias de seguridad, y pon un ejemplo concreto de cómo la aplicarías en un aula de informática.

    **Ejercicio 3**. Compara un disco duro externo, una cinta LTO y el almacenamiento en la nube como soportes para copias de seguridad, indicando una ventaja y un inconveniente de cada uno.

    **Ejercicio 4**. Explica la diferencia entre una instalación estándar de un sistema operativo y restaurar una imagen preinstalada. ¿En qué situación elegirías cada una?

    **Ejercicio 5**. ¿Por qué normalmente no se puede crear una imagen fiable del disco mientras el sistema operativo que contiene está en pleno funcionamiento? ¿Qué solución se suele usar?

    **Ejercicio 6**. Describe tres medios distintos desde los que se puede arrancar un equipo para crear o restaurar una imagen, y en qué situación usarías cada uno.

    **Ejercicio 7**. Explica la diferencia entre crear una imagen de un disco y clonar directamente un disco sobre otro. ¿Cuál elegirías si quieres sustituir un disco duro viejo por un SSD nuevo, manteniendo todo el contenido?

    **Ejercicio 8**. ¿Qué comprobaciones harías antes de restaurar una imagen sobre un disco, y por qué son importantes?

    **Ejercicio 9 (práctica en el aula)**. Utilizando Clonezilla (o la herramienta que use tu centro), crea una imagen de una partición o disco de prueba, guárdala en un soporte externo, y después restáurala en otro equipo o partición distinta. Documenta cada paso seguido y cualquier incidencia encontrada.
