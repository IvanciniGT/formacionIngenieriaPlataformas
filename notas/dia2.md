
# Metodologías ágiles como reemplazo de las metodologías tradicionales

Problemas que no habíamos ido encontrando con las metodologías tradicionales.
Esto nos lleva a buscar nuevas formas de trabajo:
- Entrega continua incremental del producto en producción = FOLLÓN DE CURRO
    Las instalaciones se multiplican
    Las pruebas ya flipas!
Aun así, merece la pena.

# Arquitecturas... y de como hemos pasado de arquitecturas monolíticas a arquitecturas de componentes desacoplados

Había problemas grandes con las arquitecturas monolíticas...
Y hoy en día además, los problemas prácticos que tenemos tampoco los mismos: Tenemos un huevo de frontales, apps móviles, apps web, servicios de terceros, etc.

Todo eso lleva a la necesidad ir a otro tipo de arquitecturas.

Y Esto.. FOLLON DE CURRO
Pasamos de 1 repo de GIT.. de un proyecto que se compila y se instala a 
300 repositorios de GIT, 300 proyectos que se compilan y se instalan.

Y Ahora multiplica... al usar una metodología ágil...
Esos 300 repos, cada uno dará lugar a 1/2 instalaciones al mes = 1500 instalaciones al mes.
Cuando tenía el monolito, con una metodología tradicional, tenía 1/4 instalación al año;

# Despliegues más complejos | Operativa más compleja en entornos de producción

Antes as apps o no escalaban o escalaban en vertical.
Hoy en día (INTERNET) las apps escalan en horizontal. <--- CLOUDS

Los clouds me dan todo automatizado... NOS HA JODIDO... de su lao!
Relleno un formulario y a los 1 minuto tengo mi servidor.
Pero si tengo que crear 20 y luego a los 15 minutos matar 5 y luego a los 10 minutos crear 10 más... FOLLON DE CURRO

# Estoy muerto! No hay pasta.. es imposible!

A no ser que Automatices TODO!
Si automatizas TODO, puedes llegar a hacerlo.

Automatizar = DEVOPS

---

Automatizar ... en nuestro mercao' al final es CREAR PROGRAMAS.
O usar programas que configuro para que hagan lo que yo quiero = Sigue siendo programar... con formularios.. con archivos de texto...

Y hay mucho que automatizar:
- La creación de entornos:
  - Crear servidores, redes, balanceadores de carga, bases de datos, etc.
  - De pruebas, de desarrollo, de producción, etc.
- El empaquetado de apps
- Las pruebas de las apps
- La instalación de las apps
- La operación de las apps
- El monitoreo de las apps

Y cada una de esas tareas puede ser muy compleja.... y puede involucrar decenas de herramientas diferentes.
Y necesito conocimiento muy específico de cada una de esas herramientas.
Y no es solo un equipo... es que son varios equipos (desarrollo, operaciones, seguridad, redes, etc.) que necesitarán de formación específica.
Y de tiempo, para montar todas esas automatizaciones.

El pasar o adoptar una cultura devops, a una organización le puede costar años... varios: 3-6 años
Implicará CAMBIOS A NIVEL ORGANIZATIVO (Nuevos departamentos, gente que la reubican, etc.)
Cambian los procesos de trabajo
Cambian las herramientas
Cambian las responsabilidades de la gente
Cambian las habilidades que se necesitan
Y... adaptar TODA LA MIERDA que ya tienes... a ese tinglao!

Eso no me lo cuentan!
Lo que pasa es que cuando este tinglao' está montao' ... es todo una maravilla. Todo rueda solito!

Decíamos que no es solo automatizar cada uno de esos trabajos.

Querremos después (antes no tiene sentido) que todo eso se haga de forma automática, sin intervención humana.
La llamada a todos esos automatismos, se hará desde un programa que orqueste todo el proceso.

Esos programas son los que llamamos pipelines de CI/CD.

> CI = Continuous Integration = Integración continua

Tener CONTINUAMENTE en el entorno de INTEGRACION la última versión del producto sometida a pruebas AUTOMATIZADAS.

Montar un programa que:                                                           JENKINS, GITLAB CI/CD, etc.
- Extraiga el código fuente de un proyecto de un repositorio de GIT:              GIT
- Compile el proyecto:                                                            MAVEN, NPM...
- Crear entornos de pruebas:                                                      TERRAFORM, ANSIBLE, DOCKER...
- Ejecute cierto tipo de pruebas automatizadas sobre él:                          JUNIT, SELENIUM... (500 herramientas)
- Emita un informe de resultados                                                  Las propias herramientas me lo generan
- Publicar ese informe en un sitio web accesible para todo el equipo:             JENKINS, GITLAB, etc.
En cuanto un desarrollador haga un COMMIT de un cambio en el repositorio de GIT.

> CD = Continuous Delivery = Entrega continua

