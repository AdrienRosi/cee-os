# Représentation JSON des fiches d'opération standardisée Certificats d'Economies d'Energie
## Schéma

### os
Code de l'OS.

### name
Nom de l'OS.

### sector
Secteur d'application de l'OS.

### lifetime
Durée de vie conventionnelle de l'OS.

### content (non validé)
Contenu textuel de la fiche OS.

### appendix (non validé)
Contenu de la partie A de l'attestation sur l'honneur de l'OS.

### amount
Montant forfaitaire des Certificats d'Economies d'Energie de l'OS. Son calcul est effectué par application de la formule suivante :

amount = base x factor + term

Où

base est le volume forfaire de CEE déterminé par l'OS
factor est le produit des coefficients déterminés par l'OS strictement supérieur à 0
term est la somme des termes déterminés par l'OS

#### base
Objet représentant le volume forfaitaire de CEE.

##### name
Nom de la base.

###### values
cf ci-après.

#### factors
Tableau d'objets facteur.

##### factor
Coefficient. Cet objet est ainsi représenté :

###### name
Nom du coefficient.

###### param
Nom du paramètre dans le cas d'un coefficient à saisir manuellement.

###### values
cf ci-après.

#### terms
Tableau d'objets term.

##### term
Terme. Cet objet est ainsi représenté :

###### name
Nom du terme.

###### param
Nom du paramètre dans le cas d'un terme à saisir manuellement.

###### values
cf ci-après.

### Variables génériques

#### values
Tableau des valeurs possibles. Chaque entité du tableau est ainsi représentée :

##### value
Valeur applicable.

##### constraints
Tableau des conditions à satisfaire. Chaque entité du tableau est ainsi représentée :

###### param
Nom du paramètre à comparer

###### operator
L'opérateur à appliquer : 
- equalTo
- lessThan
- lessThanOrEqual
- greaterThan
- greaterThanOrEqual

###### value
Valeur à comparer