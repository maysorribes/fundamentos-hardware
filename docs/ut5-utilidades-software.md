<p style="font-size: 1.3em;"><strong>CFGS Administración de Sistemas Informáticos y en Red (1º curso)</strong></p>

Material elaborado para el módulo **0371. Fonaments de Maquinari / Fundamentos de Hardware**

# Utilidades software en un sistema informático

## Programación de Aula

### Resultados de Aprendizaje

Esta unidad trabaja el **Resultado de Aprendizaje 2 (RA2)** del módulo, según el **Real Decreto 1629/2009** (Anexo I, módulo *Fundamentos de Hardware*):

2. **RA2.** Instala software de propósito general evaluando sus características y entornos de aplicación.

Los criterios de evaluación literales de este RA2 son:

a) Se han catalogado los tipos de software según su licencia, distribución y propósito.

b) Se han analizado las necesidades específicas de software asociadas al uso de sistemas informáticos en diferentes entornos productivos.

c) Se han instalado y evaluado utilidades para la gestión de archivos, recuperación de datos, mantenimiento y optimización del sistema.

d) Se han instalado y evaluado utilidades de seguridad básica.

e) Se ha instalado y evaluado software ofimático y de utilidad general.

f) Se ha consultado la documentación y las ayudas interactivas.

g) Se ha verificado la repercusión de la eliminación, modificación y/o actualización de las utilidades instaladas en el sistema.

h) Se han probado y comparado aplicaciones portables y no portables.

i) Se han realizado inventarios del software instalado y las características de su licencia.

!!! info "Nota"
    En la numeración de tu programación (DECRET 114/2025), estos criterios corresponden previsiblemente a CE20-CE28 (continuando la numeración correlativa tras los de RA1). Verifica la correspondencia exacta con tu programación.

### Ponderación de esta unidad

Según el cuadro de ponderaciones de la programación del módulo, **UT5 (Utilidades software en un sistema informático)** aporta un **20%** de la nota final del módulo, correspondiente al 100% del RA2.

### Planificación Temporal (6 sesiones / 12 horas)

| Sesión | Contenido |
| ------ | --------- |
| 1 | Tipos de software y licencias |
| 2 | Instalación de sistemas operativos: requisitos y particionado |
| 3 | Controladores (drivers) y firmware |
| 4 | Utilidades del sistema: antivirus, limpieza, compresión y monitorización |
| 5 | Software de virtualización y máquinas virtuales |
| 6 | Instalación desatendida y despliegue masivo. Repaso y ejercicios |

## 1. Tipos de software

El **software** es la parte lógica de un sistema informático: el conjunto de programas e instrucciones que permiten al hardware realizar tareas. Se clasifica principalmente en tres grandes categorías:

| Tipo | Función | Ejemplos |
| ----- | ------- | -------- |
| Software de sistema | Gestiona el propio hardware y sirve de base para el resto de programas | Sistema operativo, controladores (drivers), BIOS/UEFI |
| Software de utilidad | Realiza tareas de mantenimiento y soporte del sistema | Antivirus, compresores, limpiadores de disco, particionadores |
| Software de aplicación | Resuelve tareas concretas del usuario final | Procesadores de texto, navegadores, editores gráficos |

### 1.1 El sistema operativo con más detalle

Dentro del software de sistema, el **sistema operativo** merece una mención especial: es el programa que arranca justo después de la BIOS/UEFI y que se mantiene en ejecución mientras el equipo está encendido, realizando funciones como:

- **Gestión de procesos**: decide qué programa usa la CPU en cada momento.
- **Gestión de memoria**: asigna y libera espacio en la RAM a cada programa en ejecución.
- **Gestión de archivos**: organiza la información en el almacenamiento mediante un sistema de archivos.
- **Gestión de dispositivos**: hace de intermediario entre las aplicaciones y el hardware, a través de los drivers.
- **Interfaz con el usuario**: ya sea gráfica (GUI) o de línea de comandos (CLI).

### 1.2 Software de aplicación: categorías habituales en la empresa

Dentro del software de aplicación, en un entorno productivo suelen distinguirse varias grandes familias:

| Categoría | Función | Ejemplos |
| ---------- | ------- | -------- |
| Ofimática | Documentos, hojas de cálculo, presentaciones | Microsoft Office, LibreOffice, Google Workspace |
| ERP (Enterprise Resource Planning) | Gestión integral de los recursos de la empresa (contabilidad, almacén, producción...) | SAP, Odoo |
| CRM (Customer Relationship Management) | Gestión de la relación con clientes | Salesforce, HubSpot |
| Software de diseño/multimedia | Edición gráfica, vídeo, audio | Photoshop, GIMP, Premiere |
| Software vertical | Diseñado para un sector muy concreto | Software de gestión de clínicas, de talleres, de asesorías... |

