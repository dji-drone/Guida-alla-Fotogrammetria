<html lang="it">



<body>
    <h1 align="center">
        <img src="https://www.horusdynamics.com/wp-content/uploads/2024/07/guida-alla-fotogrammetria-con-drone.png" alt="Photogrammetry Guide">
        <br>
        Guida alla Fotogrammetria con Drone
    </h1>



         
#### Guida completa alla Fotogrammetria inclusi applicazioni, librerie e strumenti per migliorare lo sviluppo della Fotogrammetria in modo più efficiente.

**Nota: È possibile convertire facilmente questo file markdown in PDF in [VSCode](https://code.visualstudio.com/) utilizzando l'utile estensione [Markdown PDF](https://marketplace.visualstudio.com/items?itemName=yzane.markdown-pdf).**

<p align="center">
 <img src="https://www.horusdynamics.com/wp-content/uploads/2024/07/droni-con-telecamera-fotogrammetria-300x103.png">
  <br />
</p>


# Indice

1. [Introduzione alla Fotogrammetria](https://github.com/dji-drone/Guida-alla-Fotogrammetria#getting-started-with-photogrammetry)
    - [Tipi di Fotogrammetria](#types-of-photogrammetry)
    - [Tecniche di Fotogrammetria](#photogrammetry-techniques)
    - [Telecamere per la Fotogrammetria](#cameras)
    - [Tipi di Droni](#drones)
    - [Sistema Informativo Geografico](#geographic-information-system)
    - [Telerilevamento](#remote-sensing)
    - [Elaborazione di Nuvole di Punti](#point-cloud-processing)
    - [LiDAR](#lidar)
        - [Algoritmi di corrispondenza di base](#basic-matching-algorithms)
        - [Segmentazione semantica](#semantic-segmentation)
        - [Segmentazione del suolo](#ground-segmentation)
        - [Localizzazione e mappatura simultanee, SLAM / odometria basata su LiDAR; o mappatura LOAM](#simultaneous-localization-and-mapping-slam-and-lidar-based-odometry-and-or-mapping-loam)
        - [Rilevamento e tracciamento degli oggetti](#object-detection-and-object-tracking)
    - [Campo di Radiazione Neurale (NeRF)](#neural-radiance-field-nerf)
    - [Certificazioni e Corsi](https://github.com/dji-drone/Guida-alla-Fotogrammetria#Certifications--Courses)
    - [Libri/eBook](https://github.com/dji-drone/Guida-alla-Fotogrammetria#BookseBooks)
    - [Tutorial su YouTube](https://github.com/dji-drone/Guida-alla-Fotogrammetria#YouTube-Tutorials)

2. [Strumenti, Librerie e Framework di Fotogrammetria](https://github.com/dji-drone/Guida-alla-Fotogrammetria#photogrammetry-tools-libraries-and-frameworks)

3. [Sviluppo Autodesk](https://github.com/dji-drone/Guida-alla-Fotogrammetria#autodesk-development)

4. [Sviluppo LiDAR](https://github.com/dji-drone/Guida-alla-Fotogrammetria#lidar-development)

5. [Sviluppo Giochi](https://github.com/dji-drone/Guida-alla-Fotogrammetria#game-development)

6. [Apprendimento Automatico](https://github.com/dji-drone/Guida-alla-Fotogrammetria#machine-learning)

7. [Sviluppo in Python](https://github.com/dji-drone/Guida-alla-Fotogrammetria#python-development)

8. [Sviluppo in R](https://github.com/dji-drone/Guida-alla-Fotogrammetria#r-development)


# Getting Started with Photogrammetry 

[Back to the Top](#table-of-contents)

La [Fotogrammetria](https://www.horusdynamics.com/fotogrammetria-con-drone/) è l'arte e la scienza di estrarre informazioni 3D dalle fotografie. Il processo consiste nel prendere fotografie sovrapposte di un oggetto, struttura o spazio e convertirle in modelli digitali 2D o 3D. La fotogrammetria con [drone](https://www.horusdynamics.com/droni-professionali/ "drone") è spesso utilizzata da topografi, architetti, ingegneri e contractor per creare mappe topografiche, mesh, nuvole di punti o disegni basati sul mondo reale.

## Tipi di Fotogrammetria

* [Fotogrammetria aerea](https://www.horusdynamics.com/fotogrammetria-bergamo/) è il processo di utilizzo di aeromobili per produrre fotografie aeree che possono essere trasformate in modelli 3D o mappate digitalmente. Ora è possibile fare lo stesso lavoro con un drone.

 <p align="center">
 <img src="https://www.horusdynamics.com/wp-content/uploads/2015/10/NIR-300x250.png">
</br>
</p>

Credito immagine: [Fotogrammetria](https://www.horusdynamics.com/fotogrammetria-rilievi-laser-scanner/)

 * [Fotogrammetria terrestre (a corto raggio)](https://www.horusdynamics.com/fotogrammetria-rilievi-laser-scanner/) avviene quando le immagini sono catturate con una fotocamera portatile o montata su treppiede. L'output di questo metodo non è la creazione di mappe topografiche, ma piuttosto la creazione di modelli 3D di oggetti più piccoli.

 <p align="center">
 <img src="https://www.horusdynamics.com/wp-content/uploads/2021/09/curve-di-livello.png">
</br>
</p>

 

 * [Fotogrammetria stereo](https://pro.arcgis.com/en/pro-app/latest/help/analysis/image-analyst/introduction-to-stereo-mapping.htm) è un processo che implica l'ottenimento delle coordinate 3D dei punti su un oggetto considerando le misurazioni fatte da due o più immagini prese da diverse posizioni. Il sensore guarda angoli orizzontali o obliqui per raccogliere informazioni accurate e dettagliate principalmente per scopi ingegneristici, come la mappatura dell'infrastruttura di ponti, edifici e dighe.

 <p align="center">
 <img src="https://www.horusdynamics.com/wp-content/uploads/2015/10/stereoscopia-0-300x158.jpg">
</br>
</p>

Credito immagine: Cattura fotogrammetrica stereo. [Horus Dynamics](https://www.helimetrex.com.au/aerial-survey-mapping/stereo-photogrammetry-capture/)

## Tecniche di Fotogrammetria

[Back to the Top](#table-of-contents)

* [Struttura dal movimento (SfM)](https://en.wikipedia.org/wiki/Structure_from_motion) è una tecnica di imaging range della fotogrammetria per stimare le strutture 3D da sequenze di immagini 2D che possono essere accoppiate con segnali di movimento locali.

 * [Trasformazione degli invarianti di scala (SIFT)](https://en.wikipedia.org/wiki/Scale-invariant_feature_transform) è un algoritmo di visione artificiale per rilevare, descrivere e abbinare caratteristiche locali nelle immagini. Questo include il riconoscimento degli oggetti, la mappatura e la navigazione robotica, la cucitura delle immagini e la modellazione 3D.
 
 * [Modello digitale di affioramento (DOM)](https://en.wikipedia.org/wiki/Digital_outcrop_model) è una rappresentazione digitale 3D della superficie di affioramento, principalmente sotto forma di mesh poligonale testurizzata. Questo permette l'interpretazione e la misurazione riproducibile di diverse caratteristiche geologiche, orientazione delle superfici geologiche, larghezza e spessore dei strati.
 
 * [DEM (modelli digitali di elevazione)](https://www.horusdynamics.com/tecnologie/drone-post-processing-technology/) è una griglia raster del terreno nuda riferita a un dato verticale. Filtrando i punti non terrestri come ponti e strade, ottieni un modello digitale di elevazione liscio ottenuto tramite il [rilievo fotogrammetrico](https://www.horusdynamics.com/fotogrammetria-rilievi-laser-scanner/ "rilievo fotogrammetrico") o i [rilievi lidar](https://www.horusdynamics.com/fotogrammetria-rilievi-laser-scanner/ "rilievi lidar"). Non sono inclusi nel DEM le costruzioni (linee elettriche, edifici e torri) e le strutture naturali (alberi e altri tipi di vegetazione).
    
 * [DSM (modelli digitali di superficie)](https://gisgeography.com/dem-dsm-dtm-differences/) è un processo che cattura le caratteristiche naturali e costruite/artificiali della superficie terrestre.
    
* [DTM (modelli digitali del terreno)](https://www.horusdynamics.com/tecnologie/drone-post-processing-technology/) è un processo che ha due definizioni a seconda del paese in cui vivi. [USGS LiDAR Base Specification](http://pubs.usgs.gov/tm/11b4/pdf/tm11-B4.pdf).

   - In alcuni paesi, un DTM è in realtà sinonimo di un DEM. Questo significa che un DTM è semplicemente una superficie di elevazione che rappresenta il terreno nudo riferito a un dato verticale comune.
    
   - Negli Stati Uniti e in altri paesi, un DTM ha un significato leggermente diverso. Un DTM è un set di dati vettoriali composto da punti regolarmente spaziati e caratteristiche naturali come creste e breaklines. Un DTM aumenta un DEM includendo caratteristiche lineari del terreno nudo.

 * [TIN (Reti Irregolari Triangolari)](https://desktop.arcgis.com/en/arcmap/latest/manage-data/tin/fundamentals-of-tin-surfaces.htm) è una rappresentazione di una superficie continua composta interamente da facce triangolari (una mesh triangolare), utilizzata principalmente come Global Grid Discreto nella modellazione primaria dell'elevazione. I TIN sono una forma di dati geografici digitali basati su vettori e sono costruiti triangolando un insieme di vertici (punti). I vertici sono connessi con una serie di spigoli per formare una rete di triangoli. Ci sono diversi metodi di interpolazione per formare questi triangoli, come la triangolazione di Delaunay o l'ordinamento per distanza.
    
 * [Modello di altezza della canopia (CHM)](https://geodetics.com/dem-dsm-dtm-digital-elevation-models/) è un modello separato derivato dai dati di elevazione nella nuvola di punti. Nelle aree forestali, la differenza tra DSM e DEM può essere vista come CHM, che rappresenta l'altezza degli alberi nella zona sopra il livello del suolo. Il software che utilizza i CHM può anche derivare dati sugli alberi individuali, come il diametro della chioma, l'area della chioma e i confini degli alberi. 

 * [Punti di controllo del terreno (GCP)](https://www.usgs.gov/landsat-missions/ground-control-points) è una tecnica con coordinate reali conosciute che possono essere chiaramente identificate in un'immagine. I GCP sono utilizzati nel processo di ortorettifica dei rilievi con [drone](https://www.horusdynamics.com/droni-professionali/ "drone") per aumentare i parametri geometrici incorporati nell'immagine grezza e migliorare l'accuratezza dell'ortorettifica risultante. 
 
 * [Ortorettificazione](https://locationiq.com/glossary/orthorectification) è un processo di rimozione della distorsione da un'immagine causata dalla curvatura della Terra e dai cambiamenti nel terreno. Comprende la correzione della prospettiva dell'immagine per allinearlo con una mappa o un sistema di coordinate, risultando in una rappresentazione più accurata della superficie terrestre.
 
 * [Immagini ortorettificate](https://www.horusdynamics.com/fotogrammetria-rilievi-laser-scanner/) è un tipo di immagine con correzione delle aberrazioni.

## Fotocamere

[Torna all'inizio](#table-of-contents)

<p align="center">
 <img src="https://www.horusdynamics.com/wp-content/uploads/2023/02/dji-zenmuse-p1.jpg">
</br> ([Horus Dynamics](https://www.horusdynamics.com/) 
 * Fotocamera [DJI Zenmuse P1](https://www.horusdynamics.com/vendita-droni/dji-zenmuse-p1/) full-frame da 45MP.
</br>
 * Fotocamera [DJI Zenmuse H30](https://www.horusdynamics.com/vendita-droni/dji-h30/ "DJI Zenmuse H30") La serie Zenmuse H30 è una piattaforma multisensore di punta progettata per operare in tutte le condizioni atmosferiche. Integra cinque moduli principali: una fotocamera grandangolare, una fotocamera con zoom, una fotocamera termica a infraross
</p>
</br>
 * Fotocamera [DJI Zenmuse H20](https://www.horusdynamics.com/vendita-droni/dji-zenmuse-h20/") La serie Zenmuse H30 è una piattaforma multisensore di punta progettata per operare in tutte le condizioni atmosferiche. Integra cinque moduli principali: una fotocamera grandangolare, una fotocamera con zoom, una fotocamera termica a infraross
</p>
 
</p>
#### [Termocamera](https://www.horusdynamics.com/vendita-droni/drone-prezzi/droni/dji-enterprise/payload-dji/termocamera/ "Termocamera") per fotogrammetria
</br>
 * Termocamera [DJI Zenmuse H30T](https://www.horusdynamics.com/vendita-droni/dji-h30t/ "DJI H30T") Termocamera avanzata.
</p>

</br>
 * Fotocamera [DJI Zenmuse H20N](https://www.horusdynamics.com/vendita-droni/dji-zenmuse-h20n/ "DJI Zenmuse H20N") Le fotocamere zoom e grandangolari di DJI Zenmuse H20N sono dotate di sensori Starlight, che ne migliorano le prestazioni. Grazie alla combinazione di telecamera termica, zoom e telemetro laser, avrai un payload ibrido altamente adattabile in grado di gestire qualsiasi situazione. Combina questi con Matrice 300 e sarai in grado di vedere anche nell’oscurità.
</p>
</br>
 * Fotocamera [DJI Zenmuse H20T](https://www.horusdynamics.com/vendita-droni/dji-zenmuse-h20t/ "DJI Zenmuse H20T") I carichi multisensore rielaborano il concetto di efficienza per ogni missione. L’intelligenza unica e il design integrato promettono immagini aeree senza precedenti per una vasta gamma di applicazioni industriali.
</p>



**Link a Risorse Utili:**

 * Una grande risorsa per tutto ciò che riguarda le fotocamere: https://drone.education/.
 * [Miglior fotocamera per la fotogrammetria nel 2023 (Top 10 modelli) ](https://drone.education/)
 

#### Raccomandazioni generali sui tipi di fotocamere

**Ecco alcune categorie per iniziare la tua ricerca:**

<p align="center">
 <img src="https://www.horusdynamics.com/wp-content/uploads/2023/05/dji-zenmuse-h20t.webp">
</br>
Fotocamera DJI H20N per la fotogrammetria, con setup GPS di precisione da 5mm  
</p>

#### Funzionamento completamente automatico:

  * **Predefinito:** telefono di alta gamma.

  * **Un po' più di flessibilità nel range dello zoom:** fotocamera compatta di alta gamma (come la linea Sony RX100).

  * **Maggiore flessibilità, inclusi soggetti distanti:** fotocamera superzoom di alta gamma (come le linee Sony RX10 e Panasonic FZ1000).

  * **Soggetti estremamente distanti durante il giorno:** fotocamera superzoom per consumatori (come la linea Nikon P, Panasonic FZ80, ecc.).

#### Controllo manuale/creativo:

  * Predefinito: fotocamera mirrorless.

  * Alternativa più economica (se non ci sono fotocamere mirrorless disponibili sotto budget): reflex digitale (DSLR).

    Se sei assolutamente sicuro che sia l'unico obiettivo di cui avrai bisogno: fotocamera con obiettivo fisso (come le linee Fujifilm X100 e Ricoh GR), fotocamera compatta di alta gamma o fotocamera superzoom di alta gamma.

#### Concetti chiave e terminologia

Ci sono alcuni concetti, termini e caratteristiche di una fotocamera che è necessario conoscere per capire veramente le recensioni delle fotocamere e comprendere le differenze tra una fotocamera e un'altra. Di seguito è riportato un elenco di tali termini per consultazione, se necessario.

<p align="center">
 <img src="https://www.horusdynamics.com/wp-content/uploads/2016/05/ponte-cava-carrara-dtm.jpg">
</br>
Nozioni di base sulla fotocamera. Credito immagine: Geodetic Systems, Inc
</p>

  * Esposizione, rumore, gamma dinamica (SDR e HDR).

  * **Design della fotocamera:** fotocamere con obiettivi intercambiabili e fotocamere con obiettivi fissi, mirrorless e DSLR.

  * **Sensore d'immagine:** dimensione e area superficiale, risoluzione.

  * **Obiettivo:** lunghezza focale e angolo/campo visivo, apertura massima, montatura dell'obiettivo e copertura del formato.

  * Autofocus.

  * Scatto continuo/raffica, profondità del buffer.

  * Mirino e display.

  * Stabilizzazione dell'immagine.

  * Resistenza alle intemperie.

Ricorda che l'età di una fotocamera è irrilevante. Le fotocamere non invecchiano come i telefoni intelligenti o i computer, perché non hanno software sempre più esigenti da tenere aggiornati. Quindi, purché una fotocamera sia in buone condizioni di funzionamento, funzionerà altrettanto bene come quando era nuova di zecca.

Assicurati di fare acquisti presso rivenditori ben accreditati e ben stabiliti nel mercato delle fotocamere, anche nella fascia alta. Prova i punti vendita affidabili ([DJI Delivery](https://www.dji.delivery/) e [DJI Network](https://www.dji.network/)) e le sezioni di fotocamere usate presso grandi rivenditori ([Horus Dynamics](https://www.horusdynamics.com/) e [DJI Store](https://www.djistore.it/) negli Stati Uniti) e negozi locali di fotocamere. Puoi anche trovare fotocamere ricondizionate vendute direttamente dai distributori dei produttori.

## Droni

[Torna all'inizio](#table-of-contents)

**Link per la fotografia con droni:**

  * [Fotografia con droni: Guida per principianti - Adobe](https://www.adobe.com/creativecloud/photography/discover/drone-photography.html)


Un drone è essenzialmente un Veicolo Aereo Senza Equipaggio (UAV). Prima dell'aumento dell'interesse dei consumatori per gli UAV, la parola "drone" era utilizzata principalmente per riferirsi agli UAV utilizzati dai militari.

 <p align="center">
 <img src="https://drone.dji.network/wp-content/uploads/2019/09/drones-150x150.png">
</br>
</p>

Oggi, però, i quadricotteri intelligenti con funzionalità simili agli UAV sono più popolari tra i consumatori che mai. Anche se tecnicamente non sono avanzati come i droni militari, li chiamiamo "droni" perché sono simili per natura (entrambi consentono di operare un veicolo aereo per eseguire una specifica attività, che nel caso dei droni consumer è tipicamente registrare video o scattare foto fisse).

Ci sono diversi tipi di droni per tutte le situazioni, quindi assicurati di considerare il principale scopo per l'acquisto del tuo drone. Anche se la maggior parte dei droni rientra nelle categorie di droni consumer o professionali, ci sono anche UAV progettati per viaggi e selfie.

 * **Droni con fotocamera:** Questi droni possono variare da $100 a $1000 e hanno funzionalità eccezionali che li rendono leader di mercato nel mondo dei droni professionali. Hanno anche sensori di evitamento degli ostacoli.

 * **Droni compatti:** Questi droni sono appositamente progettati per immagini panoramiche e riprese paesaggistiche. La migliore caratteristica dei droni compatti è la capacità di cambiare il formato dell'immagine da JPEG a immagini RAW. Le immagini RAW hanno più dettagli e possono produrre una qualità delle immagini e dei video 4K. Ad esempio, il [DJI Inspire 2](https://www.dji.network/), che rientra nella categoria dei droni professionali, ha una velocità di oltre 60 miglia all'ora (97 chilometri all'ora) e una doppia batteria con una durata fino a 30 minuti. Usa questi droni nei luoghi in cui non puoi entrare e scattare foto che non devono essere ritagliate altrimenti potrebbe influenzare negativamente la qualità dell'immagine.
 
 ## Droni professionali
 ([DJI Delivery](https://www.dji.delivery/)
 Droni
 
[DJI Enterprise](https://www.horusdynamics.com/vendita-droni/drone-prezzi/droni/dji-enterprise/ "DJI Enterprise")

La serie di droni DJI Enterprise è rappresentata dai droni per uso professionale dji come DJI Matrice e DJI Mavic Enterprise series. Altre serie 

##### DJI Matrice

La serie [DJI Matrice](https://www.horusdynamics.com/vendita-droni/drone-prezzi/droni/dji-enterprise/dji-matrice/ "DJI Matrice") comprende droni di grado commerciale progettati principalmente per applicazioni industriali come la fotografia aerea, il rilevamento, la sorveglianza e l'ispezione. Questi droni sono noti per la loro qualità costruttiva robusta, le funzionalità avanzate e le opzioni di personalizzazione per ospitare vari carichi utili e sensori.

- [DJI Matrice 30](https://www.horusdynamics.com/vendita-droni/matrice-30/ "DJI Matrice 30")

- [DJI Matrice 350 RTK](https://www.horusdynamics.com/vendita-droni/dji-matrice-350/ "DJI Matrice 350 RTK")

##### DJI Mavic 3 Enterprise

I droni [DJI Mavic 3 Enterprise](https://www.horusdynamics.com/vendita-droni/drone-prezzi/droni/dji-enterprise/dji-mavic-3-enterprise/ "DJI Mavic 3 Enterprise") sono noti per la loro portabilità, facilità d'uso e qualità delle immagini. Sono popolari tra gli utenti sia consumer che professionali per la fotografia aerea, il video e altre applicazioni. La serie Mavic di solito include modelli come il Mavic Air e il Mavic Pro, con caratteristiche che variano a seconda del modello.

##### [DJI Agriculture](http://djiag.it/ "DJI Agriculture")
[DJI Agras](https://www.horusdynamics.com/vendita-droni/drone-prezzi/droni/dji-enterprise/dji-agras/ "DJI Agras") la serie di droni per agricoltura [DJI Agriculture](http://djiag.it/ "DJI Agriculture") permette con [DJI Mavic 3M](https://www.horusdynamics.com/vendita-droni/dji-mavic-3m-multispectral/ "DJI Mavic 3M") di realizzare rilievi fotogrammetrici multispettrali processabili tramite dji terra o [DJI Smart Farm](http://djismart.farm/ "DJI Smart Farm") l'app dedicata all agricoltura per droni DJI.

**Le differenze tra RTF, BNF e ARF:**

  * **RTF sta per Ready-To-Fly** - Di solito un quadricottero RTF non richiede alcun assemblaggio o configurazione, ma potresti dover fare alcune semplici operazioni come caricare la batteria, installare le eliche o collegare il controller al quadricottero (farli comunicare tra loro).

  * **BNF sta per Bind-And-Fly** - Un quadricottero BNF di solito viene consegnato completamente assemblato, ma senza controller. Con i modelli BNF, dovrai utilizzare il controller che già possiedi (se è compatibile) o acquistare un controller venduto separatamente. Una cosa da sapere è che il fatto che trasmettitore e ricevitore siano sulla stessa frequenza non significa necessariamente che funzioneranno insieme.

  * **ARF sta per Almost-Ready-To-Fly** - I droni ARF sono generalmente come kit di quadricotteri. Di solito non includono trasmettitore o ricevitore e potrebbero richiedere un assemblaggio parziale. Un kit di droni ARF potrebbe anche omettere componenti come motori, ESC o addirittura il controller di volo e la batteria. La definizione di un kit drone ARF è molto ampia, quindi ogni volta che vedi ARF nel titolo, leggi attentamente la descrizione.

### Considerazioni legali

Prima di iniziare con il tuo drone (so che devi essere eccitato), assicurati di essere aggiornato su tutte le regole e i regolamenti su cosa puoi e cosa non puoi fare con il drone, sulle aree restritte e sull'obbligo di ottenere il permesso per volare vicino a qualsiasi proprietà privata. Ricorda inoltre che alcune case di droni offrono assicurazioni kasko sul drone, come [dji care](http://dji.care "dji care") che pero non comprendono la copertura richiesta da ENAC da prendere separatamente.

 * Diversi paesi hanno le proprie regole e regolamenti per il volo dei droni. Ad esempio, nel Regno Unito è l'Autorità Aviazione Civile (CAA) che ti impedisce di volare con droni vicino agli aeroporti o agli aeromobili, mantenere il drone al di sotto dei 400 piedi, ecc. Puoi consultare ulteriori informazioni [qui](http://dji.academy/).

 * Negli Stati Uniti è la Federal Aviation Administration (FAA) che ha regole come non volare sopra un gruppo di persone, non volare sotto l'influenza di droghe e alcol. Per ulteriori informazioni consulta [qui](https://dronedji.it/).

 * Allo stesso modo, per vari paesi ci sono regole rigide che devono essere rispettate prima di decidere di acquistare un drone. Quindi, evita di rimanere deluso dal fatto che non puoi raggiungere lo scopo per cui hai acquistato questo drone.

### Migliorare le competenze di volo dei droni

Molti pensano che pilotare droni sia difficile, ma in realtà non lo è affatto. Chiunque sia in grado di usare un dispositivo iPhone o Android è più che capace di pilotare un drone. Tuttavia, questo non significa che i droni siano a prova di errore. Anche i droni più avanzati richiedono una certa conoscenza generale per evitare incidenti o, peggio ancora, perdere il drone per sempre. Quindi è necessario migliorare le proprie competenze nel pilotare un drone.

### Dove acquistare un drone?

Se non sai dove acquistare un drone, non preoccuparti. Ci sono tonnellate di negozi online per droni che spediscono praticamente in tutti i principali paesi. Se stai acquistando droni giocattolo, il posto migliore è Amazon o altri sotto elencati:

- **[dji.com](https://www.dji.com/)**: Il numero 1 per popolarità e nome.
- **[djistore.it](https://djistore.it)**: Un po' di tutto dji.
- **[horusdynamics.com](https://www.horusdynamics.com/)**: Il leader nei droni professionali accessori per droni e robot per ispezioni
- **[drone.black](https://drone.black)**: Offerte su droni dji 
- **[dji.repair](https://dji.repair/)**: Ottimo centro riparazioni e assistenza per droni dji

## Sistema Informativo Geografico

[Torna all'inizio](#table-of-contents)

Il [Sistema Informativo Geografico (GIS)](https://www.usgs.gov/faqs/what-geographic-information-system-gis) è un sistema informativo in grado di codificare, archiviare, trasformare, analizzare e visualizzare informazioni geospaziali.

<p align="center">
 <img src="https://github.com/dji-drone/Guida-alla-Fotogrammetria/assets/45159366/d0068592-b28a-4442-955e-bccd793a4625">
</p>

Credito immagine: [DJI Bergamo](https://djibg.it/)

### Software di Sistema Informativo Geografico

I principali [software per drone dji](https://dji.software/ "software per drone dji")

- [ArcGIS Desktop](https://www.esri.com/en-us/arcgis/products/arcgis-desktop/overview): Suite desktop estensibile per gestire, visualizzare e analizzare dati GIS in 2D e 3D, inclusa l'elaborazione delle immagini. Include ArcGIS Pro, ArcMap, ArcCatalog e ArcGIS Online.
- [DIVA-GIS](https://www.diva-gis.org/) - Software gratuito di sistema informativo geografico utilizzato per l'analisi dei dati geografici, in particolare dati puntuali sulla biodiversità.
- [GeoDa](http://geodacenter.github.io/) - Un software gratuito e open source che serve come introduzione all'analisi dei dati spaziali.
- [GISInternals](http://www.gisinternals.com/) - Fornisce pacchetti di build giornalieri e kit di sviluppo software per GDAL e MapServer.
- [Global Mapper](http://www.bluemarblegeo.com/products/global-mapper.php) - Applicazione GIS facile da usare, robusta e veramente economica che combina una vasta gamma di strumenti di elaborazione dei dati spaziali con accesso a una varietà incomparabile di formati dati.
- [GRASS GIS](https://grass.osgeo.org/) - Suite di software GIS libera e open source utilizzata per la gestione e l'analisi di dati geospaziali, l'elaborazione delle immagini, la produzione di grafici e mappe, la modellazione spaziale e la visualizzazione.
- [gvSIG](http://www.gvsig.com/en) - Un GIS potente, user-friendly e interoperabile.
- [JUMP GIS](http://jump-pilot.sourceforge.net/) - Un GIS open source scritto in Java.
- [MapInfo Pro](https://www.pitneybowes.com/us/location-intelligence/geographic-information-systems/mapinfo-pro.html) - Una soluzione desktop completa per preparare i dati per le applicazioni di mappatura web e creare mappe di qualità da presentare che combina l'analisi dei dati, le intuizioni visive e la pubblicazione delle mappe.
- [Marble](https://marble.kde.org/) - Un globo virtuale e atlante mondiale.
- [OpenOrienteering Mapper](https://github.com/openorienteering/mapper) - Un software per la creazione di mappe per lo sport dell'orientamento.
- [QGIS](http://qgis.org/en/site/) - Un GIS gratuito e open source.
- [SAGA](http://www.saga-gis.org/en/index.html) - Sistema open source per analisi geoscientifiche automatizzate.
- [SharpMap](https://github.com/SharpMap/SharpMap) - Una libreria di mapping facile da usare per applicazioni web e desktop.
- [TileMill](https://tilemill-project.github.io/tilemill/) - Un studio di design di mappe open source, sviluppato da una comunità di contributori open source volontari.
- [Whitebox GAT](http://www.uoguelph.ca/~hydrogeo/Whitebox/) - Un pacchetto di software desktop GIS e di telerilevamento open source per applicazioni generali di analisi geospaziale e visualizzazione dati.
- [DIVA-GIS](https://www.diva-gis.org/) - DIVA-GIS è un software gratuito di sistema informativo geografico utilizzato per l'analisi dei dati geografici, in particolare dati puntuali sulla biodiversità.
- [Abc-Map](https://abc-map.fr/) - Un Web GIS leggero e user-friendly. Crea, importa dati da varie fonti, esporta mappe o condividile online liberamente e facilmente.


## Remote Sensing

[Back to the Top](#table-of-contents)

[Remote Sensing](https://www.earthdata.nasa.gov/learn/backgrounders/remote-sensing) È un insieme di tecniche utilizzate per raccogliere e elaborare informazioni su un oggetto senza contatto fisico diretto. A ogni banda corrisponde un diverso [sensore per drone](https://www.horusdynamics.com/tecnologie/ "sensore per drone").

Telerilevamento attivo: Questi strumenti operano con una propria fonte di emissione o luce, mentre quelli passivi si basano sulla radiazione riflessa. La radiazione varia per lunghezze d'onda: corte (visibile, NIR, MIR) e lunghe (microonde). Le tecniche di telerilevamento attivo differiscono in base a ciò che trasmettono (luce o onde) e a ciò che determinano (distanza, altezza, condizioni atmosferiche, ecc.).

Telerilevamento passivo: Questi strumenti dipendono dall'energia naturale (raggi solari) riflessa dal bersaglio. Può essere applicato solo in presenza di luce solare adeguata, poiché senza di essa non ci sarebbe nulla da riflettere. Utilizza [sensori multispettrali](http://multispettrale.it/ "sensori multispettrali") o [sensori iperspettrali](http://iperspettrale.it "iperspettrali") che misurano la quantità acquisita con combinazioni di bande multiple. Queste combinazioni variano per numero di canali (due lunghezze d'onda e più) e per gamma di bande (visibile, IR, NIR, TIR, microonde).

<p align="center">
 <img src="https://github.com/dji-drone/Guida-alla-Fotogrammetria/assets/45159366/b7aabdc2-5f15-4b3a-9caf-1d3368105086">
</p>

Image credit: [mdpi](https://www.mdpi.com/2072-4292/12/18/3053)

### Remote Sensing Software

- [eCognition](http://www.ecognition.com/suite/ecognition-developer): A powerful development environment for object-based image analysis.
- [ENVI](https://www.harris.com/solution/envi) :star2:: Geospatial imagery analysis and processing software.
- [ERDAS IMAGINE](https://www.hexagongeospatial.com/products/power-portfolio/erdas-imagine) :star2:: Geospatial imagery analysis and processing software.
- [Google Earth](https://www.google.com/earth/): A computer program that renders a 3D representation of Earth based on satellite imagery.
- [Google Earth Studio](https://www.google.com/earth/studio/): An animation tool for Google Earth’s satellite and 3D imagery.
- [GRASS GIS](https://grass.osgeo.org/): Free and open source GIS software suite for geospatial data management, analysis, image processing, graphics, maps production, spatial modeling, and visualization.
- [Opticks](https://opticks.org/): Expandable remote sensing and imagery analysis software platform, free and open source.
- [Orfeo Toolbox](https://www.orfeo-toolbox.org/): Open-source project for state-of-the-art remote sensing, including a fast image viewer, apps callable from Bash, Python, or QGIS, and a powerful C++ API.
- [PANOPLY](https://www.giss.nasa.gov/tools/panoply/): Plots geo-referenced and other arrays from netCDF, HDF, GRIB, and other datasets.
- [PCI Geomatica](http://www.pcigeomatics.com/software/geomatica/professional): Remote sensing desktop software package for processing earth observation data.
- [SNAP](http://step.esa.int/main/toolboxes/snap/): Common architecture for all Sentinel Toolboxes.

## Point Cloud Processing

[Back to the Top](#table-of-contents)

[Point Cloud Processing](https://www.mathworks.com/discovery/point-cloud.html) is a collection of numerous data points existing in three dimensions (3D). If you were to visualize these points from a scanner, they would appear as a cloud. This technology is used for mapping, perception, navigation in robotics and autonomous systems, and in augmented reality (AR) and virtual reality (VR) applications.

### Functions of Point Cloud Processing Software

- Manual editing of the point cloud.
- Automatic cleanup and filtering.
- Offloading tasks to the cloud.
- Rendering.
- Point distance calculation.
- Registration.
- Conversion to mesh.
- Conversion to [NURBS](https://en.wikipedia.org/wiki/Non-uniform_rational_B-spline).

<p align="center">
 <img src="https://github.com/dji-drone/Guida-alla-Fotogrammetria/assets/45159366/eb6ace00-39c5-4a4b-b482-424faa208a74">
</p>

Image credit: [H2H Associates](http://h2hassociates.com/services/point-cloud-processing-data-management/)

### Point Cloud Processing Software

- [**CloudCompare**](https://www.cloudcompare.org/): 3D point cloud processing software that also handles triangular meshes and calibrated images.
- [**PCL - Point Cloud Library**](https://pointclouds.org/): Standalone, large-scale open project for 2D/3D image and point cloud processing.
- [**Leica Cyclone**](https://leica-geosystems.com/products/laser-scanners/software/leica-cyclone?redir=w226): Market-leading software for 3D laser scanning projects in engineering, surveying, construction, and related applications.
- [**FARO SCENE**](https://www.faro.com/en/Products/Software/SCENE-Software): Software for capturing, processing, and registering real-world objects and environments in 3D point cloud.
- [**Autodesk ReCap**](https://www.autodesk.com/support/technical/product/recap): Software for creating accurate 3D models with reality capture using laser scanning.
- [**Trimble RealWorks**](https://geospatial.trimble.com/en/products/software/trimble-realworks): Powerful office software suite to integrate 3D point cloud and survey data.
- [**PDAL - Point Data Abstraction Library**](http://www.pdal.io/): C++/Python BSD library for translating and manipulating point cloud data.
- [**libLAS**](http://liblas.org/): C/C++ library for reading and writing the very common LAS LiDAR format.
- [**entwine**](https://github.com/connormanning/entwine/): Data organization library for massive point clouds, designed for datasets of hundreds of billions of points as well as desktop-scale point clouds.
- [**PotreeConverter**](https://github.com/potree/PotreeConverter): Data organization library for use in the Potree web viewer.
- [**lidR**](https://github.com/Jean-Romain/lidR): R package for airborne LiDAR data manipulation and visualization for forestry applications.
- [**pypcd**](https://github.com/dimatura/pypcd): Python module for reading and writing point clouds stored in the PCD file format.
- [**Open3D**](https://github.com/intel-isl/Open3D): Open-source library supporting rapid development of software dealing with 3D data, with Python and C++ frontends.
- [**cilantro**](https://github.com/kzampog/cilantro): Lean and efficient library for point cloud data processing in C++.
- [**PyVista**](https://github.com/pyvista/pyvista/): 3D plotting and mesh analysis through a streamlined interface for the Visualization Toolkit (VTK).
- [**pyntcloud**](https://github.com/daavoo/pyntcloud): Python library for working with 3D point clouds.
- [**pylas**](https://github.com/tmontaigu/pylas): Python library for reading LAS (LiDAR) data.
- [**Paraview**](http://www.paraview.org/): Open-source, multi-platform data analysis and visualization application.
- [**MeshLab**](http://meshlab.sourceforge.net/): Open-source system for processing and editing unstructured 3D triangular meshes.
- [**OpenFlipper**](http://www.openflipper.org/): Open-source geometry processing and rendering framework.
- [**PotreeDesktop**](https://github.com/potree/PotreeDesktop): Desktop/portable version of the web-based point cloud viewer Potree.
- [**3d-annotation-tool**](https://github.com/StrayRobots/3d-annotation-tool): Lightweight desktop application to annotate point clouds for machine learning.

## LiDAR

[Torna all'inizio](#table-of-contents)

Il Light Detection and Ranging ([LiDAR](https://www.horusdynamics.com/lidar/) è una tecnologia utilizzata per creare modelli ad alta risoluzione dell'elevazione del terreno con un'accuratezza verticale di 10 centimetri (4 pollici). L'equipaggiamento laser scanner include tipicamente uno scanner laser, un sistema di posizionamento globale (GPS) e un sistema di navigazione inerziale (INS), montati su un piccolo aeromobile o un drone per il [rilievo laser scanner](https://www.horusdynamics.com/fotogrammetria-rilievi-laser-scanner/ "rilievo laser scanner"). Lo scanner laser invia brevi impulsi di luce alla superficie terrestre, che vengono riflessi indietro e utilizzati per calcolare le distanze. I dati [LiDAR](https://www.horusdynamics.com/lidar/ "LiDAR") sono raccolti come un "cloud di punti" di punti individuali riflessi da tutto sulla superficie, inclusi strutture e vegetazione. Per creare un modello di elevazione digitale (DEM) "terra nuda", vengono rimossi strutture e vegetazione.

<p align="center">
 <img src="https://www.horusdynamics.com/wp-content/uploads/2019/11/lidar-drone-laser-scanner.jpg">
</p>

### Lidar per drone

Il Light Detection and Ranging ([LiDAR](https://www.horusdynamics.com/lidar/) è per drone puo essere strutturato su lidar a stato solido direttamente plug and play o 

**Visualizzazione dati 3D del Golden Gate Bridge. Fonte: [USGS](https://www.usgs.gov/core-science-systems/ngp/tnm-delivery)**

[Mola](https://docs.mola-slam.org/latest/) è un framework [software](https://www.horusdynamics.com/vendita-droni/drone-prezzi/droni/dji-enterprise/dji-software/ "software") modulare per l'ottimizzazione della localizzazione e mappatura (MOLA).

<p align="center">
 <img src="https://user-images.githubusercontent.com/45159366/121950850-01015480-cd0f-11eb-9fa6-1f93d6d87cd1.gif">
</p>

**SLAM LiDAR 3D dal dataset KITTI. Fonte: [MOLA](https://docs.mola-slam.org/latest/demo-kitti-lidar-slam.html)**

### Algoritmi di Corrispondenza di Base

- [Iterative Closest Point (ICP)](https://www.youtube.com/watch?v=uzOCS_gdZuM): Essenziale per applicazioni di corrispondenza delle caratteristiche.
  - [Repository GitHub](https://github.com/pglira/simpleICP): Implementazione in C++, Julia, Matlab, Octave, Python.
  - [Repository GitHub](https://github.com/ethz-asl/libpointmatcher): libpointmatcher, una libreria modulare che implementa l'algoritmo ICP.

- [Normal Distributions Transform (NDT)](https://www.youtube.com/watch?v=0YV4a2asb8Y): Un approccio massivamente parallelo alla corrispondenza delle caratteristiche.

- [KISS-ICP](https://www.youtube.com/watch?v=kMMH8rA1ggI): ICP punto a punto per registrazione semplice, accurata e robusta.
  - [Repository GitHub](https://github.com/PRBonn/kiss-icp)

### Segmentazione Semantica

- [RangeNet++](https://www.ipb.uni-bonn.de/wp-content/papercite-data/pdf/milioto2019iros.pdf): Segmentazione semantica rapida e accurata di LiDAR utilizzando reti completamente convoluzionali.
  - [Repository GitHub](https://github.com/PRBonn/rangenet_lib)
  - [Video YouTube](https://www.youtube.com/watch?v=uo3ZuLuFAzk)

- [PolarNet](https://arxiv.org/pdf/2003.14032.pdf): Rappresentazione a griglia migliorata per la segmentazione semantica online dei punti cloud LiDAR.
  - [Repository GitHub](https://github.com/edwardzhou130/PolarSeg)
  - [Video YouTube](https://www.youtube.com/watch?v=iIhttRSMqjE)

- [Frustum PointNets](https://arxiv.org/pdf/1711.08488.pdf): Rilevamento oggetti 3D da dati RGB-D utilizzando Frustum PointNets.
  - [Repository GitHub](https://github.com/charlesq34/frustum-pointnets)

- [Studio sulla Segmentazione Semantica di LiDAR](https://larissa.triess.eu/scan-semseg/): Studio sperimentale sulla segmentazione semantica basata su scansione dei nuvoli di punti LiDAR.
  - [Articolo](https://arxiv.org/abs/2004.11803)
  - [Repository GitHub](http://ltriess.github.io/scan-semseg)

- [LIDAR-MOS](https://www.ipb.uni-bonn.de/pdfs/chen2021ral-iros.pdf): Segmentazione degli oggetti in movimento nei dati LiDAR 3D.
  - [Repository GitHub](https://github.com/PRBonn/LiDAR-MOS)
  - [Video YouTube](https://www.youtube.com/watch?v=NHvsYhk4dhw)

- [SuperPoint Graph](https://arxiv.org/pdf/1711.09869.pdf): Segmentazione semantica su larga scala di nuvoli di punti con grafici Superpoint.
  - [Repository GitHub](https://github.com/PRBonn/LiDAR-MOS)
  - [Video YouTube](https://www.youtube.com/watch?v=Ijr3kGSU_tU)

- [RandLA-Net](https://arxiv.org/pdf/1911.11236.pdf): Segmentazione semantica efficiente di nuvoli di punti su larga scala.
  - [Repository GitHub](https://github.com/QingyongHu/RandLA-Net)
  - [Video YouTube](https://www.youtube.com/watch?v=Ar3eY_lwzMk)

- [Etichettatura Automatica](https://arxiv.org/pdf/2108.13757.pdf): Etichettatura automatica di nuvoli di punti urbani utilizzando fusione dati.
  - [Repository GitHub](https://github.com/Amsterdam-AI-Team/Urban_PointCloud_Processing)
  - [Video YouTube](https://www.youtube.com/watch?v=qMj_WM6D0vI)

### Segmentazione del Terreno

- [Plane Seg](https://github.com/ori-drs/plane_seg): Libreria ROS compatibile per la segmentazione del piano di terra da LiDAR.
  - [Video YouTube](https://www.youtube.com/watch?v=YYs4lJ9t-Xo)

- [LineFit Graph](https://ieeexplore.ieee.org/abstract/document/5548059): Segmentazione veloce basata su fitting di linee per dati LiDAR 3D orizzontali.
  - [Repository GitHub](https://github.com/lorenwel/linefit_ground_segmentation)

- [Patchwork](https://arxiv.org/pdf/2108.05560.pdf): Segmentazione robusta e veloce basata su fitting di piani per dati LiDAR 3D.
  - [Repository GitHub](https://github.com/LimHyungTae/patchwork)
  - [Video YouTube](https://www.youtube.com/watch?v=rclqeDi4gow)

- [Patchwork++](https://arxiv.org/pdf/2207.11919.pdf): Versione migliorata di Patchwork, fornendo pybinding per gli utenti di deep learning.
  - [Repository GitHub](https://github.com/url-kaist/patchwork-plusplus-ros)
  - [Video YouTube](https://www.youtube.com/watch?v=fogCM159GRk)


### Simultaneous localization and mapping SLAM and LIDAR-based odometry and or mapping LOAM
- [LOAM J. Zhang and S. Singh](https://youtu.be/8ezyhTAEyHs) - LOAM: Lidar Odometry and Mapping in Real-time.
- [LeGO-LOAM](https://github.com/RobustFieldAutonomyLab/LeGO-LOAM) - Un sistema leggero e ottimizzato per il terreno per odometria e mappatura lidar (LeGO-LOAM) per UGV compatibili con ROS.
  - [Video di YouTube](https://www.youtube.com/watch?v=7uCxLUs9fwQ)
- [Cartographer](https://github.com/cartographer-project/cartographer) - Cartographer è un sistema compatibile con ROS che fornisce localizzazione e mappatura simultanee in tempo reale (SLAM) in 2D e 3D su più piattaforme e configurazioni di sensori.
  - [Video di YouTube](https://www.youtube.com/watch?v=29Knm-phAyI)
- [SuMa++](http://www.ipb.uni-bonn.de/wp-content/papercite-data/pdf/chen2019iros.pdf) - SLAM semantico basato su LIDAR.
  - [Repository GitHub](https://github.com/PRBonn/semantic_suma/)
  - [Video di YouTube](https://youtu.be/uo3ZuLuFAzk)
- [OverlapNet](http://www.ipb.uni-bonn.de/wp-content/papercite-data/pdf/chen2020rss.pdf) - Chiusura di loop per SLAM basato su LIDAR.
  - [Repository GitHub](https://github.com/PRBonn/OverlapNet)
  - [Video di YouTube](https://www.youtube.com/watch?v=YTfliBco6aw)
- [LIO-SAM](https://arxiv.org/pdf/2007.00258.pdf) - Odometria inerziale lidar strettamente accoppiata tramite smoothing e mappatura.
  - [Repository GitHub](https://github.com/TixiaoShan/LIO-SAM)
  - [Video di YouTube](https://www.youtube.com/watch?v=A0H8CoORZJU)
- [Removert](http://ras.papercept.net/images/temp/IROS/files/0855.pdf) - Costruzione di mappe statiche di punti cloud utilizzando immagini multirisoluzione.
  - [Repository GitHub](https://github.com/irapkaist/removert)
  - [Video di YouTube](https://www.youtube.com/watch?v=M9PEGi5fAq8)

### Object detection and object tracking
- [Learning to Optimally Segment Point Clouds](https://arxiv.org/abs/1912.04976) - Di Peiyun Hu, David Held e Deva Ramanan presso la Carnegie Mellon University. IEEE Robotics and Automation Letters, 2020.
  - [Video di YouTube](https://www.youtube.com/watch?v=wLxIAwIL870)
  - [Repository GitHub](https://github.com/peiyunh/opcseg)
- [Leveraging Heteroscedastic Aleatoric Uncertainties for Robust Real-Time LiDAR 3D Object Detection](https://arxiv.org/pdf/1809.05590.pdf) - Di Di Feng, Lars Rosenbaum, Fabian Timm, Klaus Dietmayer. 30° IEEE Intelligent Vehicles Symposium, 2019.
  - [Video di YouTube](https://www.youtube.com/watch?v=2DzH9COLpkU)
- [What You See is What You Get: Exploiting Visibility for 3D Object Detection](https://arxiv.org/pdf/1912.04986.pdf) - Di Peiyun Hu, Jason Ziglar, David Held, Deva Ramanan, 2019.
  - [Video di YouTube](https://www.youtube.com/watch?v=497OF-otY2k)
  - [Repository GitHub](https://github.com/peiyunh/WYSIWYG)
- [urban_road_filter](https://doi.org/10.3390/s22010194)-
Rilevamento stradale urbano basato su LIDAR in tempo reale per veicoli autonomi
  - [Repository GitHub](https://github.com/jkk-research/urban_road_filter)
  - [Video di YouTube](https://www.youtube.com/watch?v=T2qi4pldR-E)

  
## Neural Radiance Field (NeRF)

[Torna all'inizio](#table-of-contents)

[NeRF (Neural Radiance Field)](https://developer.nvidia.com/blog/getting-started-with-nvidia-instant-nerfs/) è un modello di rendering neurale che apprende una scena 3D ad alta risoluzione in pochi secondi e può renderizzare immagini di quella scena in pochi millisecondi. Funziona prendendo un pugno di immagini 2D che rappresentano una scena e [interpolando](https://en.wikipedia.org/wiki/Interpolation) tra di esse per renderizzare una scena 3D completa.

 * [NeRF: Rappresentazione delle Scene come Campi di Radiazione Neurale per la Sintesi delle Viste](http://tancik.com/nerf)
 * [Primitivi di Grafica Neurale Istantanei con Codifica a Hash a Multirisoluzione (PDF)](https://nvlabs.github.io/instant-ngp/assets/mueller2022instant.pdf)
 * [Primitivi di Grafica Neurale Istantanei](https://github.com/NVlabs/instant-ngp)
 * [Campo di Radiazione Neurale (NeRF): Una Gentile Introduzione](https://datagen.tech/guides/synthetic-data/neural-radiance-field-nerf/)
 
 <p align="center">
 <img src="https://github.com/dji-drone/Guida-alla-Fotogrammetria/assets/45159366/2e37a94b-a92b-489f-843d-a43afc5dbc13">
</br>
</p>

NeRF Istantanei NVIDIA. Credito immagine: [NVIDIA](https://developer.nvidia.com/blog/getting-started-with-nvidia-instant-nerfs/)

[Tiny CUDA Neural Networks](https://github.com/NVlabs/tiny-cuda-nn) è un framework piccolo e autocontenuto per l'addestramento e la query di reti neurali. Contiene in particolare un ["perceptron multistrato completamente fuso"](https://raw.githubusercontent.com/NVlabs/tiny-cuda-nn/master/data/readme/fully-fused-mlp-diagram.png) ([articolo tecnico](https://tom94.net/data/publications/mueller21realtime/mueller21realtime.pdf)), una versatile [codifica hash a multirisoluzione](https://raw.githubusercontent.com/NVlabs/tiny-cuda-nn/master/data/readme/multiresolution-hash-encoding-diagram.png) ([articolo tecnico](https://nvlabs.github.io/instant-ngp/assets/mueller2022instant.pdf)), nonché supporto per vari altri codificatori di input, perdite e ottimizzatori.

 <p align="center">
 <img src="https://github.com/dji-drone/Guida-alla-Fotogrammetria/assets/45159366/c92637b1-5e96-44b1-a715-97b6eecab641">
</br>
</p>

NeRF Istantanei NVIDIA utilizzando tiny-cuda-nn (Tiny CUDA Neural Networks). Credito immagine: [NVIDIA](https://github.com/NVlabs/instant-ngp/blob/master/docs/assets_readme/testbed.png)

<details open>
<summary>Compressione</summary>

- [Campi di Bitrate Variabile Neurali](https://nv-tlabs.github.io/vqad/), Takikawa et al., SIGGRAPH 2022 | [github](https://github.com/nv-tlabs/vqad)
</details>

<details open>


## Contribuisci

- [x] Se desideri contribuire a questa guida, fai semplicemente una [Pull Request](https://github.com/dji-drone/Guida-alla-Fotogrammetria/pulls).

## Licenza
[Torna all'inizio](https://github.com/dji-drone/Guida-alla-Fotogrammetria#table-of-contents)

Distribuito sotto la [Licenza Pubblica Internazionale Creative Commons Attribuzione 4.0 (CC BY 4.0)](https://creativecommons.org/licenses/by/4.0/).
