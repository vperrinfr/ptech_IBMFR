Maintenant que nous avons compris comment créer une action dans l'environnement de brouillon et la publier pour la mettre en ligne,
nous pouvons aller de l'avant et créer une deuxième version de notre assistant virtuel qui peut guider les utilisateurs à travers un plus
ensemble avancé d'actions.

## Aider les clients à savoir comment transférer de l'argent
Revenez à la page Actions et cette fois-ci, nous allons créer une nouvelle action qui consiste en une série de
étapes pour guider un utilisateur tout au long du processus de transfert d'argent.
Vous commencerez par cliquer sur le coin supérieur droit "New Action/Nouvelle action"

![ptech logo](/images/lab_banque_30.png)

## Créer des étapes dans l'action
Avant tout, nous soumettrons un premier exemple d'utilisateur de ce qu'il pourrait dire pour commencer son action - tapez "Je
souhaitez transférer de l'argent » dans la zone Nouvelle action qui s'affiche. Cliquez sur "Save/Enregistrer"

![ptech logo](/images/lab_banque_31.png)

Vous pouvez continuer et fournir 5 autres exemples de phrases pour vous assurer que Watson Assistant comprend ce que
Actions que l'utilisateur essaie d'effectuer. Vous pouvez ajouter ces 5 exemples ou n'hésitez pas à ajouter les vôtres :
  1. Je veux transférer 100€ à mon ami
  2. Aidez-moi à transférer de l'argent
  3. Je ne sais pas comment transférer de l'argent
  4. Je dois envoyer de l'argent
  5. Essayer d'envoyer de l'argent ici

![ptech logo](/images/lab_banque_32.png)

Une fois que vous avez ajouté quelques exemples sous votre vignette "Le client commence par" et nommé l'action, vous pouvez commencez maintenant à configurer les étapes de conversation nécessaires pour aider l'utilisateur à terminer son action. Cliquez sur l'étape 1.

![ptech logo](/images/lab_banque_33.png)

Dans cette première étape, nous voulons que Watson Assistant réponde à l'utilisateur en confirmant que nous comprenons le
l'action qu'ils essaient de prendre et nous commençons à les guider tout au long du processus.
Tapez ce qui suit dans la boîte de dialogue de l'assistant : "Quand souhaitez-vous effectuer le transfert ?"

Nous définirons les options de réponse en cliquant sur "Define Customer response/Définir la réponse du client" et en sélectionnant Date comme
taper.

![ptech logo](/images/lab_banque_34.png)
![ptech logo](/images/lab_banque_35.png)

Nous pouvons maintenant passer à la création de l'étape suivante pour capturer la réponse de l'utilisateur. Cliquez sur le bouton Nouvelle étape sur le
en bas à gauche de l'écran. Nous allons configurer notre prochaine étape.

Pour l'étape 2, sans conditions, saisissez ce qui suit dans la zone de l'assistant : "Combien voulez-vous
transfert?"
Nous définirons les options de réponse en cliquant sur "Définir la réponse du client" et en sélectionnant Devise comme
le type.

![ptech logo](/images/lab_banque_36.png)

Maintenant, nous ajoutons la troisième étape sous la deuxième étape, une confirmation rapide. Et si l'utilisateur dit oui, nous allons
envoyez-les à l'application de manière contextuelle (lien profond vers l'application) afin qu'ils puissent terminer le processus de transfert.

  - L'assistant dit "Pour confirmer, vous voulez transférer"
  - Sélectionnez la variable d'action (ou tapez le signe "$" pour faire apparaître le sélecteur de variable)

![ptech logo](/images/lab_banque_37.png)

  - Sélectionnez 2. "Combien voulez-vous transférer ?"

![ptech logo](/images/lab_banque_38.png)

  - Ajoutez un "$" après "transfert" OU tapez comme indiqué ci-dessous

![ptech logo](/images/lab_banque_39.png)

![ptech logo](/images/lab_banque_40.png)

Ajouter « à quelle date » après « 2. Combien voulez-vous transférer ? »

![ptech logo](/images/lab_banque_42.png)

  - Choisissez à nouveau la variable d'action

![ptech logo](/images/lab_banque_37.png)

  - Cette fois, sélectionnez 1. Quand souhaitez-vous effectuer le transfert ? et ajoutez un "?" à la fin.
Mettez ensuite en gras les deux variables.
  - Le flux devrait ressembler à ceci :

![ptech logo](/images/lab_banque_41.png)
