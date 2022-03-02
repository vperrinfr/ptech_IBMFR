# Scénario du Workshop 1 : Société de vente de café

**** Attention Il faut être en mode "Expérience Classique" **** Description ![ici](/images/experience.png)

Bonjour,

Vous venez d’être embauché par la société « Coffee Bean ». Cette société souhaite mettre en œuvre un chatbot pour fournir de nouvelles services à ces clients dans sa démarche de digitalisation de sa relation client.

Il voudrait permettre au travers de celui-ci :
1. Lister les différents produits à son catalogue. Il souhaite afficher une image du produit.
2. Répondre aux questions sur le prix des produits
3. Passer commande 
    - un article, 
    - sa quantité,
    - le mode de récupération (livraison / a emporter)
Pour la livraison demander le numéro de téléphone et le stocker
4. Recherche des boutiques par nom de ville. Il a 3 magasins (Paris, Lyon, Bordeaux).

5. (Optionel) Il aimerait aussi pouvoir gérer une carte de fidélité avec des numéros de la forme XXYYYY (X étant une lettre, Y étant un chiffre).

Listes des articles:
1. Café :
- Expresso : 3€
- Latte : 3.5€
- Mocha : 4€
- Cappuccino : 5€

2. Thé :
- Menthe : 2.5€
- Ceylan : 3 €

La livraison est facturé 5€ et 1 euros sur place.

Merci de votre aide pour ce projet.


# Tutorial Pas à Pas : Comment construire un agent conversationnel 
Nous allons créer un chatbot qui permet la prise de commande de café ou thé et renseigne le client sur les produits et leurs prix.

## Création d'un compte ou accès à la plateforme IBM Cloud
1. Aller sur le lien et créer un compte : https://console.bluemix.net/registration/
2. Ou, aller à  https://console.bluemix.net/ et identifiez vous avec votre compte.

## Création d'une instance IBM Watson Assistant (ex- Watson Conversation)
1. Une fois authentifié, cliquez sur `Catalog` dans la barre supérieure de l'écran
2. Recherchez `Assistant`
3. Dans la catégorie `AI ou IA`, cliquez sur `Watson Assistant`
5. Cliquez `Create/Créer`
6. Puis, cliquez sur `Launch tool/Outil de lancement`

## Création d'un Skill
1. Une fois dans l'outil d'administration de Watson Assistant, cliquez sur `Create` pour ajouter un nouveau skill
2. Donnez un nom à ce skill par exemple `Coffee-bot` et sélectionnez la langue Française 

## Création des Intents/Intentions
1. Cliquez `Add intent`
2. Nommez la nouvelle intention `commande-boisson`
3. Ajouter une description expliquant le but de cette intention. Par exemple, "Le client veut commander une boisson."
4. Cliquez `Enter` pour créer l'intention.
5. Commencer par ajouter quelques exemples de phrases qu'un client pourrait écrire pour commander une boisson. (A minima 5 phrases)
  - Je souhaiterai commander un expresso
  - J'ai besoin de cafféine
  - un latte 
  - un cappuccino serait apprécié
  - Un mocha s'il vous plait
6. Ouvrir le panneau `Try it Out` en cliquant sur la bulle en haut à droite. Cela vous permet de tester la réaction de votre bot

![Try_it Panel](/images/Try_It.png)

7. Attendez que le bot termine son entraînement, puis tapez `Pourrais-je commander un expresso`. Le bot doit classifier cette phrase `commande-boisson`. Même si vous n’avez pas appris l’intention sur cette phrase exacte, Watson peut toujours la comprendre.
8. Ajoutez quelques intentions supplémentaires pour couvrir d'autres demandes. Essayez de créer les intentions suivantes et d’ajouter quelques exemples à chacune d’elles
  - #voir-produits (Le client veut connaitre les produits disponibles)
  - #prix (Le client veut connaitre le prix des produits)
  - #recherche_magasin (Le Client cherche la localisation des magasins)
  
