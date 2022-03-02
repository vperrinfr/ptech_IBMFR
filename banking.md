# Développement d'un assistant bancaire virtuel

Bonjour,

Vous allez créer un assistant bancaire virtuel pour aider la banque DTE, les clients obtiendront les réponses dont ils ont besoin sans parler à un agent bancaire ni 
attendre au téléphone. Les compétences développés dans cet atelier peuvent s'appliquer à d'autres cas d'utilisation et industries ! ☺

## Le scénario de l'assistant virtuel DTE Bank
L'exigence principale de notre assistant virtuel est de fournir des réponses aux clients d'une banque fictive - Banque DTE. 
Dans l'intérêt d'avoir un atelier qui respecte les contraintes de temps, nous maintenons le périmètre dans le
domaines suivants :
• FAQ sur les produits et services bancaires
• Présentation guidée du processus de paiement
• Réponses à des questions complexes sur les conditions et les frais des produits

Une fois que vous avez configuré votre assistant bancaire virtuel, vous le déploierez sur un faux site Web et le rendrez disponible pour
deux types d'interactions :
• Interaction textuelle, avec votre assistant virtuel intégré dans une page Web
• Interaction vocale, avec votre assistant virtuel accessible via un numéro de téléphone

### Créez votre assistant virtuel
Si c'est la première fois que vous vous connectez au nouveau Watson Assistant, vous serez guidé pour créer votre premier
assistant depuis la page d'accueil. Comme nom d'assistant, tapez "DTE Bank Bot", puis fournissez un simple
la description. Allez-y et cliquez sur "Créer un assistant"

![ptech logo](/images/lab_banque_1.png)

Si vous avez déjà expérimenté le nouvel assistant Watson, vous devrez créer un nouveau
assistant pour ce laboratoire. Depuis la page d'accueil, cliquez sur le bouton d'appel dans la barre supérieure, puis sur "Créer nouveau".

![ptech logo](/images/lab_banque_2.png)

Nommez votre bot DTE Bank Bot (ou utilisez le nom que vous souhaitez) - ajoutez une description rapide et cliquez sur
"Créer un assistant" .

![ptech logo](/images/lab_banque_3.png)

Vous verrez que votre barre supérieure indique que vous travaillez maintenant sous votre DTE Bank Bot.

![ptech logo](/images/lab_banque_4.png)

### Créez votre première action
Dans la page **Actions**, nous allons créer notre première action - destinée à aider les clients de DTE Bank à accomplir une simple
objectif - comprendre ce qu'est un CVV de carte de crédit. Commencez par cliquer sur "Create a new action/Créer une nouvelle action".

![ptech logo](/images/lab_banque_5.png)

Vous serez invité à saisir un exemple de la manière dont un client souhaiterait généralement démarrer cette action. Dans ce
scénario, nous commencerons par taper un exemple simple - "qu'est-ce qu'un CVV ?" Et puis appuyez sur "Save/Enregistrer"

![ptech logo](/images/lab_banque_6.png)

Maintenant que nous avons donné un exemple, nous sommes invités à guider l'utilisateur à travers un ensemble d'étapes qui
conclure une fois l'action accomplie. Dans ce cas, l'étape est assez simple. Sélectionnez l'étape 1
sur le côté gauche.

![ptech logo](/images/lab_banque_7.png)

Dans l'assistant indique le type de boîte : Le CVV est un code unique à 3 chiffres que vous pouvez trouver au dos de votre avoir ou
carte de débit. Ce numéro de vérification sur la carte est conçu pour empêcher l'utilisation des cartes contrefaits ou volés.

![ptech logo](/images/lab_banque_8.png)

Une fois que vous avez tapé cette réponse, vous pouvez ensuite sélectionner "End the Action/Terminer l'action" puisque nous avons rempli le
demande du client.

![ptech logo](/images/lab_banque_9.png)

Vous pouvez maintenant cliquer sur "Preview/Aperçu" dans le coin inférieur droit pour voir les résultats de l'action et des étapes que vous
créé. Une fois le panneau de prévisualisation ouvert, tapez "qu'est-ce que le CVV ?" et vous verrez l'assistant répondre
de retour avec la bonne réponse.

![ptech logo](/images/lab_banque_91.png)

À tout moment, vous pouvez cliquer sur le panneau "Customer start with/Le client commence par" pour inclure des exemples de questions supplémentaires qui
aidera l'assistant virtuel à comprendre quelle action l'utilisateur essaie d'entreprendre (surtout si vous avez un beaucoup d'actions). 
Allez-y et incluez 3 à 5 autres exemples comme indiqué ci-dessous.

1. Où se trouve le CVV ?
2. Je n'ai aucune idée de la signification du CVV ?
3. Peux-tu m'expliquer le CVV ?
4. ...

![ptech logo](/images/lab_banque_10.png)

Vous pouvez ensuite cliquer sur Enregistrer dans le coin supérieur droit pour enregistrer vos modifications, puis les tester dans l'aperçu.
panneau.

![ptech logo](/images/lab_banque_11.png)

Il faudra quelques secondes à l'assistant virtuel pour s'entraîner, puis vous serez prêt à poser différentes questions.
variations pour cette action. Essayez de le tester avec une nouvelle variante : j'essaie de trouver le CVV. Vous remarquerez que
l'assistant virtuel utilise l'IA pour le mapper à la bonne séquence d'actions et d'étapes.

![ptech logo](/images/lab_banque_12.png)

Nous pouvons maintenant fermer cette page (cliquez sur le bouton "X" en haut à droite).

![ptech logo](/images/lab_banque_13.png)

Nous sommes maintenant revenus à la page principale des actions où vous verrez la liste des actions que vous avez créées.

![ptech logo](/images/lab_banque_14.png)

