# Plataforma para cursos en línea
###### Este sistema fue seleccionado ya que muchos estudiantes buscan adquirir conocimientos sobre temas de su interés. La plataforma facilita la gestión, visualización y seguimiento del aprendizaje. Además, permite a los alumnos acceder a cursos desde cualquier lugar, encontrar contenido educativo relevante y monitorear su progreso de manera continua. Por otro lado, permite a los docentes crear y gestionar cursos de manera sencilla, incorporando contenido multimedia y otros recursos según consideren necesario. Por último, ofrece a los administradores las herramientas necesarias para gestionar usuarios, cursos y certificaciones desde un único lugar. En conclusión, este sistema de cursos en línea proporciona una solución para el aprendizaje digital, garantizando que estudiantes, docentes y administradores dispongan de las herramientas necesarias para brindar y obtener una experiencia educativa accesible e iterativa, actualizándose con el tiempo.

##Instrucciones para ejecutar y compilar el proyecto
####Requisitos previos
- Tener instalado **Java Development Kit (JDK) de versión 8 o superior.**
- Contar con un entorno de desarrollo que pueda compilar y ejecutar Java (en este caso, IntellIJ IDEA).

####Pasos para ejecutar el proyecto
- Clonar o descargar el repositorio en una máquina local.
- Abrir el proyecto en **IntellIJ IDEA**.
- Ir a la clase denominada **Main** para correr el programa.
- Ejecutar el programa.

##Explicación de la estructura de paquetes y relación entre clases
###Relaciones entre clases
####Clase Persona
- Es la superclase de **Estudiante** y **Maestro**.
- Contiene los atributos **id**, **nombres**, **apellidos** y **correos**.
#####Relaciones
- **Estudiante** y **Maestro** heredan de persona.

####Clase Estudiante
- Representa un estudiante en la plataforma.
- Atributos adicionales: **contrasenya, fechaInicioSuscripcion, progresoCursoEstudiante, historialCursos**.
#####Relaciones
- Hereda de **Persona**.
- Interactua con **Curso** a través de **historialCursos**.
- Interactua con **registroPruebas** a través de **idEstudiante**.

####Clase Maestro
- Representa a un maestro en la plataforma.
- Atributos adicionales: **contrasenya, puntuacionMaestro, biografiaMaestro, especialidadMaestro, fechaRegistroMaestro, cursos**.
#####Relaciones
- Hereda de **Persona**.
- Interactua con **Curso** a través de **cursos**.

####Clase Curso
- Representa a un curso en la plataforma.
- Contiene estos atributos: **idCurso, idMaestro, nombreCurso, duracionCurso, precioCurso, cantidadCalificaciones, promedioCalificaciones, cantidadVisualizaciones, cantidadVideos, certificados, categoriaCurso, fechaPublicacion, requisitosCurso, numerosInscritos, estadoCurso, materialExtras**.
#####Relaciones
- Relacionado con **Maestro** a través de **idMaestro**.
- Relacionado con **Estudiante** a través de **historialCursos**.
- Relacionado con **MaterialExtra** a través de **materialExtras**.
- Relacionado con **RegistroPruebas** a través de **idCurso**.

####Clase MaterialExtra
- Representa materiales adicionales relacionados a un curso.
- Contiene estos atributos: **idCurso, fomatoArchivoMaterialExtra, fechaPublicacion**.
#####Relaciones
- Relacionado con **Curso** a través de **idCurso**.

####Clase RegistroPruebas
- Representa el registro de las pruebas realizadas por los estudiantes.
- Contiene estos atributos: **RegistroPrueba, idEstudiante, idCurso, tipoPrueba, notaObtenida, fechaEvaluacion, intentosPrueba, estadoPrueba**.
#####Relaciones
- Relacionado con **Estudiante** a través de **idEstudiante**.
- Relacionado con **Curso** a través de **idCurso**.

####Clase Foro
- Representa un foro de discusión relacionado a un curso.
- Contiene estos atributos: **idForo, idCurso, idUsuarioCreadorForo, temaForo, descripcionForo, fechaCreacionForo, estadoForo**.
#####Relaciones
- Relacionado con **Curso** a través de **idCurso**.
- Relacionado con **Estudiante**  o **Maestro** a través de **idUsuarioCreadorForo**.

####Clase Plataforma
- Representa la plataforma de cursos en línea.
- Contiene estos atributos: **planEstudio, metodoPago, configuracionesPrivacidad**.
#####Relaciones
- Gestiona **Curso, Estudiante, Maestro, Foro, MaterialExtra** y **RegistroPruebas**.

####Enumeraciones
- PlanEstudios: Define todos los tipos de planes de estudio relacionados con las suscripciones **cuentaEstandar, cuentaPro**.

