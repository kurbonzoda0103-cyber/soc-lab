# Day 3: ICMP, ping, traceroute

## ping
- Echo Request (Type 8) - это запрос к к целевому устройству
- Echo Reply (Type 0): - это ответ что есть сигнал от целевого устройства
- TTL: Request 128 - это стартовое значение счетчика на пакете
- Reply 117 -  означает столько значений осталось и прошла только 11 роутеров
- RTT in my capture: это время туда обратно в 395ms

## traceroute
- How it works (TTL 1, 2, 3... and Time Exceeded Type 11):- tracert сначала шлёт пакет с TTL = 128, затем с TTL вычитает 1 каждый роутер и так далее. Роутер, на котором TTL становится 0, выбрасывает пакет и присылает записку (Type 11), так я узнаю его адрес.
- My route to 8.8.8.8: 
 hops -10  
 first hop- default gateway 
 where time grows: на 5 уровне начинает расти ping
- What * means: что все рядом роутера получает сигнал нормально а некоторые могут просто молчать на iCMP запросы

## ICMP vs TCP/UDP
- Why ICMP has no ports: потому что он для диагностики сети а не для отправки медиа

## SOC note
- Why no ping reply does not mean host is down: Потому что марщрутизатор может иногда отклонить ICMP запрос

## Glossary
- ICMP - Internet Control Message Protoсol служебный протокол диагностики сети
Echo Request - запрос с кодом 8
Echo Reply - ответ с кодом 0
TTL - Time to Live время жизни запроса
RTT - время туда и обратно
hop - прыжок, имеется ввиду от роутеру к другому 
Time Exceeded - записка от роутера