Que mi cliente siempre pueda acceder a la última versión del producto en cuanto esté disponible:
- Si estoy creando una app Android      -> Google Play
- Si estoy creando una app iOS          -> Apple Store
- Si estoy creando un servicio web      -> Docker Hub
- Si estoy montando una librería Java   -> Artifactory, Nexus

> CD = Continuous Deployment = Despliegue continuo

Instalarle automáticamente la última versión del producto a mi cliente en cuanto esté disponible en producción.... sin mediación humana.

Y esos pipelines son acumulativos... es decir.

Me gustaría que:
  1. El desarrollador haga un COMMIT en GIT
  2. Se lanza el pipeline de CI
  3. Si el pipeline de CI termina bien, se lanza el pipeline de CDelivery
  4. Si el pipeline de CDelivery termina bien, se lanza el pipeline de CDeployment

De forma que un desarrollador hace un cambio.. y si todo va bien en 20 minutos está en producción... y de eso solo ha tenido responsabilidad el desarrollador. Otros... podrán enterarse... pero nadie más ha tenido que intervenir.


El desarrollador cuando hace commit... Cuando le da al botoncito ENTER... OSTIA TU!
Se congela el tiempo.. y su sangre!

O TIENE UNA CONFIANZA ENORME EN LO QUE ESTA HACIENDO! = PRUEBAS !

En un proyecto que tenga 1000 líneas de código... fácil puedo acabar con 10.000 líneas de código de pruebas automatizadas.

Incluso así... tengo miedo. Y.. también buscamos herramientas que nos ayuden a mitigar los riesgos.
Por ejemplo, quiero que al hacer el despliegue, se que en paralelo la versión nueva con la vieja... y que a la nueva le llegue solo el 1% de tráfico.
Si la cosa va bien... le voy subiendo el tráfico a la nueva versión y bajando el de la vieja.... hasta que desaparezca la vieja.

Una cosa a tener en cuenta es que TODO ESTO ENCAJA si uso una metodología adecuada!
Si el cliente está involucrado en el desarrollo, si el desarrollo es incremental, si las pruebas son automatizadas, etc... los riesgos de todo esto se reducen mucho.

ES UN CAMBIO DE:
- CULTURA
- PROCESOS
- HERRAMIENTAS
- ORGANIZACIÓN
- HABILIDADES
- METODOLOGÍAS
- ETC.
Y lleva su tiempo.
PERO ES EL CAMINO... Está ya marcado.

---

Supongamos que tengo a la gente mentalizada, formada, con las herramientas adecuadas, los procesos adecuados, la organización adecuada, etc.
Empieza un nuevo "proyecto"... Con proyecto no nos referimos a un sistema Completo enormimastico de esos que tardas 2 años en hacer.Un proyecto es un componentito de un sistema complejo.
Es decir.. que de esos voy a crear 300... para lo que antes era un proyecto.

Cuánto tardo en montar todo ese tinglao para ese proyecto?
- Crear el repositorio de GIT
- Crear el proyecto base ... plantilla.. de código
- Crear otro repo para las pruebas automatizadas
- Crear una plantilla de proyecto para las pruebas automatizadas
- Configurar el maven/gradle/npm
- Configurar el maven/gradle/npm para las pruebas automatizadas
- Preparar entornos de pruebas... que puede ser que necesite más de 10 cosas en cada entorno
- Preparar entornos de producción... que puede ser que necesite más de 10 cosas en cada entorno
- Preparar automatizaciones de operación de los entornos de producción
- Montar un pipeline de CI
- Montar un pipeline de CD
- Montar un pipeline de CD
... Me he llevado 1 mes... y sigo preparando cosas... sin haber empezado a desarrollar el proyecto.

Y encima si lo tengo que montar yo... lo haré a mi bola...
Y en otro proyecto lo hará otro... y lo hará a su bola...
Y en otro proyecto lo hará otro... y lo hará a su bola...

Y Esto da lugar a nuevos problemas:
- Falta de estandarización
- Falta de reutilización
- Falta de calidad
- Falta de control
- Falta de seguridad
- Tiempos enormes de arranque de nuevos proyectos

Y ahí es donde viene el concepto de INGENIERÍA DE PLATAFORMAS.
Queremos estandarizar, reutilizar, controlar, securizar, acelerar, la creación de todo lo que hay que montar para cada proyecto.

Que un desarrollador puede acceder a un catálogo de plantillas de proyectos, y desde ahí crear un nuevo proyecto... y que al hacerlo, en automático (20 minutos) tenga todo lo necesario para empezar a desarrollar.
Y al estar generado desde una plantilla, todo esté estandarizado, controlado, securizado, etc.

ES EL SIGUIENTE PASO... en esta evolución al automatizar.
Aquí estamos aún en los comienzos.
Y no hay mucha cosa... out-of-the-box.
Se están gestando... hay cositas.. pero no tan paquetizadas.

De las que más estamos usando es Backstage (Spotify).
Pero eso no me da una solución al 100%... ni al 10%.
Eso me permite montar un IDP = Internal Developer Platform
Una plataforma interna para desarrolladores.

