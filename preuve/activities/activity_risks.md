# Analyse des Risques - Activities

### Composants vulnérables :
* `jakhar.aseem.diva.APICredsActivity`
* `jakhar.aseem.diva.APICreds2Activity`

### Description :
Ces activités sont exportées et possèdent des Intent-Filters (`VIEW_CREDS`). Puisque la permission est à `null`, une application tierce peut forcer l'affichage de ces écrans.

### Scénario :
Lancement forcé de l'activité pour visualiser des identifiants API sans authentification préalable.