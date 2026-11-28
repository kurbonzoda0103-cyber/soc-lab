# Day 5: What happens when I open a website

## Steps (по порядку)
1. DNS: send request, IP:fe80::d1c3:a6b4:e973:6d4c, port: 53, Protocol: UDP, получил ответ example.com: type HTTPS, class IN
2. TCP handshake: таблица

| Packet | Flags | Who sends   | Seq/Ack    |
  54       SYN     port: 54581  seq=1 ack=1 
  54       syn-ack  port: 443   seq=1 ack=1401
  54       ack     port: 54581  seq=1890 ack=4282
|--------|-------|-----------|---------|

3. Дальше (HTTPS): после handshake идет отправка пакетов

## Evidence
- captures/day5_dns.pcapng: результаты захвата трафика по теме dns на домене example.com, указаны DNS request and DNS response
- captures/day5_tcp.pcapng: результаты захвата трафика по теме tcp на домене example.com и 3 way handshake 

## Glossary
DNS - domain name system, это протокол которое хранить в себе все имена сайтов и выдает по ip запросу
A record - IPv4 request
AAAA - IPv6 request
resolver - convert domain names into IP
SYN - запрос ты слышишь?
ACK - ответ да
RTT - время туда обратно syn, syn-ack,ack в ms
TCP -Transmission Control Protocol - протокол отправки которая отправляет и ждет успешного потверждения, пока не добьется подключения, UDP - Unit Datagram Protocol - протокол без гарантии доставки пакетов

## Мои ошибки сегодня
Что понял неправильно и как правильно
