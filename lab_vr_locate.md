# Reconnaissance visuelle - Détection d'objet

Maintenant, Imaginez vous souhaitiez localiser dans une image des personnages Lego.

### Avant de commencer

1. Téléchargement les images d'entrainement [lien](https://github.com/watson-developer-cloud/visual-recognition-coreml/tree/master/Training%20Images)
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
1. Dans l'interface de Watson Studio, dans la page de présentation de l'instance Visual Recognition, cliquez sur **Créer un modèle** dans la zone "Classify Images".

![new project](/images/new-project.jpg)

2. Glissez déposez les fichiers `hdmi_male.zip` `usb_male.zip`,` thunderbolt_male.zip` et `vga_male.zip` dans le volet de données.

3. Une fois les fichiers téléchargés, sélectionnez **Ajouter au modèle/Add to Model** dans le menu situé en regard de chaque fichier, puis cliquez sur ** Modèle de train **.

4. Maintenant que vous avez publié l'ensemble des images correspondant aux objets que vous souhaitez reconnaitre, vous pouvez entrainer le modèle.

5. Vous pouvez maintenant tester la performance de votre modèle, via l'onglet **Test**.

6. Bravo vous avez crée votre premier modèle de reconnaissance d'objet.
