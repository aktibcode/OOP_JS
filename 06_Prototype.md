Chapitre : PROTOTYPE

A-  Introduction

    Avant l'avènement des classes, l'utilisation de la méthode prototype était la méthode d'origine pour créer des classes en JavaScript. Elle fonctionne toujours de la même manière que lors de l'utilisation du mot-clé class. L'un des objectifs est de permettre la compréhension des bases de code écrites avec cette méthode. Lorsque nous créons un objet à l'aide du mot-clé class, la fonction constructeur est chargée de lier toutes les propriétés et valeurs à l'objet.

    Lorsque nous envisageons d'utiliser la méthode prototype, nous utilisons le mot-clé function pour créer notre objet qui servira de fonction constructeur qui représente désormais notre objet de classe. Pour créer la fonction constructeur :

        1-  On tape le mot clé de la fonction, puis le nom de l'objet avec une majuscule 
        2-  puis on ajoute des parenthèses [()]
        3-  Les propriétés nécessaires à la construction de l'objet sont passées en paramètres entre parenthèses.
        4-  et enfin, les accolades [{}] où nous allons continuer à ajouter toutes les propriétés nécessaires.

    Nous allons voir un exemple de cela toujours en utilisant notre classe Animal.

            https://i.imgur.com/uoSMsPG.png
    
        function Animal(name, color, isWild, sound) {

            this.name = name;
            this.color = color;
            this.isWild = isWild;
            this.sound = sound;

        }

        const dog = new Animal("dog", "black", false, "barks");
        console.log(dog);

    Il est important de noter que rien ne change dans la façon dont nous créons une nouvelle instance de cette classe. Nous utilisons toujours le mot-clé new.

    Les méthodes peuvent également être créées à l'intérieur de la fonction qui représente maintenant notre classe d'objet. La création d'une méthode ici est un peu différente de la façon dont nous l'avons créée précédemment. Pour créer une méthode :

        1-  Cela commence avec un mot-clé this
        2-  en utilisant un point, nous lions le nom de la méthode que nous voulons créer au mot-clé this
        3-  Enfin, nous attribuons une fonction (créée avec le mot-clé function) à l'étape précédente en utilisant l'opérateur d'affectation (=).

            https://i.imgur.com/KxDeVq4.png

        function Animal(name, color, isWild, sound) {

            this.name = name;
            this.color = color;
            this.isWild = isWild;
            this.sound = sound;

            // adding a method
            this.aboutAnimal = function () {

                return `the ${this.color} colored ${this.name} ${this.sound}`;

            };

        }

        const dog = new Animal("dog", "black", false, "barks");
        console.log(dog.aboutAnimal());

    Bien que l'ajout de méthodes comme celle-ci fonctionne, il est généralement préférable d'attacher des méthodes à des objets comme celui-ci en utilisant la propriété de l'objet prototype.

        function Animal(name, color, isWild, sound) {

            this.name = name;
            this.color = color;
            this.isWild = isWild;
            this.sound = sound;

            // adding a method
            this.aboutAnimal = function () {

                return `the ${this.color} colored ${this.name} ${this.sound}`;

            };

        }

        const dog = new Animal("dog", "black", false, "barks");
        console.log(dog);

