# Maintainer: Octavio Schiantarelli <octavio.schiantarelli@gmail.com>

pkgname='vipm'	
pkgver='17.0.2018'
pkgrel='1'
pkgdesc="vipm 2017.0.0.2018 - VI Package Manager (VIPM)"
arch=('i686' 'x86_64')
url="http://vipm.jki.net"
license=('custom:Copyright JKI')
groups=()
depends=('lib32-glibc' 'lib32-libxinerama' 'lib32-libglade')
makedepends=('libarchive')
optdepends=()
provides=()
conflicts=()
replaces=()
backup=()
options=('!strip') #strip - Tira de los símbolos de binarios y bibliotecas. (para revertir a el comportamiento default se debe agregar un ! al inicio de la opción.)
install=
changelog=
PKGEXT='.tar.xz'
source=('file://vipm-17.0.2018-linux.tar.gz'
        'file://vipm.desktop'
        #'file://labview-2015-rte-32bit-15.0.1-11.i386.rpm' # no se usa, ya que es parte del paquete principal vipm-17.....
        #'file://labview-2015-rte-15.0.1-11.x86_64.rpm'     # no se usa, ya que es parte del paquete principal vipm-17.....
        )
		
noextract=()

sha256sums=('e105211c39b207cae2c1c0d1fca05fe09364890b420a7e8493e1df46f53db373'
            '3b140e3df30bde02cbfea1953c30a365b426338fffe5e385b6b326a4fd3fd659'
            #'fce7c521edb75a6d460543c492ac4c30f979ea39509aca59ea0cb6f4c8f1315b'
            #'aa1216069d70b9ee791b549727f1fa75c2f73816a971d340c66b75638b1e89e4'
            ) #autofill using updpkgsums

prepare() {
    cd ${srcdir}  
    bsdtar -pxf $pkgname-$pkgver-linux.tar.gz
    cp -pf ${srcdir}/$pkgname-$pkgver-linux/LabVIEW2015SP1RTE_Linux/labview-2015-rte-32bit-15.0.1-11.i386.rpm ${srcdir}/
    cp -pf ${srcdir}/$pkgname-$pkgver-linux/LabVIEW2015SP1RTE_Linux/labview-2015-rte-15.0.1-11.x86_64.rpm ${srcdir}/
    bsdtar -pxf labview-2015-rte-32bit-15.0.1-11.i386.rpm
    bsdtar -pxf labview-2015-rte-15.0.1-11.x86_64.rpm
    #for file in ${source[@]}; do if [ ${file: -4} == ".rpm" ]; then bsdtar -xf "${file#file://}"; fi; done
}

