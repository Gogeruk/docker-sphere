
sos:
https://matthewsetter.com/setup-step-debugging-php-xdebug3-docker/
https://dev.to/jackmiras/xdebug-in-phpstorm-with-docker-2al8


1.
hostname -I | cut -d ' ' -f1

2.
in :
php/conf.d/xdebug.ini
do:
xdebug.client_host=<ip>

3.
put php-sphere in /app

4.
make sure that in:
app/config.ini
is:
url = http://localhost:8080

5.
http://localhost:8080/