### 1.3 Tipos de licencia de software

Antes de instalar cualquier software en un entorno profesional, hay que conocer bajo qué licencia se distribuye, tanto por motivos legales como económicos:

| Licencia | Características |
| --------- | ----------------- |
| Software propietario (comercial) | Requiere pago, el código fuente no es accesible, uso restringido por el fabricante |
| Freeware | Gratuito, pero normalmente sin acceso al código fuente ni derecho a modificarlo |
| Shareware | Se puede probar gratis durante un tiempo o con funciones limitadas, después requiere pago |
| Software libre / open source | El código fuente es accesible, se puede modificar y redistribuir, según los términos de su licencia (GPL, MIT, Apache...) |
| Adware | Gratuito, financiado mostrando publicidad al usuario mientras se usa |

!!! note "Copyleft"
    Algunas licencias de software libre, como la **GPL**, incluyen una cláusula llamada *copyleft*: obligan a que cualquier trabajo derivado del programa original se distribuya bajo la misma licencia libre, evitando que alguien tome código libre y lo convierta en propietario.

### 1.4 Tipos de licencia según el número de instalaciones

Además de la licencia "legal" (propietaria, libre...), en el ámbito comercial también existen distintos modelos de contratación:

| Modelo | Descripción |
| ------- | ----------- |
| Licencia individual (OEM/Retail) | Válida para un único equipo o usuario |
| Licencia por volumen | Un único contrato que cubre la instalación en muchos equipos de una organización |
| Suscripción (SaaS) | Pago periódico (mensual/anual) que da derecho a usar el software mientras dure la suscripción |
| Licencia perpetua | Pago único que da derecho a usar esa versión del software indefinidamente, sin garantía de actualizaciones futuras |

!!! info "Recuerda"
    En un entorno empresarial, instalar software sin comprobar su licencia puede suponer un incumplimiento legal para la empresa. Siempre hay que verificar cuántas instalaciones permite una licencia y en qué condiciones. Es habitual realizar **auditorías de software** periódicas para comprobar que el número de instalaciones no supera el de licencias adquiridas.

## 2. Instalación de sistemas operativos

El sistema operativo es el software de sistema más importante, ya que gestiona todo el hardware y sirve de plataforma para ejecutar el resto de programas.

### 2.1 Requisitos del sistema

Antes de instalar un sistema operativo, hay que comprobar que el hardware del equipo cumple los **requisitos mínimos** del fabricante (procesador compatible, memoria RAM suficiente, espacio en disco, y en ocasiones requisitos específicos como el chip de seguridad TPM en sistemas Windows recientes, o el modo de arranque UEFI con Secure Boot habilitado).

### 2.2 Ediciones cliente y servidor

Un mismo fabricante suele ofrecer distintas ediciones de su sistema operativo según el uso previsto:

- **Edición cliente/escritorio**: pensada para el uso individual de un usuario (por ejemplo, Windows 11 Home/Pro).
- **Edición servidor**: pensada para dar servicio a muchos usuarios y equipos a la vez, con funciones adicionales de administración centralizada, mayores límites de hardware soportado, y licencias más costosas (por ejemplo, Windows Server).

### 2.3 Particionado del disco

Antes o durante la instalación, el disco debe **particionarse**: dividirse en una o varias unidades lógicas independientes.

| Concepto | Descripción |
| --------- | ----------- |
| Partición primaria | Partición donde normalmente se instala el sistema operativo |
| Partición de arranque (EFI/Boot) | Pequeña partición que contiene los archivos necesarios para iniciar el sistema |
| Partición de recuperación | Contiene herramientas y una copia base del sistema para restaurarlo en caso de fallo grave |
| Sistema de archivos | Formato lógico con el que se organiza la información dentro de la partición (NTFS, ext4, APFS...) |

!!! example "Formatos de tabla de particiones"
    - **MBR** (Master Boot Record): esquema más antiguo, limitado a 4 particiones primarias y discos de hasta 2 TB.
    - **GPT** (GUID Partition Table): esquema moderno, sin esa limitación de tamaño ni de número de particiones, y necesario para aprovechar el arranque UEFI.

### 2.4 Arranque dual (dual boot)

