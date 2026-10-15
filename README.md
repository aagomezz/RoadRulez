# 🚐 RoadRulez

Conoce la normativa municipal y viaja con mayor tranquilidad.

RoadRulez es una aplicación gratuita para Android diseñada para ayudar a las personas que viajan en autocaravana, caravana o camper a conocer la normativa municipal relacionada con la pernocta en España.

El objetivo del proyecto es facilitar el acceso a información sobre las restricciones municipales y ayudar a los viajeros a tomar decisiones informadas, reduciendo el riesgo de posibles sanciones por desconocimiento de la normativa local.

# 📌 Características principales
🗺️ Localización municipal: identifica el municipio en el que se encuentra el usuario.
🌐 Geolocalización online: utiliza la API de Nominatim para obtener información sobre la ubicación actual.
📍 Localización sin conexión: incorpora un algoritmo del vecino más cercano para estimar el municipio a partir de su proximidad a las geocercas municipales.
🔄 Sincronización de datos: actualiza la base de datos local a partir de un archivo JSON alojado en un repositorio público.
📱 Uso gratuito y sin anuncios: la aplicación está concebida para ofrecer una experiencia accesible y sin publicidad.
📖 Descripción del proyecto

RoadRulez nace como un proyecto personal con el propósito de desarrollar una herramienta útil para la comunidad de viajeros en vehículos vivienda.

La normativa que regula la pernocta puede variar entre municipios, lo que dificulta conocer las restricciones aplicables en cada lugar. Por ello, la aplicación busca centralizar la información disponible y facilitar su consulta desde un dispositivo Android.

Además de su utilidad práctica, el proyecto constituye una oportunidad para aprender y aplicar conceptos de desarrollo móvil, persistencia de datos, consumo de API REST, sincronización de información y geolocalización.

# 🛠️ Tecnologías y metodología

El proyecto utiliza Java como lenguaje de programación y Spring Boot como framework para las funcionalidades desarrolladas con esta tecnología.

La arquitectura se organiza en diferentes componentes, separando las responsabilidades relacionadas con la gestión de datos, la localización y la interfaz de usuario.

Gestión de datos

La aplicación dispone de una base de datos local para almacenar la información municipal y permitir su consulta sin depender continuamente de una conexión a Internet.

La gestión de los datos se organiza mediante componentes específicos:

Modelos de datos: representan la información de los municipios.
DAO (Data Access Object): gestionan el acceso y las operaciones sobre la base de datos local.
Sincronización: obtiene los datos de la fuente externa y actualiza la información almacenada en el dispositivo.

La fuente de datos externa consiste en un archivo JSON alojado en el siguiente repositorio:

[🔗 RoadRulez_Data — Repositorio de datos](https://github.com/LaliCuadora/RoadRulez_Data)

Se ha elegido esta solución para mantener los costes de infraestructura reducidos, ya que RoadRulez es un proyecto gratuito y sin anuncios. De esta manera, se evita depender inicialmente de un servidor propio para distribuir los datos.

### Sincronización de la base de datos

La sincronización se ejecuta durante el proceso de inicialización de la aplicación, mediante el método onCreate() correspondiente al componente encargado de esta tarea.

Esta estrategia parte de la idea de que los cambios en la normativa municipal no suelen requerir una actualización continua a intervalos de pocas horas. No obstante, la frecuencia real de los cambios puede variar según el municipio.

Como posible mejora futura, se contempla incorporar una opción en el menú principal que permita al usuario comprobar manualmente si existen actualizaciones disponibles.

También se considera la posibilidad de evolucionar hacia una infraestructura propia para gestionar la distribución y actualización de los datos, incorporando medidas de seguridad adicionales cuando resulte necesario.

### Geolocalización online y offline

RoadRulez contempla dos mecanismos complementarios para determinar el municipio en el que se encuentra el usuario.

1. Geolocalización online

Cuando existe conexión a Internet, la aplicación utiliza la API de Nominatim para obtener información geográfica a partir de la ubicación disponible.

Este método permite identificar el municipio mediante un servicio de geocodificación inversa, aunque su precisión depende de la ubicación proporcionada y de los datos cartográficos disponibles.


2. Geolocalización offline

Cuando no hay conexión a Internet, la aplicación recurre a un algoritmo basado en el vecino más cercano.

Este algoritmo compara la posición del usuario con las geocercas municipales disponibles localmente para estimar el municipio más próximo.

Al tratarse de una aproximación, su resultado puede ser menos preciso que el obtenido mediante el servicio online. Por ello, la aplicación informa al usuario de que está utilizando este método y recomienda comprobar el municipio identificado antes de consultar su normativa.

# 📂 Estructura del proyecto

El código fuente se organiza en tres directorios principales dentro de app/:

app/

├── data/

├── Geofencing/

└── UI/

### data/

Contiene los componentes relacionados con la gestión de la información, los modelos de datos, el acceso a la base de datos local y la sincronización con la fuente externa.

### Geofencing/

Agrupa la lógica relacionada con la localización municipal sin conexión. Utiliza las geocercas disponibles y un algoritmo del vecino más cercano para estimar el municipio correspondiente a la posición del usuario.

### UI/

Contiene los elementos de la interfaz de usuario, incluyendo las pantallas principales, las ventanas emergentes y las notificaciones.

Esta separación facilita el mantenimiento del código y permite desarrollar cada área de la aplicación de forma más organizada.

# 📥 Descarga

RoadRulez está disponible para Android a través de Google Play.

Precio: gratuita.

Publicidad: sin anuncios.

# 👨‍💻 Acerca del autor

RoadRulez es un proyecto desarrollado de manera independiente por un estudiante de Ingeniería Informática de la Universidad de Granada.

Nace con la intención de aprender cómo se desarrolla una aplicación desde cero, desde el diseño de su arquitectura hasta la implementación de funcionalidades reales, la gestión de datos y la experiencia de usuario.

El proyecto combina el aprendizaje técnico con el desarrollo de una herramienta que busca aportar valor a la comunidad de personas que viajan en vehículos vivienda.

# ⚖️ Aviso legal

RoadRulez es un proyecto independiente y no está afiliado, respaldado ni avalado por ningún organismo gubernamental ni ayuntamiento.

La información proporcionada por la aplicación tiene carácter orientativo y no constituye asesoramiento jurídico ni garantiza que una determinada conducta esté permitida en un municipio concreto.

La normativa puede cambiar con el tiempo y su aplicación depende de las disposiciones vigentes y de las circunstancias específicas de cada lugar. Por este motivo, se recomienda consultar las ordenanzas municipales y las fuentes oficiales correspondientes antes de pernoctar.

El uso de RoadRulez no exime al usuario de su responsabilidad de conocer y cumplir la normativa aplicable.