Voila les intentions finies:
![finished intents](/images/Liste_Intent.png)

## Création des Entities
1. Cliquez sur l'onglet `Entities`
2. Cliquez `Add entity` and add the name `boissons`
3. Activez le `Fuzzy Matching` si vous souhaitez que Watson comprenne les erreurs de frappe.
4. Ajoutez la valeur `espresso` avec comme synonyme `cafe`. 
5. Ajoutez d'autres valeurs correspondant aux produits au catalogue :
  - Cappuccino
  - Latte
  - Menthe
  - Mocha
  - Ceylan

Voici l'entité `@boisson` finalisée:
![finished intents](/images/Entite_boisson.png)

6. Quittez la page, et cliquez sur `System entities` dans l'onglet `Entities` 
7. Activez`@sys-number` pour permettre la détection des nombres.

Voici l'entité système finalisée:
![finished intents](/images/System_Entities.png)

8. Créez d'autres entités.
9. Cliquez `Add entity` and add the name `Modèle_REGEX`
10. Désactivez le `Fuzzy Matching`
11. Saississez `Téléphone`comme nom
11. Sélectionnez `Patterns` au lien de `Synonyms`
12. Copiez l'expression régulière pour détecter/valider un numéro de téléphone : ^(\\+33|0|0033)[0-9]{9}$
13. Tester la reconnaissance d'un numéro de téléphone dans le panneau `Try it out`
14. Cliquez `Add entity` and add the name `Livraison`
14. Cliquez `Add entity` and add the name `Validation` (Oui, Non)
15. Cliquez `Add entity` and add the name `Ville` (Paris, Bordeaux, Lille...), la 

Voici la liste des entités finalisée:
![finished intents](/images/Liste_Entities.png)


