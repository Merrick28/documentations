 # Remplacer
**Outils → Remplacer**

Cet outil permet de remplacer rapidement des équipements et commandes, par exemple dans le cas d'un changement de plugin, ou d'un module.

Comme les options de remplacements sur la configuration avançée d'une commande, il remplacem les commandes dans les scénarios et autre, mais permet aussi de transferer les propriétés des équipements et des commandes.

## Filtres

Vous pouvoir afficher seulement certains équipements pour plus de lisibilité, en filtrant par objet ou par plugin.

> Dans le cas d'un remplacement d'un équipement par un équipement d'un autre plugin, sélectionnez les deux plugins.

## Options

> **Remarque**
>
> Si aucune de ces options n'est cochée, le remplacement revient à utiliser la fonction *Remplacer cette commande par la commande* en configuration avançée.

- **Copier la configuration de l'équipement source** :
Pour chaque équipement, seront copiés de la source vers la cible (liste non exhaustive) :
	* L'objet parent,
	* Les catégories,
	* Les propriétés *actif* et *visible*,
	* Les commentaires et tags,
	* L'ordre (Dashboard),
	* Les Largeur et hauteur (Tuile Dashboard),
	* Les paramètres de courbe de tuile,
	* Les paramètres optionnels,
	* La configuration d'affichage table,
	* le Type Générique,
	* La propriété *timeout*
	* La configuration *autorefresh*,
	* Les Alertes batterie et communication,

L'équipement source sera également remplacé par l'équipement cible sur les **Design** et les **Vues**.


*Cet équipement sera également remplaçé par l'équipement cible sur les Designs et les Vues.*

- **Cacher l'équipement source** : Permet de rendre l'équipement source invisible une fois remplaçé par l'équipement cible.

- **Copier la configuration de la commande source** :
Pour chaque commande, seront copiés de la source vers la cible (liste non exhaustive) :
	* La propriété *visible*,
	* L'ordre (Dashboard),
	* L'historisation,
	* Les widget Dashboard et Mobile utilisés,
	* Le Type Générique,
	* Les paramètres optionnels,
	* Les configuration *jeedomPreExecCmd* et *jeedomPostExecCmd* (action),
	* Les configuration d'Action sur valeur (info),
	* L'icône,
	* L'activation et le répertoire en *Timeline*,
	* Les configurations de *calcul* et *arrondi*,
	* La configuration influxDB,
	* La configuration de répétition de valeur,
	* Les alertes,

- **Supprimer l'historique de la commandes cible** : Supprime les données d'historisation de la commande cible.

- **Copier l'historique des commandes source** : Copie l'historique de la commande source sur la commande cible.



## Remplacements

Le bouton **Filtrer** En haut à droite permet d'afficher tous les équipements, suivant les filtres par objet et par plugin.

Pour chaque équipement :

- Cochez la case en début de ligne pour activer son remplacement.
- Sélectionnez à droite l'équipement par lequel il sera remplaçé.
- Cliquez sur son nom pour voir ses commandes, et indiquer quelles commandes les remplacent. Au choix d'un équipement, l'outil pré-remplit ces choix si il trouve une commande de même type et même nom sur l'équipement cible.


> **Remarque**
>
> Quand vous indiquez un équipement cible sur un équipement source, cet équipement cible est désactivé dans la liste.
