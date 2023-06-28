# SGBD
## Sommaire
1.[Systeme d'information](#Systeme-d-information)  
2.[Systeme de gestion de base de donneés](#Systeme-de-gestion-de-base-de-donneés)  





## Systeme d'information

Le système d'information joue un rôle crucial dans la collecte, le traitement et la transmission des informations au sein d'une organisation. Pour collecter les informations, le système peut se baser sur différents canaux tels que les documents, tels que les factures, qui sont analysés et extraits afin d'obtenir des données pertinentes.Une fois collectées, les informations sont traitées et transmises à travers le système d'information, notamment dans des domaines tels que la comptabilité où les données financières sont enregistrées et utilisées pour générer des résultats comptables. Enfin, pour assurer la mémorisation des informations, le système d'information dispose de mécanismes de stockage et de conservation des données, garantissant ainsi leur disponibilité et leur accessibilité ultérieure.

### Methode MERISE

La méthode Merise est une approche systématique et structurée pour l'analyse, l'étude de l'existant, le diagnostic des besoins et la conception de systèmes d'information. Cette méthode suit plusieurs étapes clés. Tout d'abord, l'analyse consiste à étudier en détail le domaine d'application afin de comprendre les processus métier, les règles et les contraintes. Ensuite, l'étude de l'existant permet d'évaluer les systèmes et les flux de données existants, en identifiant les forces, les faiblesses et les lacunes. Le diagnostic est une étape cruciale où les besoins des utilisateurs sont compris et documentés. Cette phase permet de déterminer les fonctionnalités, les performances et les contraintes du futur système.Enfin, la méthode Merise se concentre sur la conception de solutions, en mettant notamment l'accent sur la modélisation des données à l'aide de bases de données.

### MERISE  étape par étape

1. Étude de l’existant  
 - liste des documents, interviews  
 - analyse du domaine, recensement des objectifs  
 - Diagramme Conceptuel de Communication  
 - dictionnaire de données  
2. Modélisation
 - dépendances fonctionnelles  
 - Modèle Conceptuel de Données (MCD)  
 - Modèle Logique de Données (MLD)    
3. Réalisation  
 - Script SQL de création de base de données  
 - Application/interface client  

### Diagramme Conceptuel de Communication (DCC)

Lors de la représentation de l'existant, un des objectifs est de décrire les différents acteurs impliqués dans le fonctionnement du système d'information. Un acteur est considéré comme une unité active qui intervient dans le système. Cela peut inclure des entités telles que les clients, les fournisseurs ou les différents services au sein de l'entreprise, tels que le service comptabilité. Les acteurs peuvent être de deux types : internes ou externes à l'entreprise. Les acteurs internes sont ceux qui opèrent au sein de l'entreprise elle-même, tels que les employés ou les différents départements. En revanche, les acteurs externes sont des partenaires extérieurs à l'entreprise, tels que les fournisseurs externes, les prestataires de services ou les clients externes. La représentation de ces acteurs à travers un diagramme permet de visualiser les interactions et les relations entre les différentes entités, ce qui est essentiel pour comprendre l'existant et faciliter l'analyse et la conception du système d'information. 

**NB** Flux : échange entre deux acteurs

## Dictionnaire de données
Lors de la conception d'un système d'information, il est essentiel de créer un document qui rassemble l'ensemble des rubriques nécessaires. Chaque rubrique doit être décrite de manière précise en incluant plusieurs informations clés. Tout d'abord, le libellé de la rubrique doit décrire la réalité qu'elle représente. Par exemple, pour une rubrique liée aux adresses, le libellé pourrait être "Adresse complète". Ensuite, il est important de spécifier la catégorie ou la nature de la rubrique. Elle peut être élémentaire, ce qui signifie qu'elle représente une donnée de base, telle qu'un nom ou un montant. Une rubrique peut également être un paramètre, ce qui indique qu'elle est constante, comme un taux de TVA fixe. Une rubrique calculée est obtenue à partir d'autres données, par exemple, le coût total d'un prêt qui peut être calculé en multipliant le montant emprunté par le taux d'intérêt et en ajoutant les frais de dossier.

De plus, il est nécessaire de définir le mode de représentation ou le type de chaque rubrique. Cela peut être numérique pour les valeurs numériques, alphabétique pour les lettres, alphanumérique pour une combinaison de lettres et de chiffres, temporel pour les dates, etc. Les contraintes d'intégrité doivent également être précisées pour chaque rubrique. Par exemple, un code postal peut être composé de cinq chiffres, noté XXXXX, tandis qu'une date doit être au format jj/mm/aaaa. Enfin, pour les données calculées, il est important de spécifier la règle de calcul utilisée. Par exemple, le coût d'un prêt peut être calculé en multipliant le montant emprunté par le taux d'intérêt et en ajoutant les frais de dossier.

La création de ce document exhaustif permet de définir clairement les rubriques nécessaires pour le système d'information, en décrivant leur réalité, leur catégorie, leur mode de représentation, leurs contraintes d'intégrité et leurs règles de calcul. Cela aide à garantir la cohérence et l'efficacité du système d'information dans la gestion et la manipulation des données.

Le dictionnaire doit être épuré des `synonymes` et des `polysèmes`.  
`Synonyme` : deux mots différents pour la même réalité
`Polysème` : un même mot pour deux réalité différente

#### example de dictionaire de données

| Code rubrique | Libellé              | Type | Nature | Calcul                      | Intégrité                |
|---------------|----------------------|------|--------|-----------------------------|--------------------------|
| AddrClient    | Adresse du client    | AN   | E      |                             |                          |
| CoutEmpr      | Coût de l’emprunt    | N    | C      | MontEmpr × TauxEmpr + FraisDoss |                          |
| DatNaissClient| Date de naissance du client | D | E      |                             |                          |
| DurEmpr       | Durée de l’emprunt en ans | N | E    | > 0                         |                          |
| FraisDoss     | Frais de dossier     | N    | P      |                             |                          |
| IdClient      | Identifiant du client| N    | E      |                             |                          |
| IdCons        | Identifiant du conseiller | N | E   |                             |                          |
| MontEmpr      | Montant de l’emprunt | N    | E      | > 0                         |                          |
| NomClient     | Nom de famille du client | A | E   |                             |                          |
| NomCons       | Nom du conseiller    | A    | E      |                             |                          |
| PrenomClient  | Prénom du client     | A    | E      |                             |                          |
| PrenomCons    | Prénom du conseiller | A    | E      |                             |                          |
| SalClient     | Salaire du client    | N    | E      | > 0                         |                          |
| TauxEmpr      | Taux de l’emprunt (%) | N  | E      |                             |                          |
| TelClient     | Numéro de téléphone du client | N | E  |                             | XX XX XX XX XX          |

## Modèle Conceptuel de Donnée (MCD)


## Systeme de gestion de base de donneés

### Base de donneés relationelles

Une base de données relationnelles comprend plusieurs éléments clés. Tout d'abord, il y a le schéma, qui définit la structure des tables ou des relations présentes dans la base de données. Il spécifie les noms et les types de colonnes ou d'attributs qui composent chaque table. Ensuite, il y a le contenu, qui représente les lignes de données stockées dans chaque table. Chaque ligne correspond à une entrée spécifique dans la base de données. Enfin, les bases de données relationnelles sont dotées de contraintes d'intégrité qui garantissent la cohérence des données. Ces contraintes veillent à ce que les règles et les relations définies dans le schéma soient respectées lors de l'ajout, de la modification ou de la suppression des données.

### Contraintes d'intégrité
Les contraintes d'intégrité jouent un rôle essentiel dans la gestion des bases de données, car elles permettent de définir des limitations sur le contenu de la base de données. On distingue généralement deux types de contraintes. Tout d'abord, il y a les contraintes d'intégrité stockées dans le système de gestion de base de données (SGBD) lui-même. Ces contraintes peuvent être vérifiées automatiquement à chaque modification du contenu. Elles assurent ainsi la conformité des données aux règles définies dans le schéma de la base de données. Ensuite, il y a les contraintes `implicites`, qui sont présentes uniquement dans l'esprit de l'administrateur de la base de données. Il peut s'agir de règles spécifiques ou de logiques métier qui ne sont pas directement formalisées dans le SGBD. Ces contraintes implicites reposent sur la compréhension de l'administrateur et sont essentielles pour maintenir la cohérence et l'intégrité des données, mais elles ne sont pas vérifiées automatiquement par le système.

#### Contraintes d'intégrité : les clés
Dans le contexte des bases de données relationnelles, considérons un sous-ensemble K des colonnes d'une table T. K est considéré comme une `super-clé` de T si le nombre de lignes ayant les mêmes valeurs sur les colonnes de K est au plus égal à 1. En d'autres termes, les valeurs dans les colonnes de K sont uniques pour chaque ligne de la table T.

Ensuite, une `clé candidate` de T est une super-clé qui contient le nombre minimal de colonnes nécessaire pour satisfaire la propriété de super-clé. Parmi toutes les super-clés possibles, une clé candidate est choisie pour être la clé primaire de T. La `clé primaire` est utilisée pour identifier de manière unique chaque ligne de la table T. Elle permet d'assurer l'unicité des enregistrements et facilite les opérations de recherche et de jointure dans la base de données.

Une `clé étrangère` est un ensemble de colonnes K dans une table qui fait référence à la clé primaire d'une autre table. Elle est satisfaite si les valeurs présentes dans les colonnes de K sont également présentes dans la clé primaire de la table de référence.

## coherence BDD
Une base de données est considérée comme cohérente lorsque son contenu satisfait à la fois les contraintes d'intégrité explicites et les contraintes implicites. Les contraintes d'intégrité assurent la cohérence des données en imposant des règles sur le contenu de la base de données, tandis que les contraintes implicites, qui sont spécifiques à la logique métier, sont également prises en compte pour garantir la cohérence globale de la base de données.

`SQL` est le langage standard pour accéder et modifier une base de données relationnelle 

## Les transactions

Une transaction dans le contexte d'une base de données se réfère à l'exécution d'un programme qui contient plusieurs requêtes interagissant avec la base de données. Du point de vue du système de gestion de base de données (SGBD), une transaction est une séquence d'opérations de lecture et d'écriture sur les données. Ces opérations peuvent inclure des lectures de données existantes, des mises à jour ou des insertions de nouvelles données. Les transactions permettent de garantir l'intégrité et la cohérence des données en assurant que les opérations sont exécutées de manière atomique, cohérente, isolée et durable, selon le principe ACID (Atomicité, Cohérence, Isolation, Durabilité).

Par défaut, les contraintes sont vérifiées après chaque requêtes, ce qui n’est pas nécessaire pour
vérifier le principe de cohérence des transactions

Une transaction dans le contexte d'une base de données peut se trouver dans l'un des trois états suivants : actif, validé (commit), ou annulé (abort). L'état actif indique que la transaction est en cours d'exécution et effectue des opérations sur la base de données. L'état validé signifie que la transaction s'est terminée avec succès et que toutes les modifications effectuées ont été durablement enregistrées dans la base de données. En revanche, l'état annulé indique que la transaction a échoué et que toutes les modifications qu'elle a effectuées ont été annulées.

L'annulation d'une transaction peut être déclenchée par différentes raisons. Tout d'abord, un plantage du système, tel qu'une coupure de courant ou un disque plein, peut entraîner l'annulation d'une transaction en cours. De plus, si une erreur survient au cours de l'exécution de la transaction, le système peut également décider de l'annuler pour préserver l'intégrité des données. Enfin, un utilisateur peut également demander l'annulation d'une transaction s'il souhaite l'interrompre volontairement.

```sql
-- Début de la transaction
BEGIN TRANSACTION;

-- Vos requêtes SQL ici
-- Par exemple : INSERT INTO table1 (col1, col2) VALUES (val1, val2);

-- Validation de la transaction
COMMIT;

-- Rollback de la transaction en cas d'erreur
-- Pour annuler la transaction et restaurer l'état précédent
ROLLBACK;
```
**NB** Avec l’autocommit, chaque requête envoyée est préalablement entourée par BEGIN et COMMIT.

### revocabilité des transactions
Dans le contexte des transactions dans une base de données, il est important de noter que les opérations d'écriture peuvent être révocables tant que la transaction n'est pas terminée. Cela signifie que les modifications apportées par une transaction peuvent être annulées avant la validation définitive de la transaction.

Une fois la transaction validée avec un commit, les opérations d'écriture deviennent irrévocables. Cela signifie que les modifications effectuées ne peuvent plus être annulées. Le commit confirme que les modifications sont définitives et durables dans la base de données.

Le mécanisme de révocation est réalisé par le biais de l'instruction ROLLBACK. Lorsqu'une transaction est annulée avec un rollback, toutes les modifications non validées sont annulées et l'état précédent de la base de données est restauré.

Généralement, le mécanisme de révocation est basé sur la journalisation des données. Cela implique la création d'un journal (ou journal des transactions) qui enregistre les modifications effectuées par chaque transaction. Le journal enregistre également les images avant des données, c'est-à-dire les anciennes valeurs des données avant les modifications. Ces informations sont utilisées lors d'un rollback pour restaurer l'état précédent de la base de données.

En pratique, lors de l'exécution d'une transaction, il est essentiel que ses modifications ne soient pas visibles par les autres transactions tant qu'elle n'a pas été validée. Cela garantit l'isolation des transactions et évite les effets indésirables.

L'exécution simultanée de plusieurs transactions peut entraîner des problèmes de cohérence si les modifications effectuées par ces transactions entrent en conflit. Dans de tels cas, certaines transactions peuvent être annulées pour maintenir la cohérence des données.

L'isolation des transactions est un aspect crucial pour garantir la cohérence des données. Si toutes les transactions ne font que lire les données sans les modifier, il n'y a pas de problème d'isolation car les lectures ne perturbent pas la cohérence des données.

La gestion de la concurrence dans l'exécution des transactions vise à maintenir un degré élevé de concurrence pour des performances optimales, c'est-à-dire un faible temps de réponse. Cette gestion doit être transparente du point de vue de l'utilisateur qui envoie la transaction, afin qu'il puisse interagir avec la base de données sans se soucier des détails de la gestion de la concurrence.

Les transactions doivent vérifier les propriétés ACID :
• Atomicité chaque transaction s’exécute entièrement ou pas du tout  
• Cohérence quelque soit l’exécution des transactions, la base de données reste cohérente  
• Isolation les transactions doivent modifier la base comme si chacune était exécutée seule  
• Durabilité les modifications d’une transaction sur la base de données ne sont jamais
perdues

### les concurrences
Le gestionnaire de transactions est chargé de gérer les accès concurrents aux données.

**Définition** Une execution concurrente est une suite d’opération prises par une ou plusieurs transactions qui sont exécutées en même temps.

example : 

| Transaction T1 | Transaction T2 |
|----------------|----------------|
| 𝑟𝑒𝑎𝑑(𝐴, 𝑡)      | 𝑟𝑒𝑎𝑑(𝐴, 𝑠)     |
| 𝑡 = 𝑡 + 100        | 𝑠 = 2 * 𝑠       |
| 𝑤𝑟𝑖𝑡𝑒(𝐴, 𝑡)     | 𝑤𝑟𝑖𝑡𝑒(𝐴, 𝑠)    |
| 𝑟𝑒𝑎𝑑(𝐵, 𝑡)      | 𝑟𝑒𝑎𝑑(𝐵, 𝑠)     |
| 𝑡 = 𝑡 + 100        | 𝑠 = 2 * 𝑠       |
| 𝑤𝑟𝑖𝑡𝑒(𝐵, 𝑡)     | 𝑤𝑟𝑖𝑡𝑒(𝐵, 𝑠)    |

**Définition**: Une execution est en série si toutes les opérations de chaque transaction sont exécutées de manière consécutive.

Example:

| T1             | T2             | A     | B     |
|----------------|----------------|-------|-------|
| 𝑟𝑒𝑎𝑑(𝐴, 𝑡)   | -              | 25     | 25    |
| 𝑡 = 𝑡 + 100  | -              | -     | -     |
| 𝑤𝑟𝑖𝑡𝑒(𝐴, 𝑡) | -              | 125    | -     |
| 𝑟𝑒𝑎𝑑(𝐵, 𝑡) | -              | -     | -     |
| 𝑡 = 𝑡 + 100  | -              | -     | -     |
| 𝑤𝑟𝑖𝑡𝑒(𝐵, 𝑡) | -              | -     | 125     |
|                | 𝑟𝑒𝑎𝑑(𝐴, 𝑠) |  -  | -   |
|                | 𝑠 = 2 ∗ 𝑠     | -   | -   |
|                | 𝑤𝑟𝑖𝑡𝑒(𝐴, 𝑠) | 250   | -   |
|                | 𝑟𝑒𝑎𝑑(𝐵, 𝑠) | -   | -   |
|                | 𝑠 = 2 ∗ 𝑠     | -   | -   |
|                | 𝑤𝑟𝑖𝑡𝑒(𝐵, 𝑠) | -|   250|

**Definition**: Une execution 𝐸 est sérialisable s’il existe une exécution en série 𝐸′ qui est équivalente à 𝐸 i.e. qu’elles ont le même effet sur toutes les BDD.

Example: 

Execution concurente 𝐸 :

| T1             | T2             | A     | B     |
|----------------|----------------|-------|-------|
| 𝑟𝑒𝑎𝑑(𝐴, 𝑡)   | -              | 25    | 25    |
| 𝑡 = 𝑡 + 100  | -              |       |       |
| 𝑤𝑟𝑖𝑡𝑒(𝐴, 𝑡) | -              | 125   |       |
| 𝑟𝑒𝑎𝑑(𝐵, 𝑡) | -              |       |       |
| 𝑡 = 𝑡 + 100  | -              |       |       |
| 𝑤𝑟𝑖𝑡𝑒(𝐵, 𝑡) | -              |       | 125   |
|                | 𝑟𝑒𝑎𝑑(𝐴, 𝑠) |       |       |
|                | 𝑠 = 2 ∗ 𝑠     |       |       |
|                | 𝑤𝑟𝑖𝑡𝑒(𝐴, 𝑠) | 250   |       |
| 𝑟𝑒𝑎𝑑(𝐵, 𝑡) | -              |       |       |
| 𝑡 = 𝑡 + 100  | -              |       |       |
| 𝑤𝑟𝑖𝑡𝑒(𝐵, 𝑡) | -              |       | 250   |
|-|𝑟𝑒𝑎𝑑(𝐵, 𝑠)|-|-|
|-|𝑠 = 2 ∗ 𝑠|-|-|
|-|𝑤𝑟𝑖𝑡𝑒(𝐵, 𝑠)|-|250|

Execution en serie 𝐸′ :

| T1             | T2             | A     | B     |
|----------------|----------------|-------|-------|
| 𝑟𝑒𝑎𝑑(𝐴, 𝑡)   | -              | 25    | 25    |
| 𝑡 = 𝑡 + 100  | -              |       |       |
| 𝑤𝑟𝑖𝑡𝑒(𝐴, 𝑡) | -              | 125   |       |
| 𝑟𝑒𝑎𝑑(𝐵, 𝑡) | -              |       |       |
| 𝑡 = 𝑡 + 100  | -              |       |       |
| 𝑤𝑟𝑖𝑡𝑒(𝐵, 𝑡) | -              |       | 125   |
|                | 𝑟𝑒𝑎𝑑(𝐴, 𝑠) |       |       |
|                | 𝑠 = 2 ∗ 𝑠     |       |       |
|                | 𝑤𝑟𝑖𝑡𝑒(𝐴, 𝑠) | 250   |       |
|                | 𝑟𝑒𝑎𝑑(𝐵, 𝑠) |       |       |
|                | 𝑠 = 2 ∗ 𝑠     |       |       |
|                | 𝑤𝑟𝑖𝑡𝑒(𝐵, 𝑠) |       | 250   |

donc l'execution concurente 𝐸 est seriabilisable car les donneés ne changent pas quand on la transforme en execution en serie

### Sériabilité par conflits

**Définition** il y a conflit entre deux opérations consécutives d’une exécution lorsque leur ordre ne peut pas être inversé sans changer le résultat de l’exécution

Pour résumer, on peut exécuter deux opérations consécutives issues de deux transactions différentes si :  
• Elles sont sur des éléments différents  
• Elles sont deux lectures

###  équivalence par conflit
**Définition**: eux exécution sont équivalente par conflit si on peut passer de l’une à l’autre en inversant des opérations consécutives sans creer des nouveaux conflit.

**Propriété** Si une exécution est sérialisable par conflit alors elle est sérialisable

