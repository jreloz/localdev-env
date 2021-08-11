

Directory:
	-bin
	    -mysql
	    -php
	    -node
	    -nginx
	    -othertools
	-www
	    -website1
	    -website2



******Setting up MySQL Zip File - No Install******
1. Download MySQL
2. Extract to bin folder directory
3. Goto MySQL bin dir and execute command:
	1. mysqld --console --initialize
	2. mysqld --console
	3. mysql -u root -p {provide temporary password from the console initialization}
4. Change the root password by executing the command ALTER user 'root'@'localhost' identified by 'root';





******Setting up PHP Zip File - No Install******
1. Download PHP
2. Extract to bin folder directory
3. Enable PHP extensions in php.ini




******Setting up Nginx Server Zip File - No Install******
1. Download Nginx Server
2. Extract to bin folder directory
3. Create a filename "fastcgi.bat" inside your nginx directory with the following:

	<code>
		@ECHO OFF
		ECHO Starting PHP FastCGI...
		set PATH={your php path};%PATH%
		start {your php path}php-cgi.exe -b 127.0.0.1:9123
		start {your nginx path}nginx.exe
	</code>
	

4. Update your nginx.conf settings:

	<code>
		location ~ \.php$ {
			root           C:/www; #your document root
			fastcgi_pass   127.0.0.1:9123;
			fastcgi_index  index.php;
			fastcgi_param  SCRIPT_FILENAME  $document_root$fastcgi_script_name; #SCRIPT_FILENAME  /scripts$fastcgi_script_name;
			include        fastcgi_params;
		}
	</code>
	

4. Make sure to install vcruntime.dll
5. Run fastcgi.bat and nginx.exe






******Setting up Composer - No Install******
1. {your php path}\php -r "copy('https://getcomposer.org/installer', 'composer-setup.php');"
2. {your php path}\php composer-setup.ph
3. {your php path}\php -r "unlink('composer-setup.php');"
4. {your php path}\php composer.phar
5. create a "composer.bat" file in yout php path with the following:

	<code>
		@php "%~dp0composer.phar" %*
	</code>



******Setting up Node - No Install******
1. Download Nodejs binary
2. Extract to bin folder directory
3. Add to path



You should add composer,php and mysql to system variables PATH to make commands globally available.
see: https://docs.microsoft.com/en-us/previous-versions/office/developer/sharepoint-2010/ee537574(v=office.14)
