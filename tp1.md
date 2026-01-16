1/a: classe B
1/b oui

1/c : 

utilisation de la machine 172.16.1.0:
ping 172.16.1.1 | ok
ping 172.16.1.2 | ok
ping 172.17.1.3 | pas de reponse

utilisation de la machine 172.16.1.1:
ping 172.16.1.0 | ok
ping 172.16.1.2 | ok
ping 172.17.1.3 | pas de reponse

utilisation de la machine 172.16.1.2:
ping 172.16.1.1 | ok
ping 172.16.1.0 | ok
ping 172.17.1.3 | pas de reponse

utilisation de la machine 172.17.1.3:
ping 172.16.1.1 | pas de reponse
ping 172.16.1.2 | pas de reponse
ping 172.16.1.0 | pas de reponse

car elle n'est pas sur le meme reseau local et deplus les ip en 172 sont réserver 

masque en 255.0.0.0 est bon 

| Cas N° | PC1 Adresse IP      | PC1 Masque         | PC2 Adresse IP      | PC2 Masque         | Communication possible ? |
|-------:|---------------------|--------------------|---------------------|--------------------|---------------------------|
| 1      | 25.0.26.27          | 255.0.0.0          | 25.1.26.27          | 255.0.0.0          | oui                       |
| 2      | 10.100.255.0        | 255.255.0.0        | 10.99.255.0         | 255.255.0.0        | non                       |
| 3      | 100.0.1.2           | 255.255.255.0      | 100.0.2.1           | 255.255.255.0      | non                       |
| 4      | 128.10.0.1          | 255.255.0.0        | 128.1.0.1           | 255.255.0.0        | non                       |
| 5      | 190.191.192.193     | 255.255.128.0      | 190.191.189.1       | 255.255.128.0      | oui                       |
| 6      | 220.0.0.7           | 255.255.255.0      | 220.0.0.12          | 255.255.255.0      | oui                       |
| 7      | 192.0.168.79        | 255.255.255.224    | 192.0.168.65        | 255.255.255.224    | oui                       |
| 8      | 215.172.23.31       | 255.255.255.128    | 215.172.23.130      | 255.255.255.128    | non                       |
|--------------------------------------------------------------------------------------------------------------------------|

4/ le hub sera plus lent pour renvoyer l'info