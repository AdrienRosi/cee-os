# JSON CEE
Ce projet propose une représentation JSON des fiches d'opérations standardisées utilisées dans le cadre du dispositif des Certificats d'Economies d'Energie.

Etat de la base de données :
  - Agriculture
  - Bâtiment résidentiel => Complète
  - Bâtiment tertiaire
  - Industrie
  - Transport
  - Réseaux

## Modèle

[Modèle d'une fiche OS](model/README.md)

## Fonctionnement

### Calcul des volumes

Le montant forfaitaire d'une fiche d'opération standardisée est obtenu par application de la formule suivante :

amount = base_x * E(factor_1 * factor_2 * factor_3 ...) + E(term_1 + term_2 + term_3 ...)

### Contraintes

Chaque objet Base, Facteur ou Terme peut se voir appliquer des contraintes permettant de définir les variables admissibles en fonction des données transmises.

Par exemple, la fiche BAR-EN-101 fixe trois bases forfaitaires différente selon la zone climatique. La représentation JSON équivalente donnera :
- Trois objet Base avec pour chaque valeur possible, un unique objet Valeur
- Pour chaque objet Valeur, un objet contrainte :
  - "zone_climatique" comme paramètre
  - "equal" comme opérateur de comparaison
  - "h1", "h2" ou "h3" comme valeur comparative

Ce modèle est dupliquer pour les facteurs et les termes, à la différence que toutes les valeurs possibles pour lesquels les contraintes sont satisfaites sont retenues, alors qu'une seule base forfataire ne peut être retenue.

## Données d'entrée

**type_batiment**

Type de bâtiment


| maison individuelle |
| appartement         |
| batiment collectif  |

**type_logement**

Type de logement

| neuf     |
| existant |

**energie**

Énergie de chauffage

| electricite |
| combustible |

**zone_climatique**

Zone climatique

| h1 |
| h2 |
| h3 |

**type_vmc**

Type de VMC

| type a |
| type b |

**type_caisson / type_extracteur**

Type de caisson / Type d'extracteur

| basse consommation |
| standard           |

**type_point_singulier**

Type de point singulier

| echangeur a plaque |
| autre              |