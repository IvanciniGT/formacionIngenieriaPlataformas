

# Desarrollo de plantillas

- Plantilla para la creación de una BBDD en el Oracle corporativo
     Parámetros:
        Nombre de la BBDD
        Nombre del usuario administrador
        Tamaño de la BBDD
        Politica de Backups

     Tareas:
        Crear un repo en git con:
            - Un archivo SQL con la estructura de la BBDD
            - Archivos de documentación con ejemplos de cómo documentar la estructura de la BBDD
            - Una carpeta donde poder dejar scripts de cargas de datos iniciales
              - Con ejemplos
            - Una carpeta para ir metiendo actualizaciones de la estructura de la BBDD
              - Con ejemplos
            - Una carpeta para escribir scripts para verificar si la BBDD está bien
              - Con ejemplos
            - JenkinsFile para que Jenkins pueda ejecutar el pipeline de creación de la BBDD / o para editarla
                    ^ Que se esté revisando el repositorio cada hora... y que si hay cambios se apliquen en automático    
            - JenkinsFile para que Jenkins pueda desmantelar la BBDD
            - En el archivo del componente (catalog-info.yaml) Enlaces a los pipelines de Jenkins.. para la actualización o para el desmantelamiento
            - Y en ese archivo con una anotación configuro que se genere la documentación automática de la BBDD (con Backstage TechDocs)
            - Y en ese archivo configuro con una anotación que se muestre en la pestaña de CI/CD las ejecuciones de los pipelines de Jenkins
              
        Registrar los pipelines en Jenkins (Los Jenkinsfiles)... y necesito el plugin para Backstage de Jenkins
        
        Registrar el componente en Backstage

        Le saco como final:
        - Enlace a Jenkins
        - Enlace al repositorio de git
        - Enlace a la documentación de la BBDD (TechDocs)
        - Enlace al componente en Backstage (para que se vea en el catálogo de componentes)
        - Enlaces al Hashicorp Vault (donde estarán las contraseñas de las BBDD)

    Ya lo que me quiera liar con los pipelines de Jenkins y con el proyecto. 
    Lo primero sería crear una contraseña segura... De hecho 2, una para PRE y otra para PRO.
        Y guardarlas en un Hashicorp Vault
        Inicialmente se ejecuta un pipeline para crear la BBDD... seguido de los scripts de carga de datos iniciales y de la verificación de que la BBDD está bien... EN 2 ENTORNOS: PRE Y PRO
        Luego, cuando quiera hacer cambios en la estructura de la BBDD:
            - Aplicar el cambio a la BBDD de PRE
            - Ejecutar los scripts de verificación de que la BBDD está bien
            - Antes, hago un backup y pongo la BBDD en modo mantenimiento
            - Si ha quedado bien aplicar el cambio a la BBDD de PRO
            - Ejecutar los scripts de verificación de que la BBDD está bien
            - Si ha quedado bien
            - Si ha quedado mal, restauro el backup
            - quito el modo mantenimiento