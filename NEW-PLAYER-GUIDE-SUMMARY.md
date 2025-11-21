<!DOCTYPE html>
<html lang="it">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Gunsmoke & Dread - Quickstart per Daggerheart</title>
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Rye&family=Crimson+Text:ital,wght@0,400;0,600;0,700;1,400&family=Special+Elite&display=swap');
        
        :root {
            --desert-sand: #d4a574;
            --blood-red: #8b0000;
            --night-black: #1a1a1a;
            --parchment: #f4e8d0;
            --rust: #a0522d;
            --shadow-grey: #3a3a3a;
        }
        
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        
        body {
            font-family: 'Crimson Text', serif;
            background: linear-gradient(135deg, var(--night-black) 0%, var(--shadow-grey) 100%);
            color: var(--parchment);
            line-height: 1.7;
            font-size: 16px;
        }
        
        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 20px;
            display: grid;
            grid-template-columns: 280px 1fr;
            gap: 30px;
        }
        
        /* Navigazione laterale */
        .sidebar {
            position: sticky;
            top: 20px;
            height: fit-content;
            background: rgba(26, 26, 26, 0.95);
            border: 3px solid var(--rust);
            border-radius: 5px;
            padding: 20px;
            box-shadow: 0 8px 16px rgba(0, 0, 0, 0.6);
        }
        
        .sidebar h2 {
            font-family: 'Rye', cursive;
            color: var(--desert-sand);
            font-size: 1.4em;
            margin-bottom: 15px;
            text-align: center;
            text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.8);
        }
        
        .nav-links {
            list-style: none;
        }
        
        .nav-links li {
            margin: 8px 0;
        }
        
        .nav-links a {
            color: var(--desert-sand);
            text-decoration: none;
            display: block;
            padding: 8px 12px;
            border-left: 3px solid transparent;
            transition: all 0.3s;
            font-size: 0.95em;
        }
        
        .nav-links a:hover {
            background: rgba(212, 165, 116, 0.1);
            border-left-color: var(--blood-red);
            padding-left: 18px;
        }
        
        .nav-links .sub-link {
            font-size: 0.85em;
            padding-left: 24px;
            color: #c4a574;
        }
        
        /* Contenuto principale */
        .content {
            background: var(--parchment);
            color: var(--night-black);
            padding: 50px 60px;
            border-radius: 5px;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.8);
            border: 2px solid var(--rust);
        }
        
        /* Copertina */
        .cover {
            text-align: center;
            padding: 80px 20px;
            background: linear-gradient(135deg, var(--blood-red) 0%, var(--night-black) 100%);
            color: var(--parchment);
            border-radius: 5px;
            margin-bottom: 40px;
            border: 4px double var(--desert-sand);
            box-shadow: inset 0 0 50px rgba(0, 0, 0, 0.5);
        }
        
        .cover h1 {
            font-family: 'Rye', cursive;
            font-size: 4em;
            margin-bottom: 20px;
            text-shadow: 4px 4px 8px rgba(0, 0, 0, 0.9);
            letter-spacing: 3px;
        }
        
        .cover .subtitle {
            font-family: 'Special Elite', cursive;
            font-size: 1.5em;
            margin-bottom: 30px;
            color: var(--desert-sand);
            text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.8);
        }
        
        .cover .tagline {
            font-style: italic;
            font-size: 1.2em;
            max-width: 600px;
            margin: 0 auto;
            line-height: 1.6;
        }
        
        .cover .location {
            margin-top: 40px;
            font-family: 'Special Elite', cursive;
            font-size: 1.1em;
            letter-spacing: 2px;
        }
        
        /* Titoli */
        h1, h2, h3, h4 {
            font-family: 'Rye', cursive;
            color: var(--blood-red);
            margin-top: 40px;
            margin-bottom: 20px;
        }
        
        h1 {
            font-size: 2.8em;
            border-bottom: 3px solid var(--rust);
            padding-bottom: 15px;
            text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.2);
        }
        
        h2 {
            font-size: 2.2em;
            border-bottom: 2px solid var(--desert-sand);
            padding-bottom: 10px;
        }
        
        h3 {
            font-size: 1.7em;
            color: var(--rust);
        }
        
        h4 {
            font-size: 1.3em;
            color: var(--shadow-grey);
        }
        
        /* Paragrafi */
        p {
            margin: 15px 0;
            text-align: justify;
        }
        
        /* Liste */
        ul, ol {
            margin: 15px 0 15px 40px;
        }
        
        li {
            margin: 8px 0;
        }
        
        /* Box speciali */
        .info-box {
            background: rgba(212, 165, 116, 0.15);
            border-left: 5px solid var(--rust);
            padding: 20px;
            margin: 25px 0;
            border-radius: 3px;
        }
        
        .warning-box {
            background: rgba(139, 0, 0, 0.1);
            border-left: 5px solid var(--blood-red);
            padding: 20px;
            margin: 25px 0;
            border-radius: 3px;
        }
        
        .stat-block {
            background: rgba(58, 58, 58, 0.05);
            border: 2px solid var(--shadow-grey);
            padding: 20px;
            margin: 25px 0;
            border-radius: 5px;
            font-family: 'Special Elite', cursive;
            font-size: 0.95em;
        }
        
        .stat-block h4 {
            margin-top: 0;
            font-family: 'Rye', cursive;
        }
        
        /* Icone priorità */
        .priority-icon {
            display: inline-block;
            width: 24px;
            height: 24px;
            line-height: 24px;
            text-align: center;
            border-radius: 50%;
            margin-right: 8px;
            font-weight: bold;
        }
        
        .essential {
            background: var(--blood-red);
            color: white;
        }
        
        .important {
            background: var(--rust);
            color: white;
        }
        
        .optional {
            background: var(--desert-sand);
            color: var(--night-black);
        }
        
        /* Sezioni collassabili */
        .collapsible {
            cursor: pointer;
            padding: 15px;
            background: rgba(139, 0, 0, 0.1);
            border: 2px solid var(--rust);
            border-radius: 5px;
            margin: 20px 0;
            font-weight: 600;
            transition: background 0.3s;
        }
        
        .collapsible:hover {
            background: rgba(139, 0, 0, 0.2);
        }
        
        .collapsible::before {
            content: "▶ ";
            display: inline-block;
            margin-right: 10px;
            transition: transform 0.3s;
        }
        
        .collapsible.active::before {
            transform: rotate(90deg);
        }
        
        .collapsible-content {
            max-height: 0;
            overflow: hidden;
            transition: max-height 0.3s ease-out;
            padding: 0 20px;
        }
        
        .collapsible-content.active {
            max-height: 5000px;
            padding: 20px;
        }
        
        /* Tabelle */
        table {
            width: 100%;
            border-collapse: collapse;
            margin: 25px 0;
            background: white;
        }
        
        th, td {
            border: 1px solid var(--shadow-grey);
            padding: 12px;
            text-align: left;
        }
        
        th {
            background: var(--rust);
            color: var(--parchment);
            font-weight: 600;
        }
        
        tr:nth-child(even) {
            background: rgba(212, 165, 116, 0.1);
        }
        
        /* Separatori */
        hr {
            border: none;
            border-top: 2px solid var(--desert-sand);
            margin: 40px 0;
        }
        
        /* Stampa */
        @media print {
            body {
                background: white;
                color: black;
            }
            .sidebar {
                display: none;
            }
            .container {
                grid-template-columns: 1fr;
            }
            .content {
                box-shadow: none;
                border: none;
            }
        }
        
        /* Responsive */
        @media (max-width: 968px) {
            .container {
                grid-template-columns: 1fr;
            }
            .sidebar {
                position: relative;
                top: 0;
            }
        }
    </style>
