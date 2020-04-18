## Generando llaves SSH

1) Crear Usuario en el **servidor**

	Colocar el siguiente comando: 
	```
	sudo adduser nombredelusuario
	```
	Te mostrará lo siguiente:

	![Ejecución Comando ](https://github.com/iqvan/Generando-llaves-SSH/blob/master/Pictures/Capture_add_User.PNG)

	*Cabe señalar que para eliminar dicho usuario puede utilizar el siguiente comando:*
	```
	sudo deluser nombredelusuario
	```
	Asignar privilegios sudo:
	```
	sudo adduser vanpc sudo
	sudo usermod -a -G sudo vanpc
	```

2) Generar la llave **SSH**

	Colocar el siguiente comando en el **ordenador**:

	```
	ssh-keygen
	```
	Te mostrará lo siguiente:

	![Ejecución Comando ](https://github.com/iqvan/Generando-llaves-SSH/blob/master/Pictures/Capture_ssh-keygen.PNG)
	
	Una vez ejecutado dicho comando te generará dos archivos que contienen la llave pública y la llave privada:

	![Files generados](https://github.com/iqvan/Generando-llaves-SSH/blob/master/Pictures/Capture_file_keyprivate_keypublic.PNG)


3) Copiar la llave pública en el **servidor**
	
	Abrimos el archivo con bloc de notas para copiar la llave pública:

	![Copy File](https://github.com/iqvan/Generando-llaves-SSH/blob/master/Pictures/Capture_copy-key-public.PNG)

	Coloca el siguiente comando para dirigirte a la ruta correspondiente en el servidor:

	```
	cd /home/nombredelusuario/
	sudo mkdir .ssh
	cd .ssh/
	sudo nano authorized_keys
	```

	Finalmente pegar en ese archivo la llave pública previamente copiada:

	![Paste File](https://github.com/iqvan/Generando-llaves-SSH/blob/master/Pictures/Capture_SSH_Authorized_keys.PNG)

4) Conectarnos al acceso remoto a través de nuestra consola del **ordenador**:

	4.1) Método 1
	
	Colocar directamente la ruta que corresponde a la llave privada

	```
	ssh root@142.93.111.101 -i C:\Users\UsuarioPrueba\.ssh\keyname
	```

	4.2) Método 2

	Construir un archivo de configuración.

	```
	ssh my_vps_root
	```

4)