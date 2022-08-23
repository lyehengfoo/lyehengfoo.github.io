---
# title: "Post Template"
# date: 2022-01-01 14:30:00:00 +0800
author: foo
layout: post
icon: web
tags: web, mysql, php
#published: false
---

## Backup using phpMyAdmin

If you have access to phpMyAdmin, this would be the simplest method.

Steps to backup:
1. Select the database.
2. Click on the *Export* tab.
3. Select the approriate Export options by selecting *Custom* in the *Export method*. Some useful options:
    - Select zipped/gzipped for *Compression*.
    - Turn on *Add CREATE DATABASE / USE statement*.
    - Turn on *Add DROP TABLE / VIEW / PROCEDURE / FUNCTION / EVENT / TRIGGER statement*.
4. Click on the *Export* button.

Steps to restore:
1. Remove the corrupted database
    - Click on the *Operations* tab.
    - Goto the *Remove database* section.
    - Then, click on the *Drop the database (DROP)* link.
2. Click on the *Import* tab.
3. Select the previously exported file e.g. *backup.sql.zip*.
4. We can leave all the options as default.
5. Click on the *Import* button.


## Backup with SQL SELECT command in a PHP script

We can dump out the data to an output file by using SQL SELECT command. If you need to dump all the whole
database, you will need to loop it for each table.

Here is an example of php script to backup the table wp_options.

```php
<?php
   $dbhost = 'localhost';
   $dbuser = 'root';
   $dbpass = 'password';
   
   $conn = mysql_connect($dbhost, $dbuser, $dbpass);
   
   if(! $conn ) {
      die('Could not connect: ' . mysql_error());
   }
	
   $table_name = "wp_options";
   $backup_file  = "/tmp/wp_options.sql";
   $sql = "SELECT * INTO OUTFILE '$backup_file' FROM $table_name";
   
   mysql_select_db('wp_db');
   $retval = mysql_query( $sql, $conn );
   
   if(! $retval ) {
      die('Could not take data backup: ' . mysql_error());
   }
   
   echo "Data backed up successfully\n";
   
   mysql_close($conn);
?>
```

And to load data back into MySQL, we use the LOAD DATA INFILE command.

```php
<?php
   $dbhost = 'localhost';
   $dbuser = 'root';
   $dbpass = 'password';
   
   $conn = mysql_connect($dbhost, $dbuser, $dbpass);
   
   if(! $conn ) {
      die('Could not connect: ' . mysql_error());
   }
	
   $table_name = "wp_options";
   $backup_file  = "/tmp/wp_options.sql";
   $sql = "LOAD DATA INFILE '$backup_file' INTO TABLE $table_name";
   
   mysql_select_db('wp_db');
   $retval = mysql_query( $sql, $conn );
   
   if(! $retval ) {
      die('Could not load data : ' . mysql_error());
   }
   echo "Loaded  data successfully\n";
   
   mysql_close($conn);
?>
```

## Backup using the mysqldump utility

We can also use the utility `mysqldump`. Here is an example of `mysqldump` usage.

```php
<?php
   $dbhost = 'localhost';
   $dbuser = 'root';
   $dbpass = 'password';
   
   $backup_file = $dbname . date("Y-m-d-H-i-s") . '.gz';
   $command = "mysqldump --opt -h $dbhost -u $dbuser -p $dbpass ". "wp_db | gzip > $backup_file";
   
   system($command);
?>
```

