# BitrixVM 7 под vagrant

Для работы требуются плагин vagrant-vbguest

Порядок запуска

vagrant plugin install vagrant-vbguest
vagrant up

Есть проблемы с vbguest на VirtualBox последней версии
корректно работает на http://download.virtualbox.org/virtualbox/5.0.32/VirtualBox-5.0.32-112930-Win.exe

Почта отключена.
Для разработки включаем отправку всех писем к себе на почту:
# echo "sendmail_path = /usr/sbin/sendmail -t -i" >> /etc/php.d/z_bx_custom_settings.ini
# echo "/.+@.+/ email@example.com" > /etc/postfix/virtual-regexp
# echo "virtual_maps = hash:/etc/postfix/virtual, regexp:/etc/postfix/virtual-regexp" >> /etc/postfix/main.cf
# postmap /etc/postfix/virtual  
# postmap /etc/postfix/virtual-regexp  
# apachectl graceful
# systemctl restart postfix

после этого вся почта будет уходить на email@example.com