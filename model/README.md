# Je suis une représentation JSON d'une fiche d'opération standardisée

```json
{
  "os": "Code de l'opération standardisée",
  "name": "Nom de la fiche d'opération standardisée",
  "link": "Lien vers la fiche d'opération standardisée (ATEE)",
  "amount": {
    "bases": [{
      "name": "Base forfaitaire pour le calcul du volume de certificat",
      "values": [{
        "constraints": [{
          "param": "Paramètre de la contrainte pour application de la base forfaitaire",
          "operator": "Opérateur de comparaison",
          "value": "Valeur comparée"
        }],
        "value": "Volume forfaitaire"
      }]
    }],
    "factors": [{
      "name": "Nom du facteur à appliquer",
      "param": "Clé du facteur à transmettre"
    }, {
      "name": "Nom du facteur à appliquer",
      "values": [{
        "constraints": [{
          "param": "Clé du paramètre de la contrainte",
          "operator": "Opérateur de comparaison",
          "value": "Valeur comparée"
        }],
        "value": "Valeur du facteur"
      }]
    }],
    "terms": [{
      "name": "Nom du terme à appliquer",
      "param": "Clé du terme à transmettre"
    }, {
      "name": "Nom du terme à appliquer",
      "values": [{
        "contraints": [{
          "param": "Clé du paramètre de la contrainte",
          "operator": "Opérateur de comparaison",
          "value": "Valeur comparée"
        }],
        "value": "Valeur du terme
      }]
    }]
  }
}
```