Es posible instalar **más de un sistema operativo** en el mismo equipo (por ejemplo, Windows y Linux), cada uno en su propia partición, y elegir cuál arrancar cada vez que se enciende el equipo mediante un **gestor de arranque** (como GRUB en Linux). Es una alternativa a la virtualización cuando se necesita el máximo rendimiento nativo de ambos sistemas, aunque solo se puede usar uno de los dos a la vez.

### 2.5 Métodos de instalación

- **Instalación desde soporte físico o USB de arranque**: el método clásico, insertando un DVD o USB con el instalador.
- **Instalación desde imagen (ISO)**: se monta o se graba un archivo ISO que contiene una copia exacta del contenido de instalación.
- **Instalación por red (PXE)**: el equipo arranca directamente desde la red y descarga el sistema operativo de un servidor, sin necesidad de ningún soporte físico. Es habitual en despliegues de muchos equipos a la vez.

### 2.6 Activación del sistema operativo

Muchos sistemas operativos comerciales requieren una **activación** (mediante una clave de licencia) para desbloquear todas sus funciones y confirmar que la copia instalada es legítima. Sin activar, el sistema suele seguir funcionando pero con limitaciones (marca de agua en pantalla, imposibilidad de personalizar ciertos ajustes, o incluso bloqueo tras un periodo de gracia).

## 3. Controladores (drivers) y firmware

Un **controlador (driver)** es un programa que permite al sistema operativo comunicarse con un dispositivo de hardware concreto, "traduciendo" las instrucciones genéricas del sistema operativo a las órdenes específicas que entiende ese hardware.

- Sin el driver correcto, un dispositivo (una tarjeta gráfica, una impresora...) puede no funcionar en absoluto o funcionar solo con capacidades muy limitadas (por ejemplo, una resolución de pantalla básica).
- Los drivers deben ser específicos para el **sistema operativo** y, a menudo, para su versión concreta (un driver de Windows no sirve en Linux).
- El **firmware** es un tipo especial de software grabado directamente en un chip del propio dispositivo (por ejemplo, el firmware de un SSD o de un router), distinto del driver que se instala en el sistema operativo, aunque ambos suelen actualizarse de forma coordinada.

### 3.1 Drivers genéricos y específicos

Cuando se conecta un dispositivo nuevo sin tener aún instalado su driver específico, el sistema operativo suele asignarle automáticamente un **driver genérico** (por ejemplo, para que un monitor muestre imagen a una resolución básica, o para que un teclado funcione con sus teclas más comunes). Este driver genérico permite un funcionamiento mínimo, pero para aprovechar todas las funciones específicas del dispositivo (resoluciones avanzadas, teclas programables, funciones especiales...) es necesario instalar el **driver específico** proporcionado por el fabricante.

### 3.2 Drivers firmados y verificación de origen

Los sistemas operativos actuales exigen cada vez más que los drivers estén **firmados digitalmente** por su fabricante, como garantía de que no han sido modificados por terceros con fines maliciosos. Instalar un driver sin firmar (o de origen desconocido) puede comprometer la seguridad y estabilidad del sistema.

### 3.3 Reversión de drivers (rollback)

Si tras actualizar un driver el sistema se vuelve inestable, la mayoría de sistemas operativos permiten **revertir** al driver anterior que funcionaba correctamente, sin necesidad de reinstalar el sistema completo. Es una de las primeras comprobaciones a realizar ante una inestabilidad tras una actualización reciente.

!!! note "Recuerda"
    Siempre es recomendable descargar los drivers desde la web oficial del fabricante del componente, evitando sitios de terceros que puedan incluir software no deseado.

## 4. Utilidades del sistema

Las utilidades del sistema son programas que no resuelven una tarea del usuario final directamente, sino que mantienen, protegen o monitorizan el propio sistema:

| Categoría | Función | Ejemplos |
| ---------- | ------- | -------- |
| Antivirus / antimalware | Detecta y elimina software malicioso | Windows Defender, ESET, Malwarebytes |
| Compresores | Reducen el tamaño de archivos, agrupando varios en uno solo | 7-Zip, WinRAR |
| Limpiadores de disco | Eliminan archivos temporales y liberan espacio | Herramientas integradas del sistema operativo, CCleaner |
| Desfragmentadores | Reorganizan los datos en discos mecánicos (HDD) para mejorar la velocidad de acceso (no aplica a SSD) | Desfragmentador de Windows |
| Monitores del sistema | Muestran en tiempo real el uso de CPU, memoria, disco y red | Administrador de tareas, HWMonitor |
| Programadores de tareas | Ejecutan automáticamente una acción en un momento programado (por ejemplo, una copia de seguridad cada noche) | Programador de tareas de Windows, cron en Linux |
| Copias de seguridad | Crean copias de la información para poder recuperarla ante un fallo | (se estudiarán en profundidad en la UT6) |

