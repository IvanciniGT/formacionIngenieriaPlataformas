
# Metodologías ágiles.

Venimos de muchas décadas de desarrollo de software! (Y de operación de sistemas)
Hemos montado muchos sistemas.. con más o menos éxito.
Lo que pasa es que según hemos ido trabajando hemos aprendido mucho a cerca de cómo hacer las cosas... y acerca de cómo no hacerlas.

Durante décadas cuanto teníamos que enfrentarnos a un proyecto de desarrollo de software utilizábamos metodologías clásicas/tradicionales como el modelo en cascada (waterfall) y variates (V, espiral, etc).

        Tomar requisitos -> 
            Análisis -> 
                    Diseño -> 
                        Implementación -> 
                            Pruebas -> 
                                Despliegue -> 
                                    Mantenimiento

# Metodologías ágiles

Se basan en el concepto de entrega incremental del producto.

Cada 2,3,4, 6 semanas hay paso a producción... lo que subas tiene que ser 100% funcional.

- Primera instalación: 5% de la funcionalidad (100% funcional)
- Segunda instalación: +10% de la funcionalidad (100% funcional)
- Tercera instalación: +5% de la funcionalidad (100% funcional)

Para qué? 
- Feedback rápido por parte del cliente

> El software funcionando es la MEDIDA principal de progreso. < METRICA PARA UN CUADRO DE MANDO

La MEDIDA principal de progreso es el "software funcionando"
   ------
------------------------------- -------------------------------
SUJETO                            PREDICADO
Lo que usaremos para medir que tal va el proyecto es el concepto "software funcionando"

Qué es esto: "software funcionando"?
- Software que hace lo que tiene que hacer, lo que se espera de él.
- Y quién dice eso? 
    - ~~El cliente~~ Al cliente le tiene que llegar algo que funcione!
    - Las pruebas! Si cumple con los requisitos

El cliente me ayuda con la definición de los requisitos.


---

Las metodologías ágiles no son la panacea... Han venido resolviendo unos cuantos problemas, pero han creado otros.

HITO 1: 10-Noviembre: **R1, R2, R3**
    Si el 10 de Noviembre no estaba el R3...
    - Alarmas,
    - Ostias para todo el mundo
    - Reuniones de emergencia
    - Replanificación del HITO: Nueva fecha para el HITO 1: 15 de Noviembre
    - Vamos con retraso
HITO 2: 10-Diciembre: R4, R5, R6
HITO 3: 10-Enero: R7, R8, R9

SPRINT 1: **10-Noviembre** - R1, R2, R3 -> Entrega en producción
    Si el 10 de Noviembre no estaba el R3...
    - Alarmas,
    - Ostias para todo el mundo
    - Se instala el R1 y R2... el día 10 de Noviembre. No se aplaza la fecha ni un minuto.
    - Replanificación los requisitos del R3 para el siguiente sprint.
    - Vamos con retraso
    PASO A PRODUCCIÓN -> Pruebas extensivas a nivel de producción 5% de la funcionalidad (lo que entrego)
 
SPRINT 2: 10-Diciembre - R4, R5, R6 -> Entrega en producción
    PASO A PRODUCCIÓN -> Pruebas extensivas a nivel de producción +10% de la funcionalidad (lo que entrego nuevo) + 5% anterior

SPRINT 3: 10-Enero - R7, R8, R9 -> Entrega en producción
    PASO A PRODUCCIÓN -> Pruebas extensivas a nivel de producción +5% de la funcionalidad (lo que entrego nuevo) + 15% anterior

Y en un proyecto entonces hago 15 pases a producción en lugar de 1 que hacía antes..
Las pruebas se me multiplican como chinches!

Y de dónde sale la pasta, y los recursos? y el tiempo? NO HAY NI PASTA NI TIEMPO NI RECURSOS PARA TAN MAGNA OBRA!
Solución! Automatizar las pruebas, automatizar las instalaciones, automatizar todo lo que se pueda.

No es posible ir a una metodología ágil sin abrazar una cultura devops
---

# DEVOPS

¿Qué es esto?
No es un perfil... al menos no lo ha sido durante muchos años.
Es una cultura, es un movimiento, es una filosofía... en pro de la AUTOMATIZACIÓN.
En la empresa... Chic@s... vamos a automatizar todo lo que se pueda!!!! Vamos a hacer DEVOPS !!! AUTOMATIZAR!!!

Devops va de intentar automatizar todo lo que pueda entre el DEV ---> OPS

Parte de conceptos de ALM: Application Lifecycle Management

Hoy en día si es cierto que se usa para referirnos a un perfil.. pero luego hablamos de eso!


                AUTOMATIZABLE?          HERRAMIENTAS?

    PLAN        No mucho

    CODE        Digamos que no

    BUILD       Totalmente
        Empaquetado                     JAVA: Maven, Gradle, SBT
                                        .NET: dotnet, msbuild, nuget
                                        C/C++: make, cmake, autotools
                                        JS: npm, yarn, pnpm
    ----------------------------------------------------> git + empaquetado automatizado = Desarrollo ágil: Empaquetado del producto
    TEST        
       Definición   No mucho
       Ejecución    Totalmente
                                        Framework de pruebas: JUnit, NUnit, PyTest, Mocha, Jasmine, Selenium
                                        Pruebas de UI WEB: Selenium, Cypress, Karma
                                        Pruebas de carga: JMeter, Gatling, Locust, LoadRunner
                                        Pruebas de seguridad: OWASP ZAP, Burp Suite
                                        Pruebas de calidad de código: SonarQube, ESLint, Pylint, Checkstyle
                                        Pruebas de servicios web: Postman, SoapUI, ReadyAPI, Karate
        
        Las ejecuto en la máquina del desarrollador?   NO... No me fío.. está maleao!
        Las ejecuto en la máquina del tester?          NO... No me fío.. está maleao!
        Las ejecuto en un entorno de pruebas?          NO... No me fío.. está maleao! Antiguamente si.... solo instalaba allí pocas veces.
                                                       Hoy en día? con metodologías ágiles?   Después de 40 instalaciones en producción!  MALEAO !
           Ese entorno ha recibido muchos nombres a lo largo de la historia.. de hecho cada empresa lo llamada de una manera diferente:
           - Test, Pruebas, Q&A, PRE, Integración, Staging
  
        La tendencia hoy en día es a tener entornos de prueba de usar y tirar! como lo pañuelos de la nariz!
            Hace falta hacer pruebas: Crea un entorno, instala, prueba, destruye el entorno. Esto es lo que me asegura que el entorno está limpio.

            Eso supone mucho curro! porque estamos hablando de AUTOMATIZAR LA CREACION DEL ENTORNO, LA INSTALACION DEL SOFTWARE, LA EJECUCION DE LAS PRUEBAS, Y LA DESTRUCCION DEL ENTORNO.
            Y para automatizar la gestión de entornos e instalaciones:
                                        Infraestructura como código: Terraform, Pulumi, AWS CloudFormation
                                        Gestión de configuración: Ansible, Puppet, Chef, SaltStack
                                        Contenedores: **Docker, Podman**
                                        Máquinas virtuales: Vagrant, Packer
    -----------------------------------------------------------> Integración continua (CI= Continuous Integration)
    Cómo se llamará a tener Continuamente en el entorno de INTEGRACION la última versión del producto sometida a pruebas AUTOMATIZADAS?
    Para qué? Cuál es el producto de esto? De esta automatización? De este programa de automatización (PIPELINE)? Informe de pruebas actualizado en tiempo real. PARA QUE?

    RELEASE    Dejar un empaquetado probado de mi sistema en manos de mi cliente.
               Dejar mi app en el Google Play, App Store, Docker hub, Atifactory, Nexus
                     SI
                                        HERRAMIENTAS: Ansible, Python, apps especificas
    -----------------------------------------------------------> Entrega continua (CD= Continuous Delivery)
    DEPLOY           SI
                                        HERRAMIENTAS: Scripts de la bash, ps1, python, Kubernetes, Openshift
    -----------------------------------------------------------> Despliegue continuo (CD= Continuous Deployment)
    OPERATE          SI
        reinicio de un sistema, escalado, gestión de logs

    MONITOR          SI
    ----------------------------------------------------------> Devops completo

¿Cuál era el trabajo de un tester antes?                Probar sistemas
¿Cuál es el trabajo de un tester hoy en día?            Crear programas que prueben otros programas (sistemas)