B-  Qu'est-ce qu'un prototype ?

    Jusqu'à présent, nous avons vu une autre méthode de création de la fonction constructeur et de son utilisation pour stocker les propriétés d'une classe tout en attachant une méthode à cette classe. Nous allons maintenant examiner de plus près les prototypes. En JavaScript, chaque objet (par exemple, les tableaux, les dates, etc.) possède par défaut une propriété nommée prototype. Cette propriété est un objet qui devient le prototype des objets créés à l'aide de la fonction constructeur.

    Lorsque vous regardez notre classe Animal dans le navigateur, nous observons qu'il existe une propriété prototype. Nous observons également que la méthode aboutAnimal() créée est stockée directement sur l'objet Animal contrairement à la manière dont elles étaient stockées dans la propriété d'objet [[Prototype]] à l'intérieur de la classe pour les objets créés à l'aide du mot-clé class.

        https://i.imgur.com/u86AYup.png

    Pour améliorer l'efficacité, nous devrons attacher la méthode que nous avons créée à l'objet [[Prototype]]. Pour ce faire, nous utilisons la propriété d'objet prototype. Elle nous montre toutes les méthodes attachées à cette classe. Nous voyons toutes les méthodes attachées à la classe lorsque nous développons la propriété prototype. Le prototype est comme une carte de l'objet dans lequel il se trouve, il contient toutes les propriétés et méthodes associées à cet objet. Les nouvelles instances d'une classe d'objet hériteront de la propriété et de la méthode d'un prototype. Cela nous permettra de travailler avec le concept d'héritage de prototype.

        https://i.imgur.com/tD9oJZO.png

    À partir de l'image, nous voyons que la méthode est maintenant stockée à l'intérieur de la propriété de l'objet prototype, comme une carte de l'objet dans lequel elle se trouve, elle contient toutes les propriétés et méthodes associées à cet objet. Les nouvelles instances d'une classe d'objet hériteront de la propriété et de la méthode d'un prototype. Cela nous permettra de travailler avec le concept d'héritage de prototype.

        function Animal(name, color, isWild, sound) {

            this.name = name;
            this.color = color;
            this.isWild = isWild;
            this.sound = sound;

        }

        Animal.prototype.aboutAnimal = function(){

            return `the ${this.color} colored ${this.name} ${this.sound}`;

        }

        const dog = new Animal("dog", "black", false, "barks");
        console.log(dog);
        console.log(dog.aboutAnimal());

C-  Ajout d'une propriété à l'aide d'un prototype

    Auparavant, nous avions ajouté des méthodes à l'aide de prototypes. Nous pouvons également ajouter des propriétés à l'aide de la propriété d'objet prototype.

    Pour le créer, comme dans la méthode, nous devons saisir la classe parent et obtenir le prototype en utilisant la notation par points : Animal.prototype puis continuer en ajoutant les propriétés que nous aimerions ajouter à notre classe déjà créée et enfin lui attribuer une variable. Pour notre exemple, nous allons ajouter une propriété appelée order.

        https://i.imgur.com/5S3g6Nd.png

    D'après le résultat, il est évident que la méthode et la propriété ajoutées de cette manière sont stockées sur la propriété de l'objet prototype. Ce que nous avons fait jusqu'à présent est de définir la propriété order et la méthode aboutAnimal sur le prototype de l'objet chien. C'est une bonne chose pour les méthodes puisque nous n'avons plus besoin de les définir à l'intérieur de la classe parent après la fonction constructeur. Le prototype de la nouvelle instance va pointer vers le prototype de la classe Animal. Dans notre cas, l'instance chien hérite de la propriété order et de la méthode aboutAnimal du prototype de la classe parent. Nous accédons également à la propriété d'un objet à partir d'un prototype de la même manière que pour la méthode.

        function Animal(name, color, isWild, sound) {
                
            this.name = name;
            this.color = color;
            this.isWild = isWild;
            this.sound = sound;

        }

        // adding a METHOD using the prototype object method
        Animal.prototype.aboutAnimal = function () {

            return `the ${this.color} colored ${this.name} ${this.sound}`;

        };

        // adding a PROPERTY using the prototype object method
        Animal.prototype.order = "carnivore";

        const dog = new Animal("dog", "black", false, "barks");

        console.log(dog);

        // accessing the property
        console.log(dog.order);

    Il est important de noter que nous ne pouvons pas ajouter de propriétés ou de méthodes aux nouvelles instances de notre classe Animal en utilisant l'objet prototype. En effet, les instances de la classe n'ont pas de prototype propriété directement accessible comme le mot-clé des fonctions constructeurs. Au lieu de cela, la prototype propriété est associée à la classe elle-même.

        https://i.imgur.com/DRYDQAc.png

        function Animal(name, color, isWild, sound) {

            this.name = name;
            this.color = color;
            this.isWild = isWild;
            this.sound = sound;

        }

        // adding a METHOD using the prototype object method
        Animal.prototype.aboutAnimal = function () {

            return `the ${this.color} colored ${this.name} ${this.sound}`;

        };


        // adding a PROPERTY using the prototype object method
        Animal.prototype.order = "carnivore";


        // an instance of the class
        const dog = new Animal("dog", "black", false, "bark");
        dog.prototype.habitat = "country";

    Dans certains codes, vous verrez des prototypes ajoutés à l'aide de proto comme indiqué dans l'extrait de code ci-dessous

        Animal.__proto__.order = "carnivore";


