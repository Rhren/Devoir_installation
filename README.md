# Devoir_installation
 DEVOIR LINUx
                             Installation  à partir d’un code source
			     
 • INSTALLATION  MySQL
          
     Étape 1 :  Téléchargement d’un code source :mysql-8.3.0.tar.gz
    Étape 2 :  Terminal :
    
    ..:~$ tar -xzvf mysql-8.3.0.tar.gz
    .. :~$ cd mysql-8.3.0
    .. : :~/mysql-8.3.0$./configure
 configure:no such file or directory
 
    … :~/mysql-8.3.0$ls
    … :~/mysql-8.3.0$ more INSTALL
    … :~/mysql-8.3.0$ mkdir bld
    .. :.~/mysql-8.3.0/bld$ cmake ..
 ….ERROR : « Please install the appropriate openssl developer package »….
 
    … :~/mysql-8.3.0/bld$sudo apt-get install libssl-dev
    … :~/mysql-8.3.0/bld$ cmake..
    
  ...ERROR : »Curses library not found .Please install the appropriate package »…
  
    … :~/mysql-8.3.0/bld$ sudo apt-get install libncurses5-dev
    .. :.~/mysql-8.3.0/bld$cmake ..
  ...ERROR : »Could not find PkgConfig(missing:PKG_CONFIG_EXECUTABLE) »…
  
    … :~/mysql-8.3.0/bld$ sudo apt-get install pkg-config
     … :~/mysql-8.3.0/bld$ cmake ..
    no error
     … :~/mysql-8.3.0/bld$make
     … :~/mysql-8.3.0/bld$ sudo make install
     ...:~/mysql-8.3.0/bld$ make clean
           
 • INSTALLATION APACHE :
 
      Étape 1 :  Téléchargement d’un code source:httpd-2.4.59.tar
      Étape 2 :  Terminal :
	.. .~$ tar -xvf httpd-2.4.59.tar
	.. .~$ cd httpd-2.4.59
	...~/httpd-2.4.59$ ls
	...~ /httpd-2.4.59$ more INSTALL
	
	Étape 3 : Installation des dépendances nécessaires
	Lien dans le fichier INSTALL:pré-requis:APR/APR-UTIL/PCRE2
    • Téléchargement  code source « apr-1.7.4.tar »
    	...~/httpd-2.4.59$ tar -xvf  apr-1.7.4.tar
	...~/httpd-2.4.59$ cd apr-1.7.4
	..~/httpd-2.4.59/apr-1.7.4$ ./configure
ERROR:can not execute « libtool »command

	..~/httpd-2.4.59/apr-1.7.4$ sudo apt install libtool
	..~/httpd-2.4.59/apr-1.7.4$ ./configure
	..~/httpd-2.4.59/apr-1.7.4$ make
	..~/httpd-2.4.59/apr-1.7.4$ sudo make install
	..~/httpd-2.4.59/apr-1.7.4$ cd ..
    • Téléchargement  code source « apr-util-1.6.3.tar »
      .~/httpd-2.4.59$ tar -xvf  apr-util-1.6.3.tar
      .~/httpd-2.4.59/apr-util-1.6.3$./configure
ERROR:APR could not be located,use option –with-apr

	. ~/httpd-2.4.59/apr-util-1.6.3$ ./configure –with-apr=/usr/local/apr
	~/httpd-2.4.59/apr-util-1.6.3$ make
     ~/httpd-2.4.59/apr-util-1.6.3$  sudo make install
	~/httpd-2.4.59/apr-util-1.6.3$ cd ..
    • Téléchargement  code source « pcre2-10.43.tar »

	Même étape que apr:Désarchivage et configuration ./configure
ERROR:fatal error:expat.h:no such file or directory
	
	~/httpd-2.4.59/ pcre2-10.43$sudo apt install libexpat1-dev
	~/httpd-2.4.59/ pcre2-10.43$./configure
	~/httpd-2.4.59/ pcre2-10.43$make
	~/httpd-2.4.59/ pcre2-10.43$ sudo make install
	~/httpd-2.4.59/ pcre2-10.43$cd ..
	~/httpd-2.4.59$ ./configure
	~/httpd-2.4.59$ make
    ~/httpd-2.4.59$sudo make install
	 ~/httpd-2.4.59$make clean

• INSTALLATION PHP

    Étape 1 :Téléchargement  code source « php-8.3.6.tar »
    
    Étape 2:Terminal
        • Desarchivage php-8.3.6.tar 
    ..~$ cd php-8.3.6
    ..~/php-8.3.6$ ls
    ..~/php-8.3.6$ more README.md
    Étape 3: installation des dépendances:Autoconf ,bison,re2c
    ..~/php-8.3.6$ sudo apt install -y pkg-config build-essential autoconf bison re2c \
                            libxml2-dev libsqlite3-dev
    
    ..~/php-8.3.6$./buildconf
    ..~/php-8.3.6$./configure
    ..~/php-8.3.6$make
    ..~/php-8.3.6$sudo make install
	..~/php-8.3.6$make clean 
                
        
        
            