Pregunta... Si ya tengo todos esos programas de automatización:
- Empaquetado automatizado mediante maven                                       <- Desarrollo
- Pruebas automatizadas mediante JUnit, Selenium, JMeter, SonarQube             <- Testes / desarrollo
- Instalación automatizada mediante Ansible, Terraform, Docker                  <- Sistemas / desarrollo
- Despliegue automatizado mediante Ansible, Kubernetes                          <- Sistemas
- Operación automatizada mediante scripts, herramientas de monitoreo            <- Sistemas
- Monitoreo automatizado mediante Prometheus, Grafana, ELK                      <- Sistemas 

Ya he acabado? ya tengo todo automatizado? NO
Quién ejecuta esos programas? Ahora, que tengo todo eso, me puedo plantear un segundo nivel de automatización: 
    ORQUESTAR TODAS ESAS TAREAS DE AUTOMATIZACIÓN INDIVIDUALES que hemos creado.
    Quién orquesta TODO? Qué herramientas me ayudan a orquestar todos esos trabajo? Los servidores de Automatización: 
        - Jenkins
        - GitLab CI/CD
        - GitHub Actions
        - Azure DevOps
        - CircleCI
        - Travis CI
        - Bamboo
        - TeamCity
    Quién usa esos servidores de automatización para diseñar PIPELINES de automatización que orquesten el trabajo de TODO EL MUNDO?
    Pues.. aquí nos sale un perfil nuevo... una persona, que antes no hacía falta.. porque cada uno de estos trabajo se hacía en un reino de taifas.
    Hoy en día queremos orquestar/integrar todos esos trabajos. Y necesito alguien que tenga VISION COMPLETA del ciclo de vida del software, y que sepa de herramientas de desarrollo, de pruebas, de instalación, de despliegue, de operación y de monitoreo.

    Ese es un perfil que ha habido que crear. Y a ese perfil es a lo que se empezó llamando DEVOPS.
    El problema es que eso se ha desvirtuado mucho, y hoy en día se usa el término DEVOPS para referirse al administrador de sistemas que hoy en día automatiza su trabajo... especialmente si lo hace en clouds.


---

# Qué es automatizar?

Es crear una máquina (o cambiar el comportamiento de una que ya tengo con programas) para que haga el trabajo que antes hacía un humano.

Puedo automatizar el lavado de la ropa: LAVADORA
Incluso esa máquina tiene(admite) PROGRAMAS de lavado: Frío, Caliente, Rápido, Delicado, etc.

En nuestro campo, la máquina ya la tenemos: COMPUTADORA..
Lo que haremos será programas que sean ejecutados por la computadora para hacer el trabajo que antes hacía un humano.

HAY 2 niveles al automatizar.

Persiana... que la subo y bajo con cuerdita. Quiero automatizarlo.
1º Motor en reemplazo de la cuerdita.
2º Botón que al apretar activa el motor. <<< Quien aprieta el botón? Un humano.
---  Segundo nivel de automatización  --- Que solo tiene sentido si tenga ya un primer nivel de automatización.
3º Temporizador que cada día a las 8:00 baja la persiana y a las 20:00 la sube. 
   Dispositivo de hogar inteligente que puedo programar desde el móvil.
---

# Entornos de producción y de despliegue de aplicaciones

Una cosa es instalar una app en mi portátil.. o en un entorno de pruebas...
Otra cosa es instalarla en un entorno de producción.

Y es que los entornos de producción son muy especiales, y deben cumplir con algunos requisitos/características que no encontramos en otros entornos:
- Alta disponibilidad
   Tratar de garantizar un determinado tiempo de servicio pactado previamente de forma contractual en muchos casos (SLA). Esto es la carta a los reyes magos... Yo intentaré cumplirla, pero no te lo puedo garantizar al 100%... cuando pase el año, veremos a ver si he cumplido.. si he sido bueno.
   Normalmente lo medimos en 9s.
        90% = RUINA! => Admitimos 36,5 días de caída al año (blog con las fotos de la boda) |  €
        99%             Admitimos 3,65 días de caída al año (peluquería de barrio)          |  €€
        99.9%           Admitimos 8,76 horas de caída al año (supermercado)                 |  €€€€€€
        99.99%          Admitimos 52,56 minutos de caída al año (banco)                     |  €€€€€€€€€€€€€€
        99.999%         Admitimos 5,26 minutos de caída al año (hospital)                   |  €€€€€€€€€€€€€€€€€€€€€€€€€€€€€€€€€€€
                                                                                            v
    Realmente los 9s solo me informan de la criticidad del sistema.
    La forma de lidiar con los problemas que podamos tener es REDUNDANCIA.

