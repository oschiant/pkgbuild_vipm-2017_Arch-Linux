### Description pkgbuild_vipm-2017_Arch-Linux

Create the package.xz using PKGBUILD to install "vipm-17.0.2018-1-x86_64.tar.xz - VI Package Manager (VIPM)" on Arch Linux and Manjaro Linux Distro.

### Running VIPM for Arch Linux and Manjaro Linux

VIPM for Linux must be run with admin or root level privileges. There is no way around this. If you run VIPM as a standard user, it will not work as expected and will generate errors. To do this, navigate to the installation folder at `/usr/local/JKI/VIPM` and execute the following `$ sudo ./vipm` You will be prompted for your root password. Enter the password and VIPM will launch. 
If you need help with VIPM, visit our Community Forums at https://forums.jki.net

### To download VIPM (eng)

Access the following link https://vipm.jki.net/download and select the package for Linux, you must indicate an email to access the download, after downloading the package `vipm-17.0.2018-linux. tar.gz` copy it to the root of the PKGBUILD folder. Right there open a command terminal and run `$ makepkg -sri`, once the package is compiled it will ask you for the superuser key to install the package in your Arch Linux or Manjaro Linux distribution.

You can manually check the hash of the file `vipm-17.0.2018-linux.tar.gz` once downloaded from the VIPM server, it would be the following hash `SHA256SUM e105211c39b207cae2c1c0d1fca05fe09364890b420a7e8493e1df46f53db373`. (also the PKGBUILD verifies it automatically)

### Changelog (eng)
2020.04.18
* Content is ordered and formats the README.md file to improve understanding.
* Add dependency to the `zensu` package to be able to run` vipm` as superuser using the icon that is added to the Gnome applications. The user must belong to the `wheel` group to be able to run` vipm` in superuser mode. You can verify this by pasting the following command into a `$ groups $ USER` console.
> * In the future the idea is to run vipm as superuser using a polkit rule since it is the native authentication method of most graphical environments. See the following link https://wiki.archlinux.org/index.php/Polkit.

2020.04.12
* Initial compilation of the package for Arch Linux, to work properly you must run from console
`$ sudo /usr/local/JKI/VIPM/vipm`.
* To run this application it is necessary to have the LabVIEW2015SP1RTE module with at least 32 bits, since `vipm` is an ELF32 binary.
* Tested with LabVIEW-2018-SP1 Linux, functional it allows to install packages, you only have to reconfigure LabVIEW since the instance of it that runs LabVIEW is in superuser mode.
> * It remains to allow execution in sudo mode through an icon to access the application, since it works in common user mode, the idea is to use `gksu`, but it does not work properly in gnome.
> * Missing to add icons and mime executables, to run the application from `.vipm`, `.vim` and `.vipc` file types.


***


### Para descargar VIPM (esp)

Acceda al siguiente enlace https://vipm.jki.net/download y seleccione el paquete para Linux, debe indicar un correo electrónico para tener acceso a la descarga, una vez descargado el paquete `vipm-17.0.2018-linux.tar.gz` cópielo a la raíz de la carpeta del PKGBUILD. Allí mismo abra una terminal de comando y ejecute `$ makepkg -sri`, una vez compilado el paquete le pedirá la clave de superusuario para instalar el paquete en su distribución Arch Linux o Manjaro Linux.

Puede verificar el hash manualmente del archivo `vipm-17.0.2018-linux.tar.gz` una vez descargado desde el servidor de VIPM, sería el siguiente hash `SHA256SUM e105211c39b207cae2c1c0d1fca05fe09364890b420a7e8493e1df46f53db373`. (igualmente el PKGBUILD lo verifica automáticamente)


### Notas de cambios: (esp)
2020.04.18
* Se ordena contenido y da formato al archivo README.md para mejorar la comprensión.
* Se agrega dependencia al paquete `zensu` para poder ejecutar `vipm`  como superusuario mediante el icono que se agrega a las aplicaciones de Gnome. El usuario deberá pertenecer al grupo `wheel` para poder ejecutar `vipm` en modo superusuario. Esto lo puede verificar pegando el siguiente comando en una consola `$ groups $USER`.
> * En un futuro la idea es ejecutar vipm como superusuario mediante una regla polkit ya que es el metodo de autenticación nativo de la mayoría de los entornos gráficos. Vea el siguiente enlace https://wiki.archlinux.org/index.php/Polkit.

2020.04.12
* Compilación inicial del paquete para Arch Linux, para funcionar adecuadamente debe ejecutar desde consola 
`$ sudo /usr/local/JKI/VIPM/vipm`
* Para ejecutar esta aplicación es necesario contar con el modulo LabVIEW2015SP1RTE al menos de 32 bits, ya que `vipm` es un binario ELF32.
* Probado con LabVIEW-2018-SP1 Linux, funcional permite instalar paquetes, solamente debe volver a configuar LabVIEW ya que la instancia del mismo que ejecuta LabVIEW es en modo superusuario.
> * Falta permitir la ejecución en modo sudo mediante icono de acceso a aplicación, ya que funciona en modo usuario común la idea es usar `gksu`, pero el mismo no funciona adecuadamente en gnome.
> * Faltan agregar iconos y ejecutables mime, para ejecutar la aplicación desde los tipos de archivos `.vipm`, `.vim` y `.vipc`.
