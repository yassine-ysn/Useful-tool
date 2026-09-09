Nous avons terminé le travail qui nous a permis d'arriver à l'état actuel de cette application.

Je veux maintenant capitaliser sur toute la connaissance que tu as acquise pendant notre travail, mais avec une contrainte fondamentale :

À partir de maintenant, l'objet de la documentation est uniquement L'APPLICATION ACTUELLE.

Je ne veux pas créer une documentation de migration.

Je ne veux pas créer un agent spécialisé dans la migration.

Je ne veux pas que les futures Skills ou Agents parlent systématiquement d'une ancienne version de l'application.

Considère l'application actuellement présente dans le repository comme le produit de référence.

Utilise tout ce que tu as appris pendant notre travail uniquement comme une source permettant de mieux comprendre cette application.

Ton objectif est de construire une base de connaissance permettant à une future instance de Claude Code de devenir rapidement experte de cette application.

Analyse :

- le code actuel ;
- l'architecture ;
- les configurations ;
- les dépendances ;
- les flux fonctionnels ;
- les flux techniques ;
- le frontend ;
- le backend ;
- la persistance ;
- les intégrations ;
- la sécurité ;
- le build ;
- le déploiement ;
- les tests ;
- les problèmes techniques que nous avons découverts ;
- les subtilités que tu as apprises pendant notre travail ;
- les relations entre composants ;
- les conventions implicites du projet ;
- les zones particulièrement sensibles du code.

Tu peux utiliser la connaissance acquise pendant notre travail précédent pour comprendre ces éléments, mais transforme cette connaissance en description de L'ÉTAT ACTUEL.

Par exemple, évite :

"Pendant la migration nous avons découvert que..."

Préfère :

"Ce composant fonctionne de la manière suivante..."

Évite :

"Dans l'ancienne application X fonctionnait comme..."

Préfère :

"Dans l'architecture actuelle, X est responsable de..."

Évite :

"Nous avons remplacé X par Y."

Préfère :

"L'application utilise Y pour..."

La documentation doit pouvoir être lue par quelqu'un qui ne sait même pas qu'une migration a eu lieu.

---

Crée la structure suivante :

docs/application-knowledge/

    README.md
    architecture.md
    functional-overview.md
    technical-overview.md
    frontend.md
    backend.md
    data-model.md
    integrations.md
    security.md
    build-and-deployment.md
    testing.md
    troubleshooting.md
    conventions.md
    glossary.md

## README.md

Doit servir de carte de navigation de la connaissance.

Explique :

- quel document consulter ;
- pour quel type de problème ;
- quels sont les principaux domaines fonctionnels et techniques.

Une future instance de Claude doit pouvoir utiliser ce fichier comme index.

## architecture.md

Décris l'architecture réelle de l'application actuelle.

Inclure :

- composants principaux ;
- responsabilités ;
- interactions ;
- dépendances ;
- couches ;
- flux de données ;
- flux de contrôle ;
- frontières entre modules.

Lorsque pertinent, référence les fichiers, packages et classes du projet.

## functional-overview.md

Explique fonctionnellement ce que fait l'application.

Identifier :

- principaux domaines métier ;
- fonctionnalités ;
- acteurs ;
- concepts métier ;
- workflows importants.

Le but est qu'un développeur puisse comprendre POURQUOI le code existe.

## technical-overview.md

Donne une vue technique globale :

- technologies ;
- frameworks ;
- versions importantes ;
- organisation du repository ;
- modules ;
- processus de démarrage ;
- configuration ;
- dépendances structurantes.

## frontend.md

Documente :

- architecture frontend ;
- routing ;
- composants majeurs ;
- services ;
- gestion d'état ;
- appels backend ;
- modèles échangés ;
- validations ;
- mécanismes transverses ;
- conventions importantes.

## backend.md

Documente :

- architecture backend ;
- controllers / endpoints ;
- services ;
- domaine ;
- accès aux données ;
- transactions ;
- validations ;
- traitements asynchrones ;
- mécanismes transverses ;
- exceptions ;
- configurations importantes.

Pour les flux majeurs, indique idéalement :

Endpoint
→ Controller
→ Service
→ Domain
→ Repository
→ Database

et les objets échangés entre chaque étape.

## data-model.md

Documente :

- entités principales ;
- relations ;
- tables importantes ;
- clés ;
- contraintes ;
- objets métier ;
- DTO ;
- mappings ;
- règles d'intégrité.

## integrations.md

Documente toutes les interactions avec des systèmes externes :

- APIs ;
- messaging ;
- Kafka ;
- services internes ;
- fichiers ;
- batch ;
- LDAP ;
- bases externes ;
- autres dépendances.

Pour chaque intégration :

- responsabilité ;
- protocole ;
- entrée ;
- sortie ;
- configuration ;
- gestion des erreurs.

## security.md

Documente les mécanismes réellement présents :

- authentification ;
- autorisation ;
- rôles ;
- propagation d'identité ;
- headers ;
- filtres ;
- sécurité des endpoints ;
- configurations.

## build-and-deployment.md

Documente :

- build local ;
- Maven/npm/etc. ;
- profils ;
- variables ;
- environnement ;
- packaging ;
- serveurs ;
- déploiement ;
- CI/CD ;
- Ansible si applicable ;
- fichiers de configuration ;
- différences importantes entre environnements.

## testing.md

Documente :

