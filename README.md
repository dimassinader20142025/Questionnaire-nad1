# Questionnaire-nad1
Questionnaire pour l'Étude sur l'Éducation Sexuelle via Application Mobile

<!DOCTYPE html>
<html lang="fr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Questionnaire Éducation Sexuelle - Master en Sexologie</title>
    <script src="https://cdn.jsdelivr.net/npm/chart.js"></script>
    <script src="https://cdn.jsdelivr.net/npm/qrcode@1.5.0/build/qrcode.min.js"></script>
    <style>
        :root {
            --primary: #3498db;
            --secondary: #2ecc71;
            --accent: #e74c3c;
            --light: #f5f5f5;
            --dark: #333;
        }
        
        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }
        
        body {
            background-color: #f9f9f9;
            color: var(--dark);
            line-height: 1.6;
        }
        
        header {
            background: linear-gradient(135deg, var(--primary), var(--secondary));
            color: white;
            padding: 2rem 1rem;
            text-align: center;
            box-shadow: 0 4px 6px rgba(0,0,0,0.1);
        }
        
        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 2rem;
        }
        
        .tabs {
            display: flex;
            margin-bottom: 2rem;
            border-bottom: 2px solid var(--primary);
        }
        
        .tab {
            padding: 1rem 2rem;
            background: white;
            border: none;
            cursor: pointer;
            font-size: 1rem;
            font-weight: bold;
            transition: all 0.3s;
            border-radius: 5px 5px 0 0;
            margin-right: 5px;
        }
        
        .tab.active {
            background: var(--primary);
            color: white;
        }
        
        .tab:hover:not(.active) {
            background: #e0e0e0;
        }
        
        .tab-content {
            display: none;
            background: white;
            padding: 2rem;
            border-radius: 0 5px 5px 5px;
            box-shadow: 0 2px 10px rgba(0,0,0,0.1);
        }
        
        .tab-content.active {
            display: block;
        }
        
        .question {
            margin-bottom: 2rem;
            padding-bottom: 1.5rem;
            border-bottom: 1px solid #eee;
        }
        
        .question h3 {
            margin-bottom: 1rem;
            color: var(--primary);
        }
        
        .options {
            display: flex;
            flex-wrap: wrap;
            gap: 10px;
        }
        
        .option {
            flex: 1 0 200px;
            padding: 10px;
            background: var(--light);
            border-radius: 5px;
            cursor: pointer;
            transition: all 0.2s;
        }
        
        .option:hover {
            background: #e0e0e0;
        }
        
        .option.selected {
            background: var(--secondary);
            color: white;
        }
        
        input[type="text"], input[type="email"], input[type="number"], textarea, select {
            width: 100%;
            padding: 10px;
            border: 1px solid #ddd;
            border-radius: 5px;
            margin-top: 5px;
        }
        
        textarea {
            min-height: 100px;
            resize: vertical;
        }
        
        button {
            background: var(--primary);
            color: white;
            border: none;
            padding: 12px 25px;
            border-radius: 5px;
            cursor: pointer;
            font-size: 1rem;
            font-weight: bold;
            transition: all 0.3s;
        }
        
        button:hover {
            background: #2980b9;
            transform: translateY(-2px);
        }
        
        .stats-section {
            margin-top: 3rem;
            padding: 2rem;
            background: white;
            border-radius: 5px;
            box-shadow: 0 2px 10px rgba(0,0,0,0.1);
        }
        
        .charts-container {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 20px;
            margin-top: 2rem;
        }
        
        .chart-container {
            background: white;
            padding: 1rem;
            border-radius: 5px;
            box-shadow: 0 2px 5px rgba(0,0,0,0.1);
        }
        
        .qr-section {
            text-align: center;
            margin: 2rem 0;
            padding: 1.5rem;
            background: white;
            border-radius: 5px;
            box-shadow: 0 2px 10px rgba(0,0,0,0.1);
        }
        
        footer {
            text-align: center;
            padding: 2rem;
            margin-top: 3rem;
            background: var(--dark);
            color: white;
        }
        
        .required {
            color: var(--accent);
        }
        
        .consent {
            background: #fff9e6;
            padding: 1rem;
            border-radius: 5px;
            margin-bottom: 2rem;
            border-left: 4px solid #ffcc00;
        }
        
        .admin-section {
            margin-top: 2rem;
            padding: 1.5rem;
            background: #f8f9fa;
            border-radius: 5px;
            border: 1px solid #dee2e6;
        }
        
        @media (max-width: 768px) {
            .tabs {
                flex-direction: column;
            }
            
            .tab {
                margin-bottom: 5px;
                border-radius: 5px;
            }
            
            .options {
                flex-direction: column;
            }
            
            .option {
                flex: 1;
            }
        }
    </style>