Un portal, donde un desarrollador puede:
- Crear un nuevo proyecto desde una plantilla
- Tener una interfaz única para el seguimiento de todos sus proyectos
- Tener un sitio donde poder acudir cuando tengan que buscar información de otros proyectos
- Donde se vaya consolidando toda la documentación de cada proyecto

Pero repito: Backstage no es un IDP. Es una herramienta que me ayuda a montar un IDP.
Me lo tengo que currar.. en JS! Picando código como un bendito!
Y eso para tener el IDP.
Ahora... monta las plantillas de proyectos, los pipelines, las automatizaciones, etc. Que es lo que aporta valor.
Y que serán específico de cada organización.

FOLLON DE CURRO!
Lo que pasa es que cuando este tinglao' está montao' ... es todo una maravilla. Todo rueda solito!

Pero... montar eso, es un proyecto de varios años.

Hay cosas intermedias: Como Openshift.

Openshift es un kubernetes ultravitaminado por la gente de Red Hat.
Entre otras cosas han puesto mucho énfasis en que los desarrolladores puedan tener un AUTOSERVICIO.
Desde allí, la idea es que puedan crear sus proyectos, sus pipelines, sus entornos, etc. Mediante plantillas.
Esto está a caballo... entre lo que sería artesanal y lo que sería un IDP customizado.


---


Montemos un Microservicio. Quiero montar el microservicio de gestión de animalitos del Fermín.
(Sin perder de vista que para ese sistema, tendré otros 10-50 microservicios más)
Y que... cada uno de ellos implicará un huevo de repositorios, proyectos, entornos, etc.


---

Hay 2 piezas claves en todo este entramado:
- Cobertura de código
        ^^^^^^
- Calidad de código         <<<<<< 


----

El desarrollador puede haber creado el código que le haya venido en gana.
Y las pruebas que haya querido.

Pero.. yo desde la empresa pongo limitaciones  >  SONARQUBE
 - Audita el código del proyecto... Y LAS PRUEBAS QUE HAYA CREADO y emite un VEREDICTO:         SI / NO
     - El proyecto pasa o no a producción <.... Y lo que diga este va a misa.
 - Emite un informa de calidad del código:
   - Buenas prácticas de programación y potenciales problemas que se encuentren: SMELL CODE
   - Vulnerabilidades de seguridad encontradas en el código < Oye.. este código que has escrito es candidato a un ataque por inyección SQL
   - Potenciales problemas de seguridad en las librerías que use el proyecto
   - Este programa solicita la ejecución de las pruebas automatizadas y analiza un informe de cobertura de código
       - Qué % del código del proyecto está cubierto por pruebas automatizadas? Si el desarrollador ha escrito 800 líneas de código, pero sus pruebas al ejecutarse solo pasan por 200 líneas... el resto del código no ha sido probado.... y el código es descartado.

Cada empresa configura SonarQube a su manera.
- General : Cobertura < 90% NO
  Solo en proyectos legales : Cobertura < 70% NO


---

GIT < Workflow
      Hooks
      Pull/Request Request

COMMITs <   Es una foto completa del proyecto en un momento dado.
            Es más o menos lo mismo que hacer BOTON DERECHO en la carpeta del proyecto y hacer "Enviar a... comprimido (zip)"
            No guarda cambios... (Si era así en CVS o Subversion)

main/master ----------------------------------------------------C7-----
                                                               / < Pruebas de sistema  (Estas pruebas las monta Q&A) Pruebas de comportamiento
dev/develop/desa -------C1 -------------> C3 -----------------> C7
                         \           *1  /  \                /
        alta-de-animalito C1 ---C2 --- C3    \              /
                           \                  \            /
  recuperación-de-animalito C1 ----C4----C5----C6---------C7
                                            ^             ^
                                     Pruebas unitarias  Pruebas de integración    (Esas pruebas las monta desarrollo)


Los hooks de git son automatismos que se ejecutan en ciertos momentos del ciclo de vida de GIT.
Por ejemplo, cuando hago un COMMIT o intento copiar commits de una rama a otra, quiero que se ejecuten ciertos programas que me verifiquen que todo está bien (mvn test, sonar-scanner, etc.) y si no está bien, que no me deje hacer el COMMIT o la copia de commits.
Y eso lo configuro directamente en el repositorio de GIT... con unos scripts (de la bash) que se llaman hooks.


*1 Puede ser que yo no tenga permitida la copia de commits a esa rama (RAMA PROTEGIDA y puede que yo no tenga permisos)
   En ese escenario hago una solicitud de copia de commits (PULL REQUEST o MERGE REQUEST). Paso puramente BURROCRATICO.
   Esa deción se toma apoyada por ditintos programas:
   GITLAB/GITHUB/ETC. Me informan exactamente de los cambios concretos que hay en esos commits.
   Solicitaré a una herramienta tipo SonarQube que me analice esos cambios y me diga si son aptos o no.
   Y que me diga si se han realizado pruebas automatizadas y qué % de cobertura tienen esos cambios.

