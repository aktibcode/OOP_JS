Chapitre : METHODE DE CLASSE

A-  Que sont les méthodes ?
    
    Auparavant, nous avons appris à créer des objets en utilisant une classe pour créer plusieurs instances de cet objet. Maintenant, nous allons découvrir les méthodes et l'ajout de méthodes à la classe que nous avons créée. Nous nous souvenons que les méthodes sont des fonctions associées à des objets et appelées sur des objets, permettant ainsi aux objets d'effectuer des actions ou des calculs. Les méthodes nous permettent d'encapsuler le comportement au sein de l'objet. Elles opèrent sur les données de l'objet.

    La compréhension et l'utilisation efficace des méthodes dans les objets sont essentielles pour développer un code maintenable en JavaScript. Les méthodes permettent l'encapsulation de la logique dans les objets, favorisant ainsi une structure de code plus propre et mieux organisée.

B-  Comment ajouter des méthodes aux classes

    Pour ajouter des méthodes à notre classe, nous les plaçons immédiatement après la méthode constructeur. Vous trouverez ci-dessous un exemple de création de méthodes, en utilisant notre exemple précédent avec la classe animal. Dans l'exemple, nous ajoutons la méthode makeSound à notre classe Animal. De retour dans notre constructeur pour la classe Animal, nous avons ajouté la propriété sound afin de voir la méthode makeSound en action.

        https://i.imgur.com/VyTT9el.png

        class Animal {

            // constructor method to initialize object properties
            constructor(name, color, isWi1d, sound) {

                this.name = name;
                this.color = color;
                this.isWi1d = isWi1d;
                this.sound = sound;

            }

            // you can add your methods here
            makeSound() {

                console.log(`${this.name} ${this.sound}`);

            }
        }

C-  Accéder aux méthodes d'une classe

    Pour pouvoir accéder à toutes les méthodes créées dans une classe, nous devons créer une instance de cette classe. Pour rendre les choses plus intéressantes, nous utiliserons un exemple dans lequel nous ajouterons une méthode supplémentaire appelée aboutAnimal et créerons deux instances de la classe Animal, un chien et un lion. Nous procéderons ensuite à l'appel des méthodes makeSound et aboutAnimal sur eux.

        https://i.imgur.com/Nj9EPQ8.png

        class Animal {

            // constructor method to initialize object properties
            constructor (name, color, isWild, sound) {

                this.name = name;
                this.color = color;
                this.isWild = isWild;
                this.sound = sound;

            }

            // you can add your methods here
            makeSound(){

                console. log(`${this.name} ${this.sound}`)

            }

            aboutAnimal(){

                console.log(`the ${this.color} colored ${this.name} ${this.sound}`)

            }

        }

        const dog = new Animal("dog", "black", "true", "barks");
        const lion = new Animal("lion", "gold", "false", "roar");


        // dog
        dog.makeSound()
        dog.aboutAnimal();


        // lion
        lion.makeSound() ;
        lion.aboutAnimal();

    À partir des résultats sur le navigateur, nous voyons que nous avons pu raconter une petite histoire sur les instances animales que nous avons créées en utilisant les propriétés présentes dans le constructeur. Il est intéressant de noter que lorsque l'objet est développé, nous voyons que nous avons les méthodes enregistrées dans la propriété proto dans le navigateur, nous pouvons voir les méthodes que nous avons créées.

        https://i.imgur.com/1fmq3PT.png

        class Animal {

            // constructor method to initialize object properties
            constructor(name, color, isWild, sound) {

                this.name = name;    
                this.color = color;
                this.isWild = isWild;
                this.sound = sound;

            }


            // you can add your methods here
            makeSound() {

                console.log(`${this.name} ${this.sound}`);

            }

            aboutAnimal() {

                console.log(`the ${this.color} colored ${this.name} ${this.sound}`);

            }

        }

        const dog = new Animal("dog", "black", "true", "barks");
        const lion = new Animal("lion", "gold", "false", "roar");

        console.log(dog);
        console.log(lion);

    Ce que nous avons réussi à faire jusqu'à présent est d'encapsuler tout ce que nous voulons savoir sur l'animal à l'intérieur de la classe Animal, des propriétés et des méthodes. C'est bien mieux que de créer de nombreux objets qui ont les mêmes propriétés et méthodes en utilisant un littéral d'objet comme nous l'avons vu précédemment au début de cette compétence.