- Escalabilidad
   La capacidad de ajustar la infra a las necesidades de la aplicación en cada momento de tiempo.

    App1: App departamental... App para que los médicos de un hospital lleven el control de sus pacientes.
        Día 1:      100 usuarios
        Día 100:    100 usuarios       En un caso como este, no necesito escalar.
        Día 1000:   100 usuarios

    App2: Un app que vaya teniendo éxito
        Día 1:      100 usuarios
        Día 100:    1.000 usuarios     En un caso como este, necesito escalar. ESCALABILIDAD VERTICAL: MAS MAQUINA! (más RAM, MAS CPU...)
        Día 1000:   10.000 usuarios

    App3: Este es INTERNET
        Día n:      100 usuarios
        Día n+1:    1.000.000 usuarios   
        Día n+2:    1 usuario
        Día n+3:    10.000.000 usuarios
        Día n+4:    4 usuarios

    Pero ni por días.. por horas o minutos:
        Soy la web del telepi:
        - 6:00am     usuarios?      0 que estoy cerrado
        - 10:00am    usuarios?      0 que estoy cerrado
        - 12:00pm    usuarios?      4 que estoy abierto
        - 14:00pm    usuarios?      1000 que es la hora de comer
        - 16:20pm    usuarios?      10 ya han comío'... Menchu que solo ha escrito 40 lineas de código.
        - 18:00pm    usuarios?      300  4 cumpleaños
        - 21:00pm    Madrid Barça de por medio.. agarra que nos vamos!!!! 100000000
        - 23:30: pm    usuarios?      0 ya han cenado
                En un caso como este, necesito escalar. ESCALABILIDAD HORIZONTAL: MAS MAQUINAS o MENOS !
                Quién me ofrece eso? esa versatilidad? Libertad, Flexibilidad? CLOUDS

- Seguridad algo más estricta.

# Clouds

Un cloud es el conjunto de servicios (mundo IT) que una empresa ofrece a sus clientes a través de internet.
AWS es el cloud de Amazon. Y es el conjunto de servicios que Amazon ofrece a sus clientes IT a través de internet.
GCP es el cloud de Google. Y es el conjunto de servicios que Google ofrece a sus clientes IT a través de internet.
Azure es el cloud de Microsoft. Y es el conjunto de servicios que Microsoft ofrece a sus clientes IT a través de internet.
OracleCloud es el cloud de Oracle. Y es el conjunto de servicios que Oracle ofrece a sus clientes IT a través de internet.
IBMCloud es el cloud de IBM. Y es el conjunto de servicios que IBM ofrece a sus clientes IT a través de internet.
....

Esos servicios pueden ser de varios tipos:
- Servicios de infraestructura (IaaS = Infraestructure as a Service) Si contrato hardware: Máquinas virtuales, físicas , contenedores, redes, almacenamiento...
- Servicios de plataforma (PaaS = Platform as a Service): Si contrato no solo la infra sino programas no orientados a usuario final ya instalados y gestionados por el proveedor del cloud: Bases de datos, servidores web, servidores de aplicaciones, colas de mensajes, registries de contenedores, funciones serverless...
- Servicios de software (SaaS = Software as a Service): Si contrato aplicaciones completas orientadas a usuario final ya instaladas y gestionadas por el proveedor del cloud: Office365, Salesforce

La gracia de los clouds es que:
- No hay intermediación humana por parte del proveedor del cloud. TODO ESTA AUTOMATIZADO
- Basado en un modelo de pago por uso (pay as you go)
- Tengo flexibilidad en los contratos. Puedo subir y bajar recursos en función de mis necesidades.


# Contenedores

Un contenedor es un entorno aislado dentro de un SO Linux (Windows... bueno...) donde ejecutar procesos.
Es una forma distinta de ejecutar software dentro de un a computadora.

# Instalar / Desplegar software en una computadora