En main hay 2 reglas:
1. Nunca, bajo ningún concepto (bajo pena de cortarle al ti@ las uñas hipercortas y meterla lamano en un vaso lleno de zumo de limón) se puede hacer un COMMIT directamente.
2. Cualquier commit que hay exista se considera APTO PARA PRODUCCIÓN.

En la rama desa también hay reglas:
1. Nunca, bajo ningún concepto (bajo pena de cortarle al ti@ las uñas hipercortas y meterla lamano en un vaso lleno de zumo de limón) se puede hacer un COMMIT directamente.
2. Lo que hay en DESA se considera APTO para la siguiente versión que irá a producción.


Hoy en día ejecutamos muchas pruebas... muchos tipos de pruebas.. Y casi el 100% de ellas las podemos automatizar.
(con la gloriosa excepción de las pruebas de EXPERIENCIA DE USUARIO)

Puedo yo hacer un programa que:
    Abra un navegador: Chrome
    Le pida a ese navegador que abra la URL http://test.miaplicacion.com        SELENIUM
    Que rellene el campo del usuario con "ivan"
    Que rellene el campo de la contraseña con "1234"
    Que pulse el botón de ENTRAR
    Que espere a que se abra la siguiente página
    Que compruebe que en esa página aparece el texto "Bienvenido ivan"
    Que ahí, en el menú pulse sobre el enlace "Gestión de animalitos"
    Que espere a que se abra la siguiente página
    Que ahí pulse sobre el botón "Nuevo animalito"
    Que espere a que se abra la siguiente página
    Que ahí rellene el campo "Nombre" con "Fermín"
    Que ahí rellene el campo "Tipo" con "Perro"
    Que ahí rellene el campo "Raza" con "Pastor Alemán"
    Que ahí rellene el campo "Edad" con "3"
    Que suba una foto del animalito
    Que pulse el botón "Guardar"
    Que espere a que se abra la siguiente página
    Que compruebe que en esa página aparece el texto "El animalito ha sido creado correctamente"
    Que cierre el navegador
    Y que mire en la BBDD que efectivamente se ha creado el animalito con esos datos.

    De hecho... es habitual hoy en día utilizar lo que se llama un grid de selenium.

    Pregunta. Soy un monisterio.. un banco... el mercadona.
    Tengo mi applicación web que usan mis clientes.
    Hago pruebas desde Chrome? Aunque... no hay gente que usa Edge, Safari? Y firefox?
                            Chromium -> Chrome, Edge, Opera, Brave
                            Gecko     -> Firefox
    Y... y si usan móvil? Y si usan tablet?
    No es lo mismo usar chrome en una tablet o un movil que en un PC.... simplemente por la resolución de pantalla.
    Y si usan android o iOS?

    Pero.. de qué versión de Chrome estamos hablando? En muchas versiones de Windows .. o en Ubuntu... o en MacOS...
    
    Dónde pruebo la app? Puedo probarlo en todas las combinaciones posibles de Dispositivo/SO/NAvegador/VErsiones de todos ellos? SI
    Eso es un grid de selenium

    En la empresa montaré un grid con contenedores: PC con Edge, Firefox, Chrome en las 2 últimas versiones. para hacer el día a día de las pruebas.
    Pero antes de una subida a producción, haré una batería de pruebas en un grid comercial que me permita hacer pruebas en todas las combinaciones posibles de Dispositivo/SO/Navegador/Versiones de todos ellos.



Pipeline de CI de un proyecto como ese de los Animalitos del fermín (JENKINS)
1. Checkout del repo
2. mvn compile
3. mvn test-compile
4. mvn test        # Ejecutar las pruebas unitarias, y configuré maven para que genere informe de cobertura
5. sonar-scanner   # Analizar el código y las pruebas con SonarQube ... y le mando los informes de cobertura y pruebas
6. Y espero resultado de SonarQube
   6.1 Si es NO APTO -> Paro el pipeline y notifico al desarrollador
   6.2 Si es APTO -> Sigo
7. DOCKER-> La creación de una BBDD de verdad
8. DOCKER-> La creación de un REDIS de verdad
9. DOCKER-> La creación de un RABBITMQ/KAFKA de verdad
9. mvn verify    # Aquí puedo ejecutar pruebas de integración (que prueben la integración con otros servicios)
   9.1 Y si van mal -> Paro el pipeline y notifico al desarrollador
   9.2 Y si van bien -> Sigo
10. Publico resultados en JENKINS


