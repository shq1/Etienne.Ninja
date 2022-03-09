---
title: "Protection de son identité numérique"
tags: ["Sécurité 101", "Général"]
date: 2021-03-07T12:16:03-05:00
draft: false
---
Peut-être que vous aimeriez mieux protégez votre vie privée, mais vous ne savez pas par où commencer? Commencez par lire cette page.
Nous avons tous une vie sur internet et pourtant la sécurité de cette identité est souvent négligée. 

Je vous suggère deux étapes importantes pour corriger cette négligence.


******
## Étape 1 - Voute de mot de passe


Si vous n'utilisez pas de voûte, vous utilisez probablement un "pattern" douteux facile à deviner pour la création de vos mots de passe. Ou encore pire, vous réutilisez le même!

### Pourquoi est-ce important?

Il est possible de trouver des mots de passe rendus publics suite à une attaque informatique. Un peu n'importe qui a accès à certains de vos mots de passe... est-ce le même que tu utilises aujourd'hui? Des sites permettent de savoir si vos mots de passe sont sur internet. Le site [https://haveibeenpwned.com/](https://haveibeenpwned.com/) est un des services les plus simples à utiliser, mais loin d'être le seul. Par exemple, si je rentre une de mes plus vieilles adresses courriel, le site me donne 9 brèches de sécurité. Linkedin en 2016, Dropbox en 2012, Adobe en 2013 ... 

Pour faire simple, le moyen le plus simple de voler l'identité d'une personne est de télécharger des mots de passe maintenant rendue publique suite à une attaque informatique, trouver les mots de passe lié à votre nom utilisateur ou courriel, et les essayer...!

### Quels sont mes choix?

Un défi dans le choix de l'outil qui héberge nos précieux mots de passe c'est l'équilibre entre la confiance qu'on leur accorde et sa facilité d'utilisation. Mais je crois que n'importe quelle voute est mieux que d'utiliser le même mot de passe.
##### Option 1) Utilisez un gestionnaire de mot de passe en ligne.
Il y en a beaucoup et je n'ai pas l'intention de faire un comparable, mais j'ai utilisé un certain temps LastPass. Aujourd'hui j'encourage fortement les outils qui sont à code ouvert (Open source). Ce qui veut dire que n'importe qui peut voir comment le code fonctionne et donne une transparence à l'outil. Bitwarden est gratuit et open source et je crois que c'est l'une des meilleures solutions pour la majorité des gens.
##### Option 2) Utilisez un gestionnaire de mot de passe local.
Si vous ne faites pas confiance au cloud, vous pouvez choisir un outil que vous installez sur votre ordinateur. Le plus populaire est Keepass: gratuit, open source et local sur votre machine. Dans l'open source, plusieurs "version" (fork) d'un logiciel peut apparaitre. Dans mon cas, j'utilise l'application **KeepassXC**. L'outil génère un fichier par exemple password.kdbx chiffré avec le mot de passe (complexe) que j’ai choisi. Cette solution n'est pas pour tout le monde, parce qu'il n'y a pas de synchronisation native entre les différents appareils (laptop, cellulaire, tablette...). Dans mon cas, je sauvegarde mon fichier chiffré dans un cloud et j'y accède grâce à l'application Android keepassDX qui est lui aussi open source. La grosse différence ici c'est le fournisseur cloud ne gère pas le mot de passe maitre qu'on utilise pour déchiffrer le fichier. Contrairement aux solutions "clé en main" comme Lastpass et bitWarden qui reçoivent le mot de passe principale pour déchiffrer et gèrent le fichier.

Personnellement, j'ai appris par coeur quatre mots de passe, le reste, c'est dans une voute. 
1. Mon laptop personnel
2. Ma voute de mot de passe
3. Mon laptop professionnel 
4. Ma voute de mot de passe au travail

Si vous êtes comme moi et avez la difficulté à vous rappeler d'un mot de passe complexe, minimum 12 caractères, je suggère 16+ , écrivez-le sur un papier physique (pas numérique) jusqu'à ce que vous vous en rappelez. Évidemment, gardez-le dans un lieu sûr où le moins de gens possible ont accès à cette pièce (la chambre à coucher est habituellement un excellent endroit...). Ne le prenez pas en photo, vous pouvez changer le Xieme caractère "au cas où" et ne mettez pas de contexte au papier. Mangez-le lorsqu'il ne sera plus nécessaire. À moins que vous soyez une personnalité publique, il est plutôt rare de voir une intrusion physique chez soit pour voler son identité numérique. Mais ce n'est pas impossible non plus ;)
Dorénavant, tous vos mots de passe devraient être très complexes et générés aléatoirement. Comme vous allez utiliser un plugin à votre navigateur (évitez l'option copier/collée), pourquoi rester à 8 caractères? La voute vous permet ainsi d'avoir des mots de passe différents pour chaque application, généré aléatoirement et suffisamment complexe pour éviter un "crackage".

## Étape 2 - 2e facteur d'authentification

### Pourquoi est-ce important?

Une séquence de lettres et de chiffres n'est pas grand chose pour protéger une vie complète sur internet. Imaginez que je réussisse à mettre la main sur le mot de passe de votre adresse courriel. Pour plusieurs, je peux détruire votre vie numérique avec l'accès à votre simple courriel. On se rappelle que la majorité des sites offre l'option "j'ai oublié mon mot de passe" qui résulte à l'envoi d'un courriel pour le réinitialiser. Et un peu de recherche dans votre boîte pourrait **peut-être** me fournir les réponses aux questions secrètes comme le nom de votre meilleur ami, le prénom de votre grand-mère...

Votre mot de passe se retrouve à plusieurs endroits: dans votre presse papier (en mémoire avec l'action de copier-collé), votre navigateur internet, chez le fournisseur de service et dans votre voute! C'est beaucoup d'endroits pour quelque chose d'aussi important.
Déjà que les attaques sont parfois inconnu de l'entreprise même, il n'y a pas de répertoire centralisé de tous les mots de passe qui ont été exfiltrés. Et non, une recherche Google n'est pas suffisante pour vous en assurer. Le message important à comprendre c'est que nous ne savons jamais si notre mot de passe a été compromis, que ce soit de votre faute, ou non!
Alors votre mot de passe, même complexe et unique pourrait se retrouver chez le côté obscur de la force.

### Quels sont mes choix?

##### Option 1) Mot de passe a usage unique par SMS
La majorité des services supportent maintenant les messages textes. C'est la méthode la moins robuste, mais c'est toujours mieux que juste un mot de passe! Le problème avec cette solution c'est si j'appelle votre fournisseur de téléphone et je tente de me faire passer pour vous, je les convaincs que j'ai changé de téléphone et j'ai une nouvelle carte SIM. Je recevrai ensuite vos messages textes. Les compagnies ont mis en place des contrôles, comme demander un NIP pour vous authentifier au téléphone, mais ce n'est pas leur rôle de protéger votre identité sur internet!
##### Option 2) Mot de passe a usage unique avec une application
De plus en plus de service offre aussi des applications qui génèrent chaque minute un mot de passe unique utilisable pendant quelques minutes seulement. L'application "Authenticator" de Google ou de Microsoft sont assez populaire. De mon côté, je suis en train de migrer Google Authenticator vers andOTP qui est open source pour les sites qui ne supportent pas mon option 3.
##### Option 3) Une clé d'authentification physique.
Si vous prenez la sécurité au sérieux, considérez l'achat de deux clés physiques. Dans mon cas, j'utilise des Yubikey. C'est une clé usb qui doit être insérée dans le port USB lors de l'authentification, malheureusement, ce ne sont pas tous les services web qui le supportent encore. Actuellement je l'utilise que sur mon gmail et un autre service. J'active toujours les deux Yubikey pour le même service, au cas où j'en perds une.

Ne partez pas en peur avec toute cette sécurité!  Après une première authentification, il est possible "de se souvenir de cet ordinateur". On évite ainsi d'utiliser le 2e facteur à chaque connexion. Mais il sera requis pour chaque nouvel appareil.

Les prochaines étapes sont entre vos mains. Allez donc vous créer un compte si vous n'avez rien: [https://bitwarden.com/](https://bitwarden.com/)