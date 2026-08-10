<p style="font-size: 1.3em;"><strong>CFGS Administración de Sistemas Informáticos y en Red (1º curso)</strong></p>

Material elaborado para el módulo **0371. Fonaments de Maquinari / Fundamentos de Hardware**

# Sistemas informáticos en entornos empresariales

## Programación de Aula

### Resultados de Aprendizaje

Esta unidad trabaja el **Resultado de Aprendizaje 4 (RA4)** del módulo, según la programación didáctica del centro:

4. **RA4.** Implanta maquinari específic de centres de processament de dades (CPD), analitzant les seues característiques i aplicacions.

Según la tabla de relación entre criterios de evaluación e instrumentos de la programación del módulo, esta unidad (UT4) se evalúa sobre los criterios **CE18, CE41, CE42, CE43, CE44, CE45, CE46, CE47, CE48 y CE49**.

!!! info "Nota"
    El texto literal de cada criterio de evaluación (CE) está definido en el Real Decreto de título y en el DECRET 114/2025; consulta la redacción exacta en el currículum oficial del ciclo para citarla tal cual en tu programación.

### Ponderación de esta unidad

Según el cuadro de ponderaciones de la programación del módulo, **UT4 (Sistemes informàtics en entorns empresarials)** aporta un **14%** de la nota final del módulo, correspondiente al 100% del RA4.

También según la programación, el **RA4 es el único que se trabaja parcialmente en la formación en empresa** (FCT/formació en empresa), con un 16% del total del módulo.

### Planificación Temporal (6 sesiones / 12 horas)

| Sesión | Contenido |
| ------ | --------- |
| 1 | El Centro de Procesamiento de Datos (CPD): concepto y estructura |
| 2 | Racks, armarios y cableado estructurado |
| 3 | Servidores: tipos y características frente a un PC de sobremesa |
| 4 | Almacenamiento empresarial: NAS y SAN |
| 5 | Alimentación (SAI/PDU) y climatización del CPD |
| 6 | Seguridad física y alta disponibilidad. Repaso y ejercicios |

## 1. El Centro de Procesamiento de Datos (CPD)

Un **CPD** (Centro de Procesamiento de Datos, o *Data Center* en inglés) es una instalación especializada donde se concentran los recursos informáticos necesarios para el funcionamiento de una organización: servidores, sistemas de almacenamiento, equipos de red y toda la infraestructura de soporte (alimentación, refrigeración, seguridad) que los mantiene operativos de forma continua.

A diferencia de un ordenador de sobremesa doméstico, el hardware de un CPD está diseñado para funcionar **24 horas al día, 365 días al año**, priorizando la fiabilidad, la redundancia y la facilidad de mantenimiento sobre otros factores como el precio o el diseño estético.

!!! note "Niveles de fiabilidad (Tier)"
    El Uptime Institute clasifica los CPD en 4 niveles (**Tier I a Tier IV**) según su grado de redundancia y disponibilidad garantizada, desde un Tier I (sin redundancia, disponibilidad básica) hasta un Tier IV (redundancia completa, tolerante a fallos, con la máxima disponibilidad posible).

## 2. Racks, armarios y cableado estructurado

<img src="/assets/img/rack-servidores.jpg" alt="Rack de servidores en un CPD" style="max-width:420px; width:100%; display:block; margin:16px auto;">
<p style="text-align:center; font-size:0.85em; color:#666;"><em>Un rack o armario estandarizado permite alojar de forma ordenada servidores, switches y sistemas de almacenamiento.</em></p>

Los equipos de un CPD no se colocan sueltos, sino en **racks** (armarios metálicos normalizados) que permiten organizarlos de forma vertical, ahorrando espacio y facilitando su ventilación, cableado y mantenimiento.

### 2.1 La unidad de rack (U)

La altura de los equipos que se instalan en un rack se mide en **unidades de rack (U)**, donde 1U equivale a 1,75 pulgadas (4,45 cm) de altura. Un servidor puede ocupar, por ejemplo, 1U (muy compacto), 2U o 4U (más espacio interno para discos y refrigeración). Un rack estándar completo suele tener 42U de altura disponible.

### 2.2 Cableado estructurado

El **cableado estructurado** es un sistema de cableado organizado y documentado que permite conectar todos los equipos de una instalación de forma ordenada, normalmente distribuido en:

- **Cableado horizontal**: conecta cada puesto de trabajo o dispositivo con el armario de distribución de su planta.
- **Cableado vertical (backbone)**: conecta entre sí los distintos armarios de distribución del edificio, y estos con el CPD central.

Un buen cableado estructurado, correctamente etiquetado, es fundamental para poder diagnosticar averías y hacer cambios sin perder tiempo "siguiendo cables" a mano.

## 3. Servidores

Un **servidor** es un ordenador diseñado específicamente para ofrecer servicios y recursos a otros equipos (clientes) a través de una red, funcionando de forma ininterrumpida. Aunque comparte los mismos elementos funcionales que un PC de sobremesa (CPU, memoria, almacenamiento...), sus componentes están pensados para la fiabilidad y el funcionamiento continuo:

| Característica | PC de sobremesa | Servidor |
| ---------------- | ----------------- | --------- |
| CPU | Orientada al rendimiento monousuario | Múltiples núcleos, soporte multiprocesador, orientada a cargas concurrentes |
| Memoria | Sin corrección de errores | Memoria **ECC** (Error-Correcting Code), que detecta y corrige errores de bit automáticamente |
| Almacenamiento | Uno o pocos discos | Varios discos en RAID, a menudo intercambiables en caliente (*hot-swap*) |
| Fuente de alimentación | Una única fuente | Fuentes **redundantes** (si falla una, la otra sigue dando servicio) |
| Gestión remota | No suele tener | Tarjeta de gestión remota (iLO, iDRAC...) para administrar el servidor aunque esté apagado o sin sistema operativo |

### 3.1 Formatos de servidor

- **Servidor torre**: similar en aspecto a un PC de sobremesa grande; adecuado para empresas pequeñas con pocos equipos.
- **Servidor rack**: formato plano pensado para instalarse en un armario rack; permite concentrar muchos servidores en poco espacio.
- **Servidor blade**: módulos muy compactos que se insertan en un chasis común (*enclosure*), compartiendo elementos como la alimentación o la refrigeración entre varios servidores, maximizando la densidad de cómputo.

!!! info "Recuerda"
    La disponibilidad de piezas *hot-swap* (discos, fuentes, incluso ventiladores) permite sustituir un componente averiado **sin apagar el servidor**, evitando interrupciones del servicio.

## 4. Almacenamiento empresarial: NAS y SAN

En un entorno empresarial, el almacenamiento casi nunca está "dentro" de un único servidor, sino centralizado en sistemas dedicados a los que acceden varios servidores a la vez:

| Sistema | Significado | Cómo se accede | Uso típico |
| -------- | ------------ | ---------------- | ----------- |
| NAS (Network Attached Storage) | Almacenamiento conectado a la red | A nivel de archivo, a través de la red (protocolos como SMB o NFS), como si fuera una carpeta compartida | Compartir archivos entre usuarios, copias de seguridad |
| SAN (Storage Area Network) | Red de área de almacenamiento | A nivel de bloque, a través de una red dedicada de alta velocidad (Fibre Channel o iSCSI) | Almacenamiento de alto rendimiento para bases de datos y servidores virtualizados |

!!! example "Diferencia clave"
    Un NAS es como un disco duro compartido en red: el sistema operativo del servidor "ve" carpetas y archivos. Una SAN, en cambio, hace que el servidor "vea" el almacenamiento como si fuera un disco propio interno, permitiendo un rendimiento mucho mayor, típico de entornos de virtualización o bases de datos exigentes.

## 5. Alimentación eléctrica del CPD

### 5.1 El SAI (Sistema de Alimentación Ininterrumpida)

Un **SAI** (o UPS, *Uninterruptible Power Supply*) es un equipo que proporciona energía eléctrica durante un corte de suministro, el tiempo suficiente para que los sistemas se apaguen de forma ordenada o para que entre en funcionamiento un generador auxiliar. Los hay de distintos tipos según su tecnología (*off-line*, *line-interactive*, *on-line*), siendo el **on-line** el que ofrece mayor protección al regenerar constantemente la corriente eléctrica.

### 5.2 El PDU (Power Distribution Unit)

