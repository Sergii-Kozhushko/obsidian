- VARS
env - посмотреть переменные
unset MYVAR - удалить перменную
export PATH=$PATH:/opt/local/bin - добавить путь  переменной PAth

- SSH
ssh copy id
ssh-keygen -t rsa - создать новую пару ключей

- USER
id - посмотреть в каких группах я состою
w - -u активнеы пользователи
export HISTCONTROL=ignorespace, команды, которые начинаются с проблеа, в историю не записываются

-INFO
df -h
last - просмотр пользовательских сессий
uname - информация о системе
htop - текущие процессы
uptime - время работы сервера от последнего включения
ps aux -  процессы в реальном времени, shift-m  внутри - показать какой процесс занимает больше всего времени
cat /proc/cpuinfo
who -u - ссш-сессии с айпи


-DIR/FILE
ls -R рекурсивынй просмотр каталогов
rm -rf dir - удалить каталог и его подкаталоги
du -hs - показывает суммарный размер файлов в текущей директории 
file -s filename - определение формата файла
touch - create file

-ZIP
gzip -9 filename - сжать файл
tar cvf name.tar *.txt - создать архив
tar xvf name.tar - распаковать архив tar
tar -xvf arch.tar.gz arch/psswd - извлечь один файл
tar cvfz name.tar.gz *.txt - упаковать и сжать одной командой
tar -tvf arch.tar -  посмотреть что внутри
gunzip filename.gz - распаковатать архив gz

-WEB
wget -O filename URL_полная_ссылка - скопировать содержимое по ссылке в файл
scp -R usernamee@someserver.de:/home/*.* . - скопировать файлы рекурсивно с сервера себе на машину. Выпонять у себя

-CRON
crontab -e - открыть на редактирование таблицу с расписанием задач крон
cron -l  - посмотреть кронтаб
https://crontab.guru/ - примеры задания значения времени

-VIM
:wq! - сохранить и выйти
:q! - выйти без сохранения
:set nu! - включить нумерацию строк
dd - удалить тек строку
u - отмена посл команды
w/b - вперед-назад на слово
dw - dw - удалить слово вперед- слово назад
cw - заменить слово вперед
cb - заменить слово назад

-NANO
Alt-A - начать выделение
Ctrl-K - вырезать
Alt-6 - скопировать
Ctrl-U - вставить

-BASH
#!/bin/bash - писать в начале фалй скрипта
echo "Home for the current user is: $HOME"
grade=5
person="Adam"
echo "$person is a good boy, he is in grade $grade"
mydir=`pwd`
echo $mydir - #выполнить команду

user=operator123
if grep $user /etc/passwd
then
echo "The user $user Exists"
else
echo "The user $user doesn’t exist"
fi


-OTHER
cat /dev/random | head -5 > file.txt - читает 5 строчек из файла random (устройстов генерации случайных команд) и перезаписывает их (не дополняет) в файл 
https://www.thc.org/segfault/ - тестовый сервер с рутом
https://bellard.org/jslinux/vm.html?url=alpine-x86.cfg&mem=192 - песочница
ctr-l -  очистить экран

-LINKS
Прокси:
proxifier
nord vpn
OpenVPN Connect
Аренда серверов:
mvps - серый
digital ocean - белый

pritunl - впн клиент