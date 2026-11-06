Référentiel expert de conception et de création de jeux vidéo

Version : 1.0
Date de vérification documentaire : 6 novembre 2026
Périmètre : jeux vidéo sur PC, consoles, appareils mobiles, navigateur, réalité virtuelle/augmentée et autres environnements d'exécution pertinents.
Profondeur : expert
Nature du document : référentiel de connaissances, de possibilités et de caractéristiques servant à établir des cahiers des charges.



0. Objet, périmètre et principes documentaires

Ce document rassemble les domaines à considérer lors de la conception d'un jeu vidéo, les familles de solutions possibles, leurs paramètres, leurs dépendances et les technologies connues qui peuvent les mettre en œuvre. Il est conçu pour être consulté comme une bibliothèque documentaire et non comme un parcours obligatoire.

Il ne constitue ni un prompt, ni un protocole de programmation, ni une méthode imposant un enchaînement de décisions. Il ne contient pas de règles du type « si le jeu est de tel genre, alors choisir obligatoirement telle solution ». Les familles, variantes et technologies sont présentées pour permettre leur comparaison et leur sélection en fonction des exigences propres à chaque projet.

0.1 Portée et limites





Le référentiel couvre les dimensions conceptuelles, ludiques, artistiques, techniques, économiques, opérationnelles et réglementaires d'un jeu vidéo.



Il couvre les jeux solo et multijoueurs, les expériences connectées et hors ligne, les jeux finis et les jeux exploités sur la durée.



Il couvre les productions 2D, 2.5D, 3D, audio-interactives, textuelles, procédurales, immersives et hybrides.



Il recense des familles de possibilités. Il ne prétend pas que chaque jeu doit utiliser chacune d'elles ni que la liste de genres ou de styles constitue une classification officielle universelle.



Les exemples de produits et de technologies illustrent des familles. Leur présence ne constitue pas une recommandation automatique.



Les versions, fonctionnalités, licences, prix, conditions d'utilisation, compatibilités et politiques des plateformes peuvent changer. Ces informations doivent être revérifiées à la date de chaque projet.



Une fonction décrite par un moteur n'est pas nécessairement disponible sur toutes ses plateformes cibles, dans toutes ses versions ou avec toutes ses configurations.

0.2 Niveaux de fiabilité employés







Marque



Signification





Norme / spécification



Document publié par un organisme de normalisation ou un registre officiel. Il décrit un format, une API ou des exigences normatives.





Documentation éditeur



Documentation primaire du fournisseur d'un moteur, d'un outil ou d'une plateforme. Elle décrit le fonctionnement de son propre produit.





Référence institutionnelle



Texte juridique, organisme officiel, autorité de contrôle ou organisme de classification.





Référence de pratique



Guide professionnel ou collectif reconnu. Il fournit des recommandations ou des pratiques, mais ne doit pas être confondu avec une norme obligatoire.





Taxonomie du présent référentiel



Organisation descriptive de concepts et d'options afin de faciliter la comparaison. Elle n'est pas présentée comme une norme officielle.

0.3 Règles de lecture





Domaine : grande famille de connaissances.



Module : sous-ensemble cohérent d'un domaine.



Variante : forme ou approche possible à l'intérieur d'un module.



Paramètre : propriété qui peut être définie, mesurée ou ajustée.



Dépendance : autre domaine susceptible d'avoir une influence ou d'être influencé.



Technologie : moteur, framework, bibliothèque, API, outil, format, service ou plateforme concret.



Exigence : besoin formulé de manière vérifiable dans le cahier des charges.

Les termes anglais courants du secteur sont conservés entre parenthèses lorsqu'ils facilitent les recherches documentaires : core loop, game feel, level design, rendering, rollback netcode, asset pipeline, etc.

0.4 Structure commune d'une fiche de module

Chaque module peut être documenté selon cette grille commune :





Définition et périmètre : rôle du domaine et limites de ce qui y appartient.



Sous-domaines : sujets couverts.



Possibilités et variantes : approches, modèles et familles de solutions.



Paramètres descriptifs : variables qui caractérisent une solution.



Avantages et contraintes : bénéfices recherchés, limites et coûts de complexité.



Dépendances : domaines associés et interactions.



Conséquences pour le jeu : effets sur l'expérience, le contenu ou les règles.



Conséquences techniques : effets sur les outils, le runtime, les données, le réseau ou les performances.



Technologies associées : solutions documentées, sans présumer qu'elles conviennent à tous les projets.



Éléments à spécifier : décisions qui devront apparaître dans le dossier du projet.



Références : documentation primaire ou référence fiable permettant de vérifier les faits.

0.5 Table des matières





Partie I — Fondations et conception





01 — Fondations du projet



02 — Genres, sous-genres et formats de jeu



03 — Game Design et systèmes de règles



04 — Gameplay, commandes et interactions



05 — Progression, difficulté et rétention



06 — Monde, niveaux et génération de contenu



07 — Narration, personnages et dialogues



08 — Intelligence artificielle vidéoludique



Partie II — Création artistique et expérience





09 — Direction artistique



10 — Graphismes, rendu et représentation



11 — Animation et mouvement



12 — Caméra et espace de jeu



13 — Effets visuels et simulations visuelles



14 — Audio et conception sonore



15 — UX, interface et accessibilité



Partie III — Technologies et architecture





16 — Moteurs, frameworks et technologies



17 — Architecture logicielle et données de jeu



18 — Physique, collisions et simulation



19 — Assets, formats et pipeline de production



20 — Plateformes et environnements d'exécution



Partie IV — Services, qualité et cycle de vie





21 — Multijoueur, réseau et services en ligne



22 — Économie, achats et modèles de distribution



23 — Données, sécurité, conformité et propriété intellectuelle



24 — Production, tests, publication et maintenance



Partie V — Catalogues transversaux



Partie VI — Éléments du cahier des charges



Glossaire



Références documentaires



PARTIE I — FONDATIONS ET CONCEPTION

01 — Fondations du projet

01.1 Identité du jeu

Informations descriptives :





Titre de travail, titre définitif, sous-titre et identité de marque.



Résumé court, présentation détaillée et proposition de valeur ludique.



Concept central (high concept) et éléments distinctifs.



Univers, tonalité, atmosphère et promesse faite au joueur.



Objectifs du projet et résultats attendus.



Références d'inspiration, comparables et éléments de différenciation.



Éléments volontairement exclus du périmètre.

01.2 Public et contexte d'utilisation





Public visé : âge, expérience de jeu, habitudes, attentes et accessibilité recherchée.



Public principal, public secondaire et éventuelles communautés spécialisées.



Contexte : sessions courtes, longues sessions, jeu occasionnel, pratique régulière, expérience sociale, expérience compétitive.



Durée typique d'une session et durée globale visée.



Langues, localisation, régions de distribution et contraintes culturelles.



Conditions matérielles : espace disponible, connexion, périphériques et puissance des appareils.



Besoins d'accessibilité connus ou anticipés.

01.3 Périmètre produit





Jeu autonome, épisode, extension, contenu additionnel, jeu-service ou expérience promotionnelle.



Produit fini, accès anticipé, bêta, démonstration, prototype ou vertical slice.



Mode hors ligne, mode connecté ou combinaison des deux.



Jeu solo, local, coopératif, compétitif, asynchrone ou massivement multijoueur.



Contenu prévu au lancement et contenu susceptible d'être ajouté ensuite.



Dépendances à des services, comptes, boutiques, plateformes ou contenus tiers.

01.4 Objectifs et contraintes





Objectifs de qualité, d'expérience, de diffusion et de viabilité.



Budget de production, coûts d'exploitation et coûts de licences.



Délais, ressources humaines, compétences et outils disponibles.



Contraintes de plateforme, de certification, de publication ou de distribution.



Contraintes de taille du téléchargement, mémoire, stockage, réseau et performances.



Contraintes de propriété intellectuelle et de droits d'utilisation.



Risques techniques, artistiques, économiques, juridiques et éditoriaux.

01.5 Modèle de distribution et de relation au joueur





Distribution payante, gratuite, financée par publicité, abonnement, accès par plateforme ou distribution institutionnelle.



Produit vendu une fois, contenu additionnel, mises à jour payantes ou modèle hybride.



Relation directe avec les joueurs ou via une plateforme de distribution.



Présence éventuelle de comptes, profils, sauvegardes distantes, communautés ou outils de support.

01.6 Éléments à spécifier





Vision et description du jeu.



Public et plateformes visés.



Périmètre du produit et des modes de jeu.



Objectifs mesurables et contraintes connues.



Hypothèses, risques et décisions encore ouvertes.

02 — Genres, sous-genres et formats de jeu

La classification ci-dessous est une taxonomie pratique. Les genres se chevauchent fréquemment : un titre peut appartenir à plusieurs familles et combiner plusieurs systèmes. Aucun genre ne détermine à lui seul une mécanique obligatoire.

02.1 Action





Action en temps réel.



