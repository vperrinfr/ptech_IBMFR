# Noeuds Node-Red utilisés plus tard

Dans cette section, nous allons décrire plusieurs nœuds qui seront utilisés dans les travaux pratiques. Les laboratoires utiliseront ces services pour créer des applications Watson.

### Noeud Change

![httpin](images/node_red_change.png)

Définir, modifier ou supprimer les propriétés d'un message.

Le nœud peut spécifier plusieurs règles qui seront appliquées au message à tour de rôle.

Les opérations disponibles sont:

    Set

définit une propriété. La propriété peut être une valeur de chaîne (String) ou faire référence à une autre propriété de message par son nom, par exemple: msg.topic.

    Change

rechercher et remplacer des parties de la propriété.

    Delete

supprimer une propriété.

### Noeud Switch

![httpin](images/node_red_switch.png)

Un nœud de fonction simple pour router les messages en fonction de ses propriétés.

Lorsqu'un message arrive, la propriété sélectionnée est évaluée par rapport à chacune des règles définies. Le message est ensuite envoyé à la sortie de toutes les règles qui passent.

Remarque: la règle contraire s’applique en tant que "pas n'importe lequel/not any of" des règles qui la précèdent.

### Noeud Template

![httpin](images/node_red_template.png)

Crée un nouveau message basé sur le modèle fourni.

Cela utilise le format [Mustache](https://github.com/janl/mustache.js).

Par exemple, pour le modèle suivant:

    Hello {{name}}. Today is {{date}}

recevant le message ci-desssous :

    {
     name: "Fred",
     date: "Monday"
     payload: ...
    }

Le résulat sera :

    Hello Fred. Today is Monday

Et voilà bravo, vous connaissez maintenant les bases de la programmation NodeRed.

### HTTP in node

![httpin](images/node_red_httpinput.png)

Ce nœud fournit un nœud d'entrée pour les requêtes HTTP, permettant la création de services Web simples.

Le message résultant a les propriétés suivantes:

    msg.req : http request
    msg.res : http response

Pour les requêtes POST/PUT, le contenu (body) peut être trouvé ici:

    msg.req.body

This uses the Express bodyParser middleware to parse the content to a JSON object.

Par défaut, cela s’attend à ce que le corps de la demande soit encodé dans l’URL:

    foo=bar&this=that

Pour envoyer des données codées en JSON au nœud, l'en-tête de type de contenu (content-type header) de la demande doit être défini sur **application/json**.

Remarque: Ce nœud n'envoie aucune réponse à la demande HTTP. Cela devrait être fait avec un noeud de réponse HTTP ultérieur.

### Noeud de réponse HTTP

![httpin](images/node_red_httpresponse.png)

Ce nœud peut renvoyer des réponses aux requêtes HTTP reçues d'un nœud d'entrée HTTP.

La réponse peut être personnalisée à l'aide des propriétés de message suivantes:

    **payload**

est envoyé en tant que corps de la réponse

    **StatusCode**

si défini, est utilisé comme code d'état de la réponse (par défaut: 200)

    **headers**

si défini, doit être un objet contenant des paires champ / valeur à ajouter comme en-tête de réponse.