Pipeline de CI2 de un proyecto como ese de los Animalitos del fermín (JENKINS) que solo se actiive cuando quieran hacer una subida a producción (MAIN)
1. Exijo que se ejecute el pipeline de CI1 y que haya terminado bien
2. Preparo entornos de pruebas serios (TERRAFORM, ANSIBLE, VAGRANT, KUBERNETES/OPENSHIFT)
3. Empaqueto la app y genero una imagen de docker (MAVEN, DOCKER)
4. Despliego la app en el entorno de pruebas (KUBERNETES/OPENSHIFT)
5. Junto con un montón de programas auxiliares (SELENIUM, JUNIT, POSTMAN, etc.) ejecuto pruebas de sistema y de aceptación (Q&A)
   5.1 Y si van mal -> Paro el pipeline y notifico al desarrollador
   5.2 Y si van bien -> Sigo
6. Con JMETER, LOCUST, etc. ejecuto pruebas de carga y rendimiento
   6.1 Y si van mal -> Paro el pipeline y notifico al desarrollador
   6.2 Y si van bien -> Sigo
7. Con ZAP, BURPSUITE, etc. ejecuto pruebas de seguridad
   7.1 Y si van mal -> Paro el pipeline y notifico al desarrollador
   7.2 Y si van bien -> Sigo
...
n. Publico resultados en JENKINS

Pipeline de CDelivery de un proyecto como ese de los Animalitos del fermín (JENKINS) que solo se actiive cuando quieran hacer una subida a producción (MAIN)
1. Exijo que se ejecute el pipeline de CI2 y que haya terminado bien
2. Esa imagen de contenedor la subo a mi artefactory 

Pipeline de CDeployment de un proyecto como ese de los Animalitos del fermín (JENKINS) que solo se actiive cuando quieran hacer una subida a producción (MAIN)
1. Exijo que se ejecute el pipeline de CDelivery y que haya terminado bien
2. Asegurar que la tengo la infra adecuada en producción (TERRAFORM, ANSIBLE) <--- Hablan lenguaje declarativo IaC = Infraestructura como código
   A lo mejor ya estaba... o había una anterior.. que hay que actualizar
3. Despliego la app en el entorno de producción
4. Lanzo pruebas de humo, para asegurar que la app arranca.
5. Si no va bien -> Rollback
6. Si va bien -> Notifico al equipo y al cliente



Si estoy preparando un despliegue para kubernetes.. la cosa cambia.
- Necesito generar la imagen de contenedor
- Necesito generar el chart de helm de kubernetes... que será un proyecto en si mismo
- Y tendré que publicar en el artefactory tanto la imagen de contenedor como el chart de helm
- Y luego usaré ese chart de helm para hacer el despliegue en pruebas y en producción

Un chart de helm es una plantilla de ficheros yaml que definen los objetos de kubernetes que necesito para desplegar mi app.


Y ahi es donde entra la INGENIERÍA DE PLATAFORMAS.
Montar plantillas de proyectos, plantillas de charts de helm, plantillas de pipelines, etc.
Para que un desarrollador pueda en 20 minutos tener todo lo necesario para empezar a desarrollar.
Apretando un botón y rellenando un formulario en un IDP = Internal Developer Platform


De esto es de lo que tiene que saber un DEVOPS/INGENIERO DE PLATAFORMAS
Ese no crea los programas en MAVEN, SELENIUM, TERRAFORM, ANSIBLE, etc.
Pero si tiene que saber como funcionan esas herramientas, para poder crear las plantillas, los pipelines.
Y eso en si es un trabajón

---

# INFRAESTRUCTURA !

Infraestructura clásica:
    On Premise
    - Virtualización: VMWare, Hyper-V, KVM
    - Almacenamiento: NAS, SAN
    - Redes: Cisco, Juniper, etc.
    - Backup: Veeam, etc.
    en un Cloud:
    - AWS
    - Azure
    - Google Cloud
    - Oracle Cloud
    - IBM Cloud
    - Alibaba Cloud
    - etc.

    Al final, sigo teniendo:
    - Máquinas físicas o virtuales
    - Redes
    - Almacenamiento
    - Firewalls
    - Balanceadores de carga
    - Proxy inversos
    - VIPAs
    - DNS

Kubernetes
    No hablamos de:
    - Máquinas físicas o virtuales                  PODs
    - Redes                                        
    - Almacenamiento                                PersistentVolumeClaims
    - Firewalls                                     Network Policies
    - Balanceadores de carga                        Services
    - Proxy inversos                                Ingress Controllers
    - VIPAs                            
    - DNS                                           Route


En cualquier de los 2 caso, querremos automatizar su creación, actualización y desmantelamiento. 

    IaC <- Infrastructure as Code (Lenguaje declarativo)
        - Terraform                                 HCL (puramente declarativo)
        - AWS CloudFormation
        - Ansible                                   Playbooks YAML (Los módulos usan lenguaje declarativo, pero los playbooks en si son lenguaje imperativo)
        - Helm y sus charts para Kubernetes         Los archivos de manifesto son YAML (lenguaje declarativo)... Las plantillas de charts son lenguaje imperativo 
  
# IaC?

