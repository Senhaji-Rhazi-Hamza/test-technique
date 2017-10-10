# Test technique
Bonjour Hamza, merci d'avoir accepté de réaliser ce test technique. En voici donc l'énoncé. 

PS : J'ai conscience que l'exercice est difficile. Pour te rassurer, nous n'attendons pas de toi un programme parfait. Nous voulons juste voir comment tu as abordé le problème et si le code et l'historique git est clair. Nous n'attendons pas que tu passes des jours dessus.

# Goal
The goal of this test is use ML, NLP or any other IA way to solve the following problem

Considering that we have many customers in the e-commerce field that all have different data structure for their products. Sometime using french keys sometime english.

You will only focus on these two languages to transform any kind of input into a standardize output. In case of no recognition for a given field, you'll print the unmatched fields / properties.

Expected output: (Very basic)
```
{
  "category": string, // For example 'computer', 'clothes', 'phone' ...
  "underCategories": [string], // For example ['desktop', 'gaming'], ['shirt'], ['smartphone', 'iPhone'] ...
  "price": number, // e.g 23.78, (we don't car of HT / TTC price)
  "currency": string, // €, $ ..
  "color": string, (could be also null => do not print error in not required cases)
  "brand": string, // e.g 'Apple'
}
```
Example of inputs (Do not hesitate to test with some other ones): 

