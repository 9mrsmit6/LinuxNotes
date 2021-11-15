# Заметки по линуксу и его настройке
## Пароль рута
sudo passwd root
## Настройка ssh
https://itigic.com/ru/configure-openssh-server-on-linux-with-maximum-security/
1) Вообщем настраиваем etc/ssh/sshd-config Настраиваем порт и конфигаруцию аутенфикации
2) Незабываем закинуть в ~/.ssh/autorized_keys открытые ключи клиентов
3) Прописать корректные права (для папки .ssh 755 для autorized_keys 600)
4) Для ConnectBot надо прописывать локаль вручную при старте сесии export LC_ALL= До конца не разобрался

Пример конфига ниже

## Утилита screen
https://losst.ru/komanda-screen-linux

1) создаем с именем `sh screen -S name`
2) открываем с именем `sh screen -r name`
3) отключить окно (когда клиент по SSH отваливается помагает) `sh screen -d name`
4) Свернуть окно Ctrl+A D

## Docker под виндой с WSL2
Большая проблема с перемешением хранилищ с образами и дистрибутивами в другое место.  
Использование  
`"data-root":"address"`  
в deamon.json не помогает. Виснет и все.  
Исправил через серию команд  
`wsl --export  
wsl --unregister  
wsl --import`   
Тогда при обращениии к WSL докер не сходит с ума, а данные лежат в новом месте.  
Нужно чтобы не насиловать SSD
