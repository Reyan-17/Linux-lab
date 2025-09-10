# modifying script

## original script

```
#!/bin/bash        ---shebang
a="Reyan chauhan"           ---taking vansh in the variable a
b=40                 ---taking 40 in the variable b

if [ $a="Reyan chauhan" ] && [ $b -gt 18 ]; then      ---checking conditions and using an opreator and(&&)
    echo " you are adult "                     ---printing you are adult
fi

if [ $a="Lakshay" ] && [ $b -lt 18 ]; then       ---checking conditions and using an opreator and(&&)
    echo "you are minor"                         --- printing you are minor
fi

```
<img width="561" height="259" alt="image" src="https://github.com/user-attachments/assets/1b50185d-20f8-49a5-8410-8c34d8465d28" />
<img width="561" height="162" alt="image" src="https://github.com/user-attachments/assets/3ce12dca-97ef-4eb9-a05e-961d9d2a8cb8" />

##  modified script

```
#!/bin/bash 
# prompt user for input

read -p "enter your name: " name      --- taking name from the user
read -p "enter your age: " age        --- taking age from the user

if [ $name="Reyan chauhan" ] && [ $age -gt 18 ]; then    --- checking conditions with if and opreator and(&&)     
    echo " you are adult "                     --- printing (you are adult)
fi

if [ $name="Lakshay" ] && [ $age -lt 18 ]; then  ----  checking conditions with if and opreator and(&&)      
    echo "you are minor"                         ---- printing (you are minor)
fi
```
## the difference between the original and modified script is that in the first one we check for fixed value and in the next case we check for all cases .

<img width="564" height="277" alt="image" src="https://github.com/user-attachments/assets/75edf699-50ee-4c71-8299-bef8019450b6" />

## checking with differnt examples
#### output is :

<img width="564" height="227" alt="image" src="https://github.com/user-attachments/assets/fd164ad5-37d0-4463-a54f-1fa999b92d52" />

### Q1).differnce between $1,$@ and $# in bash?

Ans $1= this refers to positional parameters.
    $@= represents all arguments passed to the script.
    $#= returns the number of arguments passed.

### Q2).what does exit 1 mean in the script
    
Ans~general error (something went wrong) Or exit with error.



