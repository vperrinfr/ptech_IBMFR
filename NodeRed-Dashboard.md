# Tableau de bord/Dashboard & NodeRed

Commençons par examiner les nœuds node-red-dashboard et d’obtenir une configuration simple de tableau de bord.

![pic](/images/dash_0.png)

1. Pour commencer, connectons un simple flux qui envoie un nombre aléatoire entre 0 et 99 à un graphique simple. 
Pour cela, vous aurez besoin d’un **nœud d’injection** qui se déclenche de manière répétée toutes les quelques secondes, d’un nœud de fonction pour générer le nombre aléatoire et l’un des nœuds graphique du tableau de bord.

![pic](/images/dash_4.png)

2. Avant de regarder le fonctionnement du nœud de graphique, configurons le nœud d’injection pour qu’il envoie un horodatage toutes les 5 secondes en définissant la charge utile sur horodatage et sur le champ de répétition sur un intervalle de 5 secondes.

![pic](/images/dash_3.png)

3. Cela agira comme notre déclencheur à répétition. Nous devons maintenant configurer le noeud de fonction pour générer un nombre aléatoire. Pour ce faire, nous utiliserons une simple fonction mathématique JS:

```
msg.payload = Math.round(Math.random()*100);
return msg;
```
![pic](/images/dash_2.png)

4. Avant de regarder le fonctionnement du nœud de graphique, configurons le nœud d’injection pour qu’il envoie un horodatage toutes les 5 secondes en définissant la charge utile sur horodatage et sur le champ de répétition sur un intervalle de 5 secondes.

Cela générera un nombre aléatoire compris entre 0 et 99 qui sera transmis au nœud de graphique.

![pic](/images/dash_3.png)

5. Voyons maintenant le noeud **Graphique**. Lorsque vous double-cliquez dessus, vous verrez ses options de configuration:

![pic](/images/dash_1.png)

6. Déployer le flux

7. Lorsque vous visiterez cette page, vous verrez votre graphique suivant, comme indiqué ci-dessous:

![pic](/images/dash_7.png)

8. C’était assez simple, ajoutons quelques éléments d’interface utilisateur à notre tableau de bord. Commençons par créer une jauge pour afficher la dernière valeur de données envoyée. Faites glisser un nœud de jauge de la palette de l'interface utilisateur et connectez-le au nœud de fonction Nombre aléatoire.

![pic](/images/dash_8.png)

9. Cliquez sur déployer, puis allez sur votre tableau de bord et vous verrez que le graphique et la jauge sont affichés dans un groupe. Le graphique montre maintenant les 5 dernières minutes de données et jauge la dernière valeur.

![pic](/images/dash_9.png)

*Bravo, vous avez testé la fonctionnalité de Tableau de bord.*

Voici un exemple de tableau de bord un peu plus complet.

![pic](/images/dash_10.png)
