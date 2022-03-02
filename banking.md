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

Vous pouvez maintenant cliquer sur "Aperçu" dans le coin inférieur droit pour voir les résultats de l'action et des étapes que vous
créé. Une fois le panneau de prévisualisation ouvert, tapez "qu'est-ce que le CVV ?" et vous verrez l'assistant répondre
de retour avec la bonne réponse.

![ptech logo](/images/lab_banque_10.png)

À tout moment, vous pouvez cliquer sur le panneau "Le client commence par" pour inclure des exemples de questions supplémentaires qui
aidera l'assistant virtuel à comprendre quelle action l'utilisateur essaie d'entreprendre (surtout si vous avez un
beaucoup d'actions). Allez-y et incluez 3 à 5 autres exemples comme indiqué ci-dessous.

![ptech logo](/images/lab_banque_11.png)

Vous pouvez ensuite cliquer sur Enregistrer dans le coin supérieur droit pour enregistrer vos modifications, puis les tester dans l'aperçu.
panneau.

![ptech logo](/images/lab_banque_12.png)

Il faudra quelques secondes à l'assistant virtuel pour s'entraîner, puis vous serez prêt à poser différentes questions.
variations pour cette action. Essayez de le tester avec une nouvelle variante : j'essaie de trouver le CVV. Vous remarquerez que
l'assistant virtuel utilise l'IA pour le mapper à la bonne séquence d'actions et d'étapes.

![ptech logo](/images/lab_banque_13.png)

Nous pouvons maintenant fermer cette page (cliquez sur le bouton "X" en haut à droite).

![ptech logo](/images/lab_banque_14.png)

Nous sommes maintenant revenus à la page principale des actions où vous verrez la liste des actions que vous avez créées.

![ptech logo](/images/lab_banque_15.png)

Vous remarquerez que l'assistant est livré avec quelques actions prédéfinies sous "Set by Assistant/Défini par l'assistant" - telles que
Accueillir le client. À tout moment, vous pouvez modifier ces actions et les personnaliser à votre goût.

![ptech logo](/images/lab_banque_16.png)

Maintenant que nous avons notre première action, nous pouvons commencer à la tester dans notre environnement de prévisualisation (brouillon).

### Prévisualisez votre première conversation

Dans chaque environnement d'assistant virtuel, vous recevrez une version brouillon et en direct. Cela vous permet
pour travailler la version non-live et publier les mises à jour au besoin une fois testées dans le brouillon. Tester votre brouillon
version se produit dans l'aperçu. L'aperçu vous permettra de voir toutes les actions que vous avez créées. Pour y accéder, cliquez sur
sur le bouton Aperçu de la page de navigation.