package() {
  # Create necessary directories
  #mkdir -p "${pkgdir}/home/$USER/"
  #mkdir -p "${pkgdir}/opt/JKI/VIPM/"
  mkdir -p "${pkgdir}/usr/local/JKI/VIPM/"
  
  mkdir -p "${pkgdir}/usr/share/icons/hicolor/48x48/apps/"
  mkdir -p "${pkgdir}/usr/share/applications/JKI/VIPM/"
  mkdir -p "${pkgdir}/usr/local/lib/LabVIEW-2015/"
  mkdir -p "${pkgdir}/usr/local/lib64/LabVIEW-2015-64/"
  mkdir -p "${pkgdir}/usr/lib/"
  #mkdir -p "${pkgdir}/usr/lib64/"
  
  # Copy necessary files
  #cp -rp "${srcdir}/$pkgname-$pkgver-linux/JKI/" "${pkgdir}/home/$USER/" #copia /home/$USER/
  #cp -rp "${srcdir}/$pkgname-$pkgver-linux/JKI/" "${pkgdir}/opt/" #copia /opt/
  cp -rp "${srcdir}/$pkgname-$pkgver-linux/JKI/" "${pkgdir}/usr/local/" #copia /usr/local/
  
  #cp -p "${srcdir}/vipm.desktop" "${pkgdir}/home/$USER/JKI/VIPM/"
  #cp -p "${srcdir}/vipm.desktop" "${pkgdir}/opt/JKI/VIPM/"
  cp -p "${srcdir}/vipm.desktop" "${pkgdir}/usr/local/JKI/VIPM/"
  cp -p "${srcdir}/vipm.desktop" "${pkgdir}/usr/share/applications/"
  
  cp -rp "${srcdir}/usr/local/lib/LabVIEW-2015/" "${pkgdir}/usr/local/lib/"
  cp -rp "${srcdir}/usr/local/lib64/LabVIEW-2015-64/" "${pkgdir}/usr/local/lib64/"
  
  
  # Copy icon app
  #cp -p "${pkgdir}/home/$USER/JKI/VIPM/icons/linux/VIPM 48x48 - 32bit.png" "${pkgdir}/usr/share/icons/hicolor/48x48/apps/VIPM_48x48_32bit.png"
  #cp "${pkgdir}/opt/JKI/VIPM/icons/linux/VIPM 48x48 - 32bit.png" "${pkgdir}/usr/share/icons/hicolor/48x48/apps/VIPM_48x48_32bit.png"
  cp "${pkgdir}/usr/local/JKI/VIPM/icons/linux/VIPM 48x48 - 32bit.png" "${pkgdir}/usr/share/icons/hicolor/48x48/apps/VIPM_48x48_32bit.png"
  
  #se crea archivo.dir
  #echo /home/$USER/JKI/VIPM > "${pkgdir}/home/$USER/JKI/VIPM/nisvcloc.dir"
  #echo /opt/JKI/VIPM > "${pkgdir}/opt/JKI/VIPM/nisvcloc.dir"
  echo /usr/local/JKI/VIPM > "${pkgdir}/usr/local/JKI/VIPM/vipm.dir"
  
    
  # Apply specific tweaks
  #sed "s,Exec.*,Exec=/home/$USER/JKI/VIPM/vipm -launch "%F"," "${pkgdir}/home/$USER/JKI/VIPM/vipm.desktop" > "${pkgdir}/usr/share/applications/JKI/VIPM/vipm.desktop"
  #sed "s,Exec.*,Exec=/opt/JKI/VIPM/vipm -launch "%F"," "${pkgdir}/opt/JKI/VIPM/vipm.desktop" > "${pkgdir}/usr/share/applications/JKI/VIPM/vipm.desktop"
  #sed "s,Exec.*,Exec=/usr/local/JKI/VIPM/vipm %f," "${pkgdir}/usr/local/JKI/VIPM/vipm.desktop" > "${pkgdir}/usr/share/applications/vipm.desktop"

  #enlace simbolico directorio
  ln -sf "/usr/local/lib/LabVIEW-2015/" "${pkgdir}/usr/lib/"        ### "for LabVIEW 32 bits" ###
  ln -sf "/usr/local/lib64/LabVIEW-2015-64/" "${pkgdir}/usr/lib/"   ### "for LabVIEW 64 bits" ###
  
  #enlace simbolico libreria liblvrt.so
  #ln -sf "/usr/local/lib/LabVIEW-2015/liblvrt.so.15.0.1" "${pkgdir}/usr/lib/liblvrt.so.15.0"             ### "for LabVIEW 32 bits" ###
  #ln -sf "/usr/local/lib64/LabVIEW-2015-64/liblvrt.so.15.0.1" "${pkgdir}/usr/lib64/liblvrt.so.15.0"      ### "for LabVIEW 64 bits" ###


######################################################################
# symbolic links libraries labview-2015-rte-32bit-15.0.1-11.i386.rpm #
######################################################################

 #[root@centos-7-labview lib64]# ls -l /usr/local/lib/

  # liblvrtdark.so -> liblvrtdark.so.15.0
  # liblvrtdark.so.15.0 -> LabVIEW-2015/liblvrtdark.so.15.0.1
  # liblvrt.so -> liblvrt.so.15.0
  # liblvrt.so.15.0 -> LabVIEW-2015/liblvrt.so.15.0.1

 ln -sf "/usr/lib/LabVIEW-2015/liblvrtdark.so.15.0"   "${pkgdir}/usr/local/lib/liblvrtdark.so"
 ln -sf "/usr/lib/LabVIEW-2015/liblvrtdark.so.15.0.1" "${pkgdir}/usr/local/lib/liblvrtdark.so.15.0"
 ln -sf "/usr/lib/LabVIEW-2015/liblvrt.so.15.0"     "${pkgdir}/usr/local/lib/liblvrt.so"
 ln -sf "/usr/lib/LabVIEW-2015/liblvrt.so.15.0.1"     "${pkgdir}/usr/local/lib/liblvrt.so.15.0"


##################################################################
# symbolic links libraries labview-2015-rte-15.0.1-11.x86_64.rpm #
##################################################################
 
 #[root@centos-7-labview lib64]# ls -l /usr/local/lib64/
 
 #liblvrtdark.so.15.0 -> LabVIEW-2015-64/liblvrtdark.so.15.0.1
 #liblvrt.so.15.0 -> LabVIEW-2015-64/liblvrt.so.15.0.1
 
 ln -sf "/usr/lib/LabVIEW-2015-64/liblvrtdark.so.15.0.1" "${pkgdir}/usr/local/lib64/liblvrtdark.so.15.0" 
 ln -sf "/usr/lib/LabVIEW-2015-64/liblvrt.so.15.0.1" "${pkgdir}/usr/local/lib64/liblvrt.so.15.0" 
 
 echo "VI Package Manager (VIPM) is Copyright JKI
 
###################
###  Changelog  ###
###################
 
 2020.04.12 --> * Compilación inicial del paquete para archlinux, para funcionar adecuadamente debe ejecutar desde consola $sudo /usr/local/JKI/VIPM/vipm
                * Para ejecutar esta aplicación es necesario contar con el modulo LabVIEW2015SP1RTE al menos de 32 bits, ya que vipm es un binario ELF32
                * Falta permitir la ejecución en modo sudo mediante icono de acceso a aplicación, ya que funciona en modo usuario común la idea es usar gksu, pero el mismo no funciona adecuadamente en gnome
                * Faltan agregar iconos y ejecutables mime, para ejecurar la aplicacion desde los tipos de archivos .vipm, .vim y .vipc.
                

#####################
###  Notes  VIPM  ###  
#####################

Running VIPM for Linux:

VIPM for Linux must be run with admin or root level privileges. There is no way around this. If you run VIPM as a standard user, it will not work as expected and will generate errors. To do this, navigate to the installation folder at /usr/local/JKI/VIPM and execute the following:

$ sudo ./vipm

You will be prompted for your root password. Enter the password and VIPM will launch.

If you need help with VIPM, visit our Community Forums at https://forums.jki.net

JKI also provides custom LabVIEW programming services and training. Contact us at sales@jki.net and we'll do our best to help solve your tough technical challenges.

VIPM is also available on Mac and Windows. See http://vipm.jki.net for more info."

}


# vim:set et sw=2 sts=2:
