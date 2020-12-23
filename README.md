Unofficial API client of Kdecole (Mon Bureau Numérique)


#### Getting started
```javascript
const Kdecole = require('kdecole-api').Kdecole

const token = Kdecole.login('<YOUR_USERNAME>', '<YOUR_TEMP_PASSWORD>')
console.log(token)    //Afficher son jeton d'authentification


const kdecole = new Kdecole(token) //Création de l'instance du client de l'API
new Kdecole(token, appVersion, idEtablissement) //Autre possibilité d'instancier le client

kdecole.getReleve() //Relevé de notes
kdecole.getActualites() //Liste des actualités de l'établissement
kdecole.getTravailAFaire() //Liste des devoirs
kdecole.getAbsences() //Liste des absences
kdecole.getInfoUtilisateur() //Informations de l'utilisateur
kdecole.getCalendrier() //Agenda
kdecole.getNotes() //Liste des dernières notes
kdecole.getMessagerieInfo() //Informations sur la messagerie (nombre de messages non-lus)
kdecole.getMessagerieBoiteReception() //Messages de l'utilisateur
kdecole.logout() //Se déconnecter (invalidation du jeton d'authentification)
```


#### Endpoints supportés:
BASE_URL: `https://mobilite.monbureaunumerique.fr/mobilite`
- `GET /actualites/idetablissement/<ETABLISSEMENT_ID>/`
- `GET /contenuArticle/<UID_ARTICLE>/`
- `GET /activation/<USERNAME>/<CODE>/`
- `GET /desactivation/`
- `GET /infoutilisateur/`
- `GET /consulterReleves/idetablissement/<ETABLISSEMENT_ID>/`
- `GET /consulterAbsences/idetablissement/<ETABLISSEMENT_ID>/`
- `GET /calendrier/idetablissement/<ETABLISSEMENT_ID>/`
- `GET /consulterNotes/idetablissement/<ETABLISSEMENT_ID>/`
- `GET /messagerie/info/`
- `GET /messagerie/boiteReception/`
- `GET /messagerie/communication/<COMMUNICATION_ID>/`
- `DELETE /messagerie/communication/supprimer/<COMMUNICATION_ID>`
- `PUT /messagerie/communication/supprimer/<COMMUNICATION_ID>`
- `GET /travailAFaire/idetablissement/<ETABLISSEMENT_ID>/`
- `GET /contenuActivite/idetablissement/<ETABLISSEMENT_ID>/<SEANCE_UID>/<ACTIVITE_UID>/`
- `PUT /contenuActivite/idetablissement/<ETABLISSEMENT_ID>/<SEANCE_UID>/<ACTIVITE_UID>/`

Les entêtes des requêtes HTTP qui doivent être présentes sont:
- `X-KDECOLE-VERS`: La version de l'application (actuellement `3.4.14`)
- `X-KDECOLE-AUTH`: Le jeton secret d'authentification
