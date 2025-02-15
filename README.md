# Utiliser la tablette XP-PEN "Star 03" sous Linux Mint en utilisant le driver par défaut.

Ce tuto ne prend en compte que les tablettes graphiques XP-Pen Star 03 sur Linux Mint, mais il peut sans doute être adapté pour d'autre tablette ayant le même problème. 


# Requis :
- Environnement sous X11.
- Éditeur de Texte.


#Si OpenTabletDriver est installé : Ne pas brancher la tablette. (Rien de dangereux, juste un conseil pour plus tard.)

# Préparations.

#1 :
    Ouvrir en sudo avec un éditeur de texte au choix le fichier "70-wacom.conf" dans le chemin "/usr/share/X11/xorg.conf.d/"

#2 :

 À la fin du fichier, ajouter le bloc de texte si dessous :
#	

	    # Star 03 Pen Tablet
	    Section "InputClass"
		    Identifier "XP-Pen Star 03 Pen Tablet"
	    	MatchProduct "UC-Logic"
	        MatchUSBID "5543:*"
	    	MatchDevicePath "/dev/input/event*"
	        Driver "wacom"
	    EndSection
#
#3 :
    Redémarrer la session.

# Si OpenTabletDriver est déjà installé.

#4 :
    Lancer "otd-daemon".

#5 :
    Brancher la tablette graphique.

#6 :
    Fermer "otd-daemon".

# Conclusion.

#7 :
    Si tout ce passe bien le stylet devrait faire bouger le curseur !

# Au cas ou.

Le configurateur par défaut de Mint peu prendre un peu de temps avant que la tablette soit reconnu.

Je ne suis pas un expert à ce sujet, donc si vous avez une erreur je ne pourrais sans doute pas vous aider.
