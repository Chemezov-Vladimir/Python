##Задание 1

Есть скрипт:

'#!/usr/bin/env python3

a = 1  
b = '2'  
c = a + b


    1. Какое значение будет присвоено переменной c?
    2. Как получить для переменной c значение 12?
    3 .Как получить для переменной c значение 3?

###Решение

1. Будет ошибка, так как "+" не поддерживает сложение типов 'int' и 'str'
2. Сделать обе переменные строковыми: c = str (a) + b
3. Сделать обе переменные целочисленными: c = a + int (b)

##Задание 2

Мы устроились на работу в компанию, где раньше уже был DevOps Engineer. Он написал скрипт, позволяющий узнать, какие файлы модифицированы в репозитории, относительно локальных изменений. Этим скриптом недовольно начальство, потому что в его выводе есть не все изменённые файлы, а также непонятен полный путь к директории, где они находятся. Как можно доработать скрипт ниже, чтобы он исполнял требования вашего руководителя?

    "#!/usr/bin/env python3"
    
    import os

    bash_command = ["cd ~/netology/sysadm-homeworks", "git status"]  
    result_os = os.popen(' && '.join(bash_command)).read()  
    is_change = False  
    for result in result_os.split('\n'):  
        if result.find('modified') != -1:  
            prepare_result = result.replace('\tmodified:   ', '')  
            print(prepare_result)  
            break

###Решение

Первым делом не увидел, где используется булева переменная is_change. 