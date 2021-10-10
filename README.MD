# DOCUMENTATION DU SERVEUR 

## Premiere tache : 
#### Acceder au serveur 

Nous avons installé un serveur web Apache2, grâce aux commandes : 
- sudo apt update 
- sudo apt install apache2

nous avons ainsi, deux fichier de configuration principal d'apache que nous allons utilisé pour nos test avec docker : 

- /etc/apache2/sites-enabled/000-default.conf
- /var/www/html/index.html

Nous créons ensuite un projet Github sur lequel nous allons déployer nos fichier de configuration : 

- Le nom du projet est p_tp1 
- Dans ce dossier nous copions les fichiers de configurations mentionnés plus haut. 
- Enfin nous ajoutons dans les projets github ces fichiers avec les commandes dans la branche master: 	     - git init 
        - git add 000-default.conf
        - git add index.html
        - git commit -m 'commentaire'
	- git config --global user.name "MathieuLaision"
	- git commit --global user.email "mahieuthelast@gmail.com"
	- git commit -m "commit tp1"
	Création de la branche master : 
	- sudo git branch -M master  
        - git remote add origin https://github.com/MathieuLaision/tp1.git
        - git push -u origin master 

- Modification de la branche master : 
	-Création d'une branche de modification : 
		git branch "modification_tp1"
	-Basculement vers la nouvelle branch : 
		git checkout modification_tp1
	-Ensuite nous modifiions le fichier de configuration de la page web : 
		vim index.html 
		git add index.html 
		git commit -m "changement_master" 
		git checkout master 
		git merge modification_tp1
		git push -u origin master 

## Deuxieme tache 

#### Docker 

- construction d'une image docker avec le service apache : 
	- mkdir docker
	- cd ./docker 
	- cp sudo cp /etc/apache2/sites-enabled/000-default.conf .
	- cp /var/www/html/index.html .
	- vim Dockerfile
	- docker build . 
	- docker images
	- docker run -it 69
	- apt install vim 
	- vim /ect/hostname 
	changer le nom de la machine par localhost 
	changer le nom du server dans la configuration d'apache2 par localhost 
	- vim /etc/apache2/sites-enabled/000-default.conf 
	start le service apache2 
	-service start apache2 
fin 


