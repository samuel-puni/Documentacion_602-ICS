# Instalacion Debian 7 Wheezy para un entorno de virtualizacion
## Consideraciones previas
* Se debe asegurar que el equipo soporte virtualizacion por hardware que generalmen se encuantra en las opciones del procesador en el BIOS del computador. En maquinas linux se puede observar lo anterior mediante el comando:
`grep vmx /proc/cpuinfo` que tras su ejecucion mostrará algo parecido:
```
sampc@host-01:~$ sudo grep --color vmx /proc/cpuinfo 
flags		: fpu vme de pse tsc msr pae mce cx8 apic sep mtrr pge mca cmov pat pse36 clflush dts mmx fxsr sse sse2 ss ht syscall nx rdtscp lm constant_tsc arch_perfmon pebs bts nopl xtopology tsc_reliable nonstop_tsc aperfmperf pni pclmulqdq vmx ssse3 cx16 sse4_1 sse4_2 x2apic popcnt aes hypervisor lahf_lm ida arat dtherm tpr_shadow vnmi ept vpid
flags		: fpu vme de pse tsc msr pae mce cx8 apic sep mtrr pge mca cmov pat pse36 clflush dts mmx fxsr sse sse2 ss ht syscall nx rdtscp lm constant_tsc arch_perfmon pebs bts nopl xtopology tsc_reliable nonstop_tsc aperfmperf pni pclmulqdq vmx ssse3 cx16 sse4_1 sse4_2 x2apic popcnt aes hypervisor lahf_lm ida arat dtherm tpr_shadow vnmi ept vpid
flags		: fpu vme de pse tsc msr pae mce cx8 apic sep mtrr pge mca cmov pat pse36 clflush dts mmx fxsr sse sse2 ss ht syscall nx rdtscp lm constant_tsc arch_perfmon pebs bts nopl xtopology tsc_reliable nonstop_tsc aperfmperf pni pclmulqdq vmx ssse3 cx16 sse4_1 sse4_2 x2apic popcnt aes hypervisor lahf_lm ida arat dtherm tpr_shadow vnmi ept vpid
flags		: fpu vme de pse tsc msr pae mce cx8 apic sep mtrr pge mca cmov pat pse36 clflush dts mmx fxsr sse sse2 ss ht syscall nx rdtscp lm constant_tsc arch_perfmon pebs bts nopl xtopology tsc_reliable nonstop_tsc aperfmperf pni pclmulqdq vmx ssse3 cx16 sse4_1 sse4_2 x2apic popcnt aes hypervisor lahf_lm ida arat dtherm tpr_shadow vnmi ept vpid
```

## Proceso de instalación

1. Iniciar el equipo para que inicie desde el DVD/CD. Una vez que haya arrancado, se verá la siguiente pantalla en donde se deberá seleccionar la primera opcion:
![Pantalla de Instalacion](Images/00_instalacion_Devian_Servidor/00_pantalla_inicial.png)

2. Escogemos el idioma
![Pantalla de Instalacion](Images/00_instalacion_Devian_Servidor/01_pantalla_idioma.png)

3. Escogemos la Ubicacion
![Pantalla de Instalacion](Images/00_instalacion_Devian_Servidor/02_pantalla_ubicacion.png)

4. Escogemos la distribucion del teclado que usaremos para la administracion directa
![Pantalla de Instalacion](Images/00_instalacion_Devian_Servidor/03_pantalla_teclado.png)

5. Definimos un nombre para el servidor
![Pantalla de Instalacion](Images/00_instalacion_Devian_Servidor/04_pantalla_nombre_maquina.png)

6. Definimos un dominio para el equipo
![Pantalla de Instalacion](Images/00_instalacion_Devian_Servidor/05_pantalla_nombre_dominio.png)

7. Definimos la clave de root y la confirmamos
![Pantalla de Instalacion](Images/00_instalacion_Devian_Servidor/06_pantalla_clave_root.png)

![Pantalla de Instalacion](Images/00_instalacion_Devian_Servidor/06_pantalla_clave_root-01.png)

8. Definimos una cuenta de usuario con los siguientes datos: Nombre completo, cuenta y contraseña
![Pantalla de Instalacion](Images/00_instalacion_Devian_Servidor/07_pantalla_Usuario.png)