D-  Enchaînement de méthodes

    Le chaînage de méthodes consiste à appeler plusieurs méthodes sur une seule instance d'une classe où nous exécutons une méthode et enchaînons d'autres méthodes. Les méthodes sont exécutées dans l'ordre dans lequel elles sont attachées à l'instance d'une classe. Si nous passons directement à l'exécution du chaînage de méthodes avec l'exemple existant, nous obtenons une erreur indéfinie comme indiqué ci-dessous.

        https://i.imgur.com/Sjhg2NG.png

        class Animal {

            // constructor method to initialize object properties
            constructor(name, color, isWild, sound) {

                this.name = name;
                this.color = color;
                this.isWild = isWild;
                this.sound = sound;

            }

            // you can add your methods here
            makeSound() {

                console.log(`${this.name} ${this.sound}`);

            }

            aboutAnimal() {

                console.log(`the ${this.color} colored ${this.name} ${this.sound}`);

            }

        }

        const dog = new Animal("dog", "black", "true", "barks");
        const lion = new Animal("lion", "gold", "false", "roar");

        lion.makeSound().aboutAnimal()

    Nous avons cette erreur car nous ne renvoyons pas l'instance de l'objet animal (dans ce cas, lion) à l'intérieur de la méthode makeSound. Sans cet accès à cette instance, nous ne pouvons pas exécuter une autre méthode sur l'objet. Étant donné que l'instance de l'objet est stockée dans this qui se trouve dans la méthode constructeur, nous devons la renvoyer (this) à la fin de la méthode. Ce qui se passe en coulisses, c'est qu'une fois la fonctionnalité stockée dans la méthode terminée, le retour de this nous donne accès à l'instance de l'objet particulier que nous avons créé à partir de la classe.

    Avoir accès à l'instance nous permet d'enchaîner méthode après méthode sur notre objet. Pour notre exemple, nous allons continuer à ajouter une autre méthode à notre classe Animal pour avoir une meilleure compréhension de l'enchaînement des méthodes sur les objets. Nous avons d'abord notre classe animal mise à jour suivie d'une image de l'instance créée et de l'enchaînement des méthodes

            https://i.imgur.com/Ke7i9Tg.png

        -   Image de notre classe d'animaux mise à jour

        class Animal {

            // constructor method to initialize object properties
            constructor(name, color, isWild, sound) {

                this.name = name;
                this.color = color;
                this.isWild = isWild;
                this.sound = sound;

            }


            // you can add your methods here
            makeSound() {

                console.log(`${this.name} ${this.sound}`);
                    return this;

            }


            aboutAnimal() {

                console.log(`the ${this.color} colored ${this.name} ${this.sound}`);

                    return this;

            }


            isDomestic() {

                if (this.isWi1d === "false") {

                console.log(`${this.name} is a domestic animal that ${this.sound}`);

                    return this;

                } else {

                console.log(`${this.name} is a wild animal ${this.sound}`);

                    return this;

                }
            }
        }

            https://i.imgur.com/hyNrOFB.png

        -   Image de notre chaînage d'objets et de méthodes

        // our instances of the animal class
        const dog = new Animal("dog", "black", "true", "barks");
        const lion = new Animal("lion", "gold", "false", "roar");


        // chaining our methods for the lion object
        lion.makeSound().aboutAnimal().isDomestic()
        console.log("\n");
        // chaining our methods for the dog object
        dog.makeSound().aboutAnimal().isDomestic();