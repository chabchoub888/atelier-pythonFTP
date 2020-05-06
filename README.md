# atelier-pythonFTP
import ftplib as FTP
from ftplib import FTP
from getpass import getpass

host = "192.168.1.212"
ftp = FTP('192.168.1.212', 'user', getpass())

liste = ["creer", "renommer", "supprimer", "deplacer"]

# Connexion
print ("Connexion a " +host)
etat = ftp.getwelcome()
print ("Etat : ",etat)

print(liste)
choix = input("Que voulez vous faire ? ")

# Créer un répertoire
if choix == liste[0]:
nom = input("Nom ? ")
ftp.mkd(nom)

# Renommer un répertoire
if choix == liste[1]:
nom = input("Nom a renommer ? :")
nom2 = input("Nouveau nom ? : ")
ftp.rename(nom,nom2)

# Supprimer un répertoire
if choix == liste[2]:
nom = input("Nom ? ")
ftp.rmd(nom)

# Renommer
if choix == liste[3]:
nom = input("Nom a deplacer ? ")
ftp.sendcmd(nom)

#print(ftp.dir())