![Pantalla de Instalacion](Images/00_instalacion_Devian_Servidor/07_pantalla_Usuario_01.png)

![Pantalla de Instalacion](Images/00_instalacion_Devian_Servidor/07_pantalla_Usuario_02.png)

9. El instalador tratará de sincronizar la hora de la red
![Pantalla de Instalacion](Images/00_instalacion_Devian_Servidor/08_pantalla_hora_red.png)

10. A continuacion se deberá particionar el Disco duro:
![Pantalla de Instalacion](Images/00_instalacion_Devian_Servidor/09_pantalla_seleccion_hdd.png)

11. Seleccionamos el tipo de particionado, en este caso: Manual
![Pantalla de Instalacion](Images/00_instalacion_Devian_Servidor/09_pantalla_tipo_particionado.png)

12. Seleccionamos el tipo de particion, es este caso será particion primaria
![Pantalla de Instalacion](Images/00_instalacion_Devian_Servidor/10_pantalla_tipo_particion.png)

13. Definmos el tamaño de la partición, para el ejemplo se creará la particion /boot:
![Pantalla de Instalacion](Images/00_instalacion_Devian_Servidor/11_pantalla_particion_boot.png)

14. Se elige el tipo de particion:
![Pantalla de Instalacion](Images/00_instalacion_Devian_Servidor/12_pantalla_particion_boot_lugar.png)

15. Se elige la ubicacion de la particion dentro del espacio disponble:
![Pantalla de Instalacion](Images/00_instalacion_Devian_Servidor/12_pantalla_particion_boot_lugar_01.png)

16. Se configura la partición. En este caso se eligió, para la partición /boot, el sistema de archivos ext2 ya que se trata de una partición pequeña y para que el arranque de la maquina sea rapida.
![Pantalla de Instalacion](Images/00_instalacion_Devian_Servidor/12_pantalla_particion_boot_lugar_02.png)

17. Tras terminar de definir la particion, se muestra un resumen de los cambio efectuados hasta el momento:
![Pantalla de Instalacion](Images/00_instalacion_Devian_Servidor/13_pantalla_otras_particiones.png)

18. Finalmente, tras definir el resto de particiones, se muetra el resumen completo de los cambios realizados:
![Pantalla de Instalacion](Images/00_instalacion_Devian_Servidor/14_pantalla_partiones_resumen.png)

19. Se confirman los cambios a realizar:
![Pantalla de Instalacion](Images/00_instalacion_Devian_Servidor/15_pantalla_partiones_confirmaciones.png)

20. Se inicia el proceso de instalacion del sistema base:
![Pantalla de Instalacion](Images/00_instalacion_Devian_Servidor/16_pantalla_proceso_instalacion.png)

21. Se sugiere instalar una replica de red para completar los paquetes de instalacion, se elige NO
![Pantalla de Instalacion](Images/00_instalacion_Devian_Servidor/17_pantalla_replica_red.png)

22. A la pregunta sobre la encuesta de popularidad de los paquetes usados se responde NO:
![Pantalla de Instalacion](Images/00_instalacion_Devian_Servidor/20_pantalla_encuesta_popularidad.png)

23. Seguidamente seleccionamos los grupos de programas a instalar. En este caso al tratarse de un servidor donde se instalaran maquinas virtuales y a partir del cual se administrarán los mismos, elegimos: El ambiente de escritorio de Debian, el servidor SSH, porgramas de Laptop y utilidades estandar del sistema:
![Pantalla de Instalacion](Images/00_instalacion_Devian_Servidor/21_pantalla_paquetees_a_instalar.png)

24. Tras la instalacion, se nos pregunta si se instalará el cargador de arranque GRUB, a la pregunta respondemos SI:
![Pantalla de Instalacion](Images/00_instalacion_Devian_Servidor/23_pantalla_grub.png)

25. Finalmente, se nos puestra una pantalla donde se nos indica que el proceso de instalacion terminó y que se debe extraer cualquier medio de instalaciobn para inciar el equipo:
![Pantalla de Instalacion](Images/00_instalacion_Devian_Servidor/24_pantalla_finalizacion.png)