- ConfirguracionDePrivacidad: Define los niveles de privacidad de las cuentas **público, privado, soloAmigos, soloMaestros**.

- MetodosPagos: Define los métodos de pago aceptados para la plataforma **MasterCard, Visa, PayPal**.

###Estructura de los paquetes
####Paquete SistemaProyecto
- Es el paquete principal del proyecto, el **núcleo** que hace que todo funcione correctamente y que contiene todas las clases y subpaquetes.

####Paquete modelos
- Contiene todas las clases que representan las entidades relacionadas en el sistema.
#####Subpaquete enums
- Contiene ciertas enumeraciones que definen valores fijos para ciertos atributos.

####Paquete servicios
- Contiene las clases que implementan la lógica del negocio del sistema, las que gestionan las operaciones principales.

####Paquete controladores
- Contiene las clases que manejan la interacción con el usuario.

####Paquete vistas
- Contiene las clases que manejan como se presenta la información al usuario, la interfaz UI.

##Funcionalidades implementadas
### Registro e inicio de sesión
- Permite a los usuarios registrarse e iniciar sesión.

### Gestión de cursos
- Permite crear, editar y eliminar cursos.

### Gestión de materiales extras
- Permite agregar materiales adicionales a los cursos.

### Gestión de pruebas y calificaciones
- Permite crear pruebas y asignar calificaciones.

### Gestión de Foros
- Permite la creación y participación en foros de discusión..

### Visualización de progreso
- Muestra el progreso de los estudiantes en los cursos.

### Gestión de métodos de pago
- Permite a los estudiantes pagar por los cursos por medio de diferentes métodos de pago.

### Gestión de privacidad
- Permite configurar el nivel de privacidad de los usuarios.

### Generación de reportes
- Permite a los administradores generar reportes y estadísticas.

### Interfaz de usuario (UI o vistas)
- Proporciona la interfaz para que los usuarios interactúen con la plataforma.

##Autores del proyecto
- **José Aviles** ~ (20245984)
- **Kevin Luna** ~ (20245109)
- **Samuel Merino** ~ (20245356)
- **Sheyla Sarmiento** ~ (20245414)
- **René Serrano** ~ (20245492)

##Extras
###Objetos/ Entidades involucradas en la plataforma de cursos en línea
#####- Plataforma ↓
Gestiona la configuración general, guarda métodos de pago y los ajustes de privacidad de los usuarios.
#####- Estudiantes ↓
Usuarios que acceden a los cursos y monitorean su progreso.
#####- Maestros ↓ 
Usuarios que crean y gestionan cursos.
#####- Cursos ↓ 
Contenido educativo ofrecido en la plataforma.
#####- Registro de pruebas ↓
Almacena las calificaciones e intentos de los estudiantes en las evaluaciones por curso.
#####- Foros ↓
Espacios de discusión relacionados con los cursos y su contenido.
#####- Material extra ↓
Recursos adicionales proporcionados por los maestros para cada curso.

##Acciones principales para cada tipo de usuario.

####-Estudiante
#####> Registro y autenticación
- Puede registrarse
- Puede iniciar y cerrar sesión.

#####> Gestión de suscripción
- Puede ver su fecha de inicio y final de su suscripción.

#####> Exploración y monitoreo de cursos
- Puede buscar cursos por categorías o palabras clave.
- Puede ver los cursos disponibles con sus detalles respectivos.
- Puede acceder y registrarse en un curso.
- Puede ver los cursos que tiene inscritos y en progreso.
- Su progreso en el curso puede actualizarse y puede obtenerlo para saber cómo va.

#####> Material extra y pruebas por curso
- Puede acceder y ver el material extra del curso que lleva.
- Puede acceder y realizar pruebas del curso, ver cuáles ha hecho y sus calificaciones para cada una.

#####> Certificados
- Puede obtener y descargar certificados al haber aprobado cursos de manera exitosa.

#####> Foros
- Puede entrar a foros vigentes para comentarlos y a foros ya cerrados para verlos.


####- Maestros
#####> Registro y autenticación
- Puede registrarse, postularse, iniciar y cerrar sesión.

#####> Gestión de perfil
- Puede actualizar y ver su perfil.

#####>Creación y gestión de cursos
- Puede crear, modificar y eliminar cursos.
- Puede definir los detalles de cada curso.
- Puede ver la lista de estudiantes por cada curso en el que está asignado.

#####>Material extra y pruebas por curso
- Puede ver y agregar material extra al curso.
- Puede crear pruebas para los cursos y asignar calificaciones.
- Puede ver los intentos restantes de los estudiantes para cada prueba asignada.

#####> Foros
- Puede crear, entrar, moderar y responder a foros vigentes. 
- Puede solo ver foros ya cerrados.

##Gracias por llegar hasta aqui ;)
