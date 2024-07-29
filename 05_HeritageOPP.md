Chapitre : HERITAGE DE CLASSE

A-  Qu'est-ce que l'héritage de classe ?

    L'héritage de classe est un concept crucial dans la programmation orientée objet (OOP) où une classe, également appelée sous-classe ou classe enfant, peut hériter des propriétés et des méthodes d'une autre classe, appelée superclasse ou classe parent. Cela fournit un moyen structuré d'étendre les classes précédemment créées avec des propriétés et des méthodes supplémentaires. Cela signifie que nous voulons une nouvelle classe qui possède les propriétés et les méthodes de la classe précédente. Cela permet de pouvoir réutiliser du code et d'établir des relations entre les classes.

B-  Créer une sous-classe

    Pour créer une sous-classe ou étendre une classe parent, nous utilisons le mot-clé class suivi du nom de la sous-classe. Nous avons ensuite le mot-clé extends qui permet de spécifier la super-classe, la classe parent ou la classe dont nous voulons étendre ou hériter. Nous avons les accolades dans lesquelles nous ajoutons les propriétés et les méthodes que nous souhaitons ajouter.

    L'exemple de cette section impliquera la création d'une méthode à l'intérieur de la sous-classe pour répertorier tous les noms et couleurs de tous les objets animaux qui ont été créés à partir de la superclasse Animal.

        https://i.imgur.com/GkgT06X.png

        // our instances of the animal class
        const dog = new Animal("dog", "black", "true", "barks");
        const lion = new Animal("lion", "gold", "false", "roar");
        const goat = new Animal("goat", "black", "false", "bleats");
        const mosquito = new Animal("mosquito", "black", "false", "buzz");


        // an array of the animal objects created
        const animal = [dog, lion, goat, mosquito];


        // the subclass created from the Animal super class
        class ListAllAnimals extends Animal {
                
            ListAllAnimalNameAndColors() {
                
                animals.map((animal) => {
                    
                console.log(animal.name, animal.color);
                
                });
                
            }

        }

        // an instance of the ListAllAnimals class
        const listAllAnimals = new ListAllAnimals();

        // accessing the method created inside the ListAllAnimals class
        listAllAnimals.ListAllAnimalNameAndColors();

    Il est essentiel de noter que si la sous-classe n'a pas de constructeur, elle utilisera le constructeur de la super-classe. Un autre fait digne de mention est que la super-classe n'a pas accès aux propriétés ou aux méthodes de la sous-classe. Toute tentative d'accès à la sous-classe à partir de la super-classe générera une erreur.

        https://i.imgur.com/WxQZ6qt.png

        // our instances of the animal class
        const dog = new Animal("dog", "black", "true", "barks");
        const lion = new Animal("lion", "gold", "false", "roar");
        const goat = new Animal("goat", "black", "false", "bleats");
        const mosquito = new Animal("mosquito", "black", "false", "buzz");


        // an array of the animal objects created
        const animal = [dog, lion, goat, mosquito];


        // the subclass created from the Animal super class
        class ListAllAnimals extends Animal {

            ListAllAnimalNameAndColors() {

                animals.map((animal) => {
                console.log(animal.name, animal.color);
                });

            }

        }


        // an instance of the ListAllAnimals class
        const listAllAnimals = new ListAllAnimals();

        // accessing the method created inside the ListAllAnimals class
        listAllAnimals.ListAllAnimalNameAndColors();

    Nous pouvons observer à partir de l’exemple que la tentative a généré une erreur.

