# incorrect-format-parameter
xampp - phpmyadmin

While importing a database, if you face "incorrect format parameter" error
you can resolve it by following 3 steps:


1. Make sure the Collation of the exported database is the same as the newly created one.

2. Make these changes in my php.ini(xampp/php/php.ini) file

    max_execution_time = 5000
    max_input_time = 5000
    memory_limit = 1000M
    post_max_size = 750M
    upload_max_filesize = 750M
    
3. Make this change in my \phpmyadmin\libraries\config.default.php file:

    change

      $cfg['ExecTimeLimit'] = 300;
    
    to

      $cfg['ExecTimeLimit'] = 0;

    (So there is no limit)
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    #Solution from 
    https://stackoverflow.com/questions/50201874/xampp-phpmyadmin-incorrect-format-parameter