- stratégie de tests ;
- tests unitaires ;
- intégration ;
- mocks ;
- fixtures ;
- outils ;
- commandes ;
- zones mal couvertes ;
- validations importantes avant livraison.

## troubleshooting.md

Capitalise particulièrement sur les problèmes difficiles que tu as appris à diagnostiquer pendant notre travail.

Mais écris-les comme des problèmes de l'application actuelle.

Structure recommandée :

Symptôme
→ causes possibles
→ éléments à vérifier
→ diagnostic
→ solution

Inclure les fichiers/classes/configurations associés.

## conventions.md

Identifie les conventions du projet :

- naming ;
- structure des packages ;
- patterns ;
- organisation ;
- gestion des erreurs ;
- DTO ;
- mapping ;
- logging ;
- configuration ;
- règles implicites observées.

## glossary.md

Explique :

- acronymes ;
- termes métier ;
- noms spécifiques au projet ;
- concepts techniques propres à l'application.

---

Ensuite crée :

.claude/skills/application-expert/SKILL.md

Cette Skill doit permettre à Claude de répondre aux questions concernant l'application.

Son rôle est de :

1. identifier le domaine concerné ;
2. consulter uniquement les documents pertinents sous docs/application-knowledge ;
3. vérifier l'information dans le code actuel ;
4. analyser les dépendances et impacts ;
5. répondre avec des références précises au code lorsque possible.

La documentation est une aide à la navigation et à la compréhension.

Le code actuel reste la source de vérité finale.

---

Crée également :

.claude/skills/troubleshoot-application/SKILL.md

Cette Skill doit guider Claude lorsqu'on lui présente :

- une erreur ;
- une exception ;
- un comportement inattendu ;
- un problème de configuration ;
- un problème de build ;
- un problème de déploiement ;
- une régression.

Elle doit :

1. rechercher si le problème est déjà documenté ;
2. identifier les composants concernés ;
3. inspecter le code et la configuration ;
4. établir plusieurs hypothèses ;
5. proposer des vérifications permettant de discriminer les hypothèses ;
6. identifier la cause racine avant de proposer une correction lorsque possible.

---

Crée :

.claude/skills/update-application-knowledge/SKILL.md

Cette Skill doit permettre de maintenir la base de connaissance.

Lorsqu'elle est utilisée :

1. analyser les changements récents du repository ;
2. déterminer les documents impactés ;
3. mettre à jour uniquement les sections nécessaires ;
4. ajouter les nouvelles connaissances importantes ;
5. ajouter les nouveaux problèmes diagnostiqués dans troubleshooting.md ;
6. mettre à jour architecture.md lorsqu'une évolution architecturale significative apparaît ;
7. éviter les informations temporaires ou anecdotiques ;
8. ne jamais documenter quelque chose qui ne peut pas être vérifié.

---

Crée ensuite :

.claude/agents/application-expert.md

Cet agent représente un développeur senior connaissant extrêmement bien cette application.

Il doit être capable de :

- expliquer un comportement fonctionnel ;
- retrouver l'implémentation correspondante ;
- expliquer un flux end-to-end ;
- analyser l'impact d'une modification ;
- identifier les dépendances ;
- comprendre les objets échangés ;
- retrouver les configurations ;
- expliquer les choix architecturaux visibles dans le système ;
- aider à diagnostiquer un problème.

Il doit combiner :

documentation
+
inspection du code actuel
+
historique Git lorsque cela apporte réellement de la valeur.

Il ne doit jamais considérer la documentation comme plus fiable que le code.

---

Analyse également le CLAUDE.md existant.

Il doit rester compact.

Il doit contenir uniquement les informations qu'une instance Claude doit connaître quasiment tout le temps, par exemple :

- nature de l'application ;
- stack principale ;
- organisation générale ;
- commandes essentielles ;
- conventions critiques ;
- emplacement de docs/application-knowledge ;
- instruction de consulter cette base lorsqu'une compréhension approfondie du projet est nécessaire.

Ne copie pas toute la documentation dans CLAUDE.md.

---

IMPORTANT :

La base de connaissance doit décrire L'APPLICATION ACTUELLE.

Ne structure aucune documentation autour d'une migration passée.

Ne crée aucun fichier nommé migration-*.

Ne crée aucun agent nommé migration-*.

Ne crée aucune skill nommée migration-*.

Ne compare pas systématiquement l'application avec une version précédente.

Si une connaissance provenant de notre travail passé est utile, transforme-la en connaissance intemporelle sur le fonctionnement actuel de l'application.

---

Pour chaque information importante, distingue mentalement :

FACT
Information vérifiée dans le code ou la configuration.

INFERENCE
Conclusion raisonnable obtenue par analyse du code.

UNKNOWN
Élément qui ne peut pas être déterminé avec suffisamment de certitude.

N'invente jamais une information pour compléter la documentation.

---

Effectue enfin une deuxième passe.

Cherche spécifiquement la connaissance que tu possèdes grâce à notre long travail sur cette application et qui ne serait PAS évidente pour une nouvelle instance de Claude qui analyserait simplement le repository aujourd'hui.

C'est cette connaissance à forte valeur ajoutée que je veux particulièrement préserver.

Transforme-la en connaissance durable de l'application actuelle.

À la fin, donne-moi :

1. les connaissances importantes capitalisées ;
2. les domaines pour lesquels la documentation est particulièrement riche ;
3. les zones encore mal comprises ;
4. les informations que tu n'as pas pu vérifier.