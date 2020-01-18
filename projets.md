# Plusieurs exemples de projet que vous pouvez imaginer

## Idée 1 : Le TJBot me dit ce qu'il voit dans le monde ([English version](https://github.com/samuelvogelmann/visualtj))

<img align="center" src="/images/tjbot_nodered.png" width="100%">

## Fonctionnement
- Prend une photo
- Envoie la photo à [Watson Visual Recognition](https://www.ibm.com/watson/developercloud/visual-recognition.html).
- Analyse et classifie le contenu de l'image.
- Affiche le résultat et prononce l'objet le plus identifié en utilisant [Watson Text to Speech](https://www.ibm.com/watson/developercloud/text-to-speech.html) service.

### Download and Import the Sample Flow
Clone or download the repository to get the sample flow:

	git clone git@github.com:samuelvogelmann/visualtj.git
	cd visualtj

Copy the content of the [**flow.json**](https://github.com/samuelvogelmann/visualtj/blob/master/flow.json) file to clipboard. Go to http://localhost:1880 and import the flow using the import function. In the upper right corner click on the menu bar, then **Import** > **Clipboard** to import the flow:

<img align="center" src="/images/import_node_red.png" width="100%">

Paste the sample flow into the **Paste nodes here** field and click **Import**.

### Entrer les clés API des services Watson
Dans cette étape, il faut récupérer les clés API des services suivant
- Watson Visual Recognition Service
- Watson Text to Speech Service



You can leave the default values and select **Create**. Now go to **Sevice Credentials** on the left menu and copy your **api_key** into clipboard.

Then you need to update the Visual Recognition node <img src="/images/visrec_node.png"> within your flow with *your* Watson Visual Recognition credentials:

<img align="center" src="/images/visrec_node_settings.png" width="50%">

The last step is the [Watson Text to Speech](https://www.ibm.com/watson/developercloud/text-to-speech.html) service. You need to do the exact same thing you did with the Visual Recognition service. You may leave all the default values and select **Create**. Copy your credentials and add them to **Text to Speech** node <img src="/images/t2s_node.png">.


## Run the Application
Finally click the red **Deploy** button in the upper right corner to deploy your flow. Now you can access the application at
http://localhost:1880/visualtj and start taking a picture and analyze it with the IBM Watson Visual Recognition Service.

<img align="center" src="/images/webapp_new.png" width="50%">

## Whats Next?
There are a few things you can do and ways to take your robot forward:
- Create a custom classifier and train the visual recognition service to improve its classification capabilites. This [tutorial](https://www.ibm.com/watson/developercloud/doc/visual-recognition/tutorial-custom-classifier.html) and the [documentation](https://www.ibm.com/watson/developercloud/visual-recognition/api/v3/#classifiers) will help you creating your own custom classifier.


## Contributing and Issues
To contribute just fork the repository and send in a pull request. If you find any issues, feel free to open up a [github issue](https://github.com/samuelvogelmann/visualtj/issues/new).


## Dependencies List
- Watson Developer Cloud: [Watson Visual Recognition](https://www.ibm.com/watson/developercloud/visual-recognition.html) and [Watson Text to Speech](https://www.ibm.com/watson/developercloud/text-to-speech.html)
- [Node-RED](http://nodered.org/): Flow-based programming for the Internet of Things
- [Node-Red nodes for Watson services](https://flows.nodered.org/node/node-red-node-watson): A collection of Node-RED nodes for IBM Watson services


## License
MIT License


