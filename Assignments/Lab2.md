# UNDERSTANDING HOW EXISTING SCRIPTS IN REPO WORKS

## *script-1*
```
 #!/bin/bash      - shebang
 echo "Hello world !"     - printing hello world
 name="Reyan chauhan"   - taking Reyan chauhan in variable "name".
 age=17    -  taking 17 in variable "age" 

 echo "My name is $name ansd I am $age year old."  - printing name and age.
```
## OUTPUT:

<img width="535" height="198" alt="image" src="https://github.com/user-attachments/assets/54ca006f-ad6e-4029-9a00-7fd56de819e2" />


<img width="473" height="128" alt="image" src="https://github.com/user-attachments/assets/fc4636ce-fd1b-44b4-8858-54b9b047fa9e" />


##  *Script-2*

```
#!/bin/bash        -shebang
a="Reyan"           -taking Reyan in the variable 'a'.
b=21                 -taking 21 in the variable 'b'.

if [ $a="Reyan" ] && [ $b -gt 18 ]; then      -checking conditions and using an opreator and(&&)
    echo " you are adult "                     - printing you are adult
fi

if [ $a=" lakshay" ] && [ $b -lt 18 ]; then       -checking conditions and using an opreator and(&&)
    echo "you are minor"                         - printing you are minor
fi

```
<img width="546" height="256" alt="image" src="https://github.com/user-attachments/assets/f4002c7f-8922-4405-bf27-93fd858ade85" />

<img width="546" height="119" alt="image" src="https://github.com/user-attachments/assets/1776c22d-83b0-42fa-a178-21d867071b3f" />

###  Q1).What is the purpose of #!/bin/bash at the top of the script?
ANS~ The shebang line at the top of a script specifies the interpreter that should be used to the run the script.

###  Q2).How do you make a script executable?
ANS~ * 1. Add the shebang at the top.
     * 2. give permission using the chmod command
     * 3. run the code.