Combat rapproché (beat 'em up, hack and slash).



Jeu de tir : FPS, TPS, tir à la première ou troisième personne, twin-stick shooter, shoot 'em up, bullet hell.



Jeu de plateforme : plateforme de précision, plateforme à défilement, plateforme 3D, metroidvania.



Jeu d'infiltration.



Action-aventure.



Combat d'arène, jeu de combat (fighting game), duel.



Action roguelite ou roguelike.

02.2 Aventure et exploration





Aventure narrative.



Exploration libre.



Aventure graphique (point-and-click).



Enquête et investigation.



Mystère et résolution d'énigmes.



Exploration environnementale.



Aventure à embranchements.



Jeu d'aventure et de survie.

02.3 Jeu de rôle (RPG)





RPG d'action.



RPG au tour par tour.



RPG tactique.



RPG occidental ou japonais (étiquettes culturelles d'usage, non définitions techniques strictes).



Dungeon crawler.



CRPG.



Action-RPG.



MMORPG.



RPG narratif.



RPG à classes, sans classes ou à progression libre.

02.4 Stratégie et tactique





Stratégie au tour par tour.



Stratégie en temps réel (RTS).



Stratégie en temps réel avec pause.



Grande stratégie.



Tactique au tour par tour.



Tactique en temps réel.



Tower defense.



Auto-battler.



Jeu de guerre et simulation tactique.



Construction et gestion stratégique.

02.5 Simulation et gestion





Simulation de vie.



Simulation de véhicule, vol, conduite ou navigation.



Simulation sportive.



Simulation professionnelle ou technique.



Gestion d'entreprise, de ville, de colonie ou d'établissement.



Gestion de ressources et production.



Simulation agricole, économique ou logistique.



Jeu de construction et d'automatisation.



Simulation systémique ou bac à sable.

02.6 Puzzle, réflexion et logique





Puzzle spatial.



Puzzle logique ou mathématique.



Puzzle physique.



Jeu de mots, de lettres ou de langage.



Énigmes narratives.



Puzzle de combinaison, correspondance ou assemblage.



Puzzle de programmation ou d'automatisation.



Jeu de réflexion en temps réel ou au tour par tour.

02.7 Sport, course et adresse





Sport individuel ou collectif.



Jeu de course automobile, moto, aérien, nautique ou fantastique.



Simulation sportive ou arcade sportive.



Gestion d'équipe ou de carrière sportive.



Jeu de rythme et de coordination.



Jeu d'adresse, précision ou timing.

02.8 Autres familles





Party game et mini-jeux.



Jeu de société adapté au numérique.



Jeu de cartes, deck-builder et construction de paquet.



Jeu de plateau tactique.



Roguelike / roguelite.



Survival et crafting.



Sandbox et construction libre.



Idle, incremental et clicker.



Jeu musical et rythmique.



Jeu éducatif et serious game.



Jeu expérimental, artistique ou abstrait.



Jeu narratif, visual novel et fiction interactive.



Jeu social, monde virtuel et expérience communautaire.



Jeu asymétrique, party compétitif et jeu de déduction sociale.

02.9 Modes et structures de session





Solo, coopération, compétition, équipes ou chacun pour soi.



Local partagé, écran partagé, réseau local, en ligne ou asynchrone.



Campagne, scénarios, missions, matchs, parties générées ou sessions ouvertes.



Parties courtes, longues, persistantes ou continues.



Matchmaking classé ou non classé, parties privées et parties publiques.



Modes personnalisés, éditeur de règles et contenu généré par les utilisateurs.

02.10 Éléments à spécifier

Genre principal et genres secondaires, modes disponibles, structure des sessions, expérience centrale, caractéristiques hybrides et étiquettes de positionnement.

03 — Game Design et systèmes de règles

03.1 Cadres de conception





MDA (Mechanics, Dynamics, Aesthetics) : cadre d'analyse qui met en relation les mécaniques conçues, les dynamiques qui émergent de leur usage et les expériences esthétiques recherchées. Il s'agit d'un cadre d'analyse, pas d'une recette universelle. [R01]



Boucle de gameplay principale (core loop) et boucles secondaires.



Boucles de progression, de récompense, de risque et de décision.



Systèmes émergents et interactions systémiques.



Conception centrée sur les actions du joueur (player verbs).



Prototypage des règles et expérimentation de l'expérience.

03.2 Règles et états du jeu





États globaux : menu, partie, pause, victoire, défaite, transition, chargement.



États locaux : personnage, objet, mission, niveau, inventaire, événement.



Transitions, conditions, événements et priorités.



Règles déterministes ou comportant de l'aléatoire.



Règles simultanées ou séquentielles.



Tour par tour, temps réel, temps réel avec pause, résolution par phases.



Conditions de victoire, d'échec, d'égalité, d'abandon et de fin de session.



Gestion des situations limites et des conflits de règles.

03.3 Ressources et contraintes ludiques





Ressources consommables, renouvelables, limitées ou illimitées.



Ressources communes ou individuelles.



Coûts d'action, temps d'attente, énergie, munitions, santé, monnaie, matériaux.



Limites de capacité, de portée, de temps, d'espace ou d'information.



Risque, perte, récupération et conversion de ressources.



Règles de rareté, disponibilité et distribution.

03.4 Décisions et stratégie du joueur





Choix immédiats ou à long terme.



Décisions à information complète ou partielle.



Choix réversibles ou irréversibles.



Arbitrages entre temps, risque, ressources et récompense.



Spécialisation, polyvalence, synergies et contre-mécaniques.



Compétence d'exécution, planification, observation, mémoire et coopération.

03.5 Feedback et lisibilité des règles





Feedback visuel, sonore, haptique et textuel.



Indication de cible, portée, danger, état, ressource et résultat.



Prévisualisation d'une action ou d'une conséquence.



Feedback immédiat, différé, cumulatif ou contextuel.



Signaux positifs, négatifs, neutres et avertissements.



Tutoriel explicite, découverte guidée ou apprentissage par expérimentation.

03.6 Équilibrage et systèmes émergents





Équilibrage des personnages, objets, capacités, unités et stratégies.



Économie des ressources et rapports de coûts.



Synergies, combinaisons et interactions entre systèmes.



Risque de stratégie dominante, de boucle infinie ou d'exploitation de faille.



Variabilité des résultats et facteurs aléatoires.



Analyse des données de partie et retours des joueurs.

03.7 Éléments à spécifier

Règles complètes, états, transitions, objectifs, boucles, ressources, conditions de fin, feedback attendu et critères d'équilibrage.

04 — Gameplay, commandes et interactions

04.1 Contrôles et systèmes d'entrée





Clavier et souris.



Manette de jeu et périphériques spécialisés.



Écran tactile : tap, double tap, glissement, pincement, gestes multipoints, commandes virtuelles.



Écran tactile avec retour haptique.



Contrôleurs de mouvement et périphériques spatiaux.



Commande vocale ou reconnaissance de gestes lorsqu'elles sont pertinentes et disponibles.



Périphériques adaptatifs et commandes alternatives.



Contrôles hybrides et changement automatique de périphérique.

Paramètres : attribution des actions, remappage, sensibilité, zones mortes, accélération, inversion des axes, maintien ou bascule, répétition, assistance à la visée, vibrations, mode gaucher.

04.2 Déplacement et locomotion





Déplacement au sol, aérien, aquatique, sous-terrain ou spatial.



Marche, course, sprint, accroupissement, saut, double saut, escalade, glissade, roulade, nage, vol, chute, téléportation.



Déplacement direct, inertiel, basé sur une physique ou contrôlé par animation.



Déplacement en grille, par case, en espace continu ou sur rails.



Navigation libre, navigation contrainte ou déplacement automatique.



Accélération, freinage, friction, gravité, vitesse maximale, contrôle en l'air, pente et adhérence.

04.3 Interaction avec le monde





Interaction contextuelle ou par commande explicite.



Activation, collecte, inspection, déplacement, utilisation, manipulation et combinaison d'objets.



Interactions physiques, interfaces dédiées, dialogues et choix.



Interaction à distance, au contact ou par zone.



Objets permanents, temporaires, destructibles, persistants ou réinitialisés.



Interaction environnementale et objets à états multiples.

04.4 Combat et confrontation





Combat rapproché, à distance, projectile, zone ou indirect.



Combat en temps réel, au tour par tour, simultané ou tactique.



Santé, dégâts, armure, résistance, esquive, parade, blocage et invulnérabilité temporaire.



Ciblage manuel, verrouillage, visée assistée ou ciblage automatique.



Armes, munitions, rechargement, compétences, effets de statut et altérations.



Combat individuel, groupe, équipe, boss, vagues ou arènes.



Règles de PvE, PvP et PvPvE.

04.5 Systèmes de jeu fréquents





Inventaire et équipement.



Crafting, fabrication et assemblage.



Construction, placement, terraformation et décoration.



Collecte, récolte, extraction et production.



Dialogue, commerce, négociation et réputation.



Furtivité, détection et discrétion.



Exploration, cartographie et découverte.



Compétences, talents, capacités et arbres de spécialisation.



Gestion de groupe, ordres et rôles.



Contrôle d'unités, de véhicules ou de machines.



Puzzle, manipulation logique et résolution de problèmes.



Système de cartes, deck-building, tirage et combinaisons.



Élevage, relations, social et simulation de comportements.

04.6 Game feel et réponse des commandes





Délai entre entrée et réponse.



Courbes d'accélération, inertie et amortissement.



Animation anticipée, suivi et récupération.



Caméra, vibration, son et effets de confirmation.



Tolérance de fenêtre temporelle et assistance de précision.



Priorités entre actions et gestion des commandes simultanées.

04.7 Éléments à spécifier

Actions disponibles, appareils de commande, mapping, règles d'interaction, paramètres de mouvement, règles de combat éventuelles, feedback, remappage et comportements alternatifs.

05 — Progression, difficulté et rétention

05.1 Structures de progression





Progression linéaire, ramifiée, non linéaire, ouverte ou émergente.



Progression par niveaux, expérience, compétences, équipement, collection ou réputation.



Progression par scénario, missions, chapitres, zones ou objectifs.



Progression horizontale (nouvelles possibilités) ou verticale (augmentation de puissance).



Progression individuelle, collective, de compte ou de saison.



Déblocage permanent, temporaire, conditionnel ou aléatoire.

05.2 Récompenses





Récompenses fonctionnelles, cosmétiques, narratives, sociales ou symboliques.



Récompense immédiate, différée, cumulative ou conditionnelle.



Récompense garantie ou aléatoire.



Récompense de performance, exploration, coopération, persévérance ou découverte.



Objets, ressources, monnaie, trophées, titres, accès et contenu.

05.3 Difficulté et accessibilité de la difficulté





Difficulté sélectionnée avant la partie ou modifiable pendant celle-ci.



Difficulté fixe, adaptative ou personnalisable.



Paramètres indépendants : dégâts, santé, vitesse, agressivité, délais, ressources, assistance, fenêtres de réaction.



Mode d'assistance, mode histoire, mode défi, mode entraînement.



Indices, aides contextuelles, ralentissement, retour en arrière et checkpoints.



Pénalités d'échec, perte de ressources, réapparition, reprise de niveau ou fin de partie.

05.4 Rejouabilité





Parcours alternatifs, choix narratifs, défis, modes supplémentaires.



Génération procédurale et variation des configurations.



Classements, défis communautaires et objectifs renouvelés.



Succès, collections, secrets et contenus à découvrir.



Modes New Game+, parties personnalisées et modificateurs.

05.5 Progression persistante et événements





Sauvegarde locale ou distante.



Progression liée à un appareil, un profil, un compte ou une plateforme.



Défis quotidiens/hebdomadaires, événements saisonniers et contenu limité dans le temps.



Synchronisation multi-appareils et conflits de sauvegarde.



Systèmes de retour après absence et notifications, si le projet en prévoit.

05.6 Éléments à spécifier

Courbes de progression, économie de récompenses, critères de difficulté, conditions de déblocage, persistance et éventuels événements temporels.

06 — Monde, niveaux et génération de contenu

06.1 Structure spatiale





Niveau fermé, arène, couloir, hub, monde ouvert, monde semi-ouvert, monde connecté ou espace modulaire.



Monde continu ou découpé en scènes, niveaux, zones, cellules ou instances.



Carte du monde, mini-carte, carte tactique et navigation contextuelle.



Espaces intérieurs, extérieurs, verticaux, souterrains ou multidimensionnels.



Dimensions 2D, 2.5D et 3D.

06.2 Level Design





Parcours dirigé, exploration libre, arène, labyrinthe, puzzle room, parcours de plateforme, circuit ou terrain tactique.



Rythme, alternance de tension et de repos, points de décision et points de repère.



Lisibilité des objectifs, visibilité des menaces et orientation.



Difficulté spatiale, maîtrise des distances et lignes de vue.



Couverture, chemins alternatifs, raccourcis et zones secrètes.



Checkpoints, points de réapparition et transitions.



Composition modulaire et réutilisation des espaces.

06.3 Environnements et phénomènes





Biomes, météo, cycle jour/nuit, saisons et conditions locales.



Environnement statique ou dynamique.



Objets destructibles, portes, mécanismes et éléments interactifs.



Événements déclenchés par le temps, le joueur, une condition ou un événement externe.



Densité, visibilité, acoustique et lisibilité du terrain.

06.4 Génération de contenu





Contenu conçu manuellement.



Assemblage modulaire.



Génération procédurale déterministe ou aléatoire.



Génération par règles, contraintes, graphes ou données.



Génération de cartes, niveaux, quêtes, objets, ennemis, dialogues ou rencontres.



Seeds, reproductibilité et sauvegarde de la graine.



Validation des contenus générés, accessibilité et contrôle des configurations impossibles.

06.5 Éléments à spécifier

Structure du monde, topologie, dimensions, quantité de niveaux, types d'environnements, densité de contenu, règles de génération et contraintes de navigation.

07 — Narration, personnages et dialogues

07.1 Formes de narration





Narration linéaire, ramifiée, émergente, environnementale ou fragmentée.



Récit en temps réel, séquences cinématiques, textes, journaux, objets, dialogues ou événements.



Narration explicite ou indirecte.



Récit principal, récits secondaires, histoires de personnages et contenus optionnels.



Narration intégrée au gameplay ou séparée de celui-ci.

07.2 Univers et cohérence narrative





Contexte historique, géographique, culturel et technologique.



Lois physiques ou surnaturelles propres à l'univers.



Chronologie, événements antérieurs et continuité.



Factions, institutions, sociétés, espèces, langues et cultures fictives.



Ton, thèmes, motifs et limites éditoriales.

07.3 Personnages





Protagoniste, antagoniste, personnages secondaires, alliés, compagnons, figurants et personnages non joueurs.



Motivation, objectif, personnalité, rôle fonctionnel et évolution.



Relations, réputation, affinité et mémoire des événements.



Personnages contrôlables, non contrôlables ou alternés.

07.4 Dialogues et choix





Dialogues écrits, voix, sous-titres et textes dynamiques.



Choix à conséquence immédiate, différée ou cosmétique.



Arbres de dialogue, graphes de conversation, conditions et variables.



Dialogues contextuels, répétables, interrompables ou temporisés.



Localisation, gestion des variables et contraintes de longueur.

07.5 Cinématiques et mise en scène





Séquences temps réel, vidéo pré-rendue, caméra dirigée ou événements scriptés.



Synchronisation voix, animation, sous-titres, musique et actions de jeu.



Passage du contrôle au joueur et retour au gameplay.



Possibilité de passer, rejouer ou consulter les séquences.

07.6 Éléments à spécifier

Univers, personnages, structure narrative, variables, conséquences des choix, langues, doublages, sous-titres et intégration du récit dans les mécaniques.

08 — Intelligence artificielle vidéoludique

Ce domaine concerne les agents contrôlés par le jeu : ennemis, alliés, personnages non joueurs, créatures, unités, adversaires et systèmes adaptatifs. Il est distinct de l'IA utilisée comme outil de production.

08.1 Modèles de décision





Machine à états finis (FSM) et machines à états hiérarchiques.



Arbres de comportement (Behavior Trees).



Systèmes à règles et systèmes de scores/utilité (Utility AI).



Planification orientée objectifs (GOAP) et planification hiérarchique.



Systèmes de tâches, scripts événementiels et comportements dirigés par scénarios.



Systèmes hybrides combinant plusieurs modèles.

Les Behavior Trees et les Blackboards sont documentés comme outils de conception de comportements dans Unreal Engine. L'Environment Query System (EQS) permet notamment de générer et d'évaluer des emplacements ou acteurs selon des tests et contextes. Ces références décrivent l'implémentation d'Unreal, pas une obligation de conception pour tous les moteurs. [R02][R03]

08.2 Perception et représentation du monde





Vision, champ de vision et ligne de vue.



Audition, bruit et propagation sonore modélisée.



Détection de proximité, contact, dégâts ou événement.



Mémoire courte, mémoire persistante ou connaissance partagée.



Incertitude, suspicion, recherche et perte de cible.



État local, état partagé et information connue du joueur.

08.3 Navigation et déplacement des agents





Navigation sur grille, graphe ou maillage de navigation (navmesh).



Recherche de chemin et recalcul de chemin.



Coûts de terrain, zones interdites et liens spéciaux.



Évitement d'obstacles et de foule.



Déplacement en formation, poursuite, escorte, patrouille et interception.



Navigation 2D, 3D, aérienne, aquatique ou dans un environnement dynamique.

Unreal documente la génération de maillages de navigation, le calcul de chemin et des méthodes d'évitement d'agents ; Godot documente des serveurs de navigation 2D et 3D. Les détails d'implémentation et leurs limites dépendent du moteur. [R04][R05]

08.4 Comportements de personnages





Patrouille, veille, fuite, poursuite, défense, attaque, coopération et assistance.



Recherche, enquête, alerte, appel de renfort et retour à un état normal.



Comportements sociaux, routines, relations et réactions contextuelles.



Comportement déterministe, probabiliste ou influencé par des paramètres.



Difficulté artificielle, adversaires adaptatifs et ajustement de comportement.

08.5 IA avancée et systèmes apprenants





Apprentissage automatique utilisé hors ligne pour la création ou l'analyse de comportements.



Modèles utilisés à l'exécution, sous réserve de coûts, latence, confidentialité et contrôle.



Génération de contenu ou de dialogue par modèle génératif.



Agents à comportement contraint par règles, outils, données et limites de sécurité.



Entraînement, validation, reproductibilité, explicabilité et contrôle des sorties.

Ces possibilités ne garantissent pas à elles seules un comportement fiable ou amusant. Les performances, coûts, droits des données, modération, latence et fonctionnement hors ligne doivent être traités comme des exigences distinctes.

08.6 Éléments à spécifier

Types d'agents, modèles de décision, perception, mémoire, navigation, niveau d'autonomie, adaptation, déterminisme, fréquence de calcul et limites de performance.



PARTIE II — CRÉATION ARTISTIQUE ET EXPÉRIENCE

09 — Direction artistique

09.1 Identité visuelle





Intention artistique, références et cohérence de l'univers.



Silhouettes, formes, palettes, contrastes, composition et hiérarchie visuelle.



Réalisme, stylisation, abstraction ou représentation symbolique.



Lisibilité du personnage, des objets interactifs, des menaces et des objectifs.



Densité visuelle et équilibre entre décor, action et interface.

09.2 Familles de styles visuels





Pixel art : résolution artistique contrainte, sprites et palettes contrôlées.



Illustration dessinée à la main.



Peinture numérique et rendu pictural.



Vectoriel et formes géométriques.



Low poly et géométrie stylisée.



Voxel et volumes réguliers.



3D stylisée, semi-réaliste ou réaliste.



Cell shading / toon shading.



PBR stylisé ou réaliste.



Rendu monochrome, duotone, rétro, CRT ou limité par palette.



Collage, papier découpé, stop-motion simulé et styles mixtes.



Abstraction, minimalisme et formes typographiques.

09.3 Cohérence des assets





Règles de proportions, échelle et unités.



Palette de matériaux et de couleurs.



Style de contour, ombre, lumière et texture.



Niveau de détail, densité de géométrie et résolution des textures.



Direction des silhouettes, langage des formes et conventions visuelles.



Règles de nommage et classification des ressources.

09.4 Éléments à spécifier

Références artistiques, style principal et variations, palette, proportion, niveau de détail, contraintes de lisibilité et règles de cohérence.

10 — Graphismes, rendu et représentation

10.1 Dimensions et techniques de représentation





2D par sprites, tuiles, formes vectorielles, dessin ou composition de couches.



2.5D : gameplay 2D dans un espace 3D, décors en profondeur ou représentation hybride.



3D temps réel.



Rendu pré-calculé, séquences vidéo ou éléments pré-rendus.



Rendu hybride combinant géométrie, images, sprites et effets.

10.2 Rendu 2D





Sprites, atlas, tilesets, tilemaps et couches parallaxes.



Sprite sheet, animation par images et animation par squelette 2D.



Résolution interne, mise à l'échelle, filtrage et pixel-perfect.



Masques, shaders 2D, normales 2D et éclairage 2D.



Interface dessinée dans le moteur ou interface native superposée.

10.3 Rendu 3D





Rasterisation temps réel.



Rendu différé (deferred rendering) ou direct (forward rendering).



Éclairage précalculé, dynamique ou hybride.



Ombres temps réel, ombres précalculées et techniques mixtes.



Réflexions écran, probes, cubemaps et techniques de ray tracing.



Illumination globale dynamique ou précalculée.



Matériaux physiques (PBR), matériaux stylisés et shaders personnalisés.



Volumétrie, brouillard, atmosphère, eau, végétation et terrain.

10.4 Techniques de qualité et d'optimisation visuelle





LOD (niveaux de détail), culling et instancing.



Occlusion culling, frustum culling et streaming de ressources.



Compression de textures, mipmaps et formats adaptés au GPU.



Résolution dynamique, upscaling et anti-aliasing.



Gestion du nombre de lumières, ombres, matériaux, draw calls et géométrie.



Effets de post-traitement : exposition, profondeur de champ, motion blur, bloom, vignettage, color grading et aberration chromatique.



Profils graphiques et réglages de qualité.

10.5 Technologies et références concrètes





Unreal Engine documente Nanite comme système de géométrie virtualisée et Lumen comme système d'illumination globale et de réflexions dynamiques. Leurs capacités et compatibilités doivent être lues dans les sections « fonctionnalités prises en charge » et « plateformes » de la version retenue. [R06][R07]



Unity propose plusieurs pipelines de rendu ; le choix et l'état de chaque pipeline doivent être vérifiés dans la documentation de la version de Unity visée.



Godot documente des moteurs de rendu 2D et 3D ; la performance et les fonctions disponibles varient selon le moteur de rendu choisi et la plateforme cible. [R08]



Pour les applications web, WebGL et WebGPU sont des APIs graphiques distinctes ; WebGPU dispose d'une spécification W3C publiée en Candidate Recommendation Draft en septembre 2026. Ce statut documentaire ne signifie pas une prise en charge identique dans tous les navigateurs. [R09]

10.6 Éléments à spécifier

Dimension, technique de rendu, style des matériaux, éclairage, ombres, effets, niveau de détail, résolution, profils de qualité et budgets graphiques.

11 — Animation et mouvement

11.1 Types d'animation





Animation 2D par images (frame-by-frame).



Animation 2D par squelette et déformation de maillage.



Animation 3D par squelette (skeletal animation).



Animation par keyframes.



Animation procédurale.



Animation pilotée par la physique.



Animation faciale et synchronisation labiale.



Capture de mouvement et capture de performance.



Animation de caméra et animation d'interface.

11.2 Organisation de l'animation





Clips, états, transitions et blend spaces.



Machine à états d'animation.



Blend trees, couches et masques.



Retargeting entre squelettes.



IK (cinématique inverse) et contraintes.



Animation additive, root motion et animation in-place.



Synchronisation avec gameplay, événements, audio et réseau.

Godot documente notamment AnimationPlayer, les pistes d'animation, les squelettes 2D et AnimationTree. Unreal documente les systèmes d'animation et de contrôle de rig dans sa documentation d'animation. [R10]

11.3 Paramètres





Durée, fréquence, interpolation, courbe, accélération et amortissement.



Priorité, interruption, transition et blend.



Variations aléatoires contrôlées.



Répétition, boucle, inversion et synchronisation.



Coût CPU/GPU, mémoire et nombre d'instances.

11.4 Éléments à spécifier

Types d'animation, personnages concernés, squelette, bibliothèques de mouvements, transitions, retargeting, événements synchronisés et contraintes de performance.

12 — Caméra et espace de jeu

12.1 Familles de caméra





Vue latérale / side-scroller.



Vue de dessus / top-down.



Vue isométrique.



Vue à la première personne (FPV/FPS).



Vue à la troisième personne (TPS).



Vue épaule, vue libre et vue orbitale.



Caméra fixe, caméra suiveuse, caméra rail ou caméra cinématique.



Caméra tactique, stratégique ou carte.



Caméra de simulation et caméra cockpit.



Caméra stéréoscopique ou spatiale en VR/XR.

12.2 Paramètres caméra





Champ de vision (FOV), focale, zoom et distance.



Angle, inclinaison, rotation, hauteur et décalage.



Suivi, retard, amortissement, anticipation et recadrage.



Limites spatiales, collision caméra et occlusion.



Zones mortes, look-ahead, shake, tremblement et effets contextuels.



Sensibilité, inversion et commandes du joueur.

12.3 Espace et orientation





Coordonnées cartésiennes, grille, axes, échelle et unités.



Perspective, orthographique ou projection spécifique.



Orientation fixe ou libre.



Caméra liée au personnage, à la cible, à la scène ou au joueur.



Gestion des changements de perspective et transitions.

12.4 Éléments à spécifier

Type de vue, projection, comportement, contrôle joueur, paramètres, règles d'occlusion et interactions avec mouvements, niveaux et accessibilité.

13 — Effets visuels et simulations visuelles

13.1 Effets de particules





Particules CPU ou GPU.



Émetteurs ponctuels, cônes, volumes, surfaces et trajectoires.



Effets continus, ponctuels, en boucle ou déclenchés par événement.



Feu, fumée, poussière, pluie, neige, étincelles, magie, impacts et explosions.

Unreal présente Niagara comme son système principal de création d'effets visuels dans la documentation UE5. [R11]

13.2 Effets de post-traitement et atmosphère





Bloom, color grading, flou, profondeur de champ, distorsion, vignettage.



Brouillard, nuages, rayons lumineux, lumière volumétrique et atmosphère.



Effets de caméra, vignettage de dégâts et changements d'état visuels.



Effets de transition, téléportation et distorsion spatiale.

13.3 Simulation visuelle





Eau et surfaces liquides.



Végétation, tissus, cheveux, fumée et fluides.



Destruction, fractures et débris.



Déformation de terrain et objets dynamiques.



Effets météorologiques et environnementaux.

13.4 Éléments à spécifier

Inventaire d'effets, conditions de déclenchement, style, durée, niveau de qualité, paramètres visuels, budget de particules et solutions de réduction de charge.

14 — Audio et conception sonore

14.1 Familles sonores





Musique : thèmes, ambiance, combat, exploration, menus, transitions et musique adaptative.



Effets sonores : actions, impacts, interfaces, environnement, objets, véhicules et créatures.



Voix : doublage, dialogues, narration, annonces et communications en ligne.



Ambiances : intérieur, extérieur, météo, espace, foule et environnement.



Audio d'interface et audio d'accessibilité.

14.2 Organisation de l'audio





Événements audio (events).



Bus, groupes, sous-mixages et snapshots.



États et interrupteurs (states / switches).



Paramètres de contrôle en temps réel (RTPC ou paramètres équivalents selon l'outil).



Variations, randomisation et séquences de sons.



Priorité, virtualisation, nombre maximal de voix et gestion de mémoire.



Streaming ou chargement des banques audio.

FMOD documente les paramètres comme des variables pouvant piloter des événements, snapshots et éléments du mixer. Godot documente les bus audio, leur routage et l'application d'effets. [R12][R13]

14.3 Spatialisation et acoustique





Audio mono, stéréo, multicanal et binaural.



Positionnement 2D/3D, panoramique, atténuation et distance.



Occlusion, obstruction, réverbération et propagation modélisée.



Audio lié à la caméra, au personnage, à l'espace ou à une interface.



Audio spatial pour casques et expériences immersives.

14.4 Musique dynamique





Boucles, couches, transitions synchronisées et segments adaptatifs.



Musique pilotée par intensité, danger, lieu, combat ou progression.



Transitions immédiates, quantifiées ou conditionnelles.

14.5 Outils et formats





Middleware audio de jeu : FMOD Studio et Audiokinetic Wwise.



Systèmes audio intégrés aux moteurs : par exemple le système audio de Unity, Unreal ou Godot.



API audio web : Web Audio API, qui fournit un système de routage et de traitement audio pour le Web. [R14]



Formats et codecs à traiter selon le besoin : WAV, AIFF, FLAC, Ogg Vorbis, Opus, MP3, AAC et conteneurs associés. Vérifier la compatibilité réelle du runtime, les licences éventuelles des codecs et les capacités des plateformes.

14.6 Éléments à spécifier

Catégories audio, spatialisation, musique dynamique, voix, langues, contrôle du volume, sous-titres associés, streaming, mémoire et contraintes de latence.

15 — UX, interface et accessibilité

15.1 Architecture de l'interface





Écran titre, menus, pause, options, sélection de mode et sélection de niveau.



HUD et éléments contextuels.



Inventaire, équipement, carte, journal, arbre de compétences et codex.



Interface de dialogue, boutique, classement et résultats.



Tutoriels, aides, notifications et confirmations.



Interface en jeu, overlay plateforme ou interface web périphérique.

15.2 Navigation et interaction





Navigation clavier, souris, manette, tactile ou périphérique adaptatif.



Focus, sélection, navigation directionnelle et ordre de tabulation.



Navigation hiérarchique, onglets, panneaux, fenêtres et raccourcis.



Confirmation d'actions sensibles, annulation et retour.



États de chargement, absence de données, erreur, indisponibilité et succès.

15.3 Lisibilité et présentation





Taille, police, contraste, espacement et hiérarchie de l'information.



Sous-titres, légendes, transcriptions et indications directionnelles.



Icônes, codage couleur, symboles et motifs redondants.



Paramètres de HUD, taille d'interface et densité de l'information.



Réduction des animations, effets de mouvement et flashs.

15.4 Accessibilité du jeu





Remappage des commandes et alternatives à une entrée complexe.



Options de difficulté, vitesse de jeu, assistance et fenêtres temporelles.



Contraste, taille du texte et lisibilité.



Sous-titres, légendes et alternatives aux informations sonores.



Alternatives visuelles aux informations portées uniquement par la couleur.



Navigation intégrale de l'interface avec différentes méthodes d'entrée.



Réduction des effets lumineux, clignotements et mouvements susceptibles de gêner.



Paramètres de vibrations et de retour haptique.



Sauvegarde des préférences d'accessibilité.

Les Xbox Accessibility Guidelines sont un ensemble de bonnes pratiques pour améliorer l'expérience des joueurs ; Microsoft précise qu'elles ne sont pas, à elles seules, une liste de contrôle de conformité légale. Les Game Accessibility Guidelines classent leurs recommandations par niveaux Basic, Intermediate et Advanced. [R15][R16]

WCAG 2.2 concerne l'accessibilité du contenu Web. Elle peut être pertinente pour les pages web, portails, comptes, boutiques, interfaces HTML et éléments de service autour d'un jeu ; elle ne remplace pas une évaluation spécifique de l'accessibilité du gameplay. [R17]

15.5 Localisation





Traduction de l'interface, dialogues, sous-titres, voix, images et supports marketing.



Expansion de texte, formats de date, nombres, devises, unités et direction d'écriture.



Polices, glyphes, encodage, césure et contraintes d'affichage.



Voix originales, doublage localisé ou sous-titres uniquement.



Gestion des langues et changement en cours de session.

15.6 Éléments à spécifier

Plans d'interface, parcours, contrôles, tailles, contrastes, sous-titres, options d'accessibilité, langues et exigences de navigation.



PARTIE III — TECHNOLOGIES ET ARCHITECTURE

16 — Moteurs, frameworks et technologies

16.1 Distinction des catégories





Moteur de jeu : environnement intégré regroupant généralement plusieurs systèmes de création et d'exécution.



Framework : ensemble de bibliothèques et de conventions fournissant des composants à assembler ; il peut laisser à l'équipe davantage de responsabilités sur les outils et l'architecture.



Bibliothèque de rendu : composants orientés affichage graphique, sans fournir nécessairement tous les systèmes d'un moteur.



Middleware : solution spécialisée intégrée à un moteur ou à un runtime, par exemple audio, physique, réseau ou anti-triche.



API graphique : interface de bas niveau vers des fonctionnalités de rendu ou de calcul GPU.



Outil de création : logiciel de modélisation, animation, audio, texture, niveau ou production de contenu.

16.2 Moteurs généralistes documentés







Technologie



Catégorie / caractéristiques vérifiées



Points à vérifier pour un projet





Unreal Engine



Moteur de création 3D temps réel ; documentation de son Gameplay Framework, de ses systèmes d'IA, de Niagara, Nanite, Lumen et de son réseau multijoueur. [R02][R03][R06][R07][R11][R18]



Plateforme cible, budget graphique, workflow de contenu, exigences matérielles, version, licences et coûts applicables.





Unity



Moteur de création de jeux ; documentation de Netcode for GameObjects et Netcode for Entities, avec des modèles et usages différents. [R19]



Pipeline de rendu, packages, prise en charge de plateforme, dépendances, versions, conditions de licence et coûts.





Godot



Moteur libre et open source 2D/3D distribué sous licence MIT ; documentation de scènes, nœuds, scripts, physique, animation, audio, navigation et export. [R20][R21][R22][R23]



Rendu choisi, plateformes et formats d'export, limites spécifiques au Web, extensions et bibliothèques tierces.





Defold



Moteur 2D/3D avec éditeur, runtime, workflow de scripts Lua, outils de débogage et de profilage, selon son site officiel. [R24]



Besoins particuliers de rendu, plateformes, extensions natives, workflows de contenu et support.





GameMaker



Environnement de création de jeux avec IDE et langage GML ; son manuel officiel documente notamment sprites, tilesets, effets sonores, objets, séquences, pièces/niveaux et commandes. [R54]



Cibles de build, SDK requis, extensions, licences et fonctions propres à chaque plateforme.





Ren'Py



Moteur spécialisé dans les visual novels et récits interactifs intégrant textes, images et sons ; sa documentation officielle décrit aussi des usages de simulation et des cibles d'export. [R25]



Besoins de gameplay hors visual novel, export HTML5 indiqué comme bêta sur la page consultée, langues et intégrations.

16.3 Moteurs et frameworks orientés Web







Technologie



Catégorie / caractéristiques vérifiées



Points à vérifier





Phaser



Framework open source HTML5 pour jeux navigateur, avec rendu WebGL et Canvas, API JavaScript/TypeScript et systèmes de scènes, objets, physique, entrée et caméra documentés. [R26]



Version majeure, dépendances, mobile, intégration avec un framework d'interface et besoins 3D.





PixiJS



Bibliothèque/moteur de rendu 2D ; sa documentation de rendu décrit WebGL/WebGL2, WebGPU et Canvas 2D. La page consultée signale des différences de maturité entre backends. [R27]



Version, backend stable, compatibilité navigateur, couche gameplay à ajouter et stratégie de repli.





Babylon.js



Moteur 3D Web dont la page de spécifications liste WebGL, WebGPU, scènes, lumières, caméras, matériaux, animation, audio, physique et WebXR. [R28]



Compatibilité des fonctions, backend, extensions, performances mobiles et support WebXR.





PlayCanvas Engine



Moteur 3D Web open source ; la documentation officielle présente ses backends WebGPU et WebGL 2 et son usage dans les navigateurs desktop et mobiles. [R29]



Compatibilité des appareils, taille du runtime, intégration de contenu, fonctionnalités spécifiques et version.





Three.js



Bibliothèque JavaScript de rendu 3D ; sa documentation expose notamment un WebGLRenderer basé sur WebGL 2. Elle ne doit pas être assimilée automatiquement à un moteur complet de jeu. [R56]



Systèmes de gameplay, physique, éditeur, import/export, boucle de jeu, réseau et outils à sélectionner séparément.

16.4 Frameworks et moteurs orientés programmation







Technologie



Catégorie / caractéristiques vérifiées



Points à vérifier





MonoGame



Framework open source « bring your own tools » ; sa documentation précise qu'il fournit des briques pour construire les outils et le moteur du projet, et non un éditeur de scènes intégré comparable à Unity ou Unreal. [R30]



Architecture, outils, contenu, plateformes, bibliothèques et volume de développement à prendre en charge.





Bevy



Moteur de jeu open source écrit en Rust et centré sur Bevy ECS ; son site documente des systèmes de rendu 2D et 3D. [R55]



Maturité des modules, écosystème, compatibilité, stabilité API et compétences Rust.





LÖVE



Framework de développement de jeux en Lua ; le guide officiel de démarrage montre la structure minimale d'un projet utilisant main.lua et les fonctions de dessin. [R57]



Périmètre fonctionnel du framework, bibliothèques complémentaires, packaging et besoins 3D.





raylib



Bibliothèque de programmation de jeux et de multimédia ; son site officiel documente notamment des modules de graphisme, modèles, shaders, audio et entrée, ainsi que plusieurs plateformes cibles. [R58]



Architecture à construire, outils, support exact de la plateforme et bibliothèques complémentaires.

Les descriptions des trois dernières solutions sont des classifications de familles et non une évaluation comparative de performance ; les fonctions exactes doivent être vérifiées dans leur documentation officielle au moment de leur usage.

16.5 API et technologies graphiques







Technologie



Domaine





WebGL / WebGL 2



API de rendu graphique 3D depuis le navigateur ; compatibilité à contrôler par navigateur et appareil.





WebGPU



API Web exposant des opérations GPU de rendu et de calcul ; la spécification consultée était un Candidate Recommendation Draft W3C du 15 septembre 2026. [R09]





Vulkan



API graphique et de calcul GPU dont le registre Khronos publie la spécification courante et les extensions enregistrées. [R31]





OpenGL / OpenGL ES



Familles d'API graphiques définies par Khronos ; le registre publie les spécifications et références API, notamment OpenGL ES 3.2. [R32]





Direct3D 12



API graphique Microsoft destinée aux applications utilisant les GPU compatibles sous Windows. [R33]





Metal



API graphique et de calcul d'Apple pour ses plateformes ; Apple documente aussi les outils de profilage et de débogage associés. [R34]

16.6 Langages et environnements





C++, C#, Rust, Java, Kotlin, Swift, JavaScript, TypeScript, Lua, GDScript, Python et langages spécifiques aux moteurs.



Langages de shaders et environnements associés : HLSL, GLSL, WGSL et langages propres aux moteurs.



Scripts de build, automatisation, configuration et génération de contenu.



Outils de compilation, débogage, profilage et inspection.

Le choix dépend des moteurs et des API retenus ; la présence d'un langage dans une liste n'implique pas sa prise en charge par tous les environnements.

16.7 Critères de comparaison des technologies





Plateformes de développement et plateformes de distribution.



2D, 3D, XR, réseau et outils intégrés.



Langages et extensibilité.



Chaîne d'importation et création des assets.



Éditeur visuel, scripting, débogage et profiling.



Taille du runtime, temps de démarrage, temps de chargement et consommation de ressources.



Support des appareils bas de gamme.



Documentation, communauté, support professionnel et fréquence de maintenance.



Licence du moteur, licence des dépendances et conditions commerciales.



Portabilité, dépendance fournisseur, migration et pérennité.

16.8 Éléments à spécifier

Moteur ou framework, version, langages, API, packages, plateformes, outils associés, dépendances, licences et critères de comparaison.

17 — Architecture logicielle et données de jeu

17.1 Structures architecturales





Architecture monolithique ou modulaire.



Architecture orientée composants.



Entity Component System (ECS).



Architecture orientée événements.



Architecture en couches.



Architecture orientée données (data-oriented design).



Systèmes de plugins et extensions.



Services séparés et architecture distribuée lorsque le produit le justifie.

L'architecture Gameplay Framework d'Unreal présente différents rôles de classes et de composants, tandis que Godot expose un modèle de scènes, nœuds et signaux ; ces modèles sont propres aux moteurs et ne doivent pas être confondus avec une architecture universelle. [R18][R20]

17.2 Organisation du projet





Modules fonctionnels et responsabilités.



Séparation logique du jeu, interface, audio, rendu et services.



Gestion des scènes, niveaux, entités et composants.



Communication entre systèmes.



Gestion des dépendances, interfaces et contrats.



Configuration et données séparées du code lorsque pertinent.



Gestion des états et cycle de vie des objets.

17.3 Boucle d'exécution et temps





Boucle de jeu (game loop).



Mise à jour variable ou simulation à pas fixe.



Découplage simulation physique / rendu.



Gestion du delta time et du temps simulé.



Pause, ralentissement, accélération, horloge de jeu et temps réel.



Synchronisation des systèmes et traitement asynchrone.

La documentation de Godot distingue le traitement physique du traitement par image et décrit un taux physique fixe par défaut dans son exemple de moteur ; ces valeurs sont spécifiques à sa configuration documentée et ne doivent pas être généralisées à tous les moteurs. [R22]

17.4 Données de jeu





Données statiques de configuration.



Données dynamiques de session.



Données persistantes et sauvegardes.



Données de progression, profil, compte et paramètres.



Données de classement, statistiques et télémétrie.



Données générées, procédurales ou créées par les utilisateurs.



Sérialisation, versionnement, migration et compatibilité ascendante.

17.5 Sauvegarde et restauration





Sauvegarde automatique ou manuelle.



Emplacements multiples, profils et slots.



Sauvegarde locale, distante, cloud ou synchronisée.



Sauvegarde incrémentale ou complète.



Contrôle d'intégrité, corruption et récupération.



Conflits entre appareils et stratégies de résolution.



Compatibilité des sauvegardes après mises à jour.

17.6 Éléments à spécifier

Architecture cible, modules, communication, données, boucle d'exécution, persistance, migration, sauvegarde et compatibilité.

18 — Physique, collisions et simulation

18.1 Types de corps et de collision





Corps statiques, dynamiques, cinématiques et contrôlés par personnage.



Corps rigides (rigid bodies).



Corps souples (soft bodies) lorsque le moteur les prend en charge.



Zones et volumes de détection (areas / triggers).



Formes primitives, convexes, maillages et formes composées.



Collisions continues ou discrètes.



Détection de contact, intersection, chevauchement et réponse aux collisions.

Godot documente explicitement plusieurs types d'objets de collision 2D et 3D et distingue détection et réponse à la collision. [R22]

18.2 Modèles physiques





Gravité, masse, densité, friction, restitution et résistance.



Forces, impulsions, contraintes, joints et ressorts.



Mouvement de véhicule et simulation de roues.



Corps articulés, ragdoll, tissus, cordes et chaînes.



Destruction, fracture et débris.



Fluides et interactions avec l'eau selon les capacités du moteur ou middleware.

18.3 Simulation temporelle





Pas fixe et pas variable.



Substeps et interpolation.



Déterminisme ou non-déterminisme de simulation.



Synchronisation entre clients et serveur.



Reproductibilité des états et conséquences réseau.

La documentation de Godot avertit que sa simulation physique n'est pas garantie déterministe dans toutes les circonstances ; cette propriété dépend du moteur, des versions, du matériel et de la configuration. [R22]

18.4 Éléments à spécifier

Systèmes physiques nécessaires, types de corps, formes de collision, paramètres, déterminisme attendu, synchronisation, charge cible et contraintes de plateforme.

19 — Assets, formats et pipeline de production

19.1 Familles d'assets





Images, sprites, textures, atlas, icônes et éléments d'interface.



Modèles 3D, maillages, matériaux, UV, squelettes et morph targets.



Animations, clips, rigs et données de capture.



Sons, musiques, voix, banques et métadonnées audio.



Polices, textes, dialogues et fichiers de localisation.



Niveaux, scènes, prefabs, blueprints et données procédurales.



Vidéos, cinématiques, sous-titres et fichiers de synchronisation.

19.2 Formats et échanges





Images : PNG, JPEG, WebP, TIFF, EXR et formats de textures compressées selon la plateforme.



3D : glTF / GLB, FBX, OBJ et formats propres aux logiciels ou moteurs.



Échange de scène et données complexes : USD lorsque le pipeline le nécessite.



Audio : WAV, AIFF, FLAC, Ogg Vorbis, Opus, MP3, AAC selon support et licence.



Animation : formats intégrés aux moteurs, formats de scène et échanges d'animation.

Le registre Khronos décrit glTF 2.0 comme un format de livraison d'assets 3D à l'exécution ; sa spécification traite notamment des scènes, nœuds, matériaux, maillages, animations et ressources associées. [R35]

19.3 Pipeline de contenu





Création, import, conversion, validation, compression et intégration.



Convention de nommage, arborescence, métadonnées et tags.



Bibliothèques partagées et dépendances d'assets.



Gestion des versions, variantes et ressources source.



LOD, atlas, baking, normal maps et génération de mipmaps.



Contrôle qualité, doublons et ressources manquantes.



Pipeline de build, bundles, patchs et téléchargement à la demande.

19.4 Gestion des ressources et droits





Auteur, origine, date, licence, attribution, restrictions et preuve d'achat.



Autorisation d'utilisation commerciale et de modification.



Droits musicaux, voix, polices, images, marques et modèles.



Conditions des bibliothèques tierces et des contenus générés.



Conservation des sources et des fichiers modifiables.

19.5 Contrôle et versionnement





Git et gestion des branches pour le code et les fichiers adaptés à ce modèle.



Git LFS pour le suivi de fichiers volumineux lorsque son modèle convient.



Perforce Helix Core, avec contrôle de versions et verrouillage de fichiers, souvent proposé pour des workflows contenant de gros assets. Les affirmations de fournisseur sur son adoption sectorielle ne sont pas utilisées ici comme mesure indépendante. [R36]



Gestion des conflits sur fichiers binaires, verrouillage, revue et archivage.

19.6 Éléments à spécifier

Inventaire des assets, formats, résolutions, budgets, outils, pipeline, contrôles qualité, versionnement et preuves de droits.

20 — Plateformes et environnements d'exécution

20.1 PC et ordinateur





Windows, macOS, Linux et distributions ciblées.



Claviers, souris, manettes, périphériques spécialisés et écrans multiples.



Différences de GPU, CPU, mémoire, pilotes, systèmes d'exploitation et résolutions.



Distribution via boutiques, installateur, lanceur ou exécution directe.

20.2 Consoles





Plateformes PlayStation, Xbox et Nintendo.



Contrôleurs et fonctions système propres à chaque plateforme.



Gestion des comptes, succès/trophées, sauvegardes, réseau et services plateforme.



Certification, exigences techniques et règles de publication propres à chaque constructeur.



Accès aux SDK, documentation et programmes développeurs selon les procédures des détenteurs de plateforme.

Les exigences de certification et conditions de distribution peuvent être non publiques ou réservées aux partenaires. Elles ne doivent pas être déduites d'une documentation d'une autre plateforme.

20.3 Mobile et appareils tactiles





iOS/iPadOS, Android et appareils tactiles compatibles.



Résolutions, ratios, encoche, orientation et densité de pixels.



Touches virtuelles, gestes, multi-touch, manettes et gyroscope.



Consommation batterie, chauffe, mémoire et performances GPU.



Suspension/reprise, interruptions système, appels, notifications et cycle de vie.



Distribution via boutiques mobiles ou distribution contrôlée.

20.4 Web et navigateur





HTML, CSS, JavaScript/TypeScript et Canvas 2D.



WebGL / WebGL 2 et WebGPU.



Web Audio API pour le traitement et le routage audio. [R14]



Gamepad API pour accéder aux manettes compatibles ; la disponibilité générale ne garantit pas un comportement identique de chaque contrôleur. [R37]



Pointer Lock API pour l'accès aux déplacements relatifs de la souris ; la compatibilité doit être contrôlée. [R38]



Fullscreen API pour présenter un élément en plein écran ; la prise en charge varie selon le navigateur et l'environnement. [R39]



Service Workers pour intercepter des requêtes et mettre en place des expériences hors ligne ou des stratégies de cache, dans les limites de leur cycle de vie et des règles de sécurité. [R40]



IndexedDB pour stocker des quantités structurées de données côté client. [R41]



WebXR pour des expériences immersives dans les navigateurs qui le prennent en charge ; MDN signale une disponibilité limitée et des exigences de contexte sécurisé. [R42]

Points spécifiques au Web : chargement initial, cache, stockage soumis aux règles du navigateur, restrictions de sécurité, CORS, cycle de vie de l'onglet, perte de contexte GPU, compatibilité navigateur, permissions, installation PWA éventuelle et fonctionnement hors ligne.

20.5 VR, AR et XR





VR : immersion dans un environnement virtuel.



AR : superposition de contenu numérique sur le monde réel.



MR/XR : familles de systèmes de réalité étendue, selon les définitions des plateformes et standards concernés.



HMD, contrôleurs, suivi des mains, suivi de tête, regard, locomotion et espace physique.



Confort, cybersickness, champ de vision, fréquence d'affichage, calibration et sécurité de l'espace utilisateur.



API et standards : OpenXR, dont le registre Khronos publie la spécification API 1.1, pour les runtimes compatibles ; WebXR pour le Web lorsque disponible. [R59]

20.6 Cloud gaming et streaming





Exécution distante et streaming vidéo interactif.



Latence d'entrée, qualité réseau, compression vidéo et adaptation de débit.



Compatibilité manette, session, sauvegarde et authentification.



Dépendance au fournisseur et à l'infrastructure de streaming.

20.7 Éléments à spécifier

Plateformes exactes, versions minimales des systèmes, appareils cibles, contrôleurs, résolutions, contraintes matérielles, distribution et fonctions système attendues.



PARTIE IV — SERVICES, QUALITÉ ET CYCLE DE VIE

21 — Multijoueur, réseau et services en ligne

21.1 Modes réseau





Solo hors ligne.



Solo connecté à des services.



Multijoueur local.



Réseau local.



Peer-to-peer.



Hôte joueur (listen server).



Serveur dédié.



Architecture client-serveur.



Parties asynchrones et partage de données différées.



Monde persistant et architecture massivement multijoueur.

21.2 Autorité et cohérence





Autorité serveur.



Autorité client ou propriétaire d'objet.



Modèle hybride.



Validation des actions côté serveur.



Réplication d'état, événements et snapshots.



Prédiction client, interpolation, réconciliation et rollback.



Synchronisation de temps, horloges et tick réseau.

Les documentations Unity distinguent Netcode for Entities et Netcode for GameObjects et décrivent leurs orientations respectives. Roblox documente un système d'autorité serveur avec prédiction, rollback et resimulation. Ces exemples montrent des implémentations spécifiques, non une solution unique pour tous les jeux. [R19][R43]

21.3 Réseau et transport





TCP, UDP, WebSocket, WebRTC et protocoles spécialisés selon l'architecture.



Messages fiables ou non fiables.



Ordre des messages, séquencement, accusés de réception et retransmission.



Compression, sérialisation, fréquence d'envoi et taille des paquets.



Latence, jitter, perte de paquets, bande passante et reconnexion.



Relais, NAT traversal, hébergement et régions de serveurs.

21.4 Services multijoueurs





Lobby, salon, invitations et groupes.



Matchmaking, classement et recherche de partie.



Identité, amis, présence, chat et communication vocale.



Serveurs dédiés, allocation et orchestration.



Classements, statistiques, succès et sauvegardes cloud.



Modération, signalement, blocage et sanctions.



UGC, partage de cartes, replays, créations et extensions.

Steamworks documente des services tels que matchmaking, achievements, Workshop, classements, Remote Play et des fonctions réseau ; chaque fonction est optionnelle et doit être évaluée selon les besoins du jeu et les conditions de la plateforme. [R44][R45]

21.5 Sécurité multijoueur





Validation serveur des actions sensibles.



Autorité sur les résultats, inventaires, monnaie et scores.



Protection contre falsification de paquets, rejeu, spam et abus d'API.



Anti-triche côté client et serveur.



Détection comportementale et analyse de télémétrie.



Intégrité des clients et du contenu.



Protection des services, disponibilité et déni de service.



Confidentialité des communications et données des joueurs.

21.6 Éléments à spécifier

Modes réseau, topologie, autorité, nombre de joueurs, fréquence de simulation, tolérance à la latence, régions, services, modération et exigences anti-triche.

22 — Économie, achats et modèles de distribution

22.1 Modèles de distribution





Premium : achat initial.



Free-to-play : accès gratuit avec sources de revenus éventuelles.



Démonstration, shareware ou épisode.



Abonnement.



Distribution financée par publicité.



Bundle, compilation ou licence institutionnelle.



Accès via catalogue de jeux ou service d'abonnement.

22.2 Monétisation et ventes





Vente du jeu complet.



Extensions et DLC.



Contenus cosmétiques.



Pass saisonnier ou de progression.



Abonnement et services récurrents.



Publicités récompensées ou interstitielles.



Achats intégrés et monnaie virtuelle.



Objets aléatoires payants, loot boxes ou packs surprises.



Contenus générés par les utilisateurs et partage de revenus.

22.3 Économie interne





Monnaie unique ou monnaies multiples.



Ressources communes, rares, saisonnières ou liées à un mode.



Sources et puits de ressources (sources / sinks).



Récompenses, coûts, prix, taxes, frais et conversions.



Échange direct, marché, enchères, commerce joueur à joueur.



Économie contrôlée ou émergente.



Inflation, rareté, progression et équilibre des prix.

22.4 Gestion commerciale et transparence





Prix, devises, taxes et disponibilité régionale.



Confirmation d'achat et annulation selon les règles applicables.



Inventaire d'achats et restauration des achats.



Achats accidentels, contrôle parental et limites de dépenses.



Communication du contenu payant et des conditions d'accès.



Événements temporaires et offres limitées.

Les organismes de classification PEGI et ESRB documentent les achats intégrés et les éléments interactifs. PEGI a publié des règles spécifiques relatives à certains achats aléatoires payants, offres limitées et fonctionnalités de communication à compter de juin 2026 ; les critères doivent être revérifiés au moment de la soumission. [R46][R47]

22.5 Éléments à spécifier

Modèle économique, prix, achats, monnaies, sources/puits, contenus vendus, transparence, régions, contrôles parentaux et intégration aux systèmes de paiement.

23 — Données, sécurité, conformité et propriété intellectuelle

23.1 Catégories de données





Données de compte et identité.



Données de progression et sauvegarde.



Données de gameplay et télémétrie.



Données de paiement traitées par des prestataires.



Données de communication, chat et signalements.



Données de localisation ou appareil si elles sont collectées.



Données de mineurs ou catégories particulières éventuelles.



Données techniques, logs et diagnostic.

23.2 Sécurité des systèmes





Gestion des comptes, authentification et récupération.



Gestion des rôles, autorisations et accès administratifs.



Secrets, jetons, certificats et clés.



Chiffrement en transit et au repos lorsque requis par l'analyse de risque.



Validation des entrées et sorties.



Sécurité des API et communications réseau.



Gestion des dépendances et chaîne d'approvisionnement logicielle.



Journalisation, surveillance et réponse aux incidents.



Sauvegardes, restauration, disponibilité et résilience.



Protection contre triche, fraude, usurpation et abus.

Pour les applications web et services associés, OWASP Top 10:2025 est une référence de sensibilisation aux risques applicatifs ; OWASP ASVS 5.0 fournit un catalogue de exigences de vérification de sécurité pour applications web et services. Ces références ne remplacent pas une analyse de risque propre au jeu. [R48][R49]

23.3 Protection des données personnelles





Finalités et bases légales de traitement.



Minimisation des données.



Transparence et information des joueurs.



Durée de conservation et suppression.



Droits des personnes et gestion des demandes.



Sous-traitants, transferts et localisation des données.



Sécurité et protection dès la conception.



Gestion de l'âge, du consentement et des utilisateurs mineurs selon les règles applicables.



Cookies, SDK analytiques, publicité et traceurs selon le contexte juridique.

Le RGPD est le règlement (UE) 2016/679 ; l'analyse de conformité dépend du rôle des acteurs, du territoire, des traitements réels et des textes applicables. Le référentiel ne remplace pas un avis juridique. [R50]

23.4 Classification et sécurité des joueurs





Évaluation de contenu selon les territoires de distribution.



Violence, langage, peur, sexualité, discrimination, drogues, jeu d'argent et autres descripteurs pertinents.



Achats intégrés, achats aléatoires, communication et interaction entre joueurs.



Outils de blocage, signalement, modération et contrôle parental.



Risques de harcèlement, fraude, exposition à des contenus utilisateurs et contacts non sollicités.

PEGI et ESRB sont des systèmes de classification distincts ; les critères et descripteurs ne doivent pas être transposés automatiquement de l'un à l'autre. [R46][R47]

23.5 Propriété intellectuelle et licences





Droits sur le code, les assets, la musique, les voix, les textes et les marques.



Licences open source, propriétaires, commerciales et d'utilisation d'assets.



Licences de polices, bibliothèques, codecs, middleware et contenus de marketplace.



Attribution, notices, redistribution et obligations de licence.



Droits des contributeurs et contrats de cession ou licence.



Droit à l'image, droits musicaux et droit des marques selon les territoires.



Contenu généré par les utilisateurs et politique de retrait.



Contenu créé avec des outils d'IA : droits, conditions des fournisseurs, provenance, données d'entraînement et règles de plateforme à vérifier.

Les pages de licence de Godot, Unreal et autres outils font autorité pour les conditions de leurs logiciels respectifs ; toute comparaison tarifaire ou juridique doit être faite à partir du texte en vigueur à la date du projet. [R21][R51]

23.6 Éléments à spécifier

Inventaire des données, finalités, comptes, services tiers, sécurité, modération, territoires, classement, licences et éléments juridiques à faire vérifier.

24 — Production, tests, publication et maintenance

24.1 Organisation de production





Préproduction, prototype, vertical slice, production, alpha, bêta, release candidate et lancement.



Décomposition du jeu en systèmes, contenus, scènes et livrables.



Dépendances, jalons, risques, budget et ressources.



Rôles : design, programmation, art, animation, audio, QA, production, localisation et exploitation.



Gestion des versions et des environnements.



Suivi des décisions, modifications et demandes.

Ces noms de phases sont des catégories de production courantes, pas une séquence obligatoire ni une norme universelle.

24.2 Tests fonctionnels et techniques





Tests unitaires, intégration, système et end-to-end.



Tests des mécaniques, règles et transitions d'état.



Tests de sauvegarde, restauration et migration.



Tests de réseau, latence, perte de connexion et reconnexion.



Tests de compatibilité et périphériques.



Tests de performance CPU, GPU, mémoire, stockage et réseau.



Tests de sécurité et contrôle des permissions.



Tests de localisation et d'accessibilité.



Tests automatisés, exploratoires et manuels.

24.3 Playtests et validation de l'expérience





Tests internes, tests avec joueurs ciblés et tests de groupe.



Observation de la compréhension des règles et commandes.



Évaluation du rythme, de la difficulté et de la lisibilité.



Détection de frustration, confusion, blocages et stratégies non prévues.



Retours qualitatifs, questionnaires et métriques.



Tests de tutoriels et d'onboarding.



Tests de contenu et progression à long terme.

24.4 Performance et qualité





Objectifs de fréquence d'images, latence d'entrée et temps de chargement.



Budgets CPU, GPU, mémoire, stockage, bande passante et consommation électrique.



Stabilité, crash, blocage, fuite mémoire et corruption de données.



Mesure sur appareils cibles et conditions réalistes.



Profilage, télémétrie et analyse des goulets d'étranglement.

La documentation Godot recommande de mesurer les performances et de profiler sur différents matériels. La documentation Unity 2022.2 consultée indique que les mesures dans l'éditeur ne reflètent pas exactement les performances sur la plateforme cible ; cette référence étant versionnée, la documentation correspondant à la version Unity retenue doit être consultée. [R52][R53]

24.5 Distribution et publication





Build de développement, test, staging et production.



Signature, packaging, installation et mise à jour.



Page boutique, classification, visuels, bande-annonce et métadonnées.



Gestion des langues, régions, prix et disponibilité.



Certification et exigences de la plateforme.



Versionnement, notes de mise à jour et support.



Déploiement progressif, rollback et gestion d'incident.

24.6 Exploitation et maintenance





Monitoring, logs, crash reporting et alertes.



Support joueurs, FAQ et gestion des signalements.



Sauvegardes et restauration.



Mises à jour correctives, contenu et équilibre.



Gestion des versions et compatibilité des sauvegardes.



Fin de vie, retrait de services et conservation des données.



Migration, archivage et fermeture de serveurs.

24.7 Live operations et contenu continu





Événements, saisons, rotations et mises à jour.



Calendrier de contenu et communication.



Configuration à distance et feature flags.



Analyse de fréquentation, stabilité, progression et économie.



Modération, support et gestion communautaire.



Outils d'administration et de supervision.

24.8 Éléments à spécifier

Phases et livrables, couverture de tests, critères d'acceptation, appareils testés, seuils qualité, publication, monitoring, mises à jour et fin de vie.



PARTIE V — CATALOGUES TRANSVERSAUX

Les catalogues suivants regroupent des valeurs communes aux modules. Ils servent de vocabulaire partagé ; ils ne constituent pas des choix obligatoires.

A. Catalogue des genres et tags

Tags descriptifs possibles :





Action, aventure, exploration, combat, tir, plateforme, infiltration.



RPG, tactique, stratégie, simulation, gestion, construction.



Puzzle, logique, enquête, narratif, visual novel.



Survival, horror, roguelike, roguelite, sandbox, crafting.



Course, sport, rythme, musique, adresse, party.



Idle, incremental, clicker, deck-builder, tower defense.



Solo, coop, PvP, PvE, PvPvE, asynchrone, massivement multijoueur.



Monde ouvert, niveaux, missions, arènes, génération procédurale.

B. Catalogue des plateformes







Famille



Exemples / sous-catégories





Ordinateur



Windows, macOS, Linux





Console



PlayStation, Xbox, Nintendo





Mobile



iOS/iPadOS, Android





Navigateur



Desktop, mobile, tablette, PWA éventuelle





Immersif



VR, AR, MR, XR





Cloud



Streaming de jeu et exécution distante





Autres



Bornes, appareils embarqués, dispositifs spécialisés

Chaque plateforme doit être précisée par modèle, génération, version minimale, périphériques et conditions de distribution lorsqu'ils sont connus.

C. Catalogue des styles visuels





Pixel art, pixel art haute résolution, sprite animé.



Dessin à la main, illustration, peinture numérique.



Vectoriel, géométrique, minimaliste.



Low poly, voxel, stylisé 3D.



Réaliste, photoréaliste, semi-réaliste.



Toon/cel shading, flat shading, silhouettes, monochrome.



Isométrique, diorama, miniature, papier découpé.



Rétro CRT, palette limitée, dithering, scanlines.



Mélange de médias, collage, rendu procédural.

D. Catalogue des systèmes de gameplay





Mouvement et locomotion.



Combat, visée, dégâts et statut.



Interaction, collecte, utilisation et manipulation.



Inventaire, équipement, crafting et construction.



Compétences, niveaux et progression.



Économie, commerce et ressources.



Exploration, carte et navigation.



Dialogue, choix et relations.



Furtivité, détection et perception.



Puzzle, logique et combinaison.



Véhicules, pilotage et simulation.



Gestion d'équipe, unités et stratégie.



Génération procédurale et événements dynamiques.



Multijoueur, social et compétition.

E. Catalogue de commandes





Clavier : touches, raccourcis, combinaisons et remappage.



Souris : déplacement relatif/absolu, clic, molette et gestes.



Manette : boutons, sticks, gâchettes, vibration et zones mortes.



Tactile : tap, glisser, pincement, multi-touch, boutons virtuels.



Mouvement : gyroscope, accéléromètre, contrôleurs 6DoF et suivi des mains.



Accessibilité : switches, commandes alternatives, clavier à une main et interfaces adaptatives.



Voix et regard : selon matériel, permissions, confidentialité et support.

F. Catalogue de modèles d'IA de jeu





Machines à états.



Behavior Trees et Blackboards.



Utility AI et systèmes à règles.



GOAP et planification hiérarchique.



Requêtes de contexte et sélection d'emplacements.



Navigation par grille, graphe et navmesh.



Pathfinding, évitement et steering.



Comportements de groupe, formation et foule.



Simulation de routines, relations et besoins.



Systèmes procéduraux et génération par contraintes.



Apprentissage automatique et modèles génératifs, si justifiés et contrôlables.

G. Catalogue de rendu et de représentation





Canvas 2D, sprites, tuiles, atlas et couches.



Rasterisation forward/deferred.



PBR, matériaux non photoréalistes et shaders personnalisés.



Éclairage précalculé, dynamique ou hybride.



Ombres, réflexions et illumination globale.



Ray tracing / path tracing selon API, matériel et moteur.



Particules, volumétrie, post-traitement et effets de caméra.



LOD, culling, streaming et résolution dynamique.

H. Catalogue des architectures réseau





Hors ligne.



Client-serveur.



Serveur dédié.



Hôte joueur.



Peer-to-peer.



Relay.



Synchronisation d'état.



Synchronisation d'événements.



Autorité serveur.



Prédiction client, interpolation, réconciliation et rollback.



Communication temps réel ou asynchrone.

I. Catalogue des services en ligne





Authentification et identité.



Profils, amis et présence.



Lobby et matchmaking.



Classements, statistiques et succès.



Sauvegardes cloud.



Chat textuel et vocal.



Contenu généré par les utilisateurs.



Téléchargement de contenu et mises à jour.



Modération et signalement.



Analytics et télémétrie.



Boutique, achats et inventaire.



Gestion de serveurs et allocation de sessions.

J. Catalogue de qualité





Fonctionnalité et exactitude des règles.



Stabilité et fiabilité.



Performance et efficacité des ressources.



Compatibilité et portabilité.



Sécurité et confidentialité.



Accessibilité et ergonomie.



Maintenabilité et évolutivité.



Lisibilité, feedback et cohérence.



Qualité audio-visuelle.



Qualité de localisation.



Reproductibilité, observabilité et récupération.



PARTIE VI — ÉLÉMENTS DU CAHIER DES CHARGES

Cette partie décrit les informations qu'un cahier des charges de jeu peut contenir. Elle ne dicte pas l'ordre de travail : la composition finale dépend du périmètre réel du jeu.

1. Identité et résumé





Titre, pitch, concept, vision et objectifs.



Public cible, plateformes et contexte de jeu.



Genres, modes et positionnement.



Références et différences recherchées.

2. Expérience et design





Expérience joueur recherchée.



Boucles de gameplay.



Règles et systèmes de jeu.



Actions, interactions et commandes.



Défis, récompenses et progression.



Difficulté et conditions de fin.

3. Contenus et univers





Univers, personnages et factions.



Narration, dialogues et choix.



Niveaux, cartes, missions et événements.



Contenus statiques, procéduraux et créés par utilisateurs.

4. Direction artistique et audio





Style, références et règles visuelles.



Graphismes, rendu, caméra et animations.



Effets visuels et atmosphère.



Musique, voix, effets sonores et spatialisation.

5. Interface et accessibilité





Menus, HUD et interfaces contextuelles.



Navigation et contrôles.



Options visuelles, sonores, motrices et cognitives.



Sous-titres, localisation et préférences.

6. Technique





Moteur, version, langage et frameworks.



Architecture, modules et systèmes.



Physique, rendu, animation et audio.



Gestion et pipeline des assets.



Plateformes et configurations minimales.

7. Données et services





Données de jeu, profils et sauvegardes.



Services en ligne et prestataires tiers.



Multijoueur, réseau et autorité.



Comptes, achats, classement et modération.

8. Qualité et contraintes





Performance et budgets de ressources.



Sécurité, confidentialité et conformité.



Compatibilité et accessibilité.



Tests, validation et critères d'acceptation.



Risques, dépendances et hypothèses.

9. Production et exploitation





Livrables et périmètre de contenu.



Production artistique, technique et narrative.



Publication, distribution et certification.



Support, monitoring, mises à jour et maintenance.



Coûts de fonctionnement et fin de vie.

10. Nature des exigences

Un cahier des charges distingue les catégories suivantes :







Catégorie



Définition





Fonctionnelle



Comportement ou capacité que le jeu doit proposer.





Non fonctionnelle



Niveau de qualité attendu : performance, sécurité, disponibilité, maintenabilité, etc.





Artistique



Style, rendu, son, animation et cohérence visuelle ou sonore.





Contenu



Éléments narratifs, niveaux, personnages, objets, missions et ressources.





Technique



Architecture, plateformes, technologies, protocoles et contraintes matérielles.





Opérationnelle



Publication, exploitation, support, sauvegardes et maintenance.





Juridique / conformité



Obligations et restrictions vérifiées pour les territoires et activités concernés.

11. Fiche d'exigence recommandée

Chaque exigence peut être décrite avec les champs suivants :







Champ



Utilité





Identifiant



Référence stable, par exemple GAME-REQ-001.





Intitulé



Nom court de l'exigence.





Description



Besoin à satisfaire, formulé sans ambiguïté.





Domaine / module



Domaine principal et modules associés.





Type



Fonctionnel, non fonctionnel, artistique, contenu, technique, opérationnel ou juridique.





Priorité



Critique, élevée, moyenne, faible ou autre échelle définie pour le projet.





Justification



Pourquoi l'exigence existe.





Dépendances



Exigences, systèmes ou services liés.





Contraintes



Plateforme, coût, technique, règlement ou contenu.





Critère d'acceptation



Condition observable permettant de vérifier la satisfaction.





Source



Décision projet, norme, spécification ou référence documentaire.





Statut



À étudier, décidé, en cours, validé, rejeté ou remplacé.

12. Fiche de module recommandée pour une base maintenable

Pour structurer les futures extensions du référentiel :

module_id: VIS-CAM-001
nom: Systeme de camera
partie: creation_artistique_et_experience
categorie: camera_et_espace
niveau: expert
portee:
  - 2D
  - 2.5D
  - 3D
  - VR_XR
nature:
  - design
  - technique
mots_cles:
  - camera
  - perspective
  - champ_de_vision
sous_modules:
  - types_de_camera
  - parametres
  - occlusion
  - transitions
dependances:
  - gameplay_deplacement
  - level_design
  - animation
  - ergonomie
references:
  - R10
  - R18
date_verification: 2026-11-06

Cet exemple décrit des métadonnées documentaires, pas une règle de sélection ou un ordre d'exécution.

13. Liens et relations entre modules

Les liens entre modules peuvent être classés ainsi :





Dépendance fonctionnelle : deux domaines participent au même comportement de jeu.



Dépendance technique : un domaine requiert une technologie ou un système associé.



Dépendance de contenu : un domaine consomme ou produit des assets.



Dépendance de qualité : un choix influence performance, stabilité, compatibilité ou accessibilité.



Dépendance de conformité : un choix entraîne des obligations légales, contractuelles ou de plateforme.

Une relation décrit une proximité ou une conséquence potentielle, pas une obligation automatique.



GLOSSAIRE







Terme



Sens dans le présent référentiel





Asset



Ressource de contenu utilisée par le jeu : modèle, texture, son, animation, scène, etc.





Autorité serveur



Modèle où le serveur détient l'état de référence pour les éléments définis comme autoritaires.





Behavior Tree



Structure de décision organisée en nœuds et branches, utilisée notamment pour les comportements d'agents.





Core loop



Boucle d'actions et de retours récurrente au cœur de l'expérience.





ECS



Modèle Entity Component System séparant les entités, composants et systèmes de traitement.





Feedback



Information renvoyée au joueur après une action ou un événement.





Game feel



Qualité ressentie de l'interaction, du mouvement et de la réponse du jeu.





Game loop



Cycle d'exécution qui met à jour la simulation et produit les images affichées.





HUD



Interface superposée à la vue de jeu pour communiquer des informations.





LOD



Niveau de détail d'un asset ou d'un modèle selon des critères de rendu.





Navmesh



Représentation des zones navigables utilisée par des systèmes de navigation.





PBR



Famille de techniques de rendu de matériaux fondées sur des paramètres physiques ou approximations associées.





Playtest



Session de jeu observée ou évaluée pour étudier l'expérience et détecter des problèmes.





Rollback



Retour à un état antérieur puis simulation à nouveau, notamment utilisé pour corriger une prédiction réseau.





RTPC



Paramètre de contrôle en temps réel dans le vocabulaire de certains outils audio, notamment FMOD/Wwise selon l'outil.





State machine



Modèle représentant des états et des transitions entre états.





Vertical slice



Portion représentative du jeu destinée à démontrer un niveau de qualité et d'intégration.



RÉFÉRENCES DOCUMENTAIRES

Date de consultation générale : 6 novembre 2026. Les liens ci-dessous pointent vers les sources primaires ou les organismes concernés. Les versions et contenus peuvent évoluer ; les documentations de version stable ou les spécifications en vigueur doivent être privilégiées au moment d'un choix technique.

Game Design et conception





[R01] Hunicke, LeBlanc, Zubek — MDA: A Formal Approach to Game Design and Game Research, AAAI / Northwestern University (2004).
https://aaai.org/papers/ws04-04-001-mda-a-formal-approach-to-game-design-and-game-research/
https://www.cs.northwestern.edu/~hunicke/MDA.pdf

IA, navigation et systèmes de jeu





[R02] Epic Games — Behavior Trees in Unreal Engine.
https://dev.epicgames.com/documentation/unreal-engine/behavior-trees-in-unreal-engine?lang=en-US



[R03] Epic Games — Environment Query System in Unreal Engine.
https://dev.epicgames.com/documentation/en-us/unreal-engine/environment-query-system-in-unreal-engine



[R04] Epic Games — Navigation System in Unreal Engine.
https://dev.epicgames.com/documentation/unreal-engine/navigation-system-in-unreal-engine?lang=en-US



[R05] Godot Engine — Using NavigationServer.
https://docs.godotengine.org/en/stable/tutorials/navigation/navigation_using_navigationservers.html

Rendu, moteurs et technologies graphiques





[R06] Epic Games — Nanite Virtualized Geometry in Unreal Engine.
https://dev.epicgames.com/documentation/en-us/unreal-engine/nanite-in-unreal-engine



[R07] Epic Games — Lumen Global Illumination and Reflections.
https://dev.epicgames.com/documentation/unreal-engine/lumen-global-illumination-and-reflections-in-unreal-engine



[R08] Godot Engine — Documentation officielle, rendu et fonctionnalités.
https://docs.godotengine.org/en/stable/



[R09] W3C — WebGPU, Candidate Recommendation Draft du 15 septembre 2026.
https://www.w3.org/TR/webgpu/



[R10] Godot Engine — Animation.
https://docs.godotengine.org/en/stable/tutorials/animation/



[R11] Epic Games — Creating Visual Effects in Niagara for Unreal Engine.
https://dev.epicgames.com/documentation/en-us/unreal-engine/creating-visual-effects-in-niagara-for-unreal-engine

Audio





[R12] FMOD — Parameters, FMOD Studio User Manual.
https://www.fmod.com/docs/tutorials/parameters.html



[R13] Godot Engine — Audio buses.
https://docs.godotengine.org/en/latest/tutorials/audio/audio_buses.html



[R14] MDN — Web Audio API.
https://developer.mozilla.org/en-US/docs/Web/API/Web_Audio_API

UX, accessibilité et réglementation de contenu





[R15] Microsoft — Xbox Accessibility Guidelines V3.2.
https://learn.microsoft.com/gaming/accessibility/guidelines



[R16] Game Accessibility Guidelines — Basic guidelines.
https://gameaccessibilityguidelines.com/basic/



[R17] W3C — WCAG 2.2, présentation et statut.
https://www.w3.org/WAI/standards-guidelines/wcag/fr



[R46] PEGI — What do the labels mean?
https://pegi.info/what-do-the-labels-mean



[R47] ESRB — Ratings Guide.
https://www.esrb.org/ratings-guide/

Moteurs, frameworks et outils





[R18] Epic Games — Gameplay Framework in Unreal Engine.
https://dev.epicgames.com/documentation/en-us/unreal-engine/gameplay-framework-in-unreal-engine



[R19] Unity — Unity's netcode packages.
https://docs.unity.com/en-us/multiplayer/netcode/netcode



[R20] Godot Engine — Introduction et documentation officielle (version stable).
https://docs.godotengine.org/en/stable/getting_started/introduction/



[R21] Godot Engine — License.
https://godotengine.org/license/



[R22] Godot Engine — Physics introduction.
https://docs.godotengine.org/en/stable/tutorials/physics/physics_introduction.html



[R23] Godot Engine — Step by step.
https://docs.godotengine.org/en/stable/getting_started/step_by_step/index.html



[R24] Defold — About Defold.
https://defold.com/about/



[R25] Ren'Py — The Ren'Py Visual Novel Engine.
https://www.renpy.org/



[R60] Ren'Py — Web / HTML5 deployment documentation.
https://www.renpy.org/doc/html/web.html



[R26] Phaser — Phaser documentation / overview.
https://www.phaser.io/oss/docs



[R27] PixiJS — Rendering documentation.
https://pixijs.download/dev/docs/rendering.html



[R28] Babylon.js — Engine specifications.
https://www.babylonjs.com/specifications/



[R29] PlayCanvas — Engine user manual.
https://developer.playcanvas.com/user-manual/engine/



[R30] MonoGame — Documentation and framework overview.
https://docs.monogame.net/articles/index.html



[R54] GameMaker — Official manual.
https://manual.gamemaker.io/lts/en/Content.htm



[R55] Bevy — Official project site and feature overview.
https://bevy.org/



[R56] Three.js — WebGLRenderer API documentation.
https://threejs.org/docs/pages/WebGLRenderer.html



[R57] LÖVE — Getting Started guide.
https://love2d.org/wiki/Getting_Started



[R58] raylib — Official project site and feature overview.
https://www.raylib.com/



[R59] Khronos Group — OpenXR Registry and API specification.
https://registry.khronos.org/OpenXR/



[R31] Khronos Group — Vulkan Registry.
https://registry.khronos.org/vulkan/



[R32] Khronos Group — OpenGL and OpenGL ES Registry.
https://registry.khronos.org/OpenGL/



[R33] Microsoft — Direct3D 12 Graphics.
https://learn.microsoft.com/en-us/windows/win32/direct3d12/



[R34] Apple — Metal Developer Documentation.
https://developer.apple.com/metal/



[R35] Khronos Group — glTF 2.0 Registry and Specification.
https://registry.khronos.org/glTF/



[R36] Perforce — Helix Core.
https://www.perforce.com/products/helix-core

Web et navigateur





[R37] MDN — Gamepad API.
https://developer.mozilla.org/en-US/docs/Web/API/Gamepad_API



[R38] MDN — Pointer Lock API.
https://developer.mozilla.org/en-US/docs/Web/API/Pointer_Lock_API



[R39] MDN — Fullscreen API.
https://developer.mozilla.org/en-US/docs/Web/API/Fullscreen_API



[R40] MDN — Service Worker API.
https://developer.mozilla.org/en-US/docs/Web/API/Service_Worker_API



[R41] MDN — IndexedDB API.
https://developer.mozilla.org/en-US/docs/Web/API/IndexedDB_API



[R42] MDN — WebXR Device API.
https://developer.mozilla.org/en-US/docs/Web/API/WebXR_Device_API

Réseau, services et multijoueur





[R43] Roblox Creator Hub — Server authority model.
https://create.roblox.com/docs/projects/server-authority



[R44] Steamworks — Features.
https://partner.steamgames.com/doc/features



[R45] Steamworks — Steam Networking.
https://partner.steamgames.com/doc/features/multiplayer/networking

Sécurité, protection des données et licences





[R48] OWASP — Top 10:2025.
https://top10.owasp.org/2025/



[R49] OWASP — Application Security Verification Standard (ASVS), version 5.0.0 publiée le 30 mai 2025.
https://asvs.owasp.org/



[R50] Union européenne — Règlement (UE) 2016/679 (RGPD).
https://eur-lex.europa.eu/eli/reg/2016/679/oj/eng



[R51] Epic Games — Unreal Engine End User License Agreement.
https://www.unrealengine.com/eula/unreal

Tests et performance





[R52] Godot Engine — General optimization.
https://docs.godotengine.org/fr/4.x/tutorials/performance/general_optimization.html



[R53] Unity — Profiling your application (documentation version 2022.2).
https://docs.unity3d.com/2022.2/Documentation/Manual/profiler-profiling-applications.html



MAINTENANCE DU RÉFÉRENTIEL

Politique de mise à jour





Vérifier la documentation officielle d'une technologie avant d'ajouter une caractéristique, une compatibilité ou une limite.



Enregistrer la date de vérification pour chaque information volatile.



Distinguer les déclarations de l'éditeur des résultats de tests indépendants.



Ne pas transformer une recommandation en obligation normative.



Ne pas déduire une compatibilité multiplateforme d'une fonction présentée dans une seule cible.



Ajouter les nouvelles solutions avec leur catégorie, domaine, périmètre, dépendances et source.



Conserver les identifiants des modules existants ; ne pas réutiliser un identifiant supprimé.



Marquer les technologies abandonnées, expérimentales, obsolètes ou dont le support est incertain au lieu de les retirer silencieusement.



Vérifier les licences, coûts et conditions commerciales dans les textes en vigueur au moment du projet.



En cas de source contradictoire, privilégier la spécification normative ou la documentation primaire applicable et consigner l'incertitude.

Historique des versions







Version



Date



Modifications





1.0



2026-11-06



Création du référentiel expert couvrant les jeux vidéo multi-genres et multi-plateformes, avec 24 bibliothèques, catalogues transversaux, structure d'exigences et références documentaires.



Fin du référentiel.