## Tradicional: Instalaciones a hierro

        App1 + App2 + App3          Esto tiene muchos problemas... el instalar así:
    ------------------------            - App1 y App2 no sean compatibles.. o tengan dependencias incompatibles
        Sistema Operativo                  o requieran configuraciones diferentes del SO.
    ------------------------            - App2 potencialmente puede ESPIAR los datos/HDD/RAM de App1... De hecho es en lo que se basan muchos virus.
            HIERRO                      - En ocasiones las Apps tienen fallos! (BUGS) y tienen comportamientos raros. 
                                             App1 tiene un fallo.. y pone la CPU pa' freir huevos.. 100% ---> OFFLINE
                                             App2 y App3 van detrás.. Si no hay recursos no los hay para nadie.

## Máquinas virtuales

        App1  |  App2 + App3            Esto lo hemos usado mucho. Y nos soluciona todos los problemas que teníamos con las instalaciones a hierro.
    ------------------------            Pero... a qué coste? Qué problemas tengo aquí?
        SO 1  |     SO 2                      - La instalación global se complica mucho... y su mnto.
    ------------------------                  - Pérdida de recursos efectivos... Cada SO tiene su overhead.
        MV 1  |     MV 2                      - Merma en el rendimiento de las apps.
    ------------------------
        Hipervisor 
        (VMware, Hyper-V, KVM, Xen
        Citrix, VirtualBox)
    ------------------------
        Sistema Operativo
    ------------------------
            HIERRO

## Contenedores 2013

        App1  |  App2 + App3     Esto me resuelve los mismos problemas que las MVs con respecto a las instalaciones a hierro.
    ------------------------     Pero sin ninguno de sus inconvenientes
        C 1   |     C 2             Hoy en día simplemente no tiene sentido ejecutar un software en un máquina Linux, sin que éste esté en un contenedor.
    ------------------------
      Gestor de contenedores
        (Docker, Podman
        CRIO, ContainerD)
    ------------------------
    Sistema Operativo Linux
    ------------------------
            HIERRO

# Los contenedores se crean desde IMÁGENES DE CONTENEDOR

Un triste archivo comprimido .tar que tiene dentro:
- Un sistema de archivos compatible POSIX ( /bin /etc /var /usr ...)
- Programas ya instalados de antemano (Apache, Nginx, MySQL, PostgreSQL, Redis, MongoDB, cp, bash, mv, ls, etc)
- Configuraciones por defecto

Y lo único que hacemos es descomprimir ese zip (es algo similar a las apps portables de windows), pero lo que se ejecuta queda aislado del resto del sistema.

Esas imágenes de contenedor las sacamos de un REGISTRY DE CONTENEDORES: Docker hub
Todo el software empresarial hoy en día se distribuye en forma de imágenes de contenedor.


# El mundo de los contenedores ESTA TOTALMENTE ESTANDARIZADO.

Todo esta estandarizado por la CNCF (Cloud Native Computing Foundation)
Los formatos de las imágenes de contenedor están estandarizados (OCI)
Los metadatos de las imágenes de contenedor están estandarizados (OCI)
En esos metadatos viene incluso el comando que arranca el programa principal del contenedor.
 
 NGINX
            docker start nginx
            docker stop nginx
 MARIADB
            docker start mariadb
            docker stop mariadb
 JENKINS
            docker start jenkins
            docker stop jenkins

# Kubernetes es otra historia.

Ese nivel de estandarización es el que ha permitido montar herramientas como Kubernetes.

Kubernetes es una herramienta para definir entornos de producción basados en contenedores.
En los que los entornos son creados y operados por el propio Kubernetes de forma automática.

Al trabajar con kubernetes, defino cómo quiero mi entorno de producción en unos archivos de texto (YAML) y se los doy a kubernetes.
Y entonces kubernetes se pone a crear y operar ese entorno de producción de forma automática 24x7.

Los contenedores son una forma increíblemente eficiente de automatizar el despliegue y operación de software en entornos de producción / pruebas.
----

# Sistema Operativo Linux?

# Linux?

Es Linux un Sistema Operativo? NO... es un kernel de SO.
Los SO no son UN PROGRAMA. Son muchos programas trabajando juntos:
- Cargador de arranque (GRUB, LILO)
- Kernel (Linux)
- Shell (Bash, Zsh, Fish)
- Servicios de sistema (systemd, init)
- Utilidades de sistema (coreutils, util-linux)
- Entorno gráfico (X11, Wayland)