No es sólo que vayamos a definir la infra en un código.
Es que la voy a tratar como código.

La infra es un proyecto en si mismo.. y va sujeta a control de versiones, pruebas, despliegues, etc.
No es solo que la defina en código, le voy a dar el mismo tratamiento que a un proyecto de software.

Nosotros queremos tener versiones de la infra... y esas versiones normalmente irán asociadas a versiones de los proyectos que van a correr sobre esa infra.

Desplegará la app versión 1.0.0 sobre la infra versión 1.0.0
Desplegará la app versión 1.0.1 sobre la infra versión 1.0.0
Desplegará la app versión 1.0.1 sobre la infra versión 1.0.1
Desplegará la app versión 2.0.0 sobre la infra versión 2.0.0

Imaginad que tengo una app en versión 1.1.0
Y ahora quiero que use un REDIS como cache!
Podría correrla en la misma infra que tenía? NO -> Generaré la versión 2.0.0 de la app.
Esa app estaba funcionando en la versión 1.0.17 de la infra. -> Necesito pasar a la versión 1.1.0 de la infra (donde meto un redis)
                                             ^^
                                             Parche de SO

---

version a.b.c <- ESQUEMA SEMVER- Esquema semántico de versionado


                Cuándo los incremento?
    a. MAJOR    Breakin changes. Cuando hago cambios que rompen la compatibilidad con versiones anteriores
    b. MINOR    Nueva funcionalidad
                Cuando marcamos una funcionalidad como "obsoleta" (deprecated)
    c. PATCH    Bugfix. Cuando arreglamos algo que está jodiendo

---

# Lenguaje declarativo ?

Es un paradigma de programación. Programación imperativa, programación Orienta a Objetos... eso son otros paradigmas de programación.

Un paradigma es solo un nombre hortera que los desarrolladores damos a las formas de usar un lenguaje de programación.
Pero no es algo exclusivo de los lenguajes de programación. En los lenguajes naturales (los que usamos para hablar) también hay "paradigmas".

> Felipe, if (si) hay algo que no sea una silla debajo de la ventana:  CONDICIONAL
>   Quítalo IMPERATIVO
> Felipe IF not silla debajo de la ventana: CONDICIONAL
    > Felipe if silla == False GOTO IKEA!
    > Felipe, pon una silla debajo de la ventana. IMPERATIVO

Estamos muy acostumbrados a lenguaje imperativo. Pero es una mierda! y cada día lo odiamos más.
El lenguaje imperativo no hace olvidar nuestro objetivo... nos hace centrarnos en cómo conseguir ese objetivo.

> YO QUIERO Tener una silla debajo de la ventana. DESIDERATIVO

> Felipe, debajo de la ventana tiene que haber una silla. Felipe, Es tu responsabilidad conseguirlo. DECLARATIVO

No le estoy dando una orden. Simplemente le digo lo que espero, lo que quiero, lo que es.
Al usar lenguaje declarativo, me olvido del cómo conseguirlo.. ya que eso lo he delegado a Felipe.
Yo quiero que al final me diga: LISTO o NO LISTO

Adoramos el lenguaje declarativo... por su simplicidad, claridad, facilidad de mantenimiento, etc.

Kubernetes habla lenguaje declarativo.
Terraform habla lenguaje declarativo.
Los módulos de Ansible hablan lenguaje declarativo (si al que lo ha creado le ha dado la gana...el 90% lo hace)
    Pero los playbooks que montamos son puritos lenguaje imperativo.

El lenguaje declarativo tiene además una característica. POR DEFINICIÓN ME OFRECE IDEMPOTENCIA.

# Idempotencia ?

Idempotencia es una propiedad matemática. 
Una operación es idempotente si al aplicarla varias veces, el resultado es el mismo que si la aplico una sola vez.

 multiplicar un número por 1.. es idempotente? SI
 3x1=3
 3x1x1x1x1x1x1=3

En este contexto significa que da igual es estado inicial en el que esté la infra.... cuando aplico el código de la infra... si uso un lenguaje idempotente... el resultado final será siempre el mismo.


> Felipe, pon una silla debajo de la ventana. IMPERATIVO

Estado inicial                              Estado final?
Tengo una ventana sin nada debajo           Con una silla debajo de la ventana
Tengo una ventana con una mesa debajo       ERROR?
Tengo una ventana con una silla debajo      ERROR?
Si no tengo silla disponible                ERROR?                           

Y tengo que hacer yo lo que pueda por conseguir esa idempotencia.

> Felipe, if (si) hay algo que no sea una silla debajo de la ventana:  CONDICIONAL
>   Quítalo IMPERATIVO
> Felipe IF not silla debajo de la ventana: CONDICIONAL
    > Felipe if silla == False GOTO IKEA!
    > Felipe, pon una silla debajo de la ventana. IMPERATIVO

