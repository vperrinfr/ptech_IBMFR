# Reconnaissance visuelle - Classification

Imaginez que vous soyez un technicien pour une compagnie de réseau informatique et que vous souhaitiez identifier les différents types de connectique à votre disposition. 

### Avant de commencer

1. Téléchargement les images d'entrainement 4 fichiers zip. [lien](https://github.com/watson-developer-cloud/visual-recognition-coreml/tree/master/Training%20Images)
2. Aller à  https://console.bluemix.net/ et identifiez vous avec votre compte.

### Création d'une instance IBM Watson Visual Recognition
1. Une fois authentifié, cliquez sur `Catalog` dans la barre supérieure de l'écran
2. Recherchez `Visual Recognition`
5. Cliquez `Créer` en mode Standard
6. Puis, cliquez sur `Lancer Watson Studio`

![Lancer Watson Studio](/images/launch.jpg)

## Test du modèle standard

1. Dans l'interface de Watson Studio, dans la page de présentation de l'instance Visual Recognition, cliquez sur **Test** dans la zone "General".

![allmodel](/images/allmodel.jpg)

2. Cliquez sur l'onglet **Test**, puis glissez-déposez une image de votre choix.
3. Le service vous retourne l'ensemble des éléments qu'il a trouvé dans l'image, avec un degré de probabilité.

![allmodel](/images/vr.jpg)

4. Je vous propose maintenant d'essayer avec une image que vous avez télécharger dans une étape précédente.

![allmodel](/images/image-vga.jpg)

5. Comme vous le remarquez, les éléments remontés ne sont pas pertinents dans notre cas pour identifier notre connecteur.

## Création d'un modèle personnalisé

Nous allons maintenant créer un nouveau modèle de reconnaissance d'objet pour parfaitement classifier un ensemble de connecteurs.

### Entrainement du modèle
1. Dans l'interface de Watson Studio, dans la page de présentation de l'instance Visual Recognition, cliquez sur **Créer un modèle** dans la zone "Classify Images".

![new project](/images/classify.png)

2. Glissez déposez les fichiers `hdmi_male.zip` `usb_male.zip`,` thunderbolt_male.zip` et `vga_male.zip` dans le volet de données.

3. Une fois les fichiers téléchargés, sélectionnez **Ajouter au modèle/Add to Model** dans le menu situé en regard de chaque fichier, puis cliquez sur ** Modèle de train **.

4. Maintenant que vous avez publié l'ensemble des images correspondant aux objets que vous souhaitez reconnaitre, vous pouvez entrainer le modèle.

5. Vous pouvez maintenant tester la performance de votre modèle, via l'onglet **Test**.

6. Bravo vous avez crée votre premier modèle de reconnaissance d'objet.
