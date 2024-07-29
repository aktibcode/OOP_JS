Chapitre : LES CLASSES

A-  Code sans JavaScript orienté objet

    Créer plusieurs objets (comme illustré dans l'exemple ci-dessous) avec les mêmes propriétés et méthodes peut rapidement devenir un processus mouvementé, produisant de longues lignes de code inutiles tout en niant le principe de programmation DRY (Don't Repeat Yourself).

        https://i.imgur.com/smdXth6.png

        let animalOne = {
            name: "Dog",
            color: "black",
            isWi1d: false,
            makeSound() {
                console.log(`${this.name} barks`);
            },
        };

        let animalTwo = {
            name: "Cat",
            color: "white",
            isWi1d: false,
            makeSound() {
                console.log(`${this.name} barks`);
            },
        };

        let animalThree = {
            name: "Lion",
            color: "Gold",
            makeSound() {
                console.log(`${this.name} roars`);
            },
        };

B-  Une approche bien meilleure

    Une méthode plus simple consiste à créer des classes, puis des instances de ces classes. Les classes nous permettent de créer des objets qui partagent des objets et des méthodes similaires. Elles sont considérées comme un modèle pour la création d'objets qui nous permettent de définir un ensemble de propriétés et de méthodes que toutes les instances de la classe auront. L'introduction de la syntaxe de classe dans ECMAScript 2015 (ES6) a créé une approche orientée objet de la programmation en JavaScript.

    Dans notre cas avec l'objet animal, au lieu de créer plusieurs objets animaux, nous pouvons créer un animal puis plusieurs instances de ces animaux. Les étapes pour créer des classes incluent :

        *   Le mot-clé de la classe

        *   Suivi du nom de la classe (qui commence généralement par une majuscule par convention)

        *   Puis les accolades ({})

        *   À l'intérieur des accolades, nous ajoutons que notre méthode constructeur est une fonction qui effectue la création ou la construction réelle de nos objets. Elle est responsable de la création de nouvelles instances de la classe

        *   Les méthodes que nous aimerions ajouter à notre classe

            https://i.imgur.com/1nHe9Wv.png

        class Animal{

            // constructor method to initialize object properties
            constructor(name, colour, isWi1d) {

                this.name = name;
                
                this.colour = colour;
                
                this.iswild = iswild;

            }

            // can add your methods here
        }

    Nous observons que dans l'exemple ci-dessus, lorsque nous avons créé la classe animal, nous n'avons pas eu à spécifier le nom, la couleur, la classification ou le son émis par l'animal. Ces spécifications seront indiquées lorsque nous créerons des instances de la classe animal. Les arguments ajoutés à la méthode constructeur nous permettent d'ajouter dynamiquement les valeurs que nous préférons chaque fois que nous créons une nouvelle instance d'une classe. Dans notre cas, avoir name, colour, isWild comme arguments nous permet de passer les valeurs de notre choix pour chacune de ces propriétés. C'est mieux que de coder en dur les valeurs.

    Il est important de noter que ce mot-clé utilisé à l'intérieur de la fonction constructeur fait référence à chaque nouvel objet créé à partir de la classe. Ce mot-clé appelle la méthode constructeur avant de pouvoir continuer à ajouter des propriétés et des méthodes à notre nouvelle instance.

C-  Créer une nouvelle instance d'une classe

    Lorsque nous créons une nouvelle instance de la classe animal, nous créons un nouvel objet animal. À ce stade, nous passons les paramètres tels que le nom, la couleur, etc. Le mot-clé new :

        *   Crée un objet vide let animalOne = new Animal(),
        
        *   continue de définir la valeur de « this » pour qu'elle soit le nouvel objet vide au moment de sa création et
        
        *   appelle enfin la méthode constructeur.

            https://i.imgur.com/NQc05bc.png

        class Animal {

            // constructor method to initialize properties
            constructor(name, colour, isWi1d) {

                this.name = name;
                this.colour = colour;
                this.isWi1d = isWi1d;

            }
          // you an add your methods here
        }

        // creating instances of the animal class
        let animalOne = new Animal("dog", "black", false);
        console.log(animalOne);

        let animalTwo = new Animal("Lion", "gold", true);
        console.log(animalTwo);


