Introduction au JavaScript orienté objet :

    *   JavaScript prend en charge le paradigme de programmation orienté objet.
    *   Les objets sont des instances de classes et ils encapsulent des données et un comportement.

Des classes:

    *   Les classes en JavaScript fournissent un modèle pour la création d'objets avec des propriétés et des méthodes partagées.
    *   Introduites dans ECMAScript 2015 (ES6), les classes offrent un sucre syntaxique par rapport à l'héritage basé sur le prototype existant de JavaScript.

Méthodes de classe :

    *   Les méthodes de classe sont des fonctions définies dans une classe qui peuvent être appelées sur des instances de cette classe.
    *   Ils sont définis à l’aide de la methodName() {}syntaxe dans la définition de classe.

Héritage de classe :

    *   L'héritage de classe permet à une classe (sous-classe/classe enfant) d'hériter des propriétés et des méthodes d'une autre classe (superclasse/classe parent).
    *   Les sous-classes peuvent étendre les fonctionnalités de leurs classes parentes en ajoutant de nouvelles méthodes ou en remplaçant celles existantes.
    *   En JavaScript, l'héritage est réalisé à l'aide du extendsmot-clé.

Prototype:

    *   Chaque objet JavaScript possède un prototype.
    *   Un prototype est comme une carte de l'objet dans lequel il se trouve, contenant des méthodes et des propriétés associées à cet objet.
    *   Il agit comme un mécanisme de secours pour l’accès à la propriété si la propriété n’existe pas directement sur l’objet.

Héritage du prototype :

    *   L'héritage de prototype fait référence au processus par lequel les objets héritent des propriétés et des méthodes de leur prototype.
    *   En JavaScript, les objets héritent des propriétés et des méthodes de leur chaîne de prototypes, qui comprend le prototype du constructeur de l'objet et le prototype de son constructeur, et ainsi de suite.
    *   Ce mécanisme permet la réutilisabilité du code et favorise le concept d'« héritage ».