Estado inicial                              Estado final?
Tengo una ventana sin nada debajo           Con una silla debajo de la ventana
Tengo una ventana con una mesa debajo       Con una silla debajo de la ventana
Tengo una ventana con una silla debajo      Con una silla debajo de la ventana
Si no tengo silla disponible                Con una silla debajo de la ventana

> Felipe, debajo de la ventana tiene que haber una silla. Felipe, Es tu responsabilidad conseguirlo. DECLARATIVO

Estado inicial                             Estado final?                           Qué hace Felipe?
Tengo una ventana sin nada debajo          Con una silla debajo de la ventana      Felipe pone una silla debajo de la ventana
Tengo una ventana con una mesa debajo      Con una silla debajo de la ventana      Felipe quita la mesa y pone una silla debajo de la ventana
Tengo una ventana con una silla debajo     Con una silla debajo de la ventana      Felipe no hace nada
Si no tengo silla disponible               Con una silla debajo de la ventana      Felipe va a IKEA, compra una silla y la pone debajo de la ventana


En terraform DECLARO en un fichero una infraestructura.
    Quiero un servidor con estas características: RAM=8GB, CPU=4, DISCO=100GB, SO=Ubuntu 22.04
    Quiero una RED con estas características:     CIDR=10.0.0.0/24
    Quiero el servidor pinchao a la red a través del puerto eth0
    Quiero tener otros 3 servidores con estas características: RAM=16GB, CPU=8, DISCO=500GB, SO=Ubuntu 22.04
    Quiero que esos servidores estén pinchados a la red a través del puerto eth0
    Quiero un balanceador de carga con estas características: Tipo=Publico, IP=Pública, que balancee entre esos 3 servidores
     

En Kubernetes DECLARO en un fichero una "infraestructura" (de otro tipo.. no clásica... pero infraestructura+Comportamiento acerca de su operación).

    Quiero un pod con estas características: RAM=8GB, CPU=4, DISCO=100GB, IMAGEN=miapp:1.0.0
    Quiero otros 3 pods con estas características: RAM=16GB, CPU=8, DISCO=500GB, IMAGEN=miapp:1.0.0
    Quiero un servicio que balancee entre esos 3 pods

        Si pasa del 50% el uso de CPU quiero que pueda haber hasta 10 pods.. y nunca menos de 3
        Quiero que el puerto 80 del primero pod sea chequeado cada 5 segundos. y si 3 veces no contesta quiero que el pod sea reiniciado

Esas infraestructuras las aplico.
Si tengo un script de terraform:            $ terraform apply                  # Este comando le ejecuto sobre la carpeta (una carpeta es un script de terraform)
Si tengo un fichero de manifiesto de k8s:   $ kubectl apply -f miapp.yaml

Y ya es problema de terraform o kubernetes el conseguir que el estado final sea el que he declarado.
Si el estado deseado es el mismo que el estado actual... no hacen nada.
Si no tengo nada de partida... crearán todo lo necesario.
Si tengo algo de partida... lo adaptarán a lo que he declarado en este fichero.

Solo tengo que mantener actualizados mis ficheros de declaración de infraestructuras.
Y aplicaré la versión de la infra que necesite en cada momento.

Esos ficheros incluso admiten parametrización.
- Terraform, con su lenguaje la admite de forma nativa (HashCorpLanguage)
- Kubernetes, no la admite de forma nativa parametrización. Eso es lo que ofrece una herramienta llamada HELM.
    Me permite crear plantillas de infraestructuras de k8s (lenguaje llamado mustache). Esas plantillas se llaman Charts de Helm.
    Le pido a helm que genere mediante una de esas plantillas un fichero de manifiesto de k8s, pasándole unos parámetros.

Eso me permite poder aplicar variantes de la misma versión de la infra:
- Entorno producción
    - 4 servidores
    - Balanceador de carga público
- Entorno pruebas
    - 2 servidores
    - Balanceador de carga interno
- Entorno desarrollo
    - 1 servidor
    - Sin balanceador de carga

Y quizás tengo como parametros:
    - Número de servidores
    (Si numero de servidores > 1) -> Creo un balanceador de carga (en automático)

No obstante, terraform, aunque se usa principalmente para provisionar infraestructuras clásicas (on prem o en cloud) también puede usarse para provisionar infraestructuras en kubernetes... aunque es poco habitual.

Ansible también me permite provisionar infraestructuras clásicas (on prem o en cloud) y en kubernetes... aunque es poco habitual.... Solemos usa Ansible no para provisionar infraestructuras... sino para planchar esas infraestructuras (terminar de configurarlas para que estén listas para que corran las apps):
- Crea usuarios
- Abre puertos en firewalls
- Instala software


Todas ellas son herramientas muy genéricas... que operan mediante PLUGINS...
Aunque cada una llama a esos plugins de una forma diferente:
- Terraform: Providers
- Ansible: Módulos
- Kubernetes: Operadores

