# Plusieurs exemples de projet que vous pouvez imaginer

## Idée 1 : Le TJBot me dit ce qu'il voit dans le monde ([English version](https://github.com/samuelvogelmann/visualtj))

<img align="center" src="/images/tjbot_nodered.png" width="100%">

## Fonctionnement
- Prend une photo
- Envoie la photo à [Watson Visual Recognition](https://www.ibm.com/watson/developercloud/visual-recognition.html).
- Analyse et classifie le contenu de l'image.
- Affiche le résultat et prononce l'objet le plus identifié en utilisant [Watson Text to Speech](https://www.ibm.com/watson/developercloud/text-to-speech.html) service.

### Récuperer le flux

Copier (CTRL+C) le contenu du fichier [**flow.json**](flow_vr.json). 
Aller à la page http://localhost:1880 et importer le flux en utilisant la fonction IMPORT. Dans le coin supérieur droit de la barre de menu,  cliquer sur **Import** > **Clipboard** 

<img align="center" src="/images/import_node_red.png" width="100%">

Coller le contenu (CTRL+V) dans le champ **Paste nodes here**  et cliquer **Import**.

### Entrer les clés API des services Watson
Dans cette étape, il faut récupérer les clés API des services suivant
- Watson Visual Recognition Service
- Watson Text to Speech Service

Vous pouvez trouver les clés [ICI]()

Ensuite vous devez mettre à jour le noeud Visual Recognition <img src="/images/visrec_node.png">.

<img align="center" src="/images/visrec_node_settings.png" width="50%">

Puis, la même action avec le noeud **Text to Speech** <img src="/images/t2s_node.png">.

## Tester l'application
Maintenant cliquer sur le bouton rouge **Deploy** button dans le coin supérieur droit.
Vous pouvez maintenant le tester sur http://localhost:1880/visualtj en prenant une photo et en l'analysant. 

<img align="center" src="/images/webapp_new.png" width="50%">
