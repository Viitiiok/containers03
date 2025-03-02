# containers03

# Lucrare de laborator: Introducere în containerizare cu Docker

# Scop

Această lucrare de laborator are scopul de a familiariza utilizatorii cu elementele de bază ale containerizării și de a pregăti mediul de lucru pentru lucrările viitoare.

# Sarcina

Instalarea Docker Desktop și verificarea funcționării acestuia.

Crearea unui repozitoriu containers03 și clonarea acestuia pe computer.

Crearea unui fișier Dockerfile și a unui director site cu un fișier index.html.

Construirea imaginii Docker și rularea containerului.

Verificarea conținutului în container și ștergerea acestuia.

# Executare

1. Instalare Docker Desktop

Am descărcat și instalat Docker Desktop

2. Creare repozitoriu și structură de fișiere

Am creat și clonat repozitoriul containers03 și am adăugat următoarele fișiere:

Dockerfile:
FROM debian:latest
COPY ./site/ /var/www/html/
CMD ["sh", "-c", "echo hello from $HOSTNAME"]

index.html: (în directorul site/)

3. Construirea imaginii și rularea containerului

Am executat comanda pentru a construi imaginea:

docker build -t containers03 .

Durata construirii imaginii: Aproximativ 10 secunde (imagine).

Am rulat containerul cu comanda:

docker run --name containers03 containers03

Rezultatul afișat în consolă: hello from ef57ab591a86

4. Verificarea conținutului containerului

Am șters containerul și l-am pornit din nou în modul interactiv:

docker rm containers03
docker run -ti --name containers03 containers03 bash

În interiorul containerului am verificat conținutul directorului /var/www/html/:

cd /var/www/html/
ls -l

Rezultatul afișat: Listarea fișierului index.html

Am ieșit din container cu comanda: exit

Concluzii:

Am reușit să instalez și să configurez Docker Desktop.

Am creat și construit o imagine Docker pe baza unui Dockerfile personalizat.

Am rulat un container și am verificat conținutul fișierelor copiate în el.

Containerizarea facilitează gestionarea aplicațiilor într-un mediu izolat și reproductibil.

Bibliografie: Docker Documentation