Un **PDU** es, básicamente, una "regleta" inteligente de rack que distribuye la energía eléctrica a todos los equipos instalados en él, permitiendo a menudo monitorizar el consumo e incluso apagar/encender remotamente tomas individuales.

### 5.3 Redundancia eléctrica

En instalaciones críticas es habitual disponer de **doble acometida eléctrica**, generadores diésel de respaldo, y servidores con **doble fuente de alimentación**, cada una conectada a un circuito eléctrico distinto, para que un fallo en un único punto no deje sin servicio al CPD.

## 6. Climatización del CPD

La densidad de equipos de un CPD genera una cantidad de calor muy superior a la de una oficina normal, por lo que requiere sistemas de **climatización de precisión**, capaces de mantener una temperatura y humedad estables las 24 horas.

Una técnica muy habitual es la organización en **pasillo frío / pasillo caliente**: los racks se colocan enfrentados de forma que todas las tomas de aire frío de los equipos miran hacia un mismo pasillo (donde se inyecta aire frío) y todas las salidas de aire caliente miran hacia el pasillo opuesto (por donde se extrae), evitando que el aire caliente de un rack se mezcle con el aire frío que necesita otro.

## 7. Seguridad física del CPD

Además de la seguridad informática (que se trata en otros módulos), un CPD requiere medidas de **seguridad física**:

- **Control de acceso**: tarjetas, biometría o códigos que restringen quién puede entrar físicamente a la sala.
- **Videovigilancia** de la instalación.
- **Sistemas de extinción de incendios** específicos (gases inertes como el FM-200 o el CO₂), que apagan un fuego sin dañar los equipos electrónicos, a diferencia del agua.
- **Detección temprana de humo** mediante sistemas de aspiración de aire de alta sensibilidad, capaces de detectar un principio de incendio antes de que sea visible.

## 8. Alta disponibilidad

La **alta disponibilidad** (High Availability, HA) es el conjunto de técnicas orientadas a que un servicio siga funcionando incluso si falla alguno de sus componentes:

- **Redundancia N+1**: se dispone de un componente (o servidor) de más de los estrictamente necesarios, de forma que si uno falla, el sistema sigue funcionando con normalidad mientras se repara el fallo.
- **Clustering**: varios servidores trabajan de forma coordinada como si fueran uno solo; si uno falla, otro asume su carga de trabajo automáticamente (*failover*).
- **Balanceo de carga**: reparte las peticiones entrantes entre varios servidores, mejorando tanto el rendimiento como la tolerancia a fallos.

!!! note "Virtualización y hardware de CPD"
    Buena parte del hardware de un CPD moderno se dedica a servidores de virtualización: máquinas físicas potentes (muchos núcleos y mucha memoria RAM) sobre las que se ejecutan decenas de máquinas virtuales, optimizando el aprovechamiento del hardware disponible.

## Ejercicios prácticos

!!! task "Tarea"
    **Ejercicio 1**. Explica con tus propias palabras qué es un CPD y en qué se diferencia, en cuanto a exigencias de hardware, de un ordenador de oficina normal.

    **Ejercicio 2**. Un servidor ocupa 2U de espacio en un rack. ¿Cuántos servidores de ese tamaño caben, como máximo, en un rack estándar de 42U?

    **Ejercicio 3**. Compara un NAS y una SAN: ¿en qué se diferencian en la forma de acceder a los datos, y para qué tipo de uso recomendarías cada uno?

    **Ejercicio 4**. Explica qué es la memoria ECC y por qué es especialmente importante en un servidor que da servicio a muchos usuarios de forma continua.

    **Ejercicio 5**. ¿Por qué en un CPD no se usan extintores de agua para apagar un incendio? Investiga qué sistema se usa en su lugar.

    **Ejercicio 6**. Explica la diferencia entre redundancia N+1 y clustering, poniendo un ejemplo de cada uno.

    **Ejercicio 7**. Investiga y describe brevemente qué es la organización en pasillo frío/pasillo caliente, y por qué mejora la eficiencia de la climatización frente a colocar los racks sin ese criterio.

    **Ejercicio 8 (reflexión)**. Si tuvieras que montar el CPD de una pequeña empresa con un presupuesto limitado, ¿qué elementos de los vistos en esta unidad priorizarías y cuáles dejarías para una fase posterior? Justifica tu respuesta.
