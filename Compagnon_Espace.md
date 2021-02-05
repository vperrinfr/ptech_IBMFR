### Construire son assistant spatial ###

Dans cet atelier, vous créez votre propre assistant virtuel basé sur IBM Watson Assistant. Vous comprendrez les bases de la conception d'interfaces conversationnelles, en utilisant des intentions et des entités. 
Vous apprendrez à créer des réponses sous forme de texte brut, de réponses riches et même de réponses conditionnelles.

#### Watson Assistant - Configuration ####

Compte IBM Cloud: Le catalogue de IBM cloud fournit des solutions cloud à partir de plus de 190 services dans de nombreuses catégories et l'inscription est gratuite.

1. Créez un compte sur IBM Cloud: https://cloud.ibm.com

2. Recherchez «Watson Assistant» dans le catalogue:

![Picture1](https://github.com/vperrinfr/ptech_IBMFR/blob/master/images/Picture1.png)

3. Quittez la configuration standard et cliquez sur «Create/Créer».

4. Commencez par cliquer sur "Launch Tool/Lancer l'outil"

![Picture2](https://github.com/vperrinfr/ptech_IBMFR/blob/master/images/Picture2.png)

5. Configurez une nouvelle compétence en cliquant sur «Skills/Compétences» -> «Create new/Créer une nouvelle»

![Picture3](https://github.com/vperrinfr/ptech_IBMFR/blob/master/images/Picture3.png)

Tout d'abord, nous voulons donner un nom à notre compagnon spatial!

Watson Assistant - Message de bienvenue

1. Accédez à la section **Dialog/Dialogue** et cliquez sur **Create Dialog/Créer une boîte de dialogue**. Vous verrez comment une arborescence de dialogue de base se construit.

2. Cliquez sur le nœud **Welcome/Bienvenue** pour le modifier.

![Picture4](https://github.com/vperrinfr/ptech_IBMFR/blob/master/images/Picture4.png)

3. Changez le message de bienvenue en quelque chose de différent, afin que votre compagnon spatial puisse se présenter:

![Picture5](https://github.com/vperrinfr/ptech_IBMFR/blob/master/images/Picture5.png)

4. Si vous accédez au volet Essayer sur le côté droit, votre compagnon vous accueillera avec le nouveau message

![Picture6](https://github.com/vperrinfr/ptech_IBMFR/blob/master/images/Picture6.png)

Les astronautes sont des gens curieux!
Ils veulent toujours apprendre de nouvelles choses. Ils posent beaucoup de questions. Apprenons à notre assistant à comprendre les questions sur les planètes!

Watson Assistant - **Create an intent/Créer une intention**

**Intent/Intentions**: Objectifs, thèmes que vous prévoyez que vos utilisateurs demanderont lorsqu'ils interagiront avec le service.

1. Cliquez sur «Create intent/Créer une intention» et définissez-lui un nom (par exemple #tell_me_about). Cliquez sur "Create intent/Créer une intention"

![Picture7](https://github.com/vperrinfr/ptech_IBMFR/blob/master/images/Picture7.png)

2. Ajoutez plusieurs exemples différents à cette intention:

Ajoutez des exemples d'utilisateurs:
- Je veux en savoir plus sur la terre
- Veuillez expliquer quelque chose sur le mercure
- Parlez-moi de mars
- etc.

![Picture8](https://github.com/vperrinfr/ptech_IBMFR/blob/master/images/Picture8.png)

3. Génial, notre compagnon comprendra maintenant l'intention de notre question.

Watson Assistant - Entités contextuelles

Entities/Entités: une entité représente un terme ou un objet qui fournit le contexte d'une intention.

1. Ensuite, nous voulons extraire le bon objet qui intéresse notre astronaute! Nous apprendrons à l'assistant à comprendre l'objet en fonction du contexte de la question.

2. Par conséquent, veuillez marquer la planète dans l'une de vos phrases d'exemple d'intention, tapez «planète» et cliquez sur **create new entity/créer une nouvelle entité**.

![Picture8](https://github.com/vperrinfr/ptech_IBMFR/blob/master/images/Picture9.png)

3. Pour les phrases d'exemple suivantes, marquez simplement les planètes et choisissez @planet pour affecter l'entité!

![Picture8](https://github.com/vperrinfr/ptech_IBMFR/blob/master/images/Picture10.png)

4. Cool, jetons un coup d'œil à notre collection actuelle d'entités!