!!! info "Recuerda"
    Desfragmentar un SSD **no mejora su rendimiento** (al no tener partes mecánicas, no importa dónde estén físicamente los datos) y, además, reduce innecesariamente su vida útil, ya que cada escritura desgasta ligeramente la memoria flash.

### 4.1 Precaución con las utilidades "milagro"

Existen muchos programas comerciales que prometen "acelerar" o "optimizar" el ordenador de forma automática (limpiadores de registro, optimizadores de RAM...). En la práctica, muchos aportan una mejora mínima o nula, y algunos incluso pueden causar problemas si eliminan entradas del registro necesarias para el sistema. Como técnico, es preferible usar herramientas conocidas y bien documentadas, y entender qué hace exactamente cada acción antes de aplicarla.

### 4.2 Aplicaciones portables frente a no portables

- **Aplicación no portable (instalable)**: requiere un proceso de instalación que copia archivos en distintas carpetas del sistema y crea entradas en el registro (en Windows) para funcionar. Suele integrarse mejor con el sistema, pero "ensucia" el equipo si se desinstala mal.
- **Aplicación portable**: se ejecuta directamente desde un único archivo o carpeta (por ejemplo, desde un pendrive), sin necesidad de instalación ni de modificar el registro del sistema. Es muy útil para tareas puntuales de mantenimiento o para llevar herramientas de un equipo a otro, aunque algunas funciones avanzadas (como la integración con el menú contextual) pueden no estar disponibles.

## 5. Software de virtualización

La **virtualización** permite ejecutar uno o varios sistemas operativos "invitados" (máquinas virtuales) dentro de un único equipo físico, compartiendo sus recursos de hardware de forma controlada.

| Software | Tipo | Uso típico |
| --------- | ---- | ----------- |
| VirtualBox | Hipervisor de tipo 2 (sobre un sistema operativo anfitrión) | Pruebas, formación, entornos de escritorio |
| VMware Workstation/ESXi | Hipervisor de tipo 2 (Workstation) y de tipo 1 (ESXi) | ESXi es habitual en servidores de producción |
| Hyper-V | Hipervisor de tipo 1, integrado en Windows Server/Pro | Virtualización en entornos Microsoft |

!!! example "Hipervisor tipo 1 vs tipo 2"
    Un **hipervisor de tipo 1** (o *bare-metal*) se instala directamente sobre el hardware, sin necesidad de un sistema operativo anfitrión (es habitual en servidores, como vimos en la UT4). Un **hipervisor de tipo 2** se instala como una aplicación más, sobre un sistema operativo ya existente (habitual en equipos de escritorio para hacer pruebas).

### 5.1 Recursos asignados a una máquina virtual

Al crear una máquina virtual, se le asigna una parte de los recursos del equipo físico (host): un número de núcleos de CPU, una cantidad de memoria RAM, espacio de disco (normalmente en forma de un archivo que actúa como "disco duro virtual") y acceso a la red. Estos recursos quedan reservados o compartidos con el resto de máquinas virtuales, según la configuración del hipervisor.

### 5.2 Instantáneas (snapshots)

Una de las grandes ventajas de la virtualización es la posibilidad de tomar una **instantánea** (snapshot): una fotografía del estado exacto de la máquina virtual en un momento dado. Si algo sale mal después (por ejemplo, al probar una actualización o un cambio de configuración), se puede volver atrás a ese punto en segundos, algo mucho más rápido que reinstalar todo el sistema.

### 5.3 Contenedores: una alternativa ligera

Además de las máquinas virtuales tradicionales, existe otra forma de virtualización más ligera: los **contenedores** (como Docker). A diferencia de una máquina virtual, un contenedor no incluye un sistema operativo completo propio, sino que comparte el núcleo (kernel) del sistema operativo anfitrión, lo que lo hace mucho más rápido de arrancar y más eficiente en el uso de recursos, aunque con menos aislamiento que una máquina virtual completa.

Las máquinas virtuales son especialmente útiles para: probar software sin arriesgar el sistema principal, mantener varios sistemas operativos en un mismo equipo, o aprovechar mejor el hardware de un servidor ejecutando varios servicios independientes entre sí (relacionado con lo visto en la UT4 sobre CPD y consolidación de servidores).

