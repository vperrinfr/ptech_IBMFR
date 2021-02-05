# Construire son assistant spatial #

Dans cet atelier, vous créez votre propre assistant virtuel basé sur IBM Watson Assistant. Vous comprendrez les bases de la conception d'interfaces conversationnelles, en utilisant des intentions et des entités. 
Vous apprendrez à créer des réponses sous forme de texte brut, de réponses riches et même de réponses conditionnelles.

### Watson Assistant - Configuration ###

Compte IBM Cloud: Le catalogue de IBM cloud fournit des solutions cloud à partir de plus de 190 services dans de nombreuses catégories et l'inscription est gratuite.

1. Créez un compte sur IBM Cloud: https://cloud.ibm.com

2. Recherchez «Watson Assistant» dans le catalogue:

![Picture1](https://github.com/vperrinfr/ptech_IBMFR/blob/master/images/Picture1.png)

3. Quittez la configuration standard et cliquez sur «**Create/Créer**».

4. Commencez par cliquer sur "**Launch Tool/Lancer l'outil**"

![Picture2](https://github.com/vperrinfr/ptech_IBMFR/blob/master/images/Picture2.png)

5. Configurez une nouvelle compétence en cliquant sur «**Skills/Compétences**» -> «**Create new/Créer une nouvelle**»

![Picture3](https://github.com/vperrinfr/ptech_IBMFR/blob/master/images/Picture3.png)

Tout d'abord, nous voulons donner un nom à notre compagnon spatial!

### Watson Assistant - Message de bienvenue ###

1. Accédez à la section **Dialog/Dialogue** et cliquez sur **Create Dialog/Créer une boîte de dialogue**. Vous verrez comment une arborescence de dialogue de base se construit.

2. Cliquez sur le nœud **Welcome/Bienvenue** pour le modifier.

![Picture4](https://github.com/vperrinfr/ptech_IBMFR/blob/master/images/Picture4.png)

3. Changez le message de bienvenue en quelque chose de différent, afin que votre compagnon spatial puisse se présenter:

![Picture5](https://github.com/vperrinfr/ptech_IBMFR/blob/master/images/Picture5.png)

4. Si vous accédez au volet Essayer sur le côté droit, votre compagnon vous accueillera avec le nouveau message

![Picture6](https://github.com/vperrinfr/ptech_IBMFR/blob/master/images/Picture6.png)

Les astronautes sont des gens curieux!
Ils veulent toujours apprendre de nouvelles choses. Ils posent beaucoup de questions. Apprenons à notre assistant à comprendre les questions sur les planètes!

### Watson Assistant - **Create an intent/Créer une intention** ###

**Intent/Intentions**: Objectifs, thèmes que vous prévoyez que vos utilisateurs demanderont lorsqu'ils interagiront avec le service.

1. Cliquez sur «**Create intent/Créer une intention**» et définissez-lui un nom (par exemple **#tell_me_about**). Cliquez sur "**Create intent/Créer une intention**"

![Picture7](https://github.com/vperrinfr/ptech_IBMFR/blob/master/images/Picture7.png)

2. Ajoutez plusieurs exemples différents à cette intention:

Ajoutez des exemples d'utilisateurs:
- Je veux en savoir plus sur la terre
- Veuillez expliquer quelque chose sur le mercure
- Parlez-moi de mars
- etc.

![Picture8](https://github.com/vperrinfr/ptech_IBMFR/blob/master/images/Picture8.png)

3. Génial, notre compagnon comprendra maintenant l'intention de notre question.

### Watson Assistant - Entités contextuelles ###

**Entities/Entités**: une entité représente un terme ou un objet qui fournit le contexte d'une intention.

1. Ensuite, nous voulons extraire le bon objet qui intéresse notre astronaute! Nous apprendrons à l'assistant à comprendre l'objet en fonction du contexte de la question.

2. Par conséquent, veuillez marquer la planète dans l'une de vos phrases d'exemple d'intention, tapez «planète» et cliquez sur **create new entity/créer une nouvelle entité**.

![Picture8](https://github.com/vperrinfr/ptech_IBMFR/blob/master/images/Picture9.png)

3. Pour les phrases d'exemple suivantes, marquez simplement les planètes et choisissez **@planet** pour affecter l'entité!

![Picture8](https://github.com/vperrinfr/ptech_IBMFR/blob/master/images/Picture10.png)

4. Cool, jetons un coup d'œil à notre collection actuelle d'entités!

### Watson Assistant - Étendez vos entités (facultatif) ###

1. Sous Entités, vous devriez voir notre nouvelle entité que nous venons de créer: **@planet**
 
![Picture8](https://github.com/vperrinfr/ptech_IBMFR/blob/master/images/Picture11.png)

2. Vous pouvez ajouter plusieurs valeurs différentes à cette entité auxquelles vous pouvez penser:

Ajouter des valeurs à l'entité:
- Saturne
- Jupiter
- etc.

![Picture12](https://github.com/vperrinfr/ptech_IBMFR/blob/master/images/Picture12.png)

3. Notre compagnon devrait maintenant être capable de détecter plusieurs planètes différentes lorsqu'il les demande. Voyons comment nous pouvons répondre!

### Watson Assistant - Créer la boîte de dialogue ###

1. Dans l'onglet Dialogue, créez un nouveau nœud avec **Add Node/Ajouter un nœud**.

![Picture12](https://github.com/vperrinfr/ptech_IBMFR/blob/master/images/Picture13.png)

2. Remplissez la condition:
Si l'assistant reconnaît #tell_me_about

![Picture12](https://github.com/vperrinfr/ptech_IBMFR/blob/master/images/Picture14.png)

3. Dans le champ ci-dessous, répondez ensuite en remplissant une réponse dynamique qui utilise l'entité extraite:
"Je comprends que vous voulez en savoir plus sur **@planet!**"

![Picture12](https://github.com/vperrinfr/ptech_IBMFR/blob/master/images/Picture15.png)

4. Vous pouvez tester l'assistant en cliquant sur **Try It/Essayer** dans le coin supérieur droit de la fenêtre du navigateur.

![Picture6](https://github.com/vperrinfr/ptech_IBMFR/blob/master/images/Picture6.png)

5. Génial, votre assistant sait de quelle planète vous parlez! Étanchons cette soif de connaissances et apportons une réponse spécifique, en commençant par des réponses sur Mars!

### Watson Assistant - Réponses conditionnelles ###

1. Accédez à votre nœud Dialog avec la condition **#tell_me_about**

2. Cliquez sur **Customize/Personnaliser** dans le coin supérieur droit des configurations de nœuds.

![Picture12](https://github.com/vperrinfr/ptech_IBMFR/blob/master/images/Picture_custo.png)

3. Activez **Multiple conditioned responses /Réponses conditionnées multiples** et cliquez sur **Apply/Appliquer**.

![Picture12](https://github.com/vperrinfr/ptech_IBMFR/blob/master/images/Picture16.png) 

4. Créez maintenant une **new response/nouvelle réponse** dans le nœud.

5. Sous **If assistant recognizes/Si l'assistant reconnaît**, remplissez la condition **@planet:** mars pour donner une réponse spécifique aux questions liées à Mars. Amenez cette réponse au plus haut niveau:

![Picture12](https://github.com/vperrinfr/ptech_IBMFR/blob/master/images/Picture17.png)

6. Sous **Respond with/Répondre avec**, saisissez un fait intéressant sur Mars, par ex. «Mars est appelée la planète rouge en raison de la couleur rouge brunâtre de sa surface.»

7. Vous pouvez tester l'assistant en cliquant sur **Try it/Essayer** dans le coin supérieur droit de la fenêtre du navigateur.

![Picture6](https://github.com/vperrinfr/ptech_IBMFR/blob/master/images/Picture6.png)

### Watson Assistant - Réponses riches ###

**Image**: intègre une image dans la réponse.

1. Pour notre réponse autour de Mars, nous voulons montrer à notre astronaute une belle image de la planète. Par conséquent, ouvrez à nouveau le nœud **#tell_me_about** et cliquez sur le petit engrenage à côté de la réponse:

![Picture12](https://github.com/vperrinfr/ptech_IBMFR/blob/master/images/Picture18.png)

2. Faites défiler vers le bas et cliquez sur **Add Response Type/Ajouter un type de réponse**.

3. Cliquez sur le menu déroulant dans le champ de réponse pour choisir **Image** comme type de réponse.

4. Entrez un lien d'image (important: se terminant par .jpg ou .png),
par exemple. : https://space-facts.com/wp-content/uploads/mars.jpg
Vous pouvez également fournir un titre.

![Picture12](https://github.com/vperrinfr/ptech_IBMFR/blob/master/images/Picture19.png)

5. Cliquez sur **Save/Enregistrer**.
6. Vous pouvez tester l'assistant en cliquant sur **Try It/Essayer** dans le coin supérieur droit de la fenêtre du navigateur.

 ![Picture12](https://github.com/vperrinfr/ptech_IBMFR/blob/master/images/Picture6.png)

Toutes nos félicitations! Vous avez compris les outils de base dont vous avez besoin pour créer votre compagnon spatial.
Si vous le souhaitez, continuez à fournir plus de réponses à différentes planètes ou vous pouvez continuer avec le tutoriel afin d'enseigner encore plus de fonctionnalités à votre compagnon!

En raison de la vitesse à laquelle la Station spatiale tourne autour de la Terre, il ne faut qu'environ 92 minutes pour faire le tour de la Terre une fois. Cela signifie que les astronautes voient un lever ou un coucher de soleil toutes les 45 minutes, totalisant 15 à 16 de chaque, toutes les 24 heures. **Il est facile d’oublier le temps lorsque vous êtes dans l’espace!**

### Cas d'utilisation - Quelle heure est-il? ###
1. Définissez une nouvelle intention appelée **#get_time** et fournissez différents exemples d'utilisateurs afin d'apprendre à notre compagnon à comprendre la question.
2. Nous avons besoin d'un nouveau nœud Dialog avec la condition **#get_time**.
3. Il existe une fonction sympa pour restituer l'heure actuelle en fonction de votre fuseau horaire. Ces fonctions sont introduites avec des signes comme celui-ci: **<? ?>**
Sous **Respond with/Répondre avec**, tapez ce qui suit: ``<? maintenant ()?>``
4. Essayez de demander l'heure dans votre volet.

 ![Picture12](https://github.com/vperrinfr/ptech_IBMFR/blob/master/images/Picture6.png)

5. La réponse semble correcte, mais n’a pas l’air très sophistiquée, non? Reformatons cette réponse en changeant la réponse en:
C'est ``<? now (). reformatDateTime ('h: mm a')?>!``
6. Essayez à nouveau de demander du temps et remarquez la différence!
 
![Picture12](https://github.com/vperrinfr/ptech_IBMFR/blob/master/images/Picture20.png)


Bien mieux, non!

Faire de l'exercice dans l'espace est essentiel pour prévenir la perte osseuse et musculaire. En moyenne, les astronautes font de l'exercice deux heures par jour. Demandons à notre compagnon spatial quand il est temps pour le prochain entraînement!
Cas d'utilisation - Planification
1. Définissez un nouvel intent appelé **#schedule** et ajoutez différents exemples, par exemple
Ajoutez des exemples d'utilisateurs:
- Quel est mon agenda pour aujourd'hui?
- Montre-moi mon emploi du temps
- Quelles activités sont à mon agenda?

2. Créez un nœud de dialogue, définissez la condition comme **#schedule** et fournissez une réponse!
3. Si vous souhaitez demander des activités spécifiques, vous pouvez créer une nouvelle entité appelée **@schedule_items** et la remplir avec différentes activités, par exemple
Ajouter des valeurs d'entité:
- Entraînement
- Expérience
- Déjeuner
- Entretien
- Nettoyage
- etc.
4. Revenez au nœud Dialogue et activez les réponses conditionnelles.
5. Fournissez différentes réponses pour les activités spécifiques, par exemple:

![Picture12](https://github.com/vperrinfr/ptech_IBMFR/blob/master/images/Picture21.png)

6. Génial, votre astronaute peut maintenant facilement répondre sur les tâches à l'ordre du jour!

## Toutes nos félicitations! ##
Vous avez développé votre Space Companion avec IBM Watson Assistant.
Votre nouvel ami est prêt à être testé et amélioré.

Autres idées:
- Demandez à votre compagnon ce qu'il / elle ressent aujourd'hui! (Indice: #sentiment)
- Demandez à votre compagnon ce qu'il peut faire pour vous (Indice: #capabilities)
- Demandez à votre compagnon où trouver le module Columbus ou le Canadarm2!
(Indice: #location + @module)
- Étendez votre fonctionnalité #tell_me_about avec d'autres entités
(Indice: par exemple, "Parlez-moi de l'ISS!")
- … et plus encore!