C-  Créer des sous-classes avec des constructeurs de la superclasse

    La création d'une sous-classe possédant un constructeur nécessite que le mot-clé super soit utilisé pour accéder aux propriétés de la classe parent. Dans l'exemple de cette section, nous allons étendre la classe Animal pour créer une classe AnimalClassification. Avec cette nouvelle classe, nous voulons commencer par ajouter une fonction pour classer un animal en fonction de son ordre (carnivore, herbivore ou insectivore). Nous allons ensuite étendre notre classe Animal pour prendre en compte une propriété order, puis créer la fonction pour classer nos objets animaux dans notre classe étendue.

    Dans l'exemple ci-dessous, nous voyons que l'ajout de la propriété order lors de la tentative d'accès à la propriété name a provoqué une erreur.

        https://i.imgur.com/YapqjKB.png

        class AnimalClassification extends Animal{
            // constructor method to initialize object properties
            constructor(order) {
                this.order = order;
            }
            
            classifyByOrder(animalName) {
                const animalClass = animals.find((animal) => animal.name === animalName)

                if(animalClass){

                    console.log(`${animalClass.name} is a ${animalClass.order}`);

                } else{

                    console.log(`${animalName} class not found`);

                }

                return this;
            }
        }

        const goat = new AnimalClassification("goat", "herbivore")

        const dog = new AnimalClassification("dog", "herbivore")

        const lion = new AnimalClassification("lion", "herbivore")

        const mosquito = new AnimalClassification("mosquito", "herbivore")
        
        // array of AnimalClassification objects
        const animals = [dog, lion, goat, mosquito]

        // create a classifier object from the AnimalClassification class
        const classifier = new AnimalClassification()

        // use the classifier object to get the order of the animal
        classifier.classifyByOrder("mosquito")

    Pour résoudre cette erreur, il faut appeler super() afin d'invoquer le constructeur de la superclasse. Cela garantit l'initialisation correcte des propriétés de la superclasse avant l'ajout de propriétés pour la sous-classe. Nous avons la correction dans l'image ci-dessous.

        https://i.imgur.com/jfYzW8Z.png

        class AnimalClassification extends Animal{

            // constructor method to initialize object properties
            constructor(name, order) {

                super(name)
                this.order = order;

            }
            
            classifyByOrder(animalName) {

            const animalClass = animals.find((animal) => animal.name === animalName)


            if(animalClass){

                console.log(`${animalClass.name} is a ${animalClass.order}`);

            } else{

                console.log(`${animalName} class not found`);

            }

            return this;
            }

        }

        const goat = new AnimalClassification("goat", "herbivore")
        const dog = new AnimalClassification("dog", "herbivore")
        const lion = new AnimalClassification("lion", "herbivore")
        const mosquito = new AnimalClassification("mosquito", "herbivore")

        // array of AnimalClassification objects
        const animals = [dog, lion, goat, mosquito]

        // create a classifier object from the AnimalClassification class
        const classifier = new AnimalClassification()

        // use the classifier object to get the order of the animal
        classifier.classifyByOrder("mosquito")

        https://i.imgur.com/90jwtM6.png

    À partir de l’image ci-dessus, nous pouvons voir que nous classons avec succès les animaux selon leur ordre en utilisant l’approche orientée objet.

        class AnimalClassification extends Animal{
            // constructor method to initialize object properties
            constructor(name, order) {
                super(name)
                this.order = order;
            }

            classifyByOrder(animalName) {
            const animalClass = animals.find((animal) => animal.name === animalName)

            if(animalClass){
                console.log(`${animalClass.name} is a ${animalClass.order}`);
            } else{
                console.log(`${animalName} class not found`);
            }

            return this;
            }
        }
        const goat = new AnimalClassification("goat", "herbivore")
        const dog = new AnimalClassification("dog", "herbivore")
        const lion = new AnimalClassification("lion", "herbivore")
        const mosquito = new AnimalClassification("mosquito", "herbivore")

        // array of AnimalClassification objects
        const animals = [dog, lion, goat, mosquito]

        // create a classifier object from the AnimalClassification class
        const classifier = new AnimalClassification()

        // use the classifier object to get the order of the animal
        classifier.classifyByOrder("mosquito")
        classifier.classifyByOrder("goat")
        classifier.classifyByOrder("dog")
        classifier.classifyByOrder("lion")

D-  Accéder aux méthodes de la superclasse à partir de la sous-classe

    L'accès aux méthodes d'une superclasse nécessitera quelques ajouts à notre code précédent. À la classe Animal, nous ajoutons une méthode très simple appelée animalIdentity que nous utiliserons pour enregistrer le nom de l'animal dans la console. Cette nouvelle méthode sera accessible dans la classe enfant AnimalClassification.

        https://i.imgur.com/P1cVkQX.png

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
                if (this.isWild === "false") {
                console.log(`${this.name} is a domestic animal that ${this.sound}`);
                return this;
                } else {
                console.log(`${this.name} is a wild animal that ${this.sound}`);
                return this;
                }
            }

            animalName() {
                console.log(`This is a/an ${this.name}`);
            }
        }

        class AnimalClassification extends Animal {
            // constructor method to initialize object properties
            constructor(name, order) {
                super(name);
                this.order = order;
            }

            classifyByOrder(animalName) {
                const animalClass = animals.find((animal) => animal.name === animalName);
                if (animalClass) {
                console.log(`${animalClass.name} is a/an ${animalClass.order}`);
                } else {
                console.log(`${animalName} class not found`);
                }
                return this;
            }


            animalIdentity() {
                super.animalName();
            }
        }
        const dog = new AnimalClassification("dog", "carnivore", "barks");
        dog.animalIdentity();



