# Encrypt
encrypt shell code
 8
down vote

Got this while searching internet,courtesy Claudio P.

    Write your script (script-base.sh)

    #!/bin/sh 
    echo "Hello World" 

    Encrypt your script (give a password):

    openssl enc -e -aes-256-cbc -a -in script-base.sh > script-enc 

    Write de Wrapper (script-final.sh):

    #!/bin/sh 
    openssl enc -d -aes-256-cbc -a -in script-enc | sh - 
    passing password in command
     openssl enc -d -aes-256-cbc -a -in test-enc -pass pass:12345 | sh -


    Run "script-final.sh", enter the password, and the script will run without write the plain text script on disk.

