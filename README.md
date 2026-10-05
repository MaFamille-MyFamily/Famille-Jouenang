# Plusieurs Branches, une Même Racine — site familial

## Fichiers

- **index.html**: le site public (page principale avec une carte par famille, une fiche par personne, un arbre par Grande Famille)
- **admin.html**: l'administration (ajouter ou modifier les Grandes Familles, les familles, les personnes et les relations)
- **family-data.json**: toutes les données.
- **family-data.js**: la même chose, lisible quand on ouvre le site par double-clic. admin.html produit les deux fichiers ensemble.
- **photos/**: les photos des personnes (par exemple `photos/gilbert.jpg`)
- **photos/evenements/**: les photos des évènements (onglet « Nouvelles & photos »)
- **photos/familles/**: les photos de chaque famille (onglet Familles → Modifier → Photos de la famille)

## Ouvrir le site

Double-cliquez simplement sur **index.html** : le site lit alors `family-data.js`, une copie des données faite pour ça. Quand le site est hébergé (GitHub Pages, Netlify…), il lit `family-data.json`. Gardez toujours les deux fichiers ensemble, dans le même dossier que index.html.

## Mettre à jour les informations (admin.html)

1. Ouvrez **admin.html**. Les données actuelles de `family-data.json` se chargent.
2. Dans l'ordre :
   - **Grandes Familles** : créez la Grande Famille (par exemple « Jouenang »).
   - **Familles** : créez la famille (son nom, sa Grande Famille, le père et la mère). Le bouton **+** à côté de Père ou Mère crée la personne directement.
   - **Sous-familles (Niveau 2, 3…)** : quand un enfant se marie ou a des enfants, ouvrez sa fiche puis cliquez sur **« + Fonder son foyer »**. Choisissez ou créez son conjoint, puis ajoutez les enfants. La famille apparaît automatiquement sur la page principale dans « Nos Familles - Niveau 2 » (et un petit-enfant dans « Niveau 3 », etc.).
   - **Enfants déjà enregistrés** : dans la fenêtre d'une famille, y compris pendant sa création, la liste « … ou choisissez un membre déjà enregistré » permet d'ajouter comme enfant une personne qui existe déjà. Le bouton × retire un enfant de la famille sans supprimer sa fiche.
   - **+ Enfant** : ajoutez les enfants avec leur prénom, nom, sexe, mois et année de naissance, et leur photo.
   - **Relations** : ajoutez seulement les liens qui ne viennent pas déjà des familles (par exemple « X est cousin de Y » quand les parents ne sont pas saisis).
   - **Niveau d'affichage** : dans l'onglet Familles, les familles sont rangées comme sur la page principale (« Nos grandes familles », « Niveau 1 », « Niveau 2 »… puis « Grands-parents »). Le menu **Niveau** de chaque carte (aussi dans la fenêtre « Modifier ») place la famille dans la section de votre choix, et elle s'y affiche aussitôt sur le site. « Automatique » la place selon l'arbre : famille principale de chaque Grande Famille → « Nos grandes familles » ; famille d'un enfant → niveau du parent + 1. « Grands-parents » l'affiche en haut de la boîte de la famille de leur enfant, au lieu d'un carré séparé. Les parents des chefs de famille de « Nos grandes familles » (par exemple ceux d'Abel, Martine et Cécile) y sont toujours affichés en grands-parents. Toutes les familles de grands-parents ont aussi leur propre section, « Grands-parents (aïeux) », en bas de la page principale : d'abord les parents des chefs de famille (père avant mère), puis leurs propres parents. Le N° permet de changer cet ordre.
   - **Ordre d'affichage** : chaque carte a un champ **N°**, valable **dans sa section** : le N° 1 s'affiche en premier, et les familles sans numéro viennent en dernier. Dans « Nos grandes familles », la première famille occupe toute la largeur et les autres s'affichent en dessous. « Renuméroter 1, 2, 3… » redonne des numéros qui se suivent dans chaque section, et « Ordre de l'arbre » efface tous les numéros. La famille principale de chaque Grande Famille se choisit dans l'onglet Grandes Familles → Modifier → « Famille principale ».
   - **Ordre des enfants** : dans la fenêtre « Modifier » d'une famille, chaque enfant a un **N°** (1 = l'aîné·e) et des flèches ↑ ↓ pour le déplacer. Le même champ, « Rang dans la fratrie », se trouve dans la fiche de chaque personne. Les enfants sans numéro sont classés par date de naissance.
   - **Photos de famille** : dans la fenêtre « Modifier » d'une famille, cliquez sur « + Ajouter des photos » (vous pouvez ajouter une légende et changer l'ordre), puis copiez les fichiers dans `photos/familles/`. Ils s'affichent dans la section « Photos de famille » de la page de la famille.
   - **Grands-parents** : ouvrez la fiche d'une personne (par exemple Abel), puis cliquez sur **« + Parents »** à côté de « Famille (enfant de) ». Créez le père et la mère avec les boutons **+** (photo et date de naissance), enregistrez la famille, puis enregistrez la fiche. La case « Famille d'ascendants (grands-parents) » est cochée automatiquement : ces grands-parents s'affichent alors en haut de la boîte de la famille de leur enfant, et non comme un carré séparé.
3. Cliquez sur **Aperçu du site** pour voir le résultat avant de le publier.
4. Cliquez sur **⬇ Exporter les données**. Deux fichiers sont téléchargés, `family-data.json` et `family-data.js` : remplacez les anciens par ceux-ci. Si le navigateur le demande, autorisez les téléchargements multiples.
5. Copiez les nouvelles photos dans le dossier `photos/`. Le nom du fichier doit être le même que celui indiqué dans la fiche.

Tant que vous n'avez pas exporté, vos modifications restent enregistrées dans le navigateur (brouillon).

> admin.html ne peut rien modifier sur le serveur : il produit seulement un fichier à télécharger. Si vous ne voulez pas que la famille voie cette page, vous pouvez quand même ne pas la publier et la garder uniquement sur votre ordinateur.

## Masquer une personne

Dans la fiche d'une personne, cochez **« Masquer sur le site »** (par exemple pour un conjoint inconnu comme « Époux d'Alvine »). La personne reste dans admin.html, avec la mention *masqué*, mais n'apparaît plus nulle part sur le site : boîtes des familles, arbre, fiches, anniversaires et relations. La famille s'affiche alors avec l'autre parent seul. Décochez la case pour la faire réapparaître.

## Calendrier des anniversaires

La page **Anniversaires** classe les personnes par mois de naissance, en commençant par le mois en cours, et indique l'âge atteint cette année. La page d'accueil rappelle aussi les anniversaires du mois. Seules les personnes qui ont un mois de naissance y apparaissent. Le jour de naissance est facultatif : ajoutez-le dans la fiche de la personne pour un classement plus précis.

## Nouvelles et photos de famille

Dans admin.html, onglet **Nouvelles & photos**, cliquez sur **+ Nouvelle publication** et remplissez :
- le titre, la date et le texte ;
- les photos (plusieurs à la fois, avec une légende facultative et un ordre modifiable) ;
- les personnes concernées : la publication apparaîtra aussi sur leur fiche.

Copiez ensuite les photos choisies dans `photos/evenements/`, avec le même nom de fichier. Sur le site, les photos s'ouvrent en grand quand on clique dessus, et les flèches permettent de passer de l'une à l'autre.

## Relations déduites automatiquement

À partir des familles (père, mère, enfants) et des relations déclarées, le site calcule :

- les frères et sœurs, de façon transitive (A frère de B et B frère de C, donc A frère de C). Il distingue aussi les demi-frères et demi-sœurs.
- les grands-parents, arrière-grands-parents, petits-enfants…
- les oncles et tantes, grands-oncles, neveux et nièces, cousins germains, cousins issus de germain…
- les cousins, oncles et neveux **transmis par la fratrie** (le cousin de B est aussi le cousin de C si B et C sont frère et sœur).
- la belle-famille : mari et épouse, beau-père et belle-mère, gendre et belle-fille, beau-frère et belle-sœur (y compris le conjoint d'un frère ou d'une sœur, et le frère ou la sœur du conjoint), oncle ou tante par alliance…

Remarque : « le cousin de mon cousin » n'est **pas** automatiquement mon cousin, car il peut être cousin par l'autre parent. Le site applique donc la règle en passant par les frères et sœurs, ce qui est toujours exact.

Dans les fiches, les relations calculées portent la mention **déduit**.

## Format de family-data.json

```json
{
  "site": { "titre": "...", "sousTitre": "..." },
  "grandesFamilles": [ { "id": "jouenang", "nom": "Jouenang", "description": "" } ],
  "familles": [ { "id": "...", "nom": "Famille Abel & Martine", "grandeFamilleId": "jouenang", "pereId": "abel", "mereId": "martine", "niveau": 0, "ordre": 1 } ],
  "personnes": [ { "id": "gilbert", "prenom": "Gilbert", "nom": "Kamnang", "sexe": "M",
                   "jourNaissance": 12, "moisNaissance": 3, "anneeNaissance": 1965, "photo": "photos/gilbert.jpg",
                   "familleId": "famille-abel-martine", "grandeFamilleId": "jouenang" } ],
  "relations": [ { "a": "x", "type": "cousin", "b": "y" } ],
  "nouvelles": [ { "id": "...", "titre": "Réunion de famille", "date": "2026-08-15", "texte": "...",
                   "photos": [ { "src": "photos/evenements/groupe.jpg", "legende": "Photo de groupe" } ],
                   "personnes": ["jules"], "grandeFamilleId": null } ]
}
```

Le champ `niveau` d'une famille vaut `"aieul"` (grands-parents), `0` (Nos grandes familles), `1`, `2`, `3`… ou est absent (automatique). `ordre` est le numéro d'affichage dans ce niveau.

Une relation se lit ainsi : « **a** est *type* de **b** ». Les types possibles sont `parent`, `enfant`, `fratrie`, `conjoint`, `grand-parent`, `petit-enfant`, `oncle`, `neveu`, `cousin`, `grand-oncle`, `petit-neveu`, `arriere-grand-parent`, `arriere-petit-enfant`, `beau-frere`, `beau-parent` et `gendre`.
Dernière mise à jour le 5 octobre à 17h55
