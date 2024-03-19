User : Cette classe abstraite représente un utilisateur du système de paris en ligne. 
Elle a des attributs privés tels que userId (identifiant de l'utilisateur), email et loginStatus (statut de connexion).
 Elle a également une méthode publique login qui prend en paramètres l'email et le mot de passe de l'utilisateur pour se connecter.
Parieur et Bookmaker herite de cette classe.

Parieur : Cette classe représente un parieur dans le système. Elle a un attribut privé jeton pour stocker le nombre de jetons de pari du parieur. 
Les méthodes publiques incluent parisSimple et parisComplexe pour placer des paris simples ou complexes respectivement, ajouterJeton pour ajouter des jetons au compte du parieur et retirerArgent pour retirer de l'argent.

Bookmaker : Cette classe représente un bookmaker dans le système. 
Elle a des méthodes publiques telles que ajouterEvenement pour ajouter un événement au système et paramètreParis pour définir les paramètres des paris.

Sport : Cette classe représente un sport pris en charge par le système. Elle a un attribut privé sportLabel pour stocker le nom du sport.

Regle : Cette classe représente les règles associées à un sport. Elle a un attribut privé regleLabel pour stocker le nom de la règle.

paris : Cette classe représente un pari dans le système. 
Elle a des attributs tels que coteParam (cote du pari), montantLimite (limite de montant pour le pari) et créditLimite (limite de crédit pour le pari). 
La méthode publique parier permet de placer un pari.

ParisSimple : Cette classe représente un type spécifique de pari simple. Elle a un attribut numGagnant pour stocker le numéro gagnant.

ParisComplexe : Cette classe représente un type spécifique de pari complexe.
 Elle a des attributs score et temp pour stocker le score et le temps associés au pari complexe.

Evenement : Cette classe représente un événement sportif. 
Elle a des attributs tels que eventLabel (libellé de l'événement), Heure (heure de l'événement) et Date (date de l'événement).

SourceDonnees : Cette classe représente une source de données externe qui fournit des mises à jour sur les événements sportifs. 
Elle a une méthode publique miseAjourEvenement pour mettre à jour les événements.


Les  associations :

Parieur -g-> User : Cette association signifie que la classe Parieur hérite de la classe User. Cela indique que la classe Parieur possède toutes les caractéristiques et comportements d'un utilisateur, avec des fonctionnalités supplémentaires spécifiques aux parieurs.

Bookmaker -g-> User : De manière similaire à l'association précédente, cette association signifie que la classe Bookmaker hérite également de la classe User, lui conférant ainsi toutes les fonctionnalités d'un utilisateur en plus des fonctionnalités spécifiques aux bookmakers.

ParisComplexe -g-> paris : Cette association indique que la classe ParisComplexe est une spécialisation de la classe paris. Cela signifie qu'un pari complexe est un type spécifique de pari.

ParisSimple -g-> paris : De manière similaire à l'association précédente, cette association signifie que la classe ParisSimple est une spécialisation de la classe paris, ce qui en fait un type spécifique de pari.

paris  "0..*" -- "1"  Evenement : "misé" : Cette association signifie qu'un pari est associé à un événement. Un événement peut avoir plusieurs paris (0..*) tandis qu'un pari est associé à un seul événement (1). La relation est étiquetée avec "misé" pour indiquer la nature de l'association, à savoir que le pari est placé sur l'événement.

Evenement "0..*" -- "1..*" Sport : "concerne" : Cette association indique que plusieurs événements peuvent concerner un sport donné (0..*), tandis qu'un sport concerne plusieurs événements (1..*). Cette relation est étiquetée avec "concerne" pour indiquer que les événements sont liés aux sports.

paris  "0..*" -- "1" Parieur : "fait" : Cette association signifie qu'un pari est placé par un parieur spécifique. Un parieur peut placer plusieurs paris (0..*), mais chaque pari est associé à un seul parieur (1). La relation est étiquetée avec "fait" pour indiquer que le parieur a placé le pari.

SourceDonnees "1..*" -- "1..*" Evenement: "lié" : Cette association indique qu'une source de données est liée à plusieurs événements (1..*) et qu'un événement est lié à une source de données (1). La relation est étiquetée avec "lié" pour indiquer que les événements sont liés à la source de données pour obtenir des mises à jour.