## Construction du dialogue
1. Cliquez sur l'onglet `Dialog`
2. Cliquez `Create`
3. Cliquez sur le node `Bienvenue` si vous souhaitez changer/personnaliser le message d'accueil
4. Cliquez sur les 3 points du noeud `Bienvenue` et `Add node below`et nommer le `commande-boisson`
5. Ajoutez votre intention `#commande-boisson` comme valeur dans le champ `If assistant recognizes`
6. En haut à droite du noeud, cliquez sur `Customize`
7. Activez les `Slots`, sélectionnez `Prompt for everything` et appuyez sur `Apply`
12. Dans la rubrique `Check for`, ajouter `@boissons`
13. Dans la rubrique `If not present, ask` ajoutez une question comme "Que souhaitez-vous boire ?"
14. Cliquez `Add slot`, et ajoutez une condition "Check for" `@sys-number` avec la question "Combien de tasses de $boissons souhaitez-vous ?"
(Note: La syntaxe `$variable` permet l'accès au contenu du variable.)
14. Cliquez `Add slot`, et ajoutez une condition "prompt for" `@Livraison` avec la question "A emporter ou sur place ?"
15. Dans le champ "Then respond with", ajoutez la réponse "Ok, j'ai donc une $number $boissons pour vous, $Livraison ! Cela vous va ?  "
16. Créez un noeud fils, avec le nom `validation`
17. Dans le champ `If assistant recognizes`, saissisez `@Validation`. Ce noeud attend une entité de validation.
18. En haut à droite du noeud, cliquez sur `Customize`
19. Activez les `Multiples Responses` et appuyez sur `Apply`. 
20. Dans le champ `If assistant recognizes`, ajouter `@Validation:Oui`, saissisez la réponse que vous voulez renvoyer dans le champ `Respond with` suite à la confirmation.
21. Dans le champ `If assistant recognizes`, ajouter `@Validation:Non`, saissisez la réponse que vous voulez renvoyer dans le champ `Respond with`
22. Tester les "slots" avec différentes questions du type simple "je veux du café" ou plus complet comme "je veux un café sur place"
23. Créez un noeud `prix-boisson` sous (et non fils de) le noeud `commande-boisson`
24. Ajoutez votre intention `#prix-boisson` comme valeur dans le champ `If assistant recognizes`. Cliquez sur le signe `+` et rajouter l'entité `boissons` avdec le séparateur `AND`.
25. En haut à droite du noeud, cliquez sur `Customize`
26. Activez les `Multiples Responses` et appuyez sur `Apply`. 
27. Dans le champ `If assistant recognizes`, ajouter `@boissons:Latte`, saissisez la réponse dans le champ `Respond with`
28. Rajoutez d'autres conditions comme `@boissons:espresso`, `@boissons:capuccino`
29. Testez avec une question comme "Quel est le prix d'un Latte ?"

Arborescence du dialogue :
![finished dialog](/images/dialog.png)

Bravo, votre premier chatbot est en oeuvre :clap: :clap:

## Déploiement

1. Cliquez sur la flèche en haut à gauche ou cliquez sur `Skills` dans le haut de l'écran
2. Cliquez sur `Assistant` 
3. Cliquez sur `Create New`
4. Saississez le nom de votre assistant, puis cliquez sur `Create`
5. Cliquez sur `Add Dialog Skill`
6. Cliquez sur `Add existing skill` puis choisissez votre skill
7. Cliquez sur `Preview Link`, puis sur l'url pour tester votre bot dans une widget Web
8. Vous pouvez aussi l'integrer dans Facebook Messenger, Slack ou dans une application spécifique.

## Pour aller plus loin...
Vous avez fini et vous voulez tester d'autres fonctionnalités...

### Help - Digressions
Parfois, vous voudrez qu'une intention soit gérée, peu importe où se trouve l'utilisateur dans leur flux. Pensez aux digressions, ils vous permettent de répondre à une intention même si un utilisateur se trouve au milieu d'un flux de processus, puis de revenir à son flux précédent. Si votre utilisateur a besoin d'aide pour parler au bot n'importe où dans son bot, il est judicieux d'activer les digressions.
1. Créez l'intention `#Aide` avec des exemples comme "J'ai besoin d'aide"
2. Créez un noeud `Aide`à la racine.
3. Ajouter la condition `#Aide` : "
Je peux vous aider à commander un verre dans mon café. Il suffit de dire commander un café pour commencer!"
4. Aller dans la partie `Customize` du noeud
5. Cliquez sur l'onglet `Digressions` 
6. Activez `Return after digression` (Les digressions doivent être activées par défaut, ce paramètre vous permet de gérer l'intention puis de revenir au flux.)
7. Maintenant, pour tester cela, nous devons nous situer au milieu du flux de boissons de notre commande. Mais d’abord, puisque c’est un slot, il faut aller dans l’onglet `Digressions` du nœud `commande-boisson`
8. Activez `Allow digressions away while slot filling` et cliquez sur le bouton n'autorisant que les noeuds dont les retours sont activés. Cela vous aidera à contrôler les nœuds sur lesquels vous souhaitez autoriser l’écart.
9. Essayez-le en disant «commander un verre, puis, quand on vous le demandera ce que vous voulez boire, dites «Aide». Vous devriez voir une réponse de votre noeud d’aide avec un autre message de suivi pour la prochaine question de remplissage d’emplacement.

### Help - Contenu général

Les catalogues vous permettent d'ajouter facilement des intentions courantes à votre espace de travail de service Watson Assistant.

1. Cliquez sur `Content Catalog` dans la barre supérieur
2. Cliquez sur le terme `Général` pour voir les différentes intentions pré-entrainées de cette catégorie.
3. Cliquez sur `Add to skill` dans le coin supérieur droit de l'écran. L'ensemble des 10 intentions ont été rajouté à la liste de vos intentions.
4. Vous pouvez maintenant créer de nouveaux noeuds pour répondre aux questions liées à ces nouvelles intentions.
