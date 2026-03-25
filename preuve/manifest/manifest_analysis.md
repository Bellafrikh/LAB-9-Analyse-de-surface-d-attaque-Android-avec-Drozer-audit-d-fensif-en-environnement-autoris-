# Analyse du Manifeste Android (DIVA)

### Observations critiques :
* **Mode Debug :** `debuggable="true"` (Permet l'attachement d'un débogueur JDWP).
* **Backup :** `allowBackup="true"` (Permet l'extraction des données via adb backup).
* **Permissions :** - `android.permission.WRITE_EXTERNAL_STORAGE`
    - `android.permission.READ_EXTERNAL_STORAGE`
    - `android.permission.INTERNET`

### Risques :
L'application expose une surface d'attaque importante dès sa configuration globale, facilitant l'ingénierie inverse et l'accès aux fichiers du stockage externe.