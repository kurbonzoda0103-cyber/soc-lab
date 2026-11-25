# Day 3: ICMP, ping, traceroute

## ping
- Echo Request (Type 8) - это запрос есть ли сигнал от роутера
- Echo Reply (Type 0): - это ответ что есть сигнал
- TTL: Request 128 - это начала связывания и каждый роутер отнимает 1 и оставляет записку
- Reply 117 -  означает столько роутеров прошла
- RTT in my capture: это время туда обратно в ms

## traceroute
- How it works (TTL 1, 2, 3... and Time Exceeded Type 11):- команда tracert на windows показывает сколько роутеров подключается пока доходит до сервера и записка от каждого роутера и код 11 означает записку
- My route to 8.8.8.8: 
 hops -10  
 first hop- default gateway 
 where time grows: на 5 уровне начинает расти ping
- What * means:

## ICMP vs TCP/UDP
- Why ICMP has no ports: потому что он для диагностики сети а не для отправки медиа

## SOC note
- Why no ping reply does not mean host is down: Потому что марщрутизатор может иногда отклонить ICMP запрос

## Glossary
- ICMP - Internet Control Message Protokol служебный протокол диагностики сети
Echo Request - запрос с кодом 8
Echo Reply - ответ с кодом 0
TTL - Time to Live время жизни запроса
RTT - туда обратно
hop - следующий прыжок имеется ввиду от роутеру к другому 
Time Exceeded - записка от роутера