Vous remarquerez que l'assistant est livré avec quelques actions prédéfinies sous "Set by Assistant/Défini par l'assistant" - telles que
Accueillir le client. À tout moment, vous pouvez modifier ces actions et les personnaliser à votre goût.

![ptech logo](/images/lab_banque_15.png)

Maintenant que nous avons notre première action, nous pouvons commencer à la tester dans notre environnement de prévisualisation (brouillon).

### Prévisualisez votre première conversation

Dans chaque environnement d'assistant virtuel, vous avez une version brouillon et en direct. Cela vous permet
pour travailler la version de non production et publier les mises à jour au besoin une fois testées dans le brouillon. Tester votre brouillon
version se produit dans l'aperçu. L'aperçu vous permettra de voir toutes les actions que vous avez créées. Pour y accéder, cliquez sur
sur le bouton Preview/Aperçu de la page de navigation.

![ptech logo](/images/lab_banque_16.png)

Cela vous mènera à la page d'aperçu où vous pourrez tester votre assistant virtuel pour voir quels clients
l'expérience ressemblerait. Il est livré avec un brouillon de discussion en ligne que vous pouvez utiliser pour tester l'action que nous avons créée.

![ptech logo](/images/lab_banque_17.png)

Allez-y et tapez "qu'est-ce que le CVV" dans le panneau Type Something et vous verrez l'assistant virtuel
en parcourant l'action que vous avez créée.

![ptech logo](/images/lab_banque_18.png)

Étant donné que nous aimons l'apparence de cette action, nous sommes maintenant prêts à publier cette expérience brouillon et à la mettre en ligne.

## Publiez votre première conversation et passez en direct

Une fois l'expérience de brouillon finalisée, nous pouvons publier les modifications dans l'environnement en direct, puis
déployer l'assistant virtuel Live sur un canal numérique via un Webchat.

### Publiez votre première conversation

Dans la barre de navigation de gauche, cliquez sur le bouton Publish/Publier

![ptech logo](/images/lab_banque_19.png)

C'est ici que vous publiez vos modifications de contenu de brouillon à en direct. Dans ce scénario, vous pouvez publier les 4
Actions (3 prédéfinies et 1 créée par vous) en cliquant sur le bouton Publish/Publier en haut. Similaire à la gestion des versions de code
vous pouvez fournir une description pour aider à identifier le contenu de cette version. Dans le champ de description V1 fourni
vous pouvez taper - "Ma première action"

![ptech logo](/images/lab_banque_20.png)

Cliquez ensuite sur Publier et vous verrez votre assistant virtuel V1 publié en mode Live.

![ptech logo](/images/lab_banque_21.png)

Maintenant que vous avez publié vos modifications dans Live, nous pouvons continuer et configurer vos intégrations de chaîne afin que vous
pouvez tester votre assistant Live sur un faux site Web.

### Configurez l'intégration de votre canal Webchat

Avec la V1 de votre bot bancaire Live, vous pouvez continuer et configurer une intégration de canal numérique à l'aide du Webchat prédéfini. Pour ce faire, regardez la barre de navigation de gauche et cliquez sur Connecter.

![ptech logo](/images/lab_banque_22.png)

Dans cet écran, vous verrez les intégrations de canal et de back-end que votre assistant virtuel Draft et Live
sont connectés. Vous pouvez basculer entre Draft et Live en le sélectionnant dans le menu déroulant. Faites attention
attention à l'environnement dans lequel vous vous trouvez.

![ptech logo](/images/lab_banque_23.png)

Notez que la version 1 (V1) de vos Actions que vous avez Publié est connectée à votre assistant virtuel Live
et est connecté à votre chat Web en direct. Vous pouvez cliquer sur l'intégration du canal Webchat pour le personnaliser.

![ptech logo](/images/lab_banque_24.png)

Dans le panneau de personnalisation du webchat, vous pouvez modifier plusieurs éléments (style, écran d'accueil, suggestions, etc.).
N'hésitez pas à jouer avec le nom de votre assistant et les couleurs primaires et secondaires.

![ptech logo](/images/lab_banque_25.png)

Cliquez sur « Écran d'accueil » et modifiez le message d'accueil et les trois amorces de conversation.
• Message d'accueil : Salut ! Je suis l'assistante virtuelle de DTE Bank. Comment puis-je vous aider aujourd'hui?
• Initiateur de conversation 1 : Qu'est-ce que le CVV ?
• Initiateur de conversation 2 : Vérifier le solde de mon compte ?
• Initiateur de conversation 3 : Utiliser ma carte dans d'autres pays

![ptech logo](/images/lab_banque_26.png)

Nous sommes maintenant prêts à intégrer le webchat dans un faux site Web. Pour ce faire, suivez ces 3 étapes simples :

• Cliquez sur Intégrer et copiez l'extrait de code Javascript en cliquant sur "Copier dans le presse-papiers"
bouton sur le côté droit. Après cela, assurez-vous de cliquer sur le bouton "Enregistrer et quitter" sur
le côté droit de l'écran.

![ptech logo](/images/lab_banque_27.png)

• Téléchargez les fichiers "dte_bank_bg.png" et "LabHTML.html" depuis le dossier

• Faites un clic droit sur le fichier "LabHTML.html" et sélectionnez un éditeur de texte pour ouvrir le fichier, puis
remplacez le "<script> ….</script>" par ce que vous avez copié de la section Embed.

![ptech logo](/images/lab_banque_28.png)

Vous pouvez maintenant enregistrer et fermer le fichier « LabHTML.html ». Une fois fermé, double-cliquez dessus pour ouvrir un html local
restitution du site DTE Bank avec votre assistant virtuel Live !

![ptech logo](/images/lab_banque_29.png)