Random one : 
```
{
  "categorie": "ordinateur",
  "tags": ["apple", "portable", "meilleurs_ventes"],
  "prix_ht": "789,60€", 
  "color": "gris",
  "vendeur": "Apple",
  "description": "Le tout nouveau macbook cheap est enfin disponible !!!"
}
```
The one from google but also schema.org 
```
{
  "@context": "http://schema.org/",
  "@type": "Product",
  "name": "Executive Anvil",
  "image": [
    "https://example.com/photos/1x1/photo.jpg",
    "https://example.com/photos/4x3/photo.jpg",
    "https://example.com/photos/16x9/photo.jpg"
   ],
  "description": "Sleeker than ACME's Classic Anvil, the Executive Anvil is perfect for the business traveler looking for something to drop from a height.",
  "mpn": "925872",
  "brand": {
    "@type": "Thing",
    "name": "ACME"
  },
  "aggregateRating": {
    "@type": "AggregateRating",
    "ratingValue": "4.4",
    "reviewCount": "89"
  },
  "offers": {
    "@type": "Offer",
    "priceCurrency": "USD",
    "price": "119.99",
    "priceValidUntil": "2020-11-05",
    "itemCondition": "http://schema.org/UsedCondition",
    "availability": "http://schema.org/InStock",
    "seller": {
      "@type": "Organization",
      "name": "Executive Objects"
    }
  }
}
```
This one is a tricky one !
```
{
    "_id" : "126273-BLEUMA",
    "Reference" : "126273-BLEUMA",
    "Couleur" : {
        "Reference" : "BLEUMA",
        "Libelle" : "BLEU MARINE",
        "CouleurBase" : "BLEU"
    },
    "CouleurBase" : {
        "RefCouleurBase" : "BLEU",
        "CultureInfos" : [
            {
                "Culture" : "fr",
                "Libelle" : "BLEU",
            }
        ]
    },
    "CouleurInternational" : {
        "Reference" : "BLEUMA",
        "RefCouleurBase" : "BLEU",
        "CultureInfos" : [
            {
                "Culture" : "fr",
                "Libelle" : "BLEU MARINE",
                "CouleurBase" : "BLEU"
            }
        ]
    },
    "DateNouveaute" : ISODate("2012-02-01T09:00:00.000Z"),
    "Description" : "hauteur talon 2 cm",
    "Famille" : {
        "Reference" : "CHAUS",
        "Libelle" : "Chaussures"
    },
    "FamilleInternational" : {
        "Reference" : "CHAUS"
    },
    "Genre" : {
        "Reference" : "FEMME",
        "Libelle" : "Femme",
        "SEOId" : "femme"
    },
    "GenreInternational" : {
        "Reference" : "FEMME",
        "CultureInfos" : [
            {
                "Culture" : "fr",
                "Libelle" : "Femme"
            }
        ]
    },
    "ImgUrlBase" : "https://thisisafakeurl.wtf/fakeimage.jpg",
    "Lot" : {
        "DateCreation" : ISODate("2011-03-15T14:09:00.000Z"),
        "Status" : 3,
        "DateDebutVente" : ISODate("2011-05-24T08:15:00.000Z")
    },
    "Marque" : {
        "Reference" : "4075",
        "Libelle" : "GARDENIA",
        "SEOId" : "gardenia",
        "NombreProduits" : 48
    },
    "Photo" : 143,
    "Prix" : {
        "Bonus" : 0.0,
        "BonusExceptionnel" : 0.0,
        "EconomieTtc" : 200.0,
        "PrixHT" : 41.67,
        "PrixInitial" : 250.0,
        "PrixTtc" : 50.0,
        "Remise" : 80.0,
        "TauxTva" : 1.2
    },
    "RefModele" : 126273,
    "UrlFicheProduit" : "/chaussures-femme/chaussures/mocassins/gardenia-mocassins-femme-couleur-bleu-126273-bleuma.html",
    "Nature" : "CHAUSSURE",
    "WsbServiceId" : 320000,
    "Categorie" : {
        "Reference" : "MOCAS",
        "Libelle" : "Mocassins",
        "SEOId" : "mocassins"
    },
    "CategorieInternational" : {
        "Reference" : "MOCAS",
        "CultureInfos" : [
            {
                "Culture" : "fr",
                "Libelle" : "Mocassins",
                "SEOId" : "mocassins"
            }
        ]
    },
    "Tris" : {
        "Bon" : 1002014.0,
        "Remise90" : 102014.0,
        "Remise85" : 52014.0,
        "Remise80" : 2014.0,
        "Remise75" : 52014.0,
        "Remise70" : 102014.0,
        "Remise65" : 152014.0,
        "Remise60" : 202014.0,
        "Bonus10" : 102014.0,
        "Bonus15" : 152014.0,
        "Bonus20" : 202014.0,
        "Prom" : 202014.0,
        "Nouv" : ISODate("2012-02-01T09:00:00.000Z"),
        "Prix" : 50.0
    },
    "OperationAcheteOffert" : false,
    "Produits" : [
        {
            "Reference" : 299520,
            "Status" : 0,
            "Taille" : {
                "Reference" : "355",
                "Libelle" : "35 1/2",
                "Ordre" : "0VE"
            },
            "TailleEtiquette" : "35 1/2",
            "TaillesFiltre" : [
                "350|CHAUSSURE"
            ],
            "TaillesFiltreComplet" : [
                {
                    "Reference" : "350|CHAUSSURE",
                    "Libelle" : "35",
                    "Ordre" : "0V4"
                }
            ]
        },
        {
            "Reference" : 299521,
            "Status" : 0,
            "Taille" : {
                "Reference" : "375",
                "Libelle" : "37 1/2",
                "Ordre" : "0WI"
            },
            "TailleEtiquette" : "37 1/2",
            "TaillesFiltre" : [
                "370|CHAUSSURE"
            ],
            "TaillesFiltreComplet" : [
                {
                    "Reference" : "370|CHAUSSURE",
                    "Libelle" : "37",
                    "Ordre" : "0W8"
                }
           ]
        },
        {
            "Reference" : 299524,
            "Status" : 0,
            "Taille" : {
                "Reference" : "350",
                "Libelle" : "35",
                "Ordre" : "0V4"
            },
            "TailleEtiquette" : "35",
            "TaillesFiltre" : [
                "350|CHAUSSURE"
            ],
            "TaillesFiltreComplet" : [
                {
                    "Reference" : "350|CHAUSSURE",
                    "Libelle" : "35",
                    "Ordre" : "0V4"
                }
            ]
        }
    ],
    "Attributs" : [],
    "Caracteristiques" : [
        {
            "Reference" : "MATEX",
            "Libelle" : "Matière extérieure",
            "Valeur" : "Cuir"
        },
        {
            "Reference" : "SEMEX",
            "Libelle" : "Semelle extérieure",
            "Valeur" : "Cuir"
        },
        {
            "Reference" : "DOUBL",
            "Libelle" : "Doublure",
            "Valeur" : "Cuir"
        }
    ],
    "CaracteristiquesInternational" : [
        {
            "Reference" : "MATEX",
            "CultureInfos" : [
                {
                    "Culture" : "fr",
                    "Libelle" : "Matière extérieure",
                    "Valeur" : "Cuir"
                }
            ]
        },
        {
            "Reference" : "SEMEX",
            "CultureInfos" : [
                {
                    "Culture" : "fr",
                    "Libelle" : "Semelle extérieure",
                    "Valeur" : "Cuir"
                }
            ]
        },
        {
            "Reference" : "DOUBL",
            "CultureInfos" : [
                {
                    "Culture" : "fr",
                    "Libelle" : "Doublure",
                    "Valeur" : "Cuir"
                }
            ]
        }
    ],
    "Matieres" : [],
    "MatieresInternational" : [],
    "SelectionsSpeciales" : [],
    "SelectionsSpecialesInternational" : [],
    "UniversMarque" : [
        {
            "Reference" : "CHIC",
            "Libelle" : "Chic",
            "SEOId" : "chic"
        },
        {
            "Reference" : "DECONTRACTE",
            "Libelle" : "Décontracté",
            "SEOId" : "decontracte"
        }
    ],
    "UniversMarqueInternational" : [
        {
            "Reference" : "CHIC",
            "CultureInfos" : [
                {
                    "Culture" : "fr",
                    "Libelle" : "Chic",
                    "SEOId" : "chic"
                }
            ]
        },
        {
            "Reference" : "DECONTRACTE",
            "CultureInfos" : [
                {
                    "Culture" : "fr",
                    "Libelle" : "Décontracté",
                    "SEOId" : "decontracte"
                }
            ]
        }
    ],
    "Filtres" : [
        {
            "Reference" : "ACCESSOIREOUCHAUSSUR",
            "Libelle" : "Accessoires ou chaussures"
        },
        {
            "Reference" : "CUIR",
            "Libelle" : "Vêtements en cuir"
        },
        {
            "Reference" : "FEMMEOUHOMME",
            "Libelle" : "Femmes ou Hommes"
        },
        {
            "Reference" : "P+30",
            "Libelle" : "Vêtements supérieur à 30€"
        },
        {
            "Reference" : "P+50",
            "Libelle" : "Vêtements supérieur à 50€"
        },
        {
            "Reference" : "P+60",
            "Libelle" : "Vêtements supérieur à 60€"
        },
        {
            "Reference" : "P100-150",
            "Libelle" : "Vêtements entre 100 à 150€"
        }
    ],
    "UrlFicheProduits" : [
        {
            "Culture" : "fr",
            "Url" : "/chaussures-femme/chaussures/mocassins/gardenia-mocassins-femme-couleur-bleu-126273-bleuma.html"
        }
    ]
}
```

# Suggestions / Ideas

The approach should be IA based. Here are some ideas :
* Steming, lemming, language detection, tokenization
* Synonyms and distance (levenstein etc)
* Find a product dataset and train a neural network to identify keys based on values
* ... To be continued ...

As a reminder, once the test is done you can make a pull request from your fork to master and I'll review your PR :)
I suggest this format of PR : 
1/ Wich way of resolution I choose and why
2/ How to test
3/ Limits and difficulties

I hope you'll have some fun ! Good luck :)