Hay muchos SO que usan el kernel Linux.. de hecho es el kernel de SO más usado del mundo con mucha diferencia.
- Android
- ChromeOS
- GNU(70%)/Linux(30%):
  - Red Hat Enterprise Linux (RHEL)
  - Debian 
     - Ubuntu (NO ES UN SO) es una distribución de GNU/Linux
  - Suse
Por cierto.. windows corre un kernel Linux? SI DE FORMA NATIVA
En windows 10 y 11 y en los servers, podéis ir a características avanzadas de windows y activar el "Subsistema de Linux para Windows" (WSL) y os instala un kernel Linux nativo en windows.

# Qué era UNIX?

UN SISTEMA OPERATIVO, que producía la gente de los Lab Bell (AT&T). Lo dejaron de hacer a principios de los 2000.
Pero ese sistema operativo (el más influyente del mundo) se licenciaba de forma distinta a como hoy en día se licencian los SO.
Hoy en día las licencias son EULAs (End User License Agreement).
Antiguamemte UNIX se licenciaba a GRANDES COMPAÑIAS (IBM, HP, SUN, SGI, DELL, etc) o UNIVERSIDADES.
Éstas, adaptaban el SO a su hardware y lo revendían.
El problema... llegó a haber más de 400 versiones distintas de UNIX.... algunas incompatibles entre sí.
Y salieron 2 estándares para intentar unificar todo eso: SUS (The Single UNIX Specification) y POSIX (Portable Operating System Interface).
UNIX se dejó de hacer... las especificaciones siguen haciendose.

# Qué es UNIX?

UNIX NO ES UN SISTEMA OPERATIVO.
Hoy en día, un SO Unix es aquel que cumple con el estándar SUS y POSIX.

IBM: AIX (UNIX®)
ORACLE: Solaris (UNIX®)
HP: HP-UX (UNIX®)
APPLE: macOS (UNIX® 03)

Linus... supuestamente se basó en estas especificaciones para crear el kernel Linux.Nunca lo sabremos... no está certificado. Ni hay interés.
Es más,. hoy en día el desarrollo del kernel Linux va por otro lado totalmente distinto a las especificaciones UNIX.


# Windows es un sistema Operativo?

NO. Es una familia de sistemas operativos.
Windows 95, 10, Windows Server 2019.
Los SO Windows tienen kernel? Si claro.. todo SO tiene kernel.

Microsoft ha creado 2 kernels a lo largo de su historia que ha usado para montar muchos SO:
- DOS: MS-DOS, Windows 3, 95, 98, ME, Vista
- NT (New Technology): Windows NT, 2000, XP, 7, 8, 10, 11, Server 2003, 2008, 2012, 2016, 2019
En los sistemas operativos Windows tenemos un entorno gráfico que se llama Fluent Design ... antiguamente (Windows 8) se llamaba Metro... y antes Aero... 
Terminales (Shell) cmd, Powershell

---

Las herramientas, las metodologías, las culturas, las formas de trabajo, los lenguajes de programación, los frameworks, todo va cambiando en conjunto..,. para resolver los problemas a los que nos enfrentamos en un momento dado del tiempo. Si saco cualquier pieza de ese contexto y la intento encajar en otro contexto, probablemente no funcione.

Usar Kubernetes, para desplegar aplicaciones monolíticas no funciona.
Usar Kubernetes para desplegar una app que se desarrolla siguiendo una metodología tradicional no tiene sentido. No le saco partido.. Me sale más caro que hacer una instalación a hierro.

---

# Arquitecturas orientadas a componentes desacoplados (SOA, Microservicios)

> Sistema de Animalitos Fermín. 2007 (hace 17 años)

Cuál era la forma de acceder a un sistema de este tipo hace 17 años? cómo iban a acceder los usuarios? WEB que veíamos dónde? ÇEn el navegador de un pc, portatil...

    Navegador            >              Servidor de Aplicaciones (Weblogic/Websphere) > Servidor de Base de Datos (Oracle/MySQL/PostgreSQL/MSSQL)
        ^                <  html
        ^
    Cliente


> Y si ese sistema le tuviera que montar hoy en día?    
                                                                                 Servicios/Microservicios
