# Day 5: What happens when I open a website

## Steps (по порядку)
1. DNS: send request, IP:fe80::1, port: 53, Protocol: UDP, получил ответ example.com: type HTTPS, class IN и IP: 104.20.23.154 и 172.66.147.243
2. TCP handshake: таблица

| Packet | Flags   | Who sends | Seq/Ack    |
  1      | SYN     | client    | seq=0 ack=0 
  2      | syn-ack | server    | seq=0 ack=1
  3      | ack     | client    | seq=1 ack=1

3. Дальше (HTTPS): после handshake идет http внутри TLS

## Evidence
- captures/day5_dns.pcapng: результаты захвата трафика по теме dns на домене example.com, указаны DNS request and DNS response
- captures/day5_tcp.pcapng: результаты захвата трафика по теме tcp на домене example.com и 3 way handshake 

## Glossary
DNS - domain name system, это протокол которое хранить в себе все имена сайтов и выдает по запросу их ip
A record - IPv4 address
AAAA - IPv6 address
resolver - convert domain names into IP
SYN - запрос ты слышишь?
ACK - ответ да
RTT - время туда обратно syn, syn-ack,ack в ms
TCP -Transmission Control Protocol - протокол отправки которая отправляет и ждет успешного потверждения, пока не добьется подключения, UDP - User Datagram Protocol - протокол без гарантии доставки пакетов

