
## 1. Frame 3976 breakdown (OSI layers)
- Physical: signal
- Data Link (Src MAC: Intel_c8:70:b2 (40:c7:3c:c8:70:b2)/ Dst MAC: HuaweiTechno_4f:6b:bb (14:a0:f8:4f:6b:bb):
- Network (Src IP: 192.168.100.5 / Dst IP: 3.174.18.103):
- Transport (protocol: TCP / Source Port: 55752 Destination Port: 443):
- Presentation/Application: HTTPS/HTTP внутри TLS

## 2. What changes hop by hop
- IP address: не меняется, остаётся 3.174.18.103 до конца
- MAC address: меняется на каждом участке, на первом участке это MAC шлюза
- Why: Dst MAC меняется потому что запрос к другой сети, MAC не может узнать адрес другого компютера посредством ARP запроса, поэтому отправляет кадр на router и он к следующему.

## 3. My network
- IPv4 Address: 192.168.100.5
- Subnet Mask:255.255.255.0
- Default Gateway:  192.168.100.1
- Network address:  192.168.100.0
- Broadcast address:  192.168.100.255
- Host range: 1-254
- Number of hosts: 2⁸ − 2 = 254:

## 4. ARP cache (arp -a)
- Gateway MAC: 14-a0-f8-4f-6b-bb 
- Does it match Dst MAC in Frame 3976? Why: Потому что dst mac это адрес шлюза роутера

## 5. Glossary
- OSI model — состоит из 7 уровней: physical, data link, network, transport, session, presentation, application layer
- MAC address — media access control уникальный идентификатор сетевого интерфейса устройства обычно в 16-чном виде из 48 бит
- IP address — уникальный идентификатор устройства в компютерной сети, есть два вида IPv4 32bit и IPv6 128bit
- subnet mask — маска сети которое разделяет ipv4 на две части - часть сети и часть хоста
- Default Gateway — Это адрес шлюза через которое устройства выходят на другие сети
- ARP — это протокол которое связывает логический ip адрес устройства с его физическим mac адресом
