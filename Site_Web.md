# Découvrons un cas d'usage de NodeRed

Nous allons expérimenter Node-Red.

## Création d'un site Web

1. Ouvrir Node-Red via l'adresse [http://localhost:1880](http://localhost:1880)

2. Créer un nouveau flux en cliquant sur le signe PLUS

![Lancer Watson Studio](/images/basic_bots_lab2_step1_2.png)

3. Double-cliquez sur le nouvel onglet et entrez un nom pour le nouvel onglet de flux. Puis cliquez sur **Done**.

![Lancer Watson Studio](/images/basic_bots_lab2_step1_3.png)

4. Faites glisser et déposez un noeud http d'entrée sur le canevas. Utilisez le champ de recherche des noeuds de filtre pour trouver les noeuds.

![Lancer Watson Studio](/images/basic_bots_lab2_step1_4.png)

5. Faites glisser un noeud de réponse http de sortie sur le canevas et déposez-le.

![Lancer Watson Studio](/images/basic_bots_lab2_step1_5.png)

6. Glissez-déposez un nœud de modèle sur le canevas entre les nœuds de réponse http et http.

![Lancer Watson Studio](/images/basic_bots_lab2_step1_6.png)

7. Reliez les trois nœuds ensemble.

![Lancer Watson Studio](/images/basic_bots_lab2_step1_7.png)

8. Double-cliquez sur le nœud du modèle pour le modifier. Supprimez le texte présent dans le champ du modèle et entrez le code HTML simple suivant:

```<html>
      <head>
            <title>Hello World</title>
      </head>
      <body>
            <div>Hello to Watson on Node-RED</div>
      </body>
</html>
```
![Lancer Watson Studio](/images/basic_bots_lab2_step1_8.png)

9. Cliquez sur **Done** pour enregistrer vos modifications.

10. Double-cliquez sur le noeud ttp d'entrée. Modifiez-le pour créer un itinéraire HTTP vers votre page Web en entrant / <une chaîne> dans le champ URL, par exemple, / hw. Dans le champ Nom, entrez un nom tel que HTTP Hello World.

![Lancer Watson Studio](/images/basic_bots_lab2_step1_10.png)

11. Cliquez sur **Done** et déployez vos modifications.

12. Ouvrez un nouvel onglet de navigateur et accédez à votre nouvelle page Web. L'adresse Web sera basée sur votre adresse Web Node-RED qui est ajoutée à l'URL de votre page Web que vous venez d'attribuer, par exemple, / hw.

![Lancer Watson Studio](/images/basic_bots_lab2_step1_12b.png)

Bravo, vous avez fait votre 1er site Web.

## Ajout d'un code Javascript pour plus d'interactivité

Dans cette section, vous allez modifier votre page Web "Hello World" pour y inclure un champ de saisie de texte et JavaScript.

1. Double-cliquez sur le nœud de modèle et remplacez le code suivant dans le code HTML:

```<html>
    <head>
        <title>Hello World</title>
    </head>
    <body>
        <div>Hello to Watson on Node-RED</div>
        <div id="id_hello">
           <span>Hello</span>
           &nbsp;
           <span id="id_nameout"></span>
       </div>
        <form id="id_form">
            <div>
                <span>
                    What is your name:  
                </span>
                <span>
                    <input type="text" name="name"        
                                     id="id_name"/>
                </span>
            </div>
            <div>
                <input type="submit" value="Enter"
                                      id="id_enter"/>
            </div>
        </form>  
        <script
           src="https://ajax.googleapis.com/ajax/libs/jquery/2.1.4/jquery.min.js">
     </script>
        <script type="text/javascript">
            $(document).ready(function(){
                setupPage();
            });
            function setupPage(){
                $('#id_hello').hide();
                $('#id_form').submit(onSubmitClicked);
                enterbutton();
            }
            function onSubmitClicked(event){
                $('#id_nameout').text($('#id_name').val());
                $('#id_hello').show();
                $('#id_form').hide();
                event.preventDefault();
            }
            function enterbutton(){
                $(function() {
                    $("form input").keypress(function (e) {
                    if ((e.which && e.which == 13) || (e.keyCode && e.keyCode == 13)) {
                        $('#id_enter').click();
                        return false;
                    } else {
                        return true;
                    }
                });
            });
        }
        </script>       
    </body>
</html>
```

2. Cliquez sur **Done** et déployez vos modifications.

3. Essayez votre page Web avec JavaScript. Entrez votre nom et cliquez sur Entrée.


