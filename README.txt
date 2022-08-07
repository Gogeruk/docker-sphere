
sos for xdebug:
https://matthewsetter.com/setup-step-debugging-php-xdebug3-docker/
https://dev.to/jackmiras/xdebug-in-phpstorm-with-docker-2al8


1.
get <ip>
hostname -I | cut -d ' ' -f1

2.
in
php/conf.d/xdebug.ini
do
xdebug.client_host=<ip>

3.
put
<PHP SPHERE PROJECT>
in
/app

4.
make sure that in
app/config.ini
is
url = http://localhost:8080

5.
docker-compose up -d --build

6.
go into php docker container
and install stuff

7.
go to
http://localhost:8080/









