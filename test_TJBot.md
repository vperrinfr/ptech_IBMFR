# Test du montage du TJBot

Des tests matériel sont inclus  pour s'assurer que le matériel TJBot est configuré correctement. Des tests sont inclus pour la caméra, la led, le servo et le haut-parleur dans le dossier `tjbot/bootstrap/tests`


## Installer des dépendances

Installez les dépendances pour les tests matériels.

`npm install ~/Desktop/tjbot/bootstrap/tests`

## Lancer tous les tests

Utilisez le script `runTests.sh` pour exécuter tous les tests matériels.

Chaque test est **interactif** et il vous demandera si le TJBot a effectué ou non laction donnée. Si vous dites "N", le test échouera.

## Exécution de tests spécifiques
Si vous devez tester un composant matériel spécifique, vous pouvez exécuter chaque script de test séparément.

`cd ~/Desktop/tjbot/bootstrap/tests

sudo node test.camera.js

sudo node test.led.js

sudo node test.servo.js

sudo node test.speaker.js`

Si tous les tests fonctionnent, votre TJBOT est opérationnel. **BRAVO**
