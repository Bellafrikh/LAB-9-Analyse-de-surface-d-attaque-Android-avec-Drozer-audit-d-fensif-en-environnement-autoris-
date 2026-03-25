# Rapport d'audit de sécurité - Application Android

## Informations générales
- **Application** : Diva (Damn Insecure and Vulnerable App)
- **Package** : jakhar.aseem.diva
- **Version** : 1.0
- **Date d'audit** : 25 Mars 2026
- **Auditeur** : BELLAFRIKH ZAYNAB

## Résumé exécutif
L'audit de l'application DIVA a révélé des failles de sécurité critiques liées à une mauvaise configuration des composants Android. L'absence de restrictions sur les "Content Providers" et les "Activities" permet à n'importe quelle application malveillante d'extraire des données personnelles (notes) et des secrets techniques (clés API) sans aucune permission.

## Méthodologie
- Analyse statique du manifeste Android via Drozer.
- Cartographie des composants exposés (Activities, Providers).
- Vérification des protections (lecture/écriture/intent-filters).
- Preuve de concept (PoC) par extraction de données via URIs.

## Découvertes principales
1. **Fuite de données via Content Provider** : Accès total en lecture/écriture aux notes privées.
2. **Exposition de composants sensibles** : Lancement forcé d'écrans affichant des identifiants API.
3. **Configuration non sécurisée** : Mode "Debuggable" activé facilitant l'ingénierie inverse.
4. **Permissions excessives** : Accès inutilement large au stockage externe.

## Recommandations prioritaires
1. **Désactiver l'exportation** des composants non nécessaires (`exported="false"`).
2. **Protéger les Content Providers** avec des permissions personnalisées ou un accès privé.
3. **Passer l'application en mode production** (`debuggable="false"`).
4. **Renforcer les permissions** en utilisant le niveau `signature` pour les composants internes.

## Annexes
- Annexe A : Tableau de triage complet (voir triage.csv)
- Annexe B : Captures d'écran (voir dossier /preuves)
- Annexe C : Mapping OWASP MASVS (V1, V2, V3, V4, V5)