USB-Uncensored-LLM ⚡

USB-Uncensored-LLM est un environnement d’IA local entièrement hors ligne, sans dépendances, prêt à l’emploi, conçu pour fonctionner directement depuis votre disque dur local ou un USB/SSD portable. Il évite les installations complexes en exécutant nativement de grands modèles de langage directement sur votre matériel, sans connexion Internet.
Avec une architecture unifiée , vous pouvez initialiser vos modèles d’IA une seule fois et choisir de les conserver sur votre système ou de les emporter avec vous sur des PC Windows, macOS et Linux.
🚀 Fonctionnalités principales
•	Installation sans dépendances: Fourni avec Python portable et des binaires moteur isolés. Aucun droit système, aucune modification du registre et aucun gestionnaire de paquets ne sont nécessaires.
•	Interopérabilité multiplateforme: Utilise un système de volume Shared intelligent - téléchargez vos modèles d’IA de plus de 5 Go une seule fois, puis utilisez-les nativement sur Windows, macOS et Linux sans duplication.
•	Sans censure: Intègre des modèles récents affinés de type ablative et heretic pour des interactions totalement non filtrées.
•	Interface réseau proxy: Le serveur HTTP Python personnalisé sert instantanément une interface sombre très rapide. Vous pouvez accéder à l’IA depuis votre téléphone ou votre tablette sur le même réseau WiFi sans configuration CORS complexe.
•	Accélération matérielle: Utilise un moteur Ollama compilé sur mesure, capable d’exploiter nativement les instructions CPU AVX, NVIDIA CUDA ou les accélérateurs GPU Apple Metal selon la machine hôte utilisée.

💻 Configuration requise
Avant de préparer votre support, vérifiez que vous disposez de :
•	Stockage: Une clé USB 3.0+ ou un SSD avec au minimum 8 GO d’espace libre (16 GO est fortement recommandé).
•	RAM: L’ordinateur hôte doit avoir au moins 8 GO de mémoire système pour exécuter les modèles 2B/4B, et 16 GO de mémoire pour faire tourner correctement les modèles 9B/12B.

📂 Architecture des dossiers
Le projet est structuré pour isoler strictement les exécutables de chaque système d’exploitation tout en regroupant de façon sécurisée les poids volumineux des modèles afin d’économiser l’espace de stockage portable.

[Clé USB portable]

 ├── 📁 Linux      # Installateurs et lanceurs hors ligne natifs pour Ubuntu/Debian
 
 ├── 📁 Mac        # Installateurs et lanceurs hors ligne natifs pour macOS
 
 ├── 📁 Windows    # Menus d’interface automatiques hors ligne natifs pour Windows
 
 └── 📁 Shared     # Système de données unifié
 
      ├── 📁 bin         (Contient les exécutables isolés : ollama-windows.exe, ollama-darwin...)
      
      ├── 📁 chat_data   (Contient l’historique persistant des conversations multiplateforme)
      
      ├── 📁 models      (HuggingFace GGUF Weights et mappage de la base de données locale)
      
      └── 📁 python      (Environnement Python portable isolé)
      

🧠 Bibliothèque de modèles d’IA sélectionnés
Cette clé USB inclut un installateur sélectionné pour les meilleurs modèles non censurés, utilisables localement, disponibles aujourd’hui sur le marché open source :
1.	Gemma 2 2B Abliterated (~1.6 GO): Recommandé pour tous. Très rapide, très performant pour sa taille, avec des vecteurs d’alignement de sécurité supprimés mathématiquement.
2.	Gemma 4 E4B Ultra Uncensored Heretic (~5.34 GO): Un fine-tuning "heretic" qui force agressivement la conformité à toutes les requêtes utilisateur, quel que soit le contenu ou la légalité.
3.	Qwen 3.5 9B Uncensored Aggressive (~5.2 GO): Un modèle de raisonnement bien plus grand, très compétent, avec une adhérence stricte à des réponses brutes et non biaisées.
4.	Modèles personnalisés: L’installateur permet de télécharger n’importe quel .gguf directement depuis HuggingFace vers le moteur de la clé USB.


⚙️ Guide de démarrage rapide
Étape 1 : Initialiser le moteur
Selon l’ordinateur sur lequel vous êtes actuellement branché, ouvrez le dossier correspondant au système d’exploitation puis exécutez le script d’installation par double-clic.
•	Windows: Double-cliquez sur Windows/install.bat
•	macOS: Ouvrez Terminal, glissez Mac/install.command, puis appuyez sur Entrée.
•	Linux: Exécutez bash Linux/install.sh
Note: L’initialisation télécharge simplement le petit moteur d’exécution de 50 MB propre à cet ordinateur dans le dossier Shared/bin.
Étape 2 : Télécharger les modèles d’IA
Il est fortement recommandé d’effectuer la phase de téléchargement des modèles via un PC Windows (Windows/install.bat), qui fournit un catalogue interactif en terminal pour sélectionner et télécharger facilement des modèles GGUF non censurés soigneusement choisis. (Si vous n’avez pas de PC Windows, téléchargez simplement vos .gguf depuis HuggingFace et placez-les manuellement dans le dossier Shared/models ).
Étape 3 : Lancer
Ouvrez le dossier du système concerné et exécutez le script start :
•	Windows: Windows/start-fast-chat.bat
•	macOS: Mac/start.command
•	Linux: bash Linux/start.sh
Le moteur démarrera de manière sécurisée en arrière-plan, et votre navigateur web par défaut ouvrira automatiquement l’interface de chat servie en local.


🏠 Installation sur disque local
Même si ce projet est optimisé pour une utilisation portable sur USB, il fonctionne très bien comme installation légère d’IA locale sur votre ordinateur principal.
Comment installer en local :
1.	Téléchargez/Clonez ce dépôt dans un dossier de votre lecteur C:\ ou D:\ .
2.	Accédez au dossier Windows (ou Mac/Linux).
3.	Exécutez install.bat et choisissez les modèles souhaités.
4.	Le système téléchargera tout dans ce dossier local.
5.	Exécutez start-fast-chat.bat pour commencer.
Avantage: L’exécution depuis un SSD interne est nettement plus rapide que depuis une clé USB, ce qui permet un chargement presque instantané des modèles d’IA.


📱 Accès mobile LAN
Si vous voulez utiliser cette IA puissante depuis votre téléphone, tranquillement depuis votre canapé :
1.	Assurez-vous que le PC qui exécute le script start et votre téléphone sont sur le même réseau WiFi.
2.	La fenêtre du terminal détectera automatiquement votre machine hôte et affichera une adresse IP de Network Access (par exemple, http://192.168.1.15:3333).
3.	Saisissez simplement cette URL dans le navigateur de votre téléphone (Safari/Chrome). Le serveur Python personnalisé redirige directement les requêtes mobiles vers la clé USB. (Remarque : si les pages ne se chargent pas, vérifiez que le pare-feu Windows autorise les connexions entrantes sur le port 3333).


🛠️ Dépannage
•	Le script se ferme instantanément sous Windows: Vous avez probablement activé les anciens Windows App Execution Aliases, ce qui trompe le système. Lancez le script depuis l’invite de commandes, ou faites un clic droit sur le fichier .bat puis choisissez "Run as Administrator".
•	"Ollama Engine Not Found": Vous avez essayé d’exécuter le script start avant que le script install ne télécharge le logiciel de base pour votre système. Exécutez l’installateur de votre système d’exploitation!
•	Vitesses de génération lentes: Votre modèle est trop volumineux pour la RAM de votre PC hôte. Relancez install.bat et sélectionnez le modèle Gemma 2 2B Abliterated , qui fonctionne rapidement même sur des machines plus anciennes.


Avertissement : USB-Uncensored-LLM est conçu pour une liberté de calcul sans compromis. En utilisant des modèles ablative, le système ne fera pas la morale, ne donnera pas de leçons et ne refusera pas vos prompts. Veuillez l’utiliser avec responsabilité.
USB-Uncensored-LLM