PIPELINES DE DI/CD
Jenkins               1.  Montaré un programa (Script) Terraform que genere/aprovione la infra que necesito 
                            <- IPs
                            <- Password
                      2.  Playbook que genere un nuevo pasword para el usuario root en cada servidor
                          y se guarde en un vault securizado
                            <- ID del vault
                      3.  Acto seguido montaré un programa (Playbook) Ansible que planche esa infra -> IPs , ID del vault
                      4.  Montaré otro playbook Ansible que instale la app en esa infra -> IPs , ID del vault
 

Antiguamente, como los que montábamos esto no sabñiamos mocho de desarrollo... hacíamos unas cacicadas... (Joder que somos sysadmins). Por ejemplo:
    1. Montaré un programa (Script) Terraform que genere/aprovione la infra que necesito 
       y que ese programa llame a un playbook Ansible que planche esa infra

       = CAGADA !!!! = Tengo un sistema MONOLITICO! -> Sistema con componentes desacoplados = GUAY


BackStage -> IDP = Internal Developer Platform (Portal)
    En ese portal puedo montar plantillas de tipos de proyectos.
    Lo que haré con Backstage es generar un nuevo proyecto (repositorio de GIT) a partir de una plantilla.
    Y esa plantilla incluirá un pipeline de Jenkiuns (Jenkinsfile) que hará todo lo necesario para ese proyecto.
    Cuando con Backstage genere un nuevo proyecto, acaberé con:
    - Un repositorio de GIT con el código base del proyecto
    - Dentro de ese repositorio, también tendré un pipeline de Jenkins, que ya no tengo que montar yo.. Me viene montadito en automático por Backstage.
    - De hecho no lo ha creado backstage... Viene en la plantilla.. que la he creado yo a manita.
    - El BackStage si acaso habrá cambiado 4 parametros en ese Jenkinsfile... que me ha pedido en un formulario.
      - FORMULARIO PARA MONTAR MICROSERVICIO USANDO JAVA - SPRING
        - Parámetros: Nombre del microservicio
        - Versión de Java
        - Versión de Spring
    - Además de esto, BackStage mediante Plugins (Módulos) puede hablar con Jenkins para ver qué tal han ido los pipelines de nuevo proyectos.
    - Y me pondrá una panmtalla dentro del portal, para ver el estado de todos mis proyectos en jenkins,... sin necesidad de entrar en jenkins.
    - Y También le preguntará a sonarQube, para ver el estado de calidad de todos mis proyectos... sin necesidad de entrar en sonarQube.

    Tendré en Backstage un Scaffold (plantilla) para crear microservicios con Java-Spring
    Y en esa plantilla tendré un archivo POM.XML de Maven


    Un pipeline de Jenkins se define en un fichero llamado Jenkinsfile
    Que se guarda en un repositorio de GIT, junto con el código del proyecto.


    Backstage me permite generar proyectos nuevos desde un catálogo de plantillas (scaffolds)
    Por otro lado me sirve de portal único para que un desarrollador pueda ver todo lo que necesite con respecto a sus proyectos.
        Eso me ofrece una curva de aprendizaje mucho más suave para los desarrolladores nuevos... son muchas cosas.


---

# Kubernetes

Es una herramienta para automatizar la creación y operación de entornos de producción basados en contenedores.

Programas que se ejecutan en entornos/MV/Máquinas físicas/Contenedor

Y como tengo necesidad de HA, muchas veces uso clusters.
Y en cuanto uso un cluster (Activo-Pasivo o Activo-Activo) necesito un balanceador de carga delante.


                                    Servidor DNS (Entrada para mi app) (miapp.com -> IP Proxy Reverso)
                                           
Servidor Backend                                                                                    Lado del cliente  
--------------------------------------------------------------------------------------------    ---------------------------------
                        Maquina 1
                           Wordpress4    <
                        Máquina 2
                           Wordpress1    <
   MariaDB1  <   BC    <   Wordpress2    <    Balanceador de carga    <     Proxy reverso       <      Proxy     <      Clientes (http://miapp.com)
   MariaDB2  <             Wordpress3    <                                         ^^^
                                                                              Reglas de redirección
     Volumen LUN MariaDB1  \ iSCSI.  1 por servidor                             miapp.com -> IP del Balanceador de carga
     Volumen LUN MariaDB2  /
     Volumen Wordpress     - NFS.    1 común
    Cabina de almacenamiento SAN/NAS


      Los Marias DB solo pueden ser accedidos por los Wordpress
      Los Wordpress solo pueden ser accedidos por el Balanceador de carga
      El Balanceador de carga solo puede ser accedido por el Proxy Reverso

En Kubernetes cambia la terminología:
 Volumenes en las cabinas: Persistent Volumes (PV) y Persistent Volume Claims (PVC)
 Reglas de proxy inverso:  Ingress
 Balanceador de carga:     Service 
 Entrada en DNS:           Route (en Openshift)
 Máquinas:                 Nodes
 Servidor Backend:         Pod
 Cluster de Pods:          Deployment
 Reglas de firewall:       Network Policies
