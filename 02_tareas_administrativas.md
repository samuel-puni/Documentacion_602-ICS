# Tareas a realizar mediante el administrador de maquinas virtuales (Virtual Machine Manager)
Para realizar las tareas de administracion de las redes virtuales y el almacenamiento se debe acceder a las propiedades (Detalles del servidor **localhost**)
![Detalles localhost](Images/01_plataforma_virtualizacion/03_menu_contextual_localhost.png)

Tras la selección de la opcion **Detalles** se mostrará la siguiente ventana:
![Detalles localhost](Images/01_plataforma_virtualizacion/02_adm_virtual_network.png)

##1. Creacion de redes virtuales
Ya sea para crear redes virtuales, alamacenamiento o interfaces de red se cuentan con los siguientes botones de operacion:
- Añadir  ![Botón añadir](Images/01_plataforma_virtualizacion/btn_add.png)
- Iniciar  ![Detalles localhost](Images/01_plataforma_virtualizacion/btn_play.png)
- Detener  ![Detalles localhost](Images/01_plataforma_virtualizacion/btn_stop.png)
- Eliminar  ![Detalles localhost](Images/01_plataforma_virtualizacion/btn_del.png)

Para crear una nueva red virtual, hacemos click en el boton de Añadir Red Virtual ![Añadir Red Virtual](Images/01_plataforma_virtualizacion/btn_add.png) que iniciara una asistente para su configuracion:
![Asistente nueva red virtual](Images/01_plataforma_virtualizacion/04_nueva_red_virtual.png)

Deberemos completar cuatro pasos para su correcta configuracion:
1. Nombre de la red virtual:
![Nombre red virtual](Images/01_plataforma_virtualizacion/05_nombre_red.png)
2. Segmento de red IPv4
![Segmento de red IPv4](Images/01_plataforma_virtualizacion/06_segmento_de_red_ipv4.png)
3. Rango DHCP. Es posible definir un rango de direcciones para que puedan ser provistas a traves del servicio DHCP. La configuracion viene con un rango de direccion prefedini a que se puede cambiar. El servicio funciona siempre y cuando se tenga habilitada la opcion **Habilitar DHCP**
![Rango DHCP](Images/01_plataforma_virtualizacion/07_rango_dhcp.png)
4. Configuración del la conectividad a la red física. Es posible crear una red ahislada o con concetividad a la red fisica del host, para tal caso se debe activar el reenvio a la red fisica (cualquiera que éste activa en ese momento y a través de NAT)
![Tipo de conexion a la red](Images/01_plataforma_virtualizacion/08_conexion_fisica_a_la_red.png)
5. Resumen. Finalmente, se presenta un resumen de las configuraciones a aplicar:
![Resumen](Images/01_plataforma_virtualizacion/09_resumen_red_virtual.png)

Una vez creada la red virtual nos aparecera una pantalla donde nos muestra el listado de redes.
![Detalles localhost](Images/01_plataforma_virtualizacion/10_listado_red_virtual.png)
Se puede observar que no esta activa. Para activarla se debe hacer un click en el boton ![Inciar Red Virtual](Images/01_plataforma_virtualizacion/btn_play.png) y seleccionar la opción **Autostart** y despues click en el boton **Apply** para que al momento del arranque este disponible.
##2. Creacion de almacenamiento
### Consideraciones previas
Para el almacenamiento se ha creado el directorio `/datos` en el cual se almacenaran los archivos de las maquinas creadas:
```
~$ sudo mkdir /datos
```
### Proceso de configuracion del almacenamiento
Existen dos partes que se deben completar para tener el almacenamiento listo para las maquinas virtuales a crear:
- Creación del Pool de Almacenamiento.
- Creación del Volumen sobre Algun Pool disponible.
![Pestaña almacenamiento](Images/01_plataforma_virtualizacion/11_pestaña_storage.png)

**Creación del Pool de Almacenamiento.** Para crear el Pool de Almacenamiento hacemos click sobre el botón ![Añadir Pool de Almacenamiento](Images/01_plataforma_virtualizacion/btn_add.png), seguidamente se iniciará el asistente de creacion del Pool de Almacenamiento:
![Nuevo Pool](Images/01_plataforma_virtualizacion/12_nuevo_pool_storage.png)
Finalmente, se deberá indicar la ubicacion fisica (directorio) donde se guardaran los volumenes a crear, en este caso `/datos`:
![Nuevo Pool](Images/01_plataforma_virtualizacion/13_ubicacion_pool.png)

**Creación del volumen.** Para la creación de un volumen sobre el pool seleccionado, hacemos click sobre el boton ![Nuevo Volumen](Images/01_plataforma_virtualizacion/15_new_volume.png), seguidamente se mostrará la ventana de creación del nuevo volumen:
![Nuevo Volumen](Images/01_plataforma_virtualizacion/14_nuevo_volumen.png)
donde se le asignara un nombre al nuevo volumen de tipo `qcow2` y una capacidad determinada, en este caso `3000 MB`.