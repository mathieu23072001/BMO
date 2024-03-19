ExceptionConsulteCompte

L'acteur (utilisateur) initie le processus en se connectant à son compte sur la plateforme de paris en ligne.
Le système de paris en ligne vérifie les informations de connexion dans la base de données.
En cas d'erreur, c'est-à-dire si les informations de connexion sont incorrectes :
La base de données renvoie un message d'erreur au système de paris en ligne.
Le système de paris en ligne renvoie à l'acteur un message d'erreur indiquant que les informations de connexion sont incorrectes et l'invite à réessayer.

ExceptionGestionEvenSportif

L'acteur (bookmaker) initie le processus en accédant à la plateforme de paris en ligne et en sélectionnant l'option "Gestion des événements sportifs".
L'interface utilisateur envoie une requête de gestion des événements sportifs au système de paris.
Le système de paris, à son tour, tente de récupérer les informations en temps réel sur les événements sportifs auprès des sources de données.
Cependant, une exception se produit car aucune donnée n'est disponible à ce moment-là.
Le système de paris informe l'interface utilisateur de cette exception en affichant un message d'erreur indiquant "Aucun événement sportif disponible".

ExceptionGestionParamParis

L'acteur (bookmaker) accède à la plateforme de paris en ligne et sélectionne l'option "Paramètres de paris".
L'interface utilisateur envoie une demande de gestion des paramètres de paris au système de paris.
Le système de paris récupère les paramètres actuels des paris à partir de la base de données.
Les paramètres actuels sont renvoyés au système de paris, qui les affiche ensuite dans l'interface utilisateur.
Le bookmaker modifie les paramètres selon ses préférences via l'interface utilisateur.
L'interface envoie les nouveaux paramètres au système de paris.
Cependant, une erreur survient lors de la tentative de mise à jour des paramètres dans la base de données.
Le système de paris renvoie un message d'erreur à l'interface utilisateur.
L'interface utilisateur affiche également ce message d'erreur pour informer le bookmaker de l'incident.

ExceptionInscription

L'acteur (utilisateur) remplit le formulaire d'inscription sur l'interface.
L'interface transmet les informations d'inscription au système d'inscription.
Le système d'inscription vérifie la disponibilité du nom d'utilisateur dans la base de données.
Cependant, il est détecté que le nom d'utilisateur est déjà pris, ce qui entraîne une erreur.
Le système d'inscription renvoie un message d'erreur au module d'interface pour informer l'utilisateur que le nom d'utilisateur est déjà pris.
L'interface affiche alors un message d'erreur à l'utilisateur, l'invitant à choisir un autre nom d'utilisateur.

ExceptionPlacéParisAvancé

L'acteur (utilisateur) choisit un événement sportif sur l'interface.
Le système en ligne vérifie la disponibilité de l'événement dans la base de données.
Cependant, il est détecté que l'événement choisi n'est pas disponible, ce qui entraîne une erreur.
Le système renvoie un message d'erreur à l'acteur, l'informant que l'événement sélectionné n'est pas disponible.
L'acteur est alors invité à choisir un autre événement disponible.



ExceptionPlacéParisSimple

L'acteur (utilisateur) choisit un événement sportif sur l'interface.
Le système en ligne vérifie la disponibilité de l'événement dans la base de données.
Lorsque l'événement choisi n'est pas disponible, le système détecte cette erreur.
Le système renvoie un message d'erreur à l'utilisateur, l'informant que l'événement sélectionné n'est pas disponible.
L'utilisateur est alors invité à choisir un autre événement disponible.


ExceptionRechargerJeton

L'acteur (parieur) accède à la plateforme de paris en ligne et sélectionne l'option "Recharger jeton" via l'interface utilisateur.
L'interface envoie une requête de rechargement de jeton au système en ligne.
Le système initie un transfert de fonds vers la banque pour recharger les jetons du parieur.
En cas d'échec du transfert de fonds, la banque renvoie une notification au système indiquant l'échec du transfert.
Le système, détectant cette exception, affiche un message d'erreur à l'interface utilisateur, indiquant que le rechargement a échoué et invite le parieur à réessayer.
L'interface propose alors une autre méthode de recharge au parieur pour lui permettre de recharger ses jetons de manière alternative.

