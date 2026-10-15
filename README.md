# RoadRulez

Una aplicación para saber donde pernoctar 

# Descripcion

RoadRulez es una aplicación creada por iniciativa propia que tiene como objetivo ayudar a toda la gente que viaja en autocaravana, caravana, camper, etc por toda España y está cansada de exponerse a multas debido a que no conocen la normativa municipal.

# Métodología utilizada

Esta aplicación utiliza como lenguaje Java haciendo uso de Spring Boot como framework para así poder crear la aplicación de manera más rapida y sencilla. En cuanto a la estructura del código se optó por crear distintas clases para poder almacenar los municipios, gestionar la base de datos local (DAO) y sincronizar dicha base con la base de datos externa. En cuanto a la base de datos esta aplicación utiliza una sincronización que se realiza al ejecutar el método onCreate(), es decir, al iniciar la aplicación. Se escogió esta idea debido a que a la hora de actualizar la base de datos lo normal será que las leyes cambien en un tiempo determinado mayor a un día. No obstante, se baraja a opción de agregar una opción en el menú principal con el objetivo de que el propio usuario pueda realizar dicha comprobación por su cuenta. La base de datos externa está formada por un archivo JSON ubicado en un directorio público (https://github.com/LaliCuadora/RoadRulez_Data). Se optó por esta medida debido al presupuesto ajustado ya que la aplicación es gratis y sin anuncios por lo que no se obtendrá ningún beneficio con el que poder mantener dichos servidores aunque no se descarta implementar dicha medida en un futuro junto a una conexión ssh para evitar ataques MitM (Man in the middle). En cuanto a la gestión de la ubicación, se ha creado un método con el objetivo de poder obtener el municipio actual a través de Nominatim API con la que si el usuario tiene internet la ubicación será precisa. Para poder extender la usabilidad del programa se añadió además una geolocalización basandose en el algoritmo del vecino más cercano con el objetivo de conocer de manera aproximada el municipio actual mediante su cercanía al geofencer de dicho municipio. En este caso se informa al usuario de que no se tiene conexión y que se está utilizando una búsqueda del municipio mucho menos precisa incitándole a verificar correctamente el municipio en el que se encuentra.

# Estructura de la aplicación

La aplicación cuenta con una estructura formada por 3 directorios principales:
        
### app: 

Almacena todo el código fuente de la aplicación y su estructura se basa a su vez en 3 directorios:

### data 

Utilizado para toda la gestión de la información y base de datos

### Geofencing

Gestiona el cambio de municipios asignando un diámetro establecido para poder ubicar el municipio en el caso de que no haya conexión

### UI

Apartado visual de la aplicación tanto para las propias interfaces como el diseño del as ventanas emergentes y notificaciones


# Descargas

Esta disponible en android (PlayStore) y es completamente gratuita y SIN anuncios

# Acerca del autor

Esta aplicación ha sido creada por un estudiante en Ingeniería informática de la Universidad de Granada por cuenta propia con el objetivo de aprender como funciona realmente el desarrollo de una aplicación desde cero. 


# Legal

Esta aplicación no tiene ningún respaldo de ninguna organización gubernamental ni ayuntamiento por lo que se aconseja verificar la normativa del municipio para evitar posibles sanciones.

