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

