# pkgbuild_vipm-2017_Arch-Linux
Create the package.xz using PKGBUILD to install "vipm-17.0.2018-1-x86_64.tar.xz - VI Package Manager (VIPM)" on Arch Linux and Manjaro Linux Distro.

# Running VIPM for Linux:

VIPM for Linux must be run with admin or root level privileges. There is no way around this. If you run VIPM as a standard user, it will not work as expected and will generate errors. To do this, navigate to the installation folder at /usr/local/JKI/VIPM and execute the following:
$ sudo ./vipm
You will be prompted for your root password. Enter the password and VIPM will launch.
If you need help with VIPM, visit our Community Forums at https://forums.jki.net

# To download VIPM (eng)
Access the following link "https://vipm.jki.net/download" and select the package for Linux, you must indicate an email to access the download, after downloading the package "vipm-17.0.2018-linux. tar.gz "copy it to the root of the PKGBUILD folder. Right there open a command terminal and run "$ makepkg -sri", once the package is compiled it will ask you for the superuser key to install the package in your Arch Linux or Manjaro Linux distribution.

You can manually check the hash of the file "vipm-17.0.2018-linux.tar.gz" once downloaded from the VIPM server, it would be the following hash SHA256SUM 'e105211c39b207cae2c1c0d1fca05fe09364890b420a7e8493e1df46f53db373'. (also the PKGBUILD verifies it automatically)

# Para descargar VIPM (esp)
Acceda al siguiente enlace "https://vipm.jki.net/download" y seleccione el paquete para Linux, debe indicar un correo electrónico para tener acceso a la descarga, una vez descargado el paquete "vipm-17.0.2018-linux.tar.gz" copielo a la raíz de la carpeta del PKGBUILD. Allí mismo abra una terminal de comando y ejecute "$ makepkg -sri", una vez compilado el paquete le pedira la clave de superusuario para instalar el paquete en su distribución Arch Linux o Manjaro Linux.

Puede verificar el hash manualmente del archivo "vipm-17.0.2018-linux.tar.gz" una vez descargado desde el sevidor de VIPM, sería el siguiente hash SHA256SUM 'e105211c39b207cae2c1c0d1fca05fe09364890b420a7e8493e1df46f53db373'. (igualmente el PKGBUILD lo verifica automaticamente)


#  Changelog (eng)
2020.04.12 ->
* Initial compilation of the package for archlinux, to work properly you must run from console "$ sudo /usr/local/JKI/VIPM/vipm
* To run this application it is necessary to have the LabVIEW2015SP1RTE module with at least 32 bits, since vipm is an ELF32 binary
* Tested with LabVIEW-2018-SP1 linux, functional it allows to install packages, you only have to reconfigure labview since the instance of it that runs labview is in superuser mode.
* It remains to allow execution in sudo mode through an icon to access the application, since it works in common user mode, the idea is to use gksu, but it does not work properly in gnome.
* Missing to add icons and mime executables, to run the application from .vipm, .vim and .vipc file types.

# Notas de cambios: (esp) 
2020.04.12 -->
* Compilación inicial del paquete para archlinux, para funcionar adecuadamente debe ejecutar desde consola "$sudo /usr/local/JKI/VIPM/vipm"
* Para ejecutar esta aplicación es necesario contar con el modulo LabVIEW2015SP1RTE al menos de 32 bits, ya que vipm es un binario ELF32
* Probado con LabVIEW-2018-SP1 linux, funcional permite instalar paquetes, solamente debe volver a configuar labview ya que la instancia del mismo que ejecuta labview es en modo superusuario.
* Falta permitir la ejecución en modo sudo mediante icono de acceso a aplicación, ya que funciona en modo usuario común la idea es usar gksu, pero el mismo no funciona adecuadamente en gnome.
* Faltan agregar iconos y ejecutables mime, para ejecurar la aplicacion desde los tipos de archivos .vipm, .vim y .vipc.