## 6. Instalación desatendida y despliegue masivo

En una empresa con muchos equipos, instalar el sistema operativo y el software uno a uno sería inviable. Para eso existen técnicas de **despliegue masivo**:

- **Instalación desatendida**: se prepara un archivo de respuestas (por ejemplo, `unattend.xml` en Windows) que contiene todas las opciones de la instalación (idioma, particionado, usuario...) para que el proceso se complete automáticamente, sin que un técnico tenga que ir pulsando "Siguiente" en cada equipo.
- **Preparación de una imagen maestra (Sysprep)**: antes de convertir un equipo "modelo" en una imagen para clonar, se ejecuta una herramienta (como Sysprep en Windows) que elimina la información específica de ese equipo (nombre, identificador de seguridad...), para que cada copia desplegada obtenga su propia identidad única en la red.
- **Clonación de imágenes**: se instala y configura un equipo "modelo" (con el sistema operativo y todo el software necesario), se crea una imagen de su disco (con herramientas como Clonezilla), y esa misma imagen se copia al resto de equipos, ahorrando muchísimo tiempo. Esta técnica se ampliará en la UT6.
- **Herramientas de gestión centralizada**: permiten instalar, actualizar o desinstalar software en muchos equipos a la vez desde una única consola de administración (por ejemplo, WSUS o un servidor WDS en entornos Windows).

### 6.1 Gestores de paquetes

En sistemas Linux (y, cada vez más, también en Windows y macOS) es habitual instalar software mediante **gestores de paquetes**: herramientas que descargan, instalan y mantienen actualizado el software desde repositorios centralizados, resolviendo automáticamente las dependencias entre programas.

| Sistema | Gestor de paquetes habitual |
| -------- | ----------------------------- |
| Debian/Ubuntu | `apt` |
| Red Hat/Fedora | `dnf` / `yum` |
| Windows | `winget`, Chocolatey |
| macOS | Homebrew |

Este método facilita enormemente la instalación y actualización de software respecto a buscar e instalar manualmente cada programa desde su web.

## Ejercicios prácticos

!!! task "Tarea"
    **Ejercicio 1**. Clasifica estos programas según sean software de sistema, de utilidad o de aplicación: un antivirus, un navegador web, un controlador de tarjeta gráfica, un editor de fotos, un compresor de archivos.

    **Ejercicio 2**. Explica la diferencia entre freeware y software libre, poniendo un ejemplo de cada uno. ¿Qué añade el concepto de *copyleft* a una licencia libre?

    **Ejercicio 3**. ¿Qué diferencia hay entre una tabla de particiones MBR y una GPT? ¿Cuál usarías en un disco de 4 TB y por qué?

    **Ejercicio 4**. Explica con tus palabras qué es un driver y qué pasaría si intentas instalar un dispositivo sin el driver correcto. ¿Qué diferencia hay entre un driver genérico y uno específico?

    **Ejercicio 5**. ¿Por qué no tiene sentido desfragmentar un SSD? Relaciona tu respuesta con lo que estudiaste sobre el almacenamiento en la UT2.

    **Ejercicio 6**. Explica la diferencia entre un hipervisor de tipo 1 y uno de tipo 2, y pon un ejemplo de cuándo usarías cada uno. ¿Qué ventaja aporta poder hacer una instantánea (snapshot) de una máquina virtual?

    **Ejercicio 7**. Explica con tus propias palabras la diferencia entre una máquina virtual y un contenedor. ¿Cuál usarías para desplegar rápidamente muchas instancias ligeras de una misma aplicación?

    **Ejercicio 8**. Una empresa necesita instalar el mismo sistema operativo y el mismo software en 50 ordenadores nuevos. Describe qué método de instalación usarías (instalación desatendida, clonación de imágenes...) y por qué, en lugar de instalar cada equipo manualmente.

    **Ejercicio 9**. Explica qué es un gestor de paquetes y qué ventaja aporta frente a instalar cada programa manualmente desde su página web.

    **Ejercicio 10**. Una empresa descubre en una auditoría de software que tiene 30 ordenadores con un programa instalado, pero solo dispone de 20 licencias. Explica qué implicaciones tiene esta situación y qué debería hacer la empresa para regularizarla.

    **Ejercicio 11 (práctica en el aula)**. Instala una máquina virtual con VirtualBox (o el hipervisor que use tu centro), asígnale unos recursos de hardware razonables (CPU, RAM, disco), toma una instantánea antes de instalar cualquier programa adicional, e instala después algún software de prueba. Documenta los pasos seguidos.
