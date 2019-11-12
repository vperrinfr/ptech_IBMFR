# Reconnaissance visuelle - Détection d'objet

Maintenant, Imaginez vous souhaitiez localiser dans une image des personnages Lego.

### Avant de commencer

1. Téléchargement les images d'entrainement [lien](https://github.com/vperrinfr/ptech_IBMFR/blob/master/lego_train_2.zip) [lien](https://github.com/vperrinfr/ptech_IBMFR/blob/master/lego_train_3.zip)
2. Aller ensuite à l'adresse https://console.bluemix.net/ et identifiez vous avec votre compte.

### Création d'une instance IBM Watson Visual Recognition ou utilisation de l'instance déjà créée.
1. Une fois authentifié, cliquez sur `Catalog` dans la barre supérieure de l'écran
2. Recherchez `Visual Recognition`
5. Cliquez `Créer` en mode Standard
6. Puis, cliquez sur `Lancer Watson Studio` ou `Créer un modèle personnalisé`

![Lancer Watson Studio](/images/launch.jpg)

## Création d'un modèle personnalisé

Nous allons maintenant créer un nouveau modèle de détection d'objet pour apprendre à la solution à détecter les objets de votre choix..

### Entrainement du modèle
1. Dans l'interface de Watson Studio, dans la page de présentation de l'instance Visual Recognition, cliquez sur **Créer un modèle** dans la zone "Detect Objects".

![new project](/images/objects.png)

2. Glissez déposez les fichiers `lego_train_2.zip` et `lego_train_3.zip` dans le volet de données.

3. Une fois les fichiers téléchargés, sélectionnez **Ajouter au modèle/Add to Model** dans le menu situé en regard de chaque fichier, puis cliquez sur ** Modèle de train **.

![new project](/images/lego_interface.png)

4. Maintenant que vous avez publié l'ensemble des images, vous pouvez apprendre à la solution à localiser dans l'image les personnages Lego.

5. Cliquez sur une première image, puis cliquez sur "Add Objects", créez un rectangle autour d'un personnage. 
A droite, écrivez le nom de la classe identifiée dans notre cas `LEGO` puis cliquez sur "Add". Vous pouvez saisir d'autres personnages présents sur l'image puis cliquez sur "Done". Vous venez dapprendre sur une première image à localiser des personnages LEGO.

![entrainement](/images/entrainement.png)

6. Vous pouvez continuer sur environ une dizaine de photos.

7. Vous pouvez maintenant entraîner le modèle pour voir la performance de votre entrainement. Cliquez "Train Model".

![test](/images/gotest.png)

8. Cliquez "here" sur tester la performance de votre modèle, via l'onglet **Test**.  

![test](/images/test.png)

9. Le travail d'annotation est fastidieux, la solution fournit une fonctionnalité d'auto-annotation.
Cliquez sur une image non annotée et cliquez sur "Auto Label". La solution va alors vous proposer des annotations.

![test](/images/autolabel.png)

10. Bravo vous avez crée votre premier modèle de détection d'objet. Cela peut vous saisir par exemple à compter des objets dans une image.