- App móvil iOS. v.1.1.0
- App móvil Android v.1.1.0                                            xml      Programa que se ocupa de los trámites veterinario   <-MariaDB
- Web Mobile First                                                  < json    < Programa que se ocupa de las compras de comida, collares, etc < Mongo
- Web Desktop                                                                   Programa para gestión de usuarios
- IVR: Llamada telefónica                                                       Programa para la gestión de citas peluquería
- Chatbot: WhatsApp, Telegram, Messenger, Slack, Teams                          Programa para cobros
- Asistente de voz: Alexa, Google Assistant, Siri                               Programa para la gestión de animalitos v.1.2.0 (nombre, edad, foto)
                                                                                        (nombre, videos, fecha de nacimiento)
Los problemas han cambiado!                                                                                            v.2.0.0


20 instalaciones al mes a producción! solo de este sistema de Animalitos Fermín.
Esto es WEB! A primeros de mes, pueden dispararse las compras de pienso.
Mientras que las citas veterianario, se mantienen constantes a lo largo del mes.
Tengo que OPERAR ESE SISTEMA EN PRODUCCIÓN 24x7... Escalando los componentes que lo necesiten en cada momento.
Ahí, de entrada tengo 1 servidor de aplicaciones por cada instancia de cada uno de los servicios.
Lo que antes tenía 2 Weblogic en cluster (o 4), ahora tengo 6 tipos de aplicaciones (servicios) de los que iré generando entre 2/10 copias dinámicamente.
En un momento dado puedo tener 50 tomcats... y a la hora 12.

Aquí es donde entra este tinglao!
- Arquitectura de componentes desacoplados (SOA, Microservicios)
- Contenedores (Docker, Podman)
- Orquestadores de contenedores (Kubernetes, OpenShift), para automatizar la creación y operación de entornos de producción basados en contenedores.
- Metodologías ágiles (Scrum, Kanban)
- Cultura Devops (Automatización de todo lo que se pueda)

Esto sin kubernetes,... olvidate!
Esto con metodologías tradicionales... olvidate!
Esto con arquitecturas monolíticas... olvidate!

Es el pack.. es la combinación de todo esto lo que hace que funcione.

Tenemos resueltas muchas cosas, con todo esto que hemos hablado.
- Metodologías ágiles , que ayudan a buscar una forma de trabajo donde podamos ir liberando cambios en la aplicación de forma frecuente.
- Devops, que nos ayuda a automatizar todo lo que se pueda.... y entre otros a poder ir liberando cambios en la aplicación de forma frecuente a bajo coste
- Pruebas automatizadas, que nos ayudan a garantizar que los cambios que vamos liberando no rompen nada.
- Kubernetes que nos ayuda a crear y operar entornos de producción basados en contenedores de forma automática 24x7 (escalados, desescalados, reinicios, actualizaciones, etc)
- Pipelines de CI, CD que nos ayudan a orquestar todo el trabajo de desarrollo, pruebas, instalación, despliegue y operación de la aplicación.

Esto está muy pera... pero... quién monta todo esto? Y eso, para cada proyecto? para cada sistema?
- Repositorios de GIT (40)
- Pipelines de CI (80) En rama dev y en rama release
- Pipelines de CDelivery (40)
- Pipelines de CDeployment (30)
- Necesito controlar todos los microservicios (6)
- Documentarlos para que los desarrolladores sepan como usarlos (6)
- Ir controlando sus versiones... no solo la del código, sino también los despliegues, y su documentación (6)
  Es muy probable que en el mismo momento del tiempo, tenga desplegado el mismo servicio en distintas versiones en mi entorno de producción, con rutas distintas. 
- Hay que crear infra en kubernetes | cloud para cada uno de esos servicios (6)
- Hay que generar dockerfiles para cada uno de esos servicios (6)
- Y para las BBDD...

Cuánto tiempo me lleva configurar todo este tinglao? Me puedo pasar 1 año! antes de empezar a trabajar!
Y... espera.. que cada proyecto.. a su bola? quién lo hace? Lo centralizo? = CUELLO DE BOTELLA
                                                            Lo descentralizo? = Caos - CUELLO DE BOTELLA

Ahi entra el concepto de Ingeniería de Plataformas... Como el siguiente nivel de automatización... De aplicación de devops

Lo que queremos es generar los automatismos, en automático.

IDP = Internal Developer Platform


# Ingeniería de Plataformas?

- Garantizar la disponibilidad, escalabilidad y rendimiento de las aplicaciones y entornos...
- Automatización de procesos y flujos de trabajo...
- Diseño de plataformas de muchas cosas genéricas.