</head>
<body>
    <div class="container">
        <!-- Navigazione laterale -->
        <nav class="sidebar">
            <h2>📖 Indice</h2>
            <ul class="nav-links">
                <li><a href="#intro">Introduzione</a></li>
                <li><a href="#come-leggere">Come Leggere</a></li>
                <li><a href="#ambientazione">Ambientazione</a></li>
                <li><a href="#personaggi">Personaggi</a>
                    <ul>
                        <li><a href="#jack" class="sub-link">Jack Malone</a></li>
                        <li><a href="#sarah" class="sub-link">Sarah Blackwood</a></li>
                        <li><a href="#doc" class="sub-link">Doc Artemis</a></li>
                    </ul>
                </li>
                <li><a href="#regole">Regole Weird West</a></li>
                <li><a href="#avventura">Avventura</a>
                    <ul>
                        <li><a href="#atto1" class="sub-link">Atto I</a></li>
                        <li><a href="#atto2" class="sub-link">Atto II</a></li>
                        <li><a href="#atto3" class="sub-link">Atto III</a></li>
                    </ul>
                </li>
                <li><a href="#bestiario">Bestiario</a></li>
                <li><a href="#strumenti">Strumenti GM</a></li>
            </ul>
        </nav>

        <!-- Contenuto principale -->
        <main class="content">
            <!-- COPERTINA -->
            <div class="cover">
                <h1>GUNSMOKE & DREAD</h1>
                <div class="subtitle">UN QUICKSTART PER DAGGERHEART NEL WEIRD WEST</div>
                <div class="tagline">
                    Dove i pistoleri affrontano orrori cosmici<br>
                    e l'alba potrebbe non arrivare mai
                </div>
                <div class="location">NUOVO MESSICO, AGOSTO 1885</div>
                <p style="margin-top: 40px; font-size: 1.1em;">
                    Il sole tramonta sul deserto. Un treno fischia attraverso le distese vuote.<br>
                    Fra poco, i morti cammineranno.<br>
                    <strong>E voi dovrete fermarli.</strong>
                </p>
            </div>

            <!-- INTRODUZIONE -->
            <section id="intro">
                <h1>Benvenuti nel Weird West</h1>
                
                <p>L'anno è il 1885. Il West americano sta morendo lentamente sotto il peso della civilizzazione che avanza inesorabile da est. Le ferrovie attraversano il deserto come cicatrici d'acciaio. Le città nascono e muoiono nel giro di stagioni. Gli uomini cercano fortuna nell'oro e nell'argento, scavando sempre più in profondità nella terra.</p>

                <p>E a volte, scavando, trovano cose che avrebbero dovuto rimanere sepolte.</p>

                <p>Questo è il <strong>Weird West</strong> - un'America di frontiera dove il folklore si mescola con l'orrore cosmico, dove i pistoleri affrontano non solo banditi e nativi ostili, ma anche morti che camminano e sussurri da dimensioni oltre la comprensione umana. È un mondo dove il coraggio e la competenza di un uomo con la pistola si scontrano con l'insignificanza dell'esistenza umana davanti all'eternità degli Antichi.</p>

                <p><strong>Gunsmoke & Dread</strong> è un quickstart completo per giocare un'avventura di Weird West utilizzando il sistema Daggerheart. Include tre personaggi pregenerati, regole speciali per l'ambientazione, un'avventura completa giocabile in una sessione (3-4 ore), e tutto ciò che serve per esplorare questo incrocio affascinante tra western e horror lovecraftiano.</p>
            </section>

            <hr>

            <!-- COME LEGGERE -->
            <section id="come-leggere">
                <h1>Come Leggere Questo Quickstart</h1>

                <h2>Cosa Contiene Questo Documento</h2>

                <div class="info-box">
                    <p><strong>AMBIENTAZIONE</strong> - Il Weird West spiegato in due pagine: tono, temi, atmosfera.</p>
                    
                    <p><strong>PERSONAGGI</strong> - Tre eroi pronti da giocare: un pistolero tormentato, una predicatrice redenta, un medico inventore. Ognuno con statistiche complete, background, e Connessioni.</p>
                    
                    <p><strong>REGOLE SPECIALI</strong> - Quattro sistemi che catturano il Weird West: Tenuta Mentale per l'horror psicologico, regole per combattere orrori cosmici, armi da fuoco dell'epoca, duelli e sopravvivenza. Marcate con icone di priorità.</p>
                    
                    <p><strong>AVVENTURA</strong> - "Sangue sui Binari", completa in tre atti: una rapina al treno che diventa incubo quando i morti si alzano, una notte disperata di sopravvivenza, e una discesa finale in una miniera maledetta per confrontare l'origine dell'oscurità.</p>
                    
                    <p><strong>BESTIARIO</strong> - Sei creature dall'umano al cosmico, con statistiche snelle in stile Daggerheart.</p>
                    
                    <p><strong>STRUMENTI</strong> - Tabelle, consigli, note di design per il Game Master.</p>
                    
                    <p><strong>📄 MATERIALI STAMPABILI</strong> - Quick Reference Sheet (1 pagina A4 con tutte le regole essenziali) e Character Sheets completi per i tre personaggi (3 pagine A4). Disponibili come file HTML separati nella stessa cartella di questo quickstart.</p>
                </div>

                <div class="warning-box">
                    <h3>🖨️ MATERIALI STAMPABILI INCLUSI</h3>
                    <p>Questo quickstart include due file aggiuntivi pensati per essere stampati:</p>
                    <ul>
                        <li><strong>gunsmoke-dread-quick-reference.html</strong> - Scheda di riferimento rapido (1 pagina A4) con tutte le regole core, difficoltà, distanze, combattimento, e regole Weird West. Stampa e tieni dietro lo schermo del GM!</li>
                        <li><strong>gunsmoke-dread-character-sheets.html</strong> - Schede personaggio complete per Jack, Sarah e Doc (3 pagine A4). Include stats, abilità, background, connessioni, equipaggiamento e spazi per note.</li>
                    </ul>
                    <p><strong>Consiglio:</strong> Stampa entrambi i file prima della sessione per avere tutto sottomano e rendere il gioco molto più fluido.</p>
                </div>

                <h2>Se Sei il Game Master</h2>

                <div class="collapsible">CON 2 ORE DI PREPARAZIONE (lettura completa)</div>
                <div class="collapsible-content">
                    <p>Leggi nell'ordine: Ambientazione (10 min) → Regole marcate 🔥 (15 min) → Bestiario (10 min) → Avventura completa (60 min) → Personaggi (15 min) → Strumenti (10 min). Stampa la Scheda di Riferimento.</p>
                </div>

                <div class="collapsible">CON 1 ORA (essenziale)</div>
                <div class="collapsible-content">
                    <p>Leggi solo: Ambientazione (5 min) → Tenuta Mentale e Combattere Orrori (10 min) → Atto Primo (15 min) → Scorri Bestiario (5 min) → Memorizza Scheda Riferimento (10 min). Consulta il resto durante il gioco leggendo ogni atto prima che inizi.</p>
                    <p><strong>💡 IMPORTANTE:</strong> Stampa e leggi attentamente la <strong>Quick Reference Sheet</strong> (gunsmoke-dread-quick-reference.html). Contiene tutte le regole essenziali in formato compatto e sarà il tuo migliore amico durante la sessione.</p>
                </div>

                <div class="collapsible">CON 30 MINUTI (emergenza)</div>
                <div class="collapsible-content">
                    <p>Ambientazione + Tenuta Mentale + inizio Atto Primo + Scheda Riferimento. Stampa Bestiario e Scheda. Improvvisa molto, consulta costantemente.</p>
                </div>

                <h2>Se Sei un Giocatore</h2>

                <div class="warning-box" style="background: rgba(212, 165, 116, 0.15); border-color: var(--desert-sand);">
                    <h3>📋 USA LE CHARACTER SHEETS STAMPABILI!</h3>
                    <p>Invece di leggere tutte le statistiche qui sotto, chiedi al tuo GM di stamparti la scheda personaggio dal file <strong>gunsmoke-dread-character-sheets.html</strong>. Ogni personaggio ha una pagina A4 completa con:</p>
                    <ul style="margin-left: 20px; margin-top: 10px;">
                        <li>✅ Tratti e statistiche già calcolate e pronte all'uso</li>
                        <li>✅ Spazi per segnare HP, Stress, Tenuta Mentale, Speranza</li>
                        <li>✅ Armi e abilità dettagliate con formule dadi</li>
                        <li>✅ Background completo e connessioni con altri PG</li>
                        <li>✅ Area note per prendere appunti durante la sessione</li>
                    </ul>
                    <p style="margin-top: 15px;"><strong>Molto più comodo che consultare l'HTML durante il gioco!</strong></p>
                </div>

                <div class="info-box">
                    <p><strong>PRIMA DELLA SESSIONE</strong> (35 minuti, opzionale ma utile):</p>
                    <p>Ambientazione (10 min) → La scheda del TUO personaggio, non tutte e tre (15 min) → Scorri Regole Speciali per capire cosa aspettarti (10 min).</p>
                    
                    <p><strong>SENZA TEMPO</strong>: Arriva 15 minuti prima, scegli personaggio, leggi solo il background (prima pagina della scheda). Il resto si impara giocando.</p>
                </div>

                <h3>Prerequisiti</h3>

                <p>Questo quickstart assume che tu conosca le <strong>regole base di Daggerheart</strong>: tiri con 1d12 Speranza + 1d12 Paura, il sistema di risorse Speranza/Paura, Connessioni tra personaggi, combattimento base (attacchi, Evasione, PF, Armatura), azioni (Azione, Azione Minore, Reazione).</p>

                <p>Se non conosci Daggerheart, il sistema si impara giocando - chiedi al GM una spiegazione di 5 minuti delle meccaniche fondamentali all'inizio della sessione.</p>

                <h3>Materiali Necessari</h3>

                <div class="stat-block">
                    <p><strong>Per il gruppo:</strong> Questo documento, 2d12 per giocatore, dadi poliedrici standard, segnalini per Speranza/Paura, carta e matite.</p>
                    
                    <p><strong>Per il GM:</strong> Scheda di Riferimento stampata, schermo, Bestiario stampato.</p>
                    
                    <p><strong>Per ogni giocatore:</strong> Scheda del proprio personaggio, matita per tracciare risorse.</p>
                </div>
            </section>

            <hr>

            <!-- AMBIENTAZIONE -->
            <section id="ambientazione">
                <h1>Il Weird West</h1>

                <h2>Dove la Frontiera Incontra l'Impossibile</h2>

                <p>Il West americano del 1885 è una terra di contrasti violenti. È l'epoca delle ultime grandi mandrie di bestiame che attraversano il Texas, dei cercatori d'oro che setacciano i fiumi della California, delle ferrovie transcontinentali che uniscono oceano a oceano. È l'epoca degli sceriffi e dei fuorilegge, dei duelli a mezzogiorno nelle strade polverose, delle saloon piene di fumo dove si gioca la vita su una mano di poker.</p>

                <p>Ma è anche qualcos'altro.</p>

                <p>Sotto la superficie della storia che conosciamo, qualcosa di più oscuro pulsa. I nativi americani, spinti sempre più lontano dalle loro terre ancestrali, sussurrano di spiriti antichi che si risvegliano disturbati. I minatori che scavano troppo in profondità a volte non tornano, o tornano cambiati, con gli occhi che hanno visto cose che la mente umana non dovrebbe contemplare. Le notti di luna nuova, quando l'oscurità è completa, si sentono ululati che non appartengono a nessun coyote o lupo.</p>

                <p>Il <strong>Weird West</strong> è questa America di frontiera contaminata dall'orrore cosmico. È Sergio Leone che incontra H.P. Lovecraft. È il duello a mezzogiorno che diventa lotta disperata contro morti che camminano. È il coraggio dell'uomo che impugna due revolver che affronta l'insignificanza dell'esistenza umana davanti all'eternità aliena.</p>

                <h2>Il Tono: Competenza e Vulnerabilità</h2>

                <p>I personaggi in questa ambientazione non sono vittime impotenti come nell'horror tradizionale. Sono <strong>competenti</strong> - pistoleri addestrati, predicatori con fede genuina, medici con nervi d'acciaio forgiati sui campi di battaglia. Sanno combattere, sanno sopravvivere, sanno che la violenza a volte è l'unica risposta.</p>

                <p>Ma sono anche <strong>vulnerabili</strong>. Non per mancanza di abilità, ma perché stanno affrontando cose che violano le leggi fondamentali della realtà che hanno sempre dato per scontate. Un morto che si alza sfida tutto ciò che sanno essere vero. Un'entità cosmica che esiste in dimensioni oltre la percezione umana mette in discussione il significato stesso della loro esistenza.</p>

                <p>Questa dualità crea il dramma. Non è solo "riusciranno a sopravvivere?" ma anche "riusciranno a rimanere sani di mente? Riusciranno a mantenere la loro umanità?"</p>

                <h2>I Temi Centrali</h2>

                <div class="info-box">
                    <h4>LA MORTE CHE NON È FINALE</h4>
                    <p>Il West è violento, la morte è comune. Ma cosa succede quando la morte perde il suo significato? Quando i cadaveri si alzano e camminano? Il confine tra vivo e morto si sfoca, e con esso le certezze morali su cui i personaggi hanno costruito le loro vite.</p>
                </div>

                <div class="info-box">
                    <h4>IL COSTO DELLA CONOSCENZA</h4>
                    <p>Sapere troppo è pericoloso. La mente umana non è progettata per comprendere verità cosmiche. Ogni passo verso la comprensione dell'impossibile è un passo verso la follia. Ma l'ignoranza è altrettanto mortale - come combatti qualcosa che non capisci?</p>
                </div>

                <div class="info-box">
                    <h4>LA FEDE CONTRO IL VUOTO</h4>
                    <p>In un universo dove esistono forze così vaste e indifferenti che l'umanità intera è meno significativa di un granello di sabbia, ha ancora senso credere in un Dio che si cura di noi? Sarah Blackwood incarna questa domanda - la sua fede è genuina e potente, ma è costantemente testata dall'orrore che affronta.</p>
                </div>

                <div class="info-box">
                    <h4>IL PREZZO DEL PROGRESSO</h4>
                    <p>L'America sta conquistando il West, costruendo ferrovie, scavando miniere, erigendo città. Ma questa conquista disturba cose che dormivano. Forse c'erano ragioni per cui certe terre erano considerate sacre o maledette. Forse alcuni confini non dovrebbero essere attraversati.</p>
                </div>

                <h2>L'Estetica: Polvere e Sangue e Geometrie Impossibili</h2>

                <p>Visivamente, il Weird West giustappone il familiare con l'alieno. Un duello in una strada polverosa all'alba - ma uno dei duellanti ha occhi completamente bianchi e non respira. Un treno a vapore che attraversa il deserto sotto un tramonto rosso sangue - ma sul tetto ci sono simboli che feriscono gli occhi quando li guardi. Una miniera abbandonata con carrelli arrugginiti e lanterne rotte - ma più scendi, più le pareti iniziano a mostrare angoli che sembrano simultaneamente acuti e ottusi.</p>

                <p>Il contrasto è deliberato. Il normale rende l'anormale più terrificante. Il banale evidenzia il cosmico.</p>

                <h2>Cosa Questo Quickstart Ti Offre</h2>

                <p><strong>"Sangue sui Binari"</strong> cattura tutti questi elementi. Inizia come western classico - una rapina al treno, sparatorie, banditismo. Poi, quando il sole tramonta e i morti iniziano a camminare, diventa horror survival. Infine, nella discesa nella miniera maledetta, diventa confronto con l'orrore cosmico vero e proprio.</p>

                <p>Giocherai eroi competenti che affrontano l'impossibile. Userai le pistole e la fede e l'ingegno per combattere cose che non dovrebbero esistere. E alla fine, se sopravvivi, porterai cicatrici - sia fisiche che mentali - che ricorderai per sempre.</p>

                <div class="warning-box">
                    <p style="text-align: center; font-weight: 600; font-size: 1.2em;">
                        Il West è weird. La notte è oscura. L'avventura ti aspetta.
                    </p>
                </div>
            </section>

            <hr>

            <!-- PERSONAGGI -->
            <section id="personaggi">
                <h1>Personaggi Pregenerati</h1>
                
                <p style="font-style: italic; text-align: center; margin: 30px 0;">
                    Tre eroi del Weird West, ognuno con le proprie abilità, il proprio passato tormentato,<br>
                    e la propria ragione per affrontare l'oscurità invece di fuggirne.
                </p>

                <!-- JACK MALONE -->
                <article id="jack">
                    <h2>Jack Malone - Il Pistolero Tormentato</h2>

                    <h3>Chi È Jack Malone</h3>

                    <p>Ci sono uomini che portano la morte con loro ovunque vadano, non per scelta ma per destino. Jack Malone è uno di questi uomini.</p>

                    <p>Ha trentaquattro anni ma ne dimostra dieci di più. Il sole del deserto ha inciso rughe profonde intorno agli occhi, sempre socchiusi come se stesse eternamente mirando lungo la canna di un revolver. I capelli, un tempo neri come carbone, stanno iniziando a ingrigire alle tempie. Le mani sono quelle di un artigiano - dita lunghe, callose, con una stabilità innaturale che arriva solo dopo anni di pratica quotidiana con le armi.</p>

                    <p>Indossa sempre lo stesso abbigliamento: camicia bianca di cotone sotto un gilet di pelle scura, pantaloni neri consumati, stivali che hanno camminato migliaia di miglia attraverso ogni tipo di terreno. Il cappello a tesa larga getta ombra sul volto, nascondendo gli occhi a chi non lo conosce. E due revolver pesanti, sempre carichi, sempre pronti, pendono dalle fondine legate basse sulle cosce.</p>

                    <p>Jack non parla molto. Non perché sia timido o antisociale, ma perché ha imparato che le parole raramente risolvono i problemi che lui è chiamato a affrontare. Quando parla, la sua voce è bassa e rauca, come ghiaia trascinata su legno ruvido. Sceglie le parole con la stessa cura con cui sceglie i bersagli - ogni frase ha uno scopo, nessuna è sprecata.</p>

                    <div class="collapsible">Il Passato che Non Muore</div>
                    <div class="collapsible-content">
                        <p>Cinque anni fa, Jack Malone era un uomo diverso. Lavorava come guardia di sicurezza per la Consolidated Mining Company nel Nevada settentrionale. Il lavoro era semplice: proteggere i minatori mentre lavoravano, tenere lontani i banditi che cercavano di rubare l'argento, assicurarsi che le buste paga arrivassero intatte ogni mese.</p>

                        <p>Aveva anche un amico - l'unico vero amico che avesse mai avuto. Danny O'Brien, un irlandese dalla lingua sciolta e dal cuore grande, che lavorava nella stessa miniera come caposquadra. I due avevano combattuto insieme durante la Guerra Civile (entrambi nell'Unione, entrambi sopravvissuti a battaglie che avrebbero dovuto ucciderli), e quella fratellanza forgiata nel fuoco era continuata anche nella pace.</p>

                        <p>Poi venne quella notte di marzo.</p>

                        <p>Una squadra di minatori stava lavorando nel livello più profondo della miniera, seguendo una vena particolarmente ricca di minerale. Alle due di notte, le lanterne si spensero tutte simultaneamente - tutte e venticinque, in un istante. Nel buio completo che seguì, iniziarono le urla.</p>

                        <p>Jack e Danny corsero giù con le torce, scendendo attraverso i tunnel che sembravano stringersi intorno a loro come gole di pietra. Quando arrivarono al livello inferiore, trovarono... qualcosa. Ancora oggi Jack non riesce a descriverlo coerentemente. La sua mente rifiuta di ricordare la forma esatta, sostituendo i dettagli con nebbia e terrore. Ricorda tentacoli, o forse zampe, o forse solo ombre che si muovevano in modi che l'ombra non dovrebbe poter muoversi. Ricorda occhi, troppi occhi, che brillavano nell'oscurità come stelle malate.</p>

                        <p>I minatori erano morti. Tutti e sette. Non semplicemente uccisi - consumati in modi che la biologia non dovrebbe permettere.</p>

                        <p>Danny urlò qualcosa - forse una preghiera, forse una maledizione - e corse verso la cosa con il suo piccone alzato. Jack lo seguì, sparando i suoi revolver contro quella massa impossibile. Ricorda che i proiettili sembravano passare attraverso invece di colpire, come se stessero sparando contro nebbia condensata.</p>

                        <p>Poi Danny cadde. La cosa lo toccò - Jack ancora non sa se fu un tentacolo o un artiglio o semplicemente il contatto con qualcosa che non dovrebbe esistere in questa realtà - e Danny semplicemente... si spense. Come una candela soffiata via. Un momento era vivo, urlante, combattente. Il momento dopo era un guscio vuoto che crollava a terra.</p>

                        <p>Jack non ricorda come fuggì. Non ricorda come arrivò in superficie. La sua prossima memoria chiara è di essere seduto all'alba fuori dall'ingresso della miniera, coperto di polvere e sangue (non suo), mentre altri uomini lo guardavano con una mistura di pietà e terrore.</p>

                        <p>La compagnia mineraria sigillò quel livello della miniera. La storia ufficiale fu un crollo - tragico ma comprensibile. I corpi non furono mai recuperati. Danny O'Brien venne registrato come morto in un incidente minerario, e sua moglie ricevette una piccola pensione.</p>

                        <p>Jack Malone lasciò il Nevada quella stessa settimana e non è mai tornato.</p>
                    </div>

                    <h3>L'Uomo che È Adesso</h3>

                    <p>Da quella notte, Jack ha vagato attraverso il West accettando lavori che nessun altro vuole. Scorta di carichi pericolosi attraverso territorio ostile. Caccia di fuorilegge con taglie così alte che suggeriscono che nessuno si aspetta che il cacciatore torni vivo. Protezione di cittadine remote che hanno problemi che lo sceriffo locale non può o non vuole affrontare.</p>

                    <p>Non lo fa per soldi, anche se la paga è buona. Lo fa perché non riesce a fermarsi. Ogni lavoro pericoloso è una penitenza per essere sopravvissuto quando Danny è morto. Ogni bandito abbattuto è una piccola vendetta contro un universo che ha preso il suo unico amico e lo ha consumato nell'oscurità.</p>

                    <p>E in fondo, così in profondità che raramente ammette anche a se stesso, Jack sta cercando quella cosa. Quella massa impossibile che uccise Danny. Perché forse, se la trova e la uccide, potrà finalmente dormire senza sognare tentacoli e occhi che brillano nell'oscurità.</p>

                    <p>È un uomo tormentato che cerca redenzione attraverso la violenza - che è l'unica lingua che parla fluentemente.</p>

                    <h3>Statistiche e Abilità</h3>

                    <div class="stat-block">
                        <h4>STATISTICHE BASE</h4>
                        <p><strong>CLASSE:</strong> Guerriero (Gunslinger variant) | <strong>LIVELLO:</strong> 2</p>
                        <p><strong>PUNTI FERITA:</strong> 28 | <strong>ARMATURA:</strong> 2 | <strong>EVASIONE:</strong> 14 | <strong>SOGLIA:</strong> 3</p>
                        <p><strong>CARATTERISTICHE:</strong> Forza +2 | Agilità +3 | Finezza +1 | Istinto +3 | Presenza +0 | Conoscenza +1</p>
                        <p><strong>ESPERIENZE:</strong> 🔫 Armi da Fuoco (Maestro) | ⚔️ Combattimento Ravvicinato | 👁️ Sensi Acuti del Soldato | 🏜️ Sopravvivenza nel Deserto</p>
                    </div>

                    <div class="collapsible">MANI PIÙ VELOCI DELLA MORTE (2 utilizzi/riposo)</div>
                    <div class="collapsible-content">
                        <p>I tuoi riflessi sono stati affinati da anni di duelli dove un istante di esitazione significa morte. Quando inizi il combattimento, puoi dichiarare questa abilità per agire per primo automaticamente, prima di qualsiasi nemico. Inoltre, il tuo primo attacco in quel round infligge +2d8 danni extra mentre cogli i nemici completamente impreparati.</p>
                        <p>Durante un duello formale, questa abilità ti garantisce automaticamente l'iniziativa senza bisogno di tirare.</p>
                    </div>

                    <div class="collapsible">DUE PISTOLE, DUE BERSAGLI (Sempre attiva)</div>
                    <div class="collapsible-content">
                        <p>Hai addestrato il tuo corpo a sparare con entrambe le mani simultaneamente con precisione mortale. Quando usi la tua azione per attaccare con i revolver, puoi effettuare due attacchi separati contro bersagli diversi entro distanza Ravvicinata invece di un singolo attacco. Ogni attacco usa il tuo normale bonus per colpire.</p>
                        <p>Se entrambi gli attacchi colpiscono lo stesso bersaglio, il secondo attacco infligge +1d8 danni extra.</p>
                    </div>

                    <div class="collapsible">FREDDEZZA SOTTO PRESSIONE (Passiva)</div>
                    <div class="collapsible-content">
                        <p>Hai visto troppo per lasciarti facilmente spaventare. Hai vantaggio su tutti i tiri contro Paura, Intimidazione, o effetti mentali che cercano di farti esitare o fuggire. Quando riempi segmenti del tuo Orologio della Tenuta Mentale, riempi sempre 1 segmento in meno del normale (minimo 1).</p>
                        <p>Questo non ti rende immune alla follia - semplicemente resisti più a lungo prima che la tua mente si spezzi.</p>
                    </div>

                    <div class="collapsible">COLPO MORTALE (1 utilizzo/riposo)</div>
                    <div class="collapsible-content">
                        <p>Quando dichiari questa abilità prima di un attacco, quel singolo colpo è caricato con tutta la tua esperienza letale. Se l'attacco colpisce, infliggi danno massimo automaticamente invece di tirare i dadi (per esempio, un revolver che normalmente fa 2d8+3 infligge automaticamente 19 danni).</p>
                        <p>Se questo attacco riduce un nemico esattamente a 0 Punti Ferita, guadagni immediatamente un'azione minore bonus che puoi usare per ricaricare, muoverti, o fare un secondo attacco contro un bersaglio diverso.</p>
                    </div>

                    <div class="collapsible">ISTINTO DI SOPRAVVIVENZA (Passiva)</div>
                    <div class="collapsible-content">
                        <p>Anni di pericolo costante hanno affilato i tuoi sensi a un livello soprannaturale. Non puoi essere sorpreso da imboscate (tiri sempre Istinto per notare anche imboscate ben pianificate). Quando un alleato entro distanza Ravvicinata sta per subire un colpo che lo ridurrebbe a 0 PF, puoi usare la tua reazione per spostarti e prendere tu il colpo al suo posto, subendo tutto il danno destinato all'alleato.</p>
                        <p><em>Danny è morto perché non sei stato abbastanza veloce. Non permetterai che accada di nuovo.</em></p>
                    </div>

                    <h3>Connessioni</h3>

                    <div class="info-box">
                        <h4>CON SARAH BLACKWOOD</h4>
                        <p><em>"La reverenda ha una fede che invidio - crede ancora che ci sia significato in tutto questo. Io ho smesso di credere la notte in cui Danny è morto. Ma quando la vedo pregare con quella convinzione assoluta, per un momento quasi riesco a sperare che abbia ragione."</em></p>
                        <p><strong>Meccanica:</strong> Quando Sarah usa un'abilità divina per aiutare Jack, lui recupera 1 segmento del suo Orologio della Tenuta Mentale oltre all'effetto normale dell'abilità - la sua fede lo ancora alla sanità.</p>
                    </div>

                    <div class="info-box">
                        <h4>CON DOC ARTEMIS</h4>
                        <p><em>"Il dottore ha visto le stesse cose che ho visto io. Lo riconosco nei suoi occhi - quella consapevolezza che il mondo è più strano e più terribile di quanto la gente normale possa immaginare. Non ne parliamo mai direttamente, ma c'è una comprensione silenziosa tra noi. Siamo sopravvissuti quando non avremmo dovuto."</em></p>
                        <p><strong>Meccanica:</strong> Quando Jack e Doc combattono fianco a fianco (entro distanza Ravvicinata), entrambi guadagnano +1 a tutti i tiri di attacco grazie alla coordinazione tattica forgiata da esperienze condivise di orrore.</p>
                    </div>

                    <h3>Equipaggiamento</h3>

                    <div class="stat-block">
                        <p><strong>ARMI:</strong></p>
                        <ul>
                            <li>Due Revolver Pesanti (.44 Magnum) - 2d8 danni ciascuno, Ricarica 6, Penetrante 2, Rumorosi</li>
                            <li>Coltello da Combattimento - 1d6+2 danni, distanza Molto Ravvicinata</li>
                            <li>72 proiettili standard (12 round completi di ricarica)</li>
                        </ul>
                        
                        <p><strong>ARMATURA:</strong> Gilet di pelle rinforzato (Armatura 2)</p>
                        
                        <p><strong>EQUIPAGGIAMENTO:</strong> Kit manutenzione armi, borraccia, corda 50 piedi, fiammiferi, tabacco e cartine, 35 dollari</p>
                        
                        <p><strong>OGGETTO PERSONALE:</strong> Una fotografia sbiadita di Danny O'Brien, piegata e ripiegata così tante volte che i bordi stanno iniziando a lacerarsi. Jack non la guarda mai, ma la porta sempre nel taschino della camicia vicino al cuore.</p>
                    </div>

                    <div class="collapsible">Come Giocare Jack</div>
                    <div class="collapsible-content">
                        <p><strong>IN COMBATTIMENTO:</strong> Jack è un cannone di vetro - infligge danni devastanti rapidamente ma non può sostenere combattimenti prolungati. Usa Mani Più Veloci per eliminare i nemici più pericolosi nel primo round. Due Pistole Due Bersagli ti permette di gestire nemici multipli. Conserva Colpo Mortale per minacce maggiori. Posizionati dove puoi colpire ma sei difficile da raggiungere.</p>
                        
                        <p><strong>NELLE SCENE SOCIALI:</strong> Jack è l'archetipo del "uomo silenzioso". Parla poco, osserva molto. Quando parla, è diretto e senza fronzoli. Lascia che Sarah o Doc gestiscano la diplomazia. Ma quando qualcuno minaccia innocenti, Jack non esita a farsi avanti con minacce calme e terrificanti.</p>
                        
                        <p><strong>CON GLI ALTRI PERSONAGGI:</strong> Con Sarah - rispettoso ma distante, la chiama "Reverenda". Con Doc - cameratismo silenzioso da veterani. Condividono sigarette in silenzio.</p>
                        
                        <p><strong>MOMENTI CHIAVE:</strong> Quando vedi i morti alzarsi = flashback alla miniera. Quando qualcuno muore sotto la tua protezione = ti incolpi. Se Sarah o Doc sono in pericolo mortale = usi Istinto di Sopravvivenza senza esitazione.</p>
                        
                        <p><strong>LA TUA DOMANDA CENTRALE:</strong> Puoi trovare redenzione per essere sopravvissuto quando Danny è morto?</p>
                    </div>
                </article>

                <hr>

                <!-- SARAH BLACKWOOD -->
                <article id="sarah">
                    <h2>Sarah Blackwood - La Predicatrice Redenta</h2>

                    <h3>Chi È Sarah Blackwood</h3>

                    <p>Sarah Blackwood è una donna che ha guardato nell'abisso e ha scelto deliberatamente di non lasciarsi consumare da esso.</p>

                    <p>Ha ventotto anni ma il suo sguardo è quello di qualcuno che ha vissuto molte vite diverse. Alta e snella, con movimenti che alternano grazia fluida e tensione controllata - il corpo di qualcuno addestrato sia alla violenza che alla compassione. I capelli castano scuro sono sempre raccolti in una treccia pratica che cade lungo la schiena. Gli occhi sono grigi-verdi, del colore del mare prima della tempesta, e hanno quella qualità di guardare non solo l'esterno ma anche l'interno delle persone.</p>

                    <p>Indossa un abito nero di taglio pratico, senza fronzoli o decorazioni eccessive. L'unico ornamento è una croce d'argento che pende da una catena al collo - ma non è una croce ordinaria. È stata benedetta con acqua santa, incisa con preghiere in latino, e porta i segni del combattimento (graffi, ammaccature) che raccontano di scontri con forze oscure. Alla cintura porta un revolver che, come la croce, è stato benedetto - le parole del Salmo 23 sono incise sulla canna.</p>

                    <p>Quando Sarah parla, la sua voce ha quella qualità risonante dei predicatori nati - può sussurrare e essere udita chiaramente, può alzare il tono e riempire una chiesa intera senza urlare. Ma c'è anche qualcos'altro nella voce: una corrente sotterranea di acciaio forgiato in fuoco, la voce di qualcuno che ha affrontato tentazioni terribili e ha scelto di resistere.</p>

                    <div class="collapsible">Il Passato Oscuro</div>
                    <div class="collapsible-content">
                        <p>Sarah non è sempre stata una reverenda. Quella è la parte della sua storia che preferisce non raccontare, ma che è scritta nelle cicatrici (fisiche ed emotive) che porta con sé.</p>

                        <p>Nacque in una famiglia povera nel sud post-Guerra Civile, dove la ricostruzione aveva portato più corruzione che speranza. Suo padre beveva, sua madre era morta giovane, e Sarah crebbe selvaggia per le strade di New Orleans - una città dove il vizio e la violenza convivevano con una facciata di gentilezza sudista.</p>

                        <p>A sedici anni, stanca della povertà e della brutalità della vita che conosceva, Sarah fuggì con un uomo più grande che promise ricchezza e avventura. L'uomo si rivelò essere William "Black Bill" Thornton, un fuorilegge, truffatore, e occasionalmente assassino che operava lungo il Mississippi. Bill non era completamente malvagio - a modo suo, era persino affascinante - ma era certamente pericoloso.</p>

                        <p>Per quasi otto anni, Sarah cavalcò con la banda di Bill. Imparò a sparare, a imbrogliare a carte, a mentire con convinzione assoluta. Partecipò a rapine che lasciarono persone ferite o morte. Bevve troppo whisky e ridacchiò mentre città intere le maledivano. Divenne, in breve, esattamente il tipo di persona che avrebbe dovuto temere il giudizio divino.</p>

                        <p>Poi venne Fort Smith, Arkansas, nell'inverno del 1880.</p>

                        <p>La banda stava rapinando una banca. Qualcosa andò terribilmente storto - forse qualcuno li tradì, forse furono semplicemente incauti. Lo sceriffo e i suoi uomini li stavano aspettando. Ne seguì una sparatoria che durò mezz'ora e lasciò sette persone morte - tre banditi, tre deputati, e una ragazzina di undici anni che era nel posto sbagliato al momento sbagliato.</p>

                        <p>Sarah sparò il colpo che uccise la bambina. Fu un incidente - stava mirando a un deputato e la bambina corse nella traiettoria - ma l'intenzione non importa quando un corpo piccolo crolla a terra con un fiore rosso che si espande sul petto.</p>

                        <p>Bill e gli altri sopravvissuti fuggirono. Sarah rimase, inginocchiata accanto al corpo della bambina, incapace di muoversi mentre realizzava cosa aveva fatto. Gli occhi della bambina - ancora aperti, ancora sorpresi - la fissavano con un'accusa silenziosa.</p>

                        <p>Fu arrestata e condannata a impiccagione.</p>
                    </div>

                    <div class="collapsible">La Redenzione Trovata</div>
                    <div class="collapsible-content">
                        <p>Nel carcere di Fort Smith, aspettando l'esecuzione, Sarah incontrò Reverenda Martha Hayes, una predicatrice metodista che visitava i condannati per offrire conforto spirituale nelle loro ultime settimane.</p>

                        <p>Martha non offrì perdono facile. Non disse "Dio ti ama" come una frase vuota. Invece disse: "Hai fatto cose terribili. Hai preso una vita innocente. Il peso di quella colpa non scomparirà mai completamente. Ma puoi scegliere cosa farne. Puoi lasciare che ti distrugga, o puoi trasformarla in qualcosa che redime."</p>

                        <p>Per settimane, Sarah e Martha parlarono attraverso le sbarre della cella. Martha condivise la sua fede - non come una dottrina rigida ma come una relazione vivente con il divino, come una scelta quotidiana di fare il bene anche quando è difficile. E lentamente, molto lentamente, qualcosa in Sarah iniziò a cambiare.</p>

                        <p>Tre giorni prima dell'esecuzione programmata, arrivò un telegramma dal governatore: grazia. Non clemenza completa, ma commutazione della pena in dieci anni di prigione. Qualcuno - Sarah non ha mai saputo chi - aveva interceduto per lei, forse toccato dalla sua conversione religiosa, forse semplicemente credendo che meritasse una seconda possibilità.</p>

                        <p>Sarah servì sette anni prima di essere rilasciata per buona condotta. Durante quegli anni, studiò con Martha (che continuò a visitarla regolarmente), imparando non solo teologia ma anche pratiche spirituali più profonde - come pregare con potere reale, come benedire oggetti, come riconoscere la presenza del male soprannaturale.</p>

                        <p>Quando fu rilasciata nel 1887, prese i voti come predicatrice itinerante. Da allora ha viaggiato attraverso il West portando il vangelo a chi ne ha bisogno, ma anche - e forse più importante - combattendo attivamente contro le forze oscure che minacciano le anime innocenti.</p>
                    </div>

                    <h3>La Donna che È Adesso</h3>

                    <p>Sarah è una predicatrice, sì, ma non del tipo che predica solo la domenica in una chiesa sicura. È una guerriera spirituale che cerca attivamente il male e lo combatte con fede e pistola in egual misura.</p>

                    <p>Ha una relazione complessa con Dio. Crede fermamente, prega con devozione, e ha visto il potere divino manifestarsi attraverso le sue mani. Ma crede anche che Dio le abbia dato libero arbitrio e si aspetti che lo usi - che la fede senza azione sia vuota, che pregare senza agire sia ipocrisia.</p>

                    <p>Porta il peso della bambina che ha ucciso ogni singolo giorno. Quel peso non è diminuito con gli anni - se mai, è diventato più pesante mentre è diventata più consapevole del valore di ogni singola vita. Ma ha imparato a trasformare quel peso in motivazione invece che in disperazione. Ogni persona che salva, ogni anima che protegge dall'oscurità, è un piccolo passo verso una redenzione che sa di non poter mai completare del tutto.</p>

                    <p>È gentile ma non debole. Compassionevole ma non ingenua. Perdonerà quasi qualsiasi peccato - conosce fin troppo bene come le circostanze possano spingere le persone a fare cose terribili - ma non tollererà crudeltà deliberata o danno agli innocenti. Quando affronta il male genuino, non esita a usare la violenza sacra per fermarlo.</p>

                    <p>Crede che tutti meritino una seconda possibilità. Ma solo una. Se qualcuno rifiuta la redenzione e continua a fare il male, Sarah farà ciò che è necessario.</p>

                    <h3>Statistiche e Abilità</h3>

                    <div class="stat-block">
                        <h4>STATISTICHE BASE</h4>
                        <p><strong>CLASSE:</strong> Chierico (Guerriero della Fede variant) | <strong>LIVELLO:</strong> 2</p>
                        <p><strong>PUNTI FERITA:</strong> 24 | <strong>ARMATURA:</strong> 1 | <strong>EVASIONE:</strong> 13 | <strong>SOGLIA:</strong> 3</p>
                        <p><strong>CARATTERISTICHE:</strong> Forza +1 | Agilità +2 | Finezza +1 | Istinto +2 | Presenza +3 | Conoscenza +2</p>
                        <p><strong>ESPERIENZE:</strong> ✝️ Teologia e Testi Sacri (Maestro) | 🔫 Armi da Fuoco | 🗣️ Oratoria e Persuasione | 👁️ Riconoscere il Male Soprannaturale</p>
                    </div>

                    <div class="collapsible">PAROLA CHE GUARISCE (3 utilizzi/riposo)</div>
                    <div class="collapsible-content">
                        <p>Il tuo tocco e le tue preghiere possono sanare ferite attraverso la grazia divina. Con un'azione, tocca un alleato entro distanza Molto Ravvicinata e pronuncia una preghiera di guarigione. L'alleato recupera 2d8+3 Punti Ferita immediatamente. Inoltre, rimuove una condizione minore (Stordito, Indebolito, Rallentato).</p>
                        <p>Se l'alleato è ridotto sotto la metà dei suoi PF massimi, recupera invece 3d8+3 PF - la tua fede è più forte quando la disperazione è maggiore.</p>
                    </div>

                    <div class="collapsible">FUOCO PURIFICATORE (2 utilizzi/riposo)</div>
                    <div class="collapsible-content">
                        <p>Invochi fiamme divine che bruciano il male ma non toccano gli innocenti. Scegli un punto che puoi vedere entro distanza Ravvicinata. Fiamme bianche e dorate esplodono in un'area di 10 piedi di raggio. Ogni creatura nemica nell'area subisce 3d8 danni da fuoco sacro (bypassa armatura). Creature con tag [NON-MORTO], [DEMONIACO], o [CORROTTO] subiscono 5d8 danni invece.</p>
                        <p>Gli alleati nell'area non subiscono danni - le fiamme li lambiscono senza bruciare.</p>
                    </div>

                    <div class="collapsible">LA PAROLA CHE SCACCIA (2 utilizzi/riposo)</div>
                    <div class="collapsible-content">
                        <p>Pronunci il nome di Dio con tale potere che l'oscurità stessa indietreggia. Scegli fino a 3 creature con tag [NON-MORTO] o [DEMONIACO] che puoi vedere entro distanza Ravvicinata. Ogni creatura deve fare un tiro di Presenza contro Difficoltà 15. Se fallisce, deve immediatamente usare il suo prossimo turno per fuggire lontano da te il più velocemente possibile e non può avvicinarsi volontariamente a te per 1 minuto.</p>
                        <p>Creature con Soglia 3 o inferiore che falliscono di 5+ punti sono distrutte completamente - la tua fede le dissolve.</p>
                    </div>

                    <div class="collapsible">BENEDIZIONE DELL'ARMA (Rituale, 10 minuti)</div>
                    <div class="collapsible-content">
                        <p>Puoi benedire fino a 12 proiettili o un'arma da mischia con preghiere e acqua santa. L'arma o i proiettili benedetti contano come sacri: infliggono +2d6 danni contro [NON-MORTO], [DEMONIACO], [CORROTTO] e generano 1 punto Speranza quando colpiscono queste creature. La benedizione dura fino all'alba successiva.</p>
                        <p>Il tuo revolver personale è stato benedetto permanentemente e ha sempre questo effetto.</p>
                    </div>

                    <div class="collapsible">SCUDO DI FEDE (1 utilizzo/riposo)</div>
                    <div class="collapsible-content">
                        <p>Quando un alleato entro distanza Ravvicinata sta per subire danni, puoi usare la tua reazione per invocare protezione divina. Una barriera luminosa e semi-trasparente appare davanti all'alleato. I danni che sta per subire sono ridotti di 2d8+4 (minimo 0). Se i danni sono ridotti completamente a 0, genera 1 punto Speranza - il gruppo vede tangibilmente che la fede ti protegge.</p>
                    </div>

                    <h3>Connessioni</h3>

                    <div class="info-box">
                        <h4>CON JACK MALONE</h4>
                        <p><em>"Jack ha smesso di credere in Dio la notte in cui il suo amico è morto. Non lo giudico - ho visto abbastanza orrore per capire perché qualcuno perderebbe la fede. Ma continuo a pregare per lui, perché forse il mio credere può essere abbastanza forte per entrambi finché non trova di nuovo la sua strada."</em></p>
                        <p><strong>Meccanica:</strong> Quando Jack subisce danni che riempirebbero segmenti della sua Tenuta Mentale, Sarah può scegliere di riempire quei segmenti sulla propria Tenuta invece - assorbe il trauma psicologico attraverso la sua fede.</p>
                    </div>

                    <div class="info-box">
                        <h4>CON DOC ARTEMIS</h4>
                        <p><em>"Il dottore cerca di razionalizzare tutto quello che vede, di metterlo in categorie scientifiche ordinate. È il suo modo di affrontare l'impossibile. Io affronto l'impossibile con la fede. A volte discutiamo - lui con logica, io con teologia. Ma entrambi stiamo cercando verità, solo attraverso lenti diverse."</em></p>
                        <p><strong>Meccanica:</strong> Quando Sarah e Doc lavorano insieme per aiutare qualcuno (lei guarisce, lui fornisce cure mediche), l'effetto combinato recupera +1d8 PF extra grazie alla sinergia tra fede e scienza.</p>
                    </div>

                    <h3>Equipaggiamento</h3>

                    <div class="stat-block">
                        <p><strong>ARMI:</strong></p>
                        <ul>
                            <li>Revolver Benedetto (.38 Special) - 1d8+2 danni base, +2d6 vs [NON-MORTO]/[DEMONIACO]/[CORROTTO], Ricarica 6</li>
                            <li>48 proiettili standard + 12 proiettili benedetti</li>
                        </ul>
                        
                        <p><strong>EQUIPAGGIAMENTO SACRO:</strong> Bibbia rilegata in pelle con note personali, croce d'argento benedetta, fiaschetta acqua santa (3 utilizzi), kit per rituali (candele, incenso, sale consacrato)</p>
                        
                        <p><strong>GENERALE:</strong> Abito nero pratico (Armatura 1), mantello, borraccia, diario personale, 28 dollari</p>
                        
                        <p><strong>OGGETTO PERSONALE:</strong> Una fotografia sbiadita di una bambina sorridente - la ragazzina che Sarah uccise anni fa. Sul retro, scritto con calligrafia infantile: "Per la mamma, con amore, Emily." Sarah la tiene come promemoria del perché fa quello che fa.</p>
                    </div>

                    <div class="collapsible">Come Giocare Sarah</div>
                    <div class="collapsible-content">
                        <p><strong>IN COMBATTIMENTO:</strong> Sarah è supporto offensivo - guarisce gli alleati ma può anche infliggere danni devastanti ai non-morti. Usa Parola che Guarisce liberamente. Conserva Fuoco Purificatore per gruppi di nemici o boss non-morti. La Parola che Scaccia è eccellente per controllare il campo di battaglia. Posizionati centralmente per raggiungere tutti.</p>
                        
                        <p><strong>NELLE SCENE SOCIALI:</strong> Sarah è carismatica e persuasiva. Usa Presenza +3 liberamente per diplomazia. Quando parla, la gente ascolta. È gentile per default ma diventa acciaio puro quando affronta il male. Non alza mai la voce, ma quando dice "Questo finisce adesso" con calma assoluta, è terrificante.</p>
                        
                        <p><strong>CON GLI ALTRI PERSONAGGI:</strong> Con Jack - preoccupata ma rispettosa, offre preghiere non sermoni. Con Doc - rispetto intellettuale reciproco, discussioni filosofiche su scienza vs fede.</p>
                        
                        <p><strong>MOMENTI CHIAVE:</strong> Quando vedi i morti alzarsi = shock teologico poi fede consolidata. Quando qualcuno muore = preghi immediatamente per la loro anima. Se incontri Jeremiah = provi a salvarlo prima di combatterlo. Quando benedici armi = fallo con rituale appropriato.</p>
                        
                        <p><strong>LA TUA DOMANDA CENTRALE:</strong> Puoi redimerti completamente per aver preso una vita innocente?</p>
                    </div>
                </article>

                <hr style="margin: 60px 0;">

                <p style="text-align: center; font-style: italic; color: var(--rust);">
                    [Il personaggio Doc Artemis e le sezioni successive continuano nel file successivo per gestire la dimensione...]
                </p>
            </section>

        </main>
    </div>

    <script>
        // Script per le sezioni collassabili
        document.querySelectorAll('.collapsible').forEach(button => {
            button.addEventListener('click', function() {
                this.classList.toggle('active');
                const content = this.nextElementSibling;
                content.classList.toggle('active');
            });
        });

        // Smooth scroll per i link di navigazione
        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function (e) {
                e.preventDefault();
                const target = document.querySelector(this.getAttribute('href'));
                if (target) {
                    target.scrollIntoView({
                        behavior: 'smooth',
                        block: 'start'
                    });
                }
            });
        });
    </script>
</body>
</html>

        </main>
    </div>

    <script>
        // Script per le sezioni collassabili
        document.querySelectorAll('.collapsible').forEach(button => {
            button.addEventListener('click', function() {
                this.classList.toggle('active');
                const content = this.nextElementSibling;
                content.classList.toggle('active');
            });
        });

        // Smooth scroll per i link di navigazione
        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function (e) {
                e.preventDefault();
                const target = document.querySelector(this.getAttribute('href'));
                if (target) {
                    target.scrollIntoView({
                        behavior: 'smooth',
                        block: 'start'
                    });
                }
            });
        });
    </script>
</body>
</html>