</head>
<body>
    <header>
        <h1>Étude sur l'Éducation Sexuelle via Application Mobile</h1>
        <p>Master en Sexologie Clinique - Mémoire de Fin d'Études</p>
    </header>
    
    <div class="container">
        <div class="tabs">
            <button class="tab active" data-tab="jeunes">Questionnaire Jeunes Tunisiens</button>
            <button class="tab" data-tab="professionnels">Questionnaire Professionnels de Santé</button>
            <button class="tab" data-tab="statistiques">Statistiques et Analyses</button>
            <button class="tab" data-tab="admin">Administration</button>
        </div>
        
        <div class="tab-content active" id="jeunes">
            <h2>Questionnaire pour les Jeunes Tunisiens</h2>
            <p>Ce questionnaire vise à comprendre vos besoins et attentes concernant une application mobile d'éducation sexuelle.</p>
            
            <div class="consent">
                <p><strong>Consentement éclairé :</strong> En participant à cette étude, vous acceptez que vos réponses soient utilisées de manière anonyme à des fins de recherche. Vous pouvez quitter l'étude à tout moment sans avoir à justifier votre décision.</p>
            </div>
            
            <form id="form-jeunes">
                <div class="question">
                    <h3>1. Quel est votre âge ? <span class="required">*</span></h3>
                    <input type="number" id="age" name="age" min="15" max="30" required>
                </div>
                
                <div class="question">
                    <h3>2. Quel est votre genre ? <span class="required">*</span></h3>
                    <div class="options">
                        <div class="option" data-value="homme">Homme</div>
                        <div class="option" data-value="femme">Femme</div>
                        <div class="option" data-value="non-binaire">Non-binaire</div>
                        <div class="option" data-value="prefere-ne-pas-repondre">Je préfère ne pas répondre</div>
                    </div>
                    <input type="hidden" id="genre" name="genre" required>
                </div>
                
                <div class="question">
                    <h3>3. Quel est votre niveau d'éducation ? <span class="required">*</span></h3>
                    <div class="options">
                        <div class="option" data-value="secondaire">Secondaire</div>
                        <div class="option" data-value="bac">Bac</div>
                        <div class="option" data-value="universitaire">Universitaire</div>
                        <div class="option" data-value="autre">Autre</div>
                    </div>
                    <input type="hidden" id="education" name="education" required>
                </div>
                
                <div class="question">
                    <h3>4. Comment évaluez-vous votre niveau actuel de connaissances en éducation sexuelle ? <span class="required">*</span></h3>
                    <div class="options">
                        <div class="option" data-value="faible">Faible</div>
                        <div class="option" data-value="moyen">Moyen</div>
                        <div class="option" data-value="bon">Bon</div>
                        <div class="option" data-value="excellent">Excellent</div>
                    </div>
                    <input type="hidden" id="niveau-connaissances" name="niveau-connaissances" required>
                </div>
                
                <div class="question">
                    <h3>5. Quelles sont vos principales sources d'information sur la santé sexuelle actuellement ? (Plusieurs réponses possibles)</h3>
                    <div class="options">
                        <div class="option" data-value="internet">Internet / Réseaux sociaux</div>
                        <div class="option" data-value="amis">Amis</div>
                        <div class="option" data-value="famille">Famille</div>
                        <div class="option" data-value="ecole">École / Université</div>
                        <div class="option" data-value="professionnels">Professionnels de santé</div>
                        <div class="option" data-value="livres">Livres / Publications</div>
                        <div class="option" data-value="autre">Autre</div>
                    </div>
                    <input type="hidden" id="sources" name="sources">
                </div>
                
                <div class="question">
                    <h3>6. Quels sujets liés à la santé sexuelle souhaiteriez-vous mieux comprendre ? (Plusieurs réponses possibles)</h3>
                    <div class="options">
                        <div class="option" data-value="anatomie">Anatomie et physiologie</div>
                        <div class="option" data-value="contraception">Méthodes contraceptives</div>
                        <div class="option" data-value="mst">Infections sexuellement transmissibles (IST)</div>
                        <div class="option" data-value="consentement">Consentement et relations saines</div>
                        <div class="option" data-value="orientation">Orientation sexuelle et identité de genre</div>
                        <div class="option" data-value="plaisir">Plaisir et sexualité positive</div>
                        <div class="option" data-value="sante-mentale">Santé sexuelle et mentale</div>
                    </div>
                    <input type="hidden" id="sujets" name="sujets">
                </div>
                
                <div class="question">
                    <h3>7. Seriez-vous intéressé(e) par une application mobile d'éducation sexuelle ? <span class="required">*</span></h3>
                    <div class="options">
                        <div class="option" data-value="oui">Oui</div>
                        <div class="option" data-value="non">Non</div>
                        <div class="option" data-value="peut-etre">Peut-être</div>
                    </div>
                    <input type="hidden" id="interet-app" name="interet-app" required>
                </div>
                
                <div class="question">
                    <h3>8. Quelles fonctionnalités souhaiteriez-vous trouver dans une telle application ? (Plusieurs réponses possibles)</h3>
                    <div class="options">
                        <div class="option" data-value="contenus-educatifs">Contenus éducatifs (articles, vidéos)</div>
                        <div class="option" data-value="faq">FAQ et réponses aux questions courantes</div>
                        <div class="option" data-value="chat">Chat avec des professionnels</div>
                        <div class="option" data-value="test">Tests de connaissances</div>
                        <div class="option" data-value="ressources">Ressources locales (centres de santé)</div>
                        <div class="option" data-value="anonymat">Anonymat complet</div>
                        <div class="option" data-value="adaptation-culturelle">Adaptation au contexte tunisien</div>
                    </div>
                    <input type="hidden" id="fonctionnalites" name="fonctionnalites">
                </div>
                
                <div class="question">
                    <h3>9. Quels seraient vos principales préoccupations concernant l'utilisation d'une application d'éducation sexuelle ?</h3>
                    <textarea id="preoccupations" name="preoccupations" placeholder="Vos réponses ici..."></textarea>
                </div>
                
                <div class="question">
                    <h3>10. Avez-vous des commentaires ou suggestions supplémentaires ?</h3>
                    <textarea id="commentaires" name="commentaires" placeholder="Vos commentaires ici..."></textarea>
                </div>
                
                <button type="submit">Soumettre le questionnaire</button>
            </form>
        </div>
        
        <div class="tab-content" id="professionnels">
            <h2>Questionnaire pour les Professionnels de Santé</h2>
            <p>Ce questionnaire vise à recueillir votre expertise concernant les besoins en éducation sexuelle et l'utilisation d'une application mobile dans ce domaine.</p>
            
            <div class="consent">
                <p><strong>Consentement éclairé :</strong> En participant à cette étude, vous acceptez que vos réponses soient utilisées de manière anonyme à des fins de recherche. Vous pouvez quitter l'étude à tout moment sans avoir à justifier votre décision.</p>
            </div>
            
            <form id="form-professionnels">
                <div class="question">
                    <h3>1. Quel est votre domaine de spécialisation ? <span class="required">*</span></h3>
                    <input type="text" id="specialisation" name="specialisation" required>
                </div>
                
                <div class="question">
                    <h3>2. Depuis combien d'années exercez-vous ? <span class="required">*</span></h3>
                    <input type="number" id="annees-experience" name="annees-experience" min="0" max="50" required>
                </div>
                
                <div class="question">
                    <h3>3. Dans quel type d'établissement travaillez-vous principalement ? <span class="required">*</span></h3>
                    <div class="options">
                        <div class="option" data-value="hopital-public">Hôpital public</div>
                        <div class="option" data-value="hopital-prive">Hôpital privé</div>
                        <div class="option" data-value="cabinet">Cabinet privé</div>
                        <div class="option" data-value="centre-sante">Centre de santé</div>
                        <div class="option" data-value="universitaire">Établissement universitaire</div>
                        <div class="option" data-value="autre">Autre</div>
                    </div>
                    <input type="hidden" id="etablissement" name="etablissement" required>
                </div>
                
                <div class="question">
                    <h3>4. À quelle fréquence êtes-vous confronté(e) à des questions liées à la santé sexuelle dans votre pratique ? <span class="required">*</span></h3>
                    <div class="options">
                        <div class="option" data-value="quotidiennement">Quotidiennement</div>
                        <div class="option" data-value="hebdomadairement">Hebdomadairement</div>
                        <div class="option" data-value="mensuellement">Mensuellement</div>
                        <div class="option" data-value="rarement">Rarement</div>
                    </div>
                    <input type="hidden" id="frequence-questions" name="frequence-questions" required>
                </div>
                
                <div class="question">
                    <h3>5. Quels sont les principaux défis que vous rencontrez dans la fourniture d'éducation sexuelle ? (Plusieurs réponses possibles)</h3>
                    <div class="options">
                        <div class="option" data-value="temps">Manque de temps</div>
                        <div class="option" data-value="formation">Manque de formation spécifique</div>
                        <div class="option" data-value="ressources">Manque de ressources adaptées</div>
                        <div class="option" data-value="tabous">Tabous culturels/sociaux</div>
                        <div class="option" data-value="langage">Difficulté à adapter le langage</div>
                        <div class="option" data-value="confidentialite">Problèmes de confidentialité</div>
                    </div>
                    <input type="hidden" id="defis" name="defis">
                </div>
                
                <div class="question">
                    <h3>6. Comment évaluez-vous le niveau général de connaissances en santé sexuelle chez les jeunes Tunisiens ? <span class="required">*</span></h3>
                    <div class="options">
                        <div class="option" data-value="faible">Faible</div>
                        <div class="option" data-value="moyen">Moyen</div>
                        <div class="option" data-value="bon">Bon</div>
                        <div class="option" data-value="variable">Variable selon les individus</div>
                    </div>
                    <input type="hidden" id="niveau-jeunes" name="niveau-jeunes" required>
                </div>
                
                <div class="question">
                    <h3>7. Pensez-vous qu'une application mobile d'éducation sexuelle pourrait être bénéfique ? <span class="required">*</span></h3>
                    <div class="options">
                        <div class="option" data-value="oui">Oui, certainement</div>
                        <div class="option" data-value="peut-etre">Peut-être</div>
                        <div class="option" data-value="non">Non</div>
                    </div>
                    <input type="hidden" id="utilite-app" name="utilite-app" required>
                </div>
                
                <div class="question">
                    <h3>8. Quels aspects cliniques devraient être prioritaires dans une telle application ? (Plusieurs réponses possibles)</h3>
                    <div class="options">
                        <div class="option" data-value="exactitude">Exactitude scientifique</div>
                        <div class="option" data-value="adaptation">Adaptation développementale</div>
                        <div class="option" data-value="contextualisation">Contextualisation culturelle</div>
                        <div class="option" data-value="accessibilite">Accessibilité linguistique</div>
                        <div class="option" data-value="inclusivite">Inclusivité</div>
                        <div class="option" data-value="confidentialite">Confidentialité</div>
                    </div>
                    <input type="hidden" id="aspects-cliniques" name="aspects-cliniques">
                </div>
                
                <div class="question">
                    <h3>9. Quels sont les principaux enjeux éthiques à considérer selon vous ?</h3>
                    <textarea id="enjeux-ethiques" name="enjeux-ethiques" placeholder="Vos réponses ici..."></textarea>
                </div>
                
                <div class="question">
                    <h3>10. Avez-vous des recommandations spécifiques pour le développement d'une telle application ?</h3>
                    <textarea id="recommandations" name="recommandations" placeholder="Vos recommandations ici..."></textarea>
                </div>
                
                <button type="submit">Soumettre le questionnaire</button>
            </form>
        </div>
        
        <div class="tab-content" id="statistiques">
            <h2>Statistiques et Analyses des Réponses</h2>
            <p>Les données ci-dessous sont mises à jour en temps réel au fur et à mesure que les participants répondent aux questionnaires.</p>
            
            <div class="charts-container">
                <div class="chart-container">
                    <h3>Répartition des participants</h3>
                    <canvas id="participants-chart"></canvas>
                </div>
                
                <div class="chart-container">
                    <h3>Intérêt pour une application mobile (Jeunes)</h3>
                    <canvas id="interet-app-chart"></canvas>
                </div>
                
                <div class="chart-container">
                    <h3>Utilité perçue (Professionnels)</h3>
                    <canvas id="utilite-app-chart"></canvas>
                </div>
                
                <div class="chart-container">
                    <h3>Niveau de connaissances (Jeunes)</h3>
                    <canvas id="niveau-connaissances-chart"></canvas>
                </div>
                
                <div class="chart-container">
                    <h3>Principales sources d'information (Jeunes)</h3>
                    <canvas id="sources-info-chart"></canvas>
                </div>
                
                <div class="chart-container">
                    <h3>Défis identifiés (Professionnels)</h3>
                    <canvas id="defis-chart"></canvas>
                </div>
            </div>
            
            <div class="stats-section">
                <h3>Données détaillées</h3>
                <div id="stats-details">
                    <p>Nombre total de participants (jeunes) : <span id="total-jeunes">0</span></p>
                    <p>Nombre total de participants (professionnels) : <span id="total-professionnels">0</span></p>
                    <p>Âge moyen des jeunes participants : <span id="age-moyen">0</span> ans</p>
                    <p>Années d'expérience moyennes (professionnels) : <span id="experience-moyenne">0</span> ans</p>
                    <p>Dernière mise à jour : <span id="last-update">-</span></p>
                </div>
            </div>
        </div>
        
        <div class="tab-content" id="admin">
            <h2>Administration des Données</h2>
            
            <div class="admin-section">
                <h3>Export des données</h3>
                <p>Téléchargez toutes les données collectées pour votre analyse.</p>
                <button id="export-data">Exporter les données (JSON)</button>
                <button id="export-csv">Exporter les données (CSV)</button>
            </div>
            
            <div class="admin-section">
                <h3>Gestion des données</h3>
                <p>Attention : Ces actions sont irréversibles.</p>
                <button id="reset-data" style="background-color: var(--accent);">Réinitialiser toutes les données</button>
                <button id="add-sample-data">Ajouter des données d'exemple</button>
            </div>
            
            <div class="admin-section">
                <h3>Statut du stockage</h3>
                <div id="storage-status">
                    <p>Méthode de stockage : <span id="storage-method">LocalStorage</span></p>
                    <p>Données sauvegardées : <span id="backup-status">Non</span></p>
                </div>
            </div>
        </div>
        
        <div class="qr-section">
            <h3>Partagez ce questionnaire</h3>
            <p>Scannez ce code QR pour accéder au questionnaire sur mobile</p>
            <div id="qrcode"></div>
            <p>URL du questionnaire : <strong id="site-url">Chargement...</strong></p>
        </div>
    </div>
    
    <footer>
        <p>Mémoire de fin d'études - Master en Sexologie Clinique</p>
        <p>© 2023 - Tous droits réservés</p>
    </footer>

    <script>
        // Gestion des onglets
        document.querySelectorAll('.tab').forEach(tab => {
            tab.addEventListener('click', () => {
                // Désactiver tous les onglets et contenus
                document.querySelectorAll('.tab').forEach(t => t.classList.remove('active'));
                document.querySelectorAll('.tab-content').forEach(c => c.classList.remove('active'));
                
                // Activer l'onglet et le contenu sélectionnés
                tab.classList.add('active');
                document.getElementById(tab.dataset.tab).classList.add('active');
                
                // Si on passe à l'onglet statistiques, mettre à jour les données
                if (tab.dataset.tab === 'statistiques') {
                    updateStatistics();
                }
            });
        });
        
        // Gestion des options sélectionnables
        document.querySelectorAll('.option').forEach(option => {
            option.addEventListener('click', function() {
                const parent = this.closest('.question');
                const input = parent.querySelector('input[type="hidden"]');
                
                // Si c'est une question à choix multiples
                if (input.id === 'sources' || input.id === 'sujets' || input.id === 'fonctionnalites' || 
                    input.id === 'defis' || input.id === 'aspects-cliniques') {
                    this.classList.toggle('selected');
                    
                    // Mettre à jour la valeur du champ caché
                    const selectedOptions = parent.querySelectorAll('.option.selected');
                    const values = Array.from(selectedOptions).map(opt => opt.dataset.value);
                    input.value = values.join(',');
                } 
                // Si c'est une question à choix unique
                else {
                    parent.querySelectorAll('.option').forEach(opt => opt.classList.remove('selected'));
                    this.classList.add('selected');
                    input.value = this.dataset.value;
                }
            });
        });
        
        // Génération du QR Code
        document.addEventListener('DOMContentLoaded', function() {
            const currentUrl = window.location.href;
            const qrContainer = document.getElementById('qrcode');
            
            // Nettoyer le conteneur QR
            qrContainer.innerHTML = '';
            
            // Générer le QR Code
            QRCode.toCanvas(qrContainer, currentUrl, { width: 150 }, function(error) {
                if (error) {
                    console.error('Erreur génération QR Code:', error);
                    qrContainer.innerHTML = '<p>Erreur lors de la génération du QR Code</p>';
                }
            });
            
            // Afficher l'URL du site
            document.getElementById('site-url').textContent = currentUrl;
            
            // Initialisation des graphiques
            initializeCharts();
            
            // Chargement des données existantes
            loadExistingData();
            
            // Configuration des boutons d'administration
            setupAdminButtons();
        });
        
        // Gestion de la soumission des formulaires
        document.getElementById('form-jeunes').addEventListener('submit', function(e) {
            e.preventDefault();
            saveResponse('jeunes', collectFormData(this));
            this.reset();
            document.querySelectorAll('#jeunes .option.selected').forEach(opt => opt.classList.remove('selected'));
            alert('Merci pour votre participation !');
        });
        
        document.getElementById('form-professionnels').addEventListener('submit', function(e) {
            e.preventDefault();
            saveResponse('professionnels', collectFormData(this));
            this.reset();
            document.querySelectorAll('#professionnels .option.selected').forEach(opt => opt.classList.remove('selected'));
            alert('Merci pour votre participation !');
        });
        
        // Fonction pour collecter les données du formulaire
        function collectFormData(form) {
            const formData = new FormData(form);
            const data = {};
            for (let [key, value] of formData.entries()) {
                data[key] = value;
            }
            return data;
        }
        
        // Simulation du stockage des données (dans un environnement réel, cela serait envoyé à un serveur)
        function saveResponse(type, data) {
            // Récupérer les données existantes
            const existingData = JSON.parse(localStorage.getItem(`questionnaire-${type}`) || '[]');
            
            // Ajouter la nouvelle réponse avec un timestamp
            data.timestamp = new Date().toISOString();
            data.id = Date.now() + Math.random().toString(36).substr(2, 9);
            existingData.push(data);
            
            // Sauvegarder
            localStorage.setItem(`questionnaire-${type}`, JSON.stringify(existingData));
            
            // Mettre à jour les statistiques
            updateStatistics();
            
            // Sauvegarder également dans un backup
            backupData();
        }
        
        // Sauvegarde des données
        function backupData() {
            const jeunesData = JSON.parse(localStorage.getItem('questionnaire-jeunes') || '[]');
            const prosData = JSON.parse(localStorage.getItem('questionnaire-professionnels') || '[]');
            
            const allData = {
                jeunes: jeunesData,
                professionnels: prosData,
                backupTimestamp: new Date().toISOString()
            };
            
            localStorage.setItem('questionnaire-backup', JSON.stringify(allData));
            document.getElementById('backup-status').textContent = 'Oui (' + new Date().toLocaleTimeString() + ')';
        }
        
        // Chargement des données existantes
        function loadExistingData() {
            // Vérifier s'il y a une sauvegarde
            const backup = localStorage.getItem('questionnaire-backup');
            if (backup) {
                document.getElementById('backup-status').textContent = 'Oui';
            }
            
            updateStatistics();
        }
        
        // Mise à jour des statistiques et graphiques
        function updateStatistics() {
            const jeunesData = JSON.parse(localStorage.getItem('questionnaire-jeunes') || '[]');
            const prosData = JSON.parse(localStorage.getItem('questionnaire-professionnels') || '[]');
            
            // Mettre à jour les compteurs
            document.getElementById('total-jeunes').textContent = jeunesData.length;
            document.getElementById('total-professionnels').textContent = prosData.length;
            
            // Calculer l'âge moyen des jeunes
            if (jeunesData.length > 0) {
                const totalAge = jeunesData.reduce((sum, response) => sum + parseInt(response.age || 0), 0);
                document.getElementById('age-moyen').textContent = (totalAge / jeunesData.length).toFixed(1);
            } else {
                document.getElementById('age-moyen').textContent = '0';
            }
            
            // Calculer l'expérience moyenne des professionnels
            if (prosData.length > 0) {
                const totalExp = prosData.reduce((sum, response) => sum + parseInt(response['annees-experience'] || 0), 0);
                document.getElementById('experience-moyenne').textContent = (totalExp / prosData.length).toFixed(1);
            } else {
                document.getElementById('experience-moyenne').textContent = '0';
            }
            
            // Mettre à jour l'heure de la dernière mise à jour
            document.getElementById('last-update').textContent = new Date().toLocaleString();
            
            // Mettre à jour les graphiques
            updateCharts(jeunesData, prosData);
        }
        
        // Initialisation des graphiques
        function initializeCharts() {
            // Graphique de répartition des participants
            window.participantsChart = new Chart(document.getElementById('participants-chart'), {
                type: 'doughnut',
                data: {
                    labels: ['Jeunes', 'Professionnels'],
                    datasets: [{
                        data: [0, 0],
                        backgroundColor: ['#3498db', '#2ecc71']
                    }]
                },
                options: {
                    responsive: true,
                    plugins: {
                        legend: {
                            position: 'bottom'
                        }
                    }
                }
            });
            
            // Graphique d'intérêt pour l'application (jeunes)
            window.interetAppChart = new Chart(document.getElementById('interet-app-chart'), {
                type: 'bar',
                data: {
                    labels: ['Oui', 'Non', 'Peut-être'],
                    datasets: [{
                        label: 'Nombre de réponses',
                        data: [0, 0, 0],
                        backgroundColor: '#3498db'
                    }]
                },
                options: {
                    responsive: true,
                    scales: {
                        y: {
                            beginAtZero: true
                        }
                    }
                }
            });
            
            // Graphique d'utilité perçue (professionnels)
            window.utiliteAppChart = new Chart(document.getElementById('utilite-app-chart'), {
                type: 'pie',
                data: {
                    labels: ['Oui, certainement', 'Peut-être', 'Non'],
                    datasets: [{
                        data: [0, 0, 0],
                        backgroundColor: ['#2ecc71', '#f39c12', '#e74c3c']
                    }]
                },
                options: {
                    responsive: true,
                    plugins: {
                        legend: {
                            position: 'bottom'
                        }
                    }
                }
            });
            
            // Graphique du niveau de connaissances (jeunes)
            window.niveauConnaissancesChart = new Chart(document.getElementById('niveau-connaissances-chart'), {
                type: 'bar',
                data: {
                    labels: ['Faible', 'Moyen', 'Bon', 'Excellent'],
                    datasets: [{
                        label: 'Nombre de réponses',
                        data: [0, 0, 0, 0],
                        backgroundColor: '#9b59b6'
                    }]
                },
                options: {
                    responsive: true,
                    scales: {
                        y: {
                            beginAtZero: true
                        }
                    }
                }
            });
            
            // Graphique des sources d'information (jeunes)
            window.sourcesInfoChart = new Chart(document.getElementById('sources-info-chart'), {
                type: 'bar',
                data: {
                    labels: ['Internet', 'Amis', 'Famille', 'École', 'Professionnels', 'Livres', 'Autre'],
                    datasets: [{
                        label: 'Nombre de citations',
                        data: [0, 0, 0, 0, 0, 0, 0],
                        backgroundColor: '#3498db'
                    }]
                },
                options: {
                    responsive: true,
                    indexAxis: 'y',
                    scales: {
                        x: {
                            beginAtZero: true
                        }
                    }
                }
            });
            
            // Graphique des défis (professionnels)
            window.defisChart = new Chart(document.getElementById('defis-chart'), {
                type: 'bar',
                data: {
                    labels: ['Manque de temps', 'Manque de formation', 'Manque de ressources', 'Tabous', 'Langage', 'Confidentialité'],
                    datasets: [{
                        label: 'Nombre de citations',
                        data: [0, 0, 0, 0, 0, 0],
                        backgroundColor: '#e74c3c'
                    }]
                },
                options: {
                    responsive: true,
                    scales: {
                        y: {
                            beginAtZero: true
                        }
                    }
                }
            });
        }
        
        // Mise à jour des graphiques avec les données
        function updateCharts(jeunesData, prosData) {
            // Mettre à jour le graphique des participants
            window.participantsChart.data.datasets[0].data = [jeunesData.length, prosData.length];
            window.participantsChart.update();
            
            // Mettre à jour le graphique d'intérêt pour l'application (jeunes)
            if (jeunesData.length > 0) {
                const interetCount = { 'oui': 0, 'non': 0, 'peut-etre': 0 };
                jeunesData.forEach(response => {
                    if (response['interet-app'] in interetCount) {
                        interetCount[response['interet-app']]++;
                    }
                });
                window.interetAppChart.data.datasets[0].data = [
                    interetCount.oui, interetCount.non, interetCount['peut-etre']
                ];
                window.interetAppChart.update();
                
                // Mettre à jour le graphique du niveau de connaissances
                const niveauCount = { 'faible': 0, 'moyen': 0, 'bon': 0, 'excellent': 0 };
                jeunesData.forEach(response => {
                    if (response['niveau-connaissances'] in niveauCount) {
                        niveauCount[response['niveau-connaissances']]++;
                    }
                });
                window.niveauConnaissancesChart.data.datasets[0].data = [
                    niveauCount.faible, niveauCount.moyen, niveauCount.bon, niveauCount.excellent
                ];
                window.niveauConnaissancesChart.update();
                
                // Mettre à jour le graphique des sources d'information
                const sourcesCount = {
                    'internet': 0, 'amis': 0, 'famille': 0, 'ecole': 0, 
                    'professionnels': 0, 'livres': 0, 'autre': 0
                };
                jeunesData.forEach(response => {
                    if (response.sources) {
                        response.sources.split(',').forEach(source => {
                            if (source in sourcesCount) {
                                sourcesCount[source]++;
                            }
                        });
                    }
                });
                window.sourcesInfoChart.data.datasets[0].data = [
                    sourcesCount.internet, sourcesCount.amis, sourcesCount.famille,
                    sourcesCount.ecole, sourcesCount.professionnels, sourcesCount.livres,
                    sourcesCount.autre
                ];
                window.sourcesInfoChart.update();
            }
            
            // Mettre à jour le graphique d'utilité perçue (professionnels)
            if (prosData.length > 0) {
                const utiliteCount = { 'oui': 0, 'peut-etre': 0, 'non': 0 };
                prosData.forEach(response => {
                    if (response['utilite-app'] in utiliteCount) {
                        utiliteCount[response['utilite-app']]++;
                    }
                });
                window.utiliteAppChart.data.datasets[0].data = [
                    utiliteCount.oui, utiliteCount['peut-etre'], utiliteCount.non
                ];
                window.utiliteAppChart.update();
                
                // Mettre à jour le graphique des défis
                const defisCount = {
                    'temps': 0, 'formation': 0, 'ressources': 0, 'tabous': 0, 
                    'langage': 0, 'confidentialite': 0
                };
                prosData.forEach(response => {
                    if (response.defis) {
                        response.defis.split(',').forEach(defi => {
                            if (defi in defisCount) {
                                defisCount[defi]++;
                            }
                        });
                    }
                });
                window.defisChart.data.datasets[0].data = [
                    defisCount.temps, defisCount.formation, defisCount.ressources,
                    defisCount.tabous, defisCount.langage, defisCount.confidentialite
                ];
                window.defisChart.update();
            }
        }
        
        // Configuration des boutons d'administration
        function setupAdminButtons() {
            // Export JSON
            document.getElementById('export-data').addEventListener('click', function() {
                const jeunesData = JSON.parse(localStorage.getItem('questionnaire-jeunes') || '[]');
                const prosData = JSON.parse(localStorage.getItem('questionnaire-professionnels') || '[]');
                
                const allData = {
                    jeunes: jeunesData,
                    professionnels: prosData,
                    exportTimestamp: new Date().toISOString()
                };
                
                const dataStr = JSON.stringify(allData, null, 2);
                const dataBlob = new Blob([dataStr], {type: 'application/json'});
                
                const url = URL.createObjectURL(dataBlob);
                const link = document.createElement('a');
                link.href = url;
                link.download = 'donnees_questionnaire_' + new Date().toISOString().split('T')[0] + '.json';
                document.body.appendChild(link);
                link.click();
                document.body.removeChild(link);
            });
            
            // Export CSV
            document.getElementById('export-csv').addEventListener('click', function() {
                // Cette fonction serait plus complexe pour convertir JSON en CSV
                alert("Fonction d'export CSV à implémenter");
            });
            
            // Réinitialisation des données
            document.getElementById('reset-data').addEventListener('click', function() {
                if (confirm('Êtes-vous sûr de vouloir réinitialiser toutes les données ? Cette action est irréversible.')) {
                    localStorage.removeItem('questionnaire-jeunes');
                    localStorage.removeItem('questionnaire-professionnels');
                    localStorage.removeItem('questionnaire-backup');
                    updateStatistics();
                    alert('Toutes les données ont été réinitialisées.');
                }
            });
            
            // Ajout de données d'exemple
            document.getElementById('add-sample-data').addEventListener('click', function() {
                const sampleJeunes = [
                    {
                        age: '20',
                        genre: 'femme',
                        education: 'universitaire',
                        'niveau-connaissances': 'moyen',
                        sources: 'internet,amis',
                        sujets: 'contraception,consentement',
                        'interet-app': 'oui',
                        fonctionnalites: 'contenus-educatifs,chat,anonymat',
                        preoccupations: 'Confidentialité des données',
                        commentaires: 'Application très utile',
                        timestamp: new Date().toISOString(),
                        id: 'sample1'
                    }
                ];
                
                const samplePros = [
                    {
                        specialisation: 'Gynécologie',
                        'annees-experience': '10',
                        etablissement: 'hopital-public',
                        'frequence-questions': 'quotidiennement',
                        defis: 'temps,tabous',
                        'niveau-jeunes': 'faible',
                        'utilite-app': 'oui',
                        'aspects-cliniques': 'exactitude,contextualisation',
                        'enjeux-ethiques': 'Respect de la vie privée',
                        recommandations: 'Inclure des professionnels locaux',
                        timestamp: new Date().toISOString(),
                        id: 'sample2'
                    }
                ];
                
                localStorage.setItem('questionnaire-jeunes', JSON.stringify(sampleJeunes));
                localStorage.setItem('questionnaire-professionnels', JSON.stringify(samplePros));
                backupData();
                updateStatistics();
                alert('Données d\'exemple ajoutées.');
            });
        }
    </script>
</body>
</html>