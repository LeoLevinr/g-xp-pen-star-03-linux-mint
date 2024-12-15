# Utiliser la tablette XP-PEN "Star 03" sous Linux Mint en utilisant le driver par défaut

Ce tuto ne prend en compte que les tablettes graphiques XP-Pen Star 03 sur Linux Mint, il peut sans doute être adapté pour d'autre tablette ayant le même problème par contre. Je fais ce tuto car ma tablette graphique ne marche jamais sans OpenTabletDriver", l'ajouter résout le problème, mais le mode artiste m'oblige à forcer sur ma tablette pour une faible pression.

# Requis :
- Environnement sous X11.
- Éditeur de Texte.
- OpenTabletDriver (ne pourra pas être utilisé pour configurer la tablette).


#0 :
    Ne pas brancher la tablette. (Rien de dangereux, juste un conseil pour plus tard.)

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

#4 :
    Installer OpenTabletDriver.

# Utiliser la tablette graphique.

#5 :
    Lancer "otd-daemon".

#6 :
    Brancher la tablette graphique.

#7 :
    Fermer "otd-daemon".

#8 :
    Si tout ce passe bien le stylet devrait faire bouger le curseur ! 
    De mon côté je ne peux pas configuer la tablette avec le configurateur par défaut de Linux Mint, si c'est aussi votre cas vous pourriez peut-être utiliser le logiciel "OpenTabletUI" : [https://github.com/Mainman002/Linux-OpenTabletUI].

# Au cas ou.

 Je ne suis pas un expert à ce sujet, donc si vous avez une erreur je ne pourrais sans doute pas vous aider.
