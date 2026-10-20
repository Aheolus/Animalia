# Animalia

**Esplora la classificazione del regno animale, ramo dopo ramo.**  
**Explore the classification of the animal kingdom, branch by branch.**

Animalia è un'app Android gratuita realizzata con Flutter. Permette di navigare la classificazione zoologica, seguire il percorso tassonomico e cercare i taxa per nome.

Animalia is a free Android app built with Flutter. It lets you browse zoological classification, follow the taxonomic path, and search taxa by name.

## Stato del progetto / Project status

Il progetto è in sviluppo. La navigazione usa un database SQLite separato dall'APK. Nella versione attuale il database si importa dall'app selezionando il file sul dispositivo; il download automatico al primo avvio è pianificato, ma non ancora disponibile.

The project is under development. Browsing uses a SQLite database separate from the APK. In the current version, import the database from inside the app by selecting the file on the device; automatic first-launch download is planned but not yet available.

## Database / Database

Il catalogo tassonomico di base è preparato a partire dal **Catalogue of Life (CoL)**. La copertura, i nomi e la classificazione dipendono dalla versione della fonte. I nomi comuni italiani e inglesi vengono mostrati quando sono presenti nei dati; in caso contrario l'app usa il nome scientifico. Le descrizioni e le immagini delle schede saranno aggiunte da fonti specialistiche, con attribuzione e licenza registrate per ogni contenuto.

The baseline taxonomy is prepared from the **Catalogue of Life (CoL)**. Coverage, names, and classification depend on the source release. Italian and English common names are shown when present; otherwise the app uses the scientific name. Descriptions and images for species cards will be added from specialist sources, with attribution and license recorded for each item.

### Scaricare il database / Download the database

Il file `animalia.sqlite` è voluminoso e **non va aggiunto ai normali file versionati della repository**. Quando è disponibile, scaricalo dalla sezione **Releases** di questa repository. Per consultare la classificazione offline, importa il file nell'app.

The `animalia.sqlite` file is large and **should not be committed to the repository's regular version history**. When available, download it from this repository's **Releases** section. To browse offline, import the file in the app.

> Le schede descrittive e le immagini non sono incluse nel database tassonomico di base. Il download di schede singole, per gruppo o di tutte quelle disponibili, insieme ai pacchetti lingua aggiuntivi, è pianificato.
>
> Species descriptions and images are not included in the baseline taxonomy database. Downloading individual cards, cards by taxonomic group, or all available cards, along with additional language packs, is planned.

## Compilare l'app / Build the app

Requisiti: Flutter SDK, Android SDK e un dispositivo Android o emulatore configurato.

Requirements: Flutter SDK, Android SDK, and a configured Android device or emulator.

Da PowerShell, nella cartella del progetto:

From PowerShell, in the project directory:

```powershell
flutter pub get
flutter build apk --release
```

L'APK viene creato in `build\app\outputs\flutter-apk\app-release.apk`.

The APK is created at `build\app\outputs\flutter-apk\app-release.apk`.

## Rigenerare il database / Regenerate the database

Per preparare il database sorgente su Windows, esegui:

To prepare the source database on Windows, run:

```powershell
.\tools\prepare_animalia_database.ps1
```

Lo script scarica il TextTree di CoL e genera `assets\data\animalia.sqlite`. La versione della fonte e i crediti vanno mantenuti insieme a ogni database pubblicato.

The script downloads the CoL TextTree and creates `assets\data\animalia.sqlite`. Keep the source release and attribution alongside every published database.

## Fonti e attribuzione / Sources and attribution

- **Catalogue of Life** — classificazione e nomi. La licenza generale indicata da CoL è CC BY 4.0, salvo componenti con condizioni diverse. Consultare i metadati della release e conservare le attribuzioni.
- **Fonti specialistiche previste / Planned specialist sources** — AviList (uccelli/birds), The Reptile Database (rettili/reptiles), AmphibiaWeb (anfibi/amphibians), ASM Mammal Diversity Database (mammiferi/mammals), Eschmeyer's Catalog of Fishes (pesci/fishes). I relativi dati saranno integrati dopo aver verificato formato, provenienza e condizioni di riuso.

## Contributi / Contributions

Segnalazioni su errori tassonomici, nomi comuni o problemi dell'app sono benvenute. Indicare, quando possibile, il nome scientifico, la versione del database e una fonte verificabile.

Reports of taxonomy errors, common-name issues, or app bugs are welcome. When possible, include the scientific name, database release, and a verifiable source.
