Chapitre : HERITAGE DU PROTOTYPE

A-  Hériter des propriétés de l'objet parent

    Dans cette compétence, nous allons étendre la classe Animal que nous avons créée dans la leçon précédente. Cela nous permettra de comprendre l'héritage du prototype. Cette classe étendue aura toutes les propriétés de la classe parent. Pour ce faire, nous créons une fonction qui s'appellera DogLocation, qui nous indiquera simplement l'habitat du chien. Elle est créée comme la classe précédente avec le mot-clé function et le nom du constructeur en majuscules.

    Afin d'hériter des propriétés de l'objet parent, nous utilisons un paramètre rest(...) à l'intérieur des parenthèses de la classe étendue. Cela prendra les différentes propriétés fournies et les placera dans un tableau. Ce tableau est ensuite accessible à l'intérieur du corps (qui est constitué des accolades) de la classe étendue comme indiqué ci-dessous :

        https://i.imgur.com/PdKl6ry.png

    Le paramètre de repos pour notre exemple est …props.

        function Animal(name, color, isWild, sound) {

            this.name = name;
            this.color = color;
            this.isWild = isWild;
            this.sound = sound;

        }

        // adding a PROPERTY using the prototype object method
        Animal.prototype.order = "carnivore";

        // an instance of the class
        const dog = new Animal("dog", "black", false, "bark");


        function DogLocation(...props) {

            console.log(props);

        }

        const dogHabitat = new DogLocation("dog", "black", false, "bark");

    Maintenant que nous pouvons accéder aux propriétés en utilisant le paramètre rest, nous pouvons appeler la fonction parent (Animal), qui prendra toutes les propriétés et les appliquera à l'objet enfant (dogHabitat). Pour ce faire, le nom de la fonction est ajouté au corps de l'objet enfant, puis la méthode '.apply' est utilisée sur le nom de la fonction parent. La méthode apply prend 2 paramètres, le contenu de l'objet parent en utilisant ce mot-clé et les arguments réels (qui seront un tableau, …props) que nous recevons lors de la création d'une nouvelle instance de notre objet enfant. Cela nous permet de sélectionner les propriétés dont nous souhaitons hériter au lieu d'hériter de la totalité. Pour voir cette action, nous allons simplement hériter du nom et de la propriété colour et ajouter la propriété que nous souhaitons pour dogLocation en utilisant ce mot-clé.

            https://i.imgur.com/M0MDjmu.png

    Nous pouvons voir maintenant que la propriété location a été appliquée. En regardant de plus près la propriété de l'objet prototype, nous voyons que les méthodes n'ont pas été héritées.

        function Animal(name, color, isWild, sound) {

            this.name = name;
            this.color = color;
            this.isWild = isWild;
            this.sound = sound;

        }

        // adding a PROPERTY using the prototype object method
        Animal.prototype.order = "carnivore";


        // an instance of the class
        const dog = new Animal("dog", "black", false, "bark");


        function DogLocation(...props) {

            Animal.apply(this, props);
            // adding a new property
            this.location = "city";

        }

        const dogHabitat = new DogLocation("dog", "brown");
        console.log(dogHabitat);

B-  Hériter des méthodes de l'objet parent

    L'objet enfant ne peut pas hériter efficacement des méthodes de l'objet parent car les méthodes ont été ajoutées à l'aide de la méthode prototype. Cela signifie que le prototype créé après l'objet parent appartient uniquement à cet objet. Dans ce cas, notre objet étendu ou enfant va avoir sa propre méthode. Nous ne voulons vraiment pas enfreindre le principe DRY (Do not Repeat Yourself) en écrivant toutes les méthodes de l'objet parent sur l'objet enfant, nous voulons simplement l'hériter de l'objet parent.

    Pour y parvenir, nous utilisons la méthode Object.create qui est un moyen de créer un objet en JavaScript. Cela est possible car la propriété prototype en elle-même est un objet. Nous voulons créer un nouvel objet pour le prototype dogLocation qui est basé sur le prototype de l'objet parent, Animal.

        https://i.imgur.com/h1OVIw4.png

    À partir de notre exemple, nous pouvons voir que nous avons hérité avec succès de la méthode de notre objet parent.

        function Animal(name, color, isWild, sound) {

            this.name = name;
            this.color = color;
            this.isWild = isWild;
            this.sound = sound;

        }


        // adding a PROPERTY using the prototype object method
        Animal.prototype.order = "carnivore";


        // an instance of the class
        const dog = new Animal("dog", "black", false, "bark");


        function DogLocation(...props) {
            Animal.apply(this, props);
            // adding a new property
            this.location = "city";
        }

        // inheriting the Animal prototype
        DogLocation.prototype = Object.create(Animal.prototype);

        const dogHabitat = new DogLocation("dog", "brown");

        console.log(dogHabitat);

C-  Ajout de méthodes à l'objet enfant

    Nous pouvons ajouter des méthodes supplémentaires à l'objet enfant. Pour cela, nous pouvons ajouter une méthode pour les propriétaires de chiens.

        https://i.imgur.com/dNenSqE.png

    Nous avons pu ajouter une nouvelle méthode à notre objet enfant. Lorsque nous vérifions l'objet parent, nous remarquons que cette nouvelle méthode créée n'existe pas sur l'objet parent.

        https://i.imgur.com/Esmr33i.png

        function Animal(name, color, isWild, sound) {

            this.name = name;
            this.color = color;
            this.isWild = isWild;
            this.sound = sound;

        }

        // adding a PROPERTY using the prototype object method
        Animal.prototype.order = "carnivore";

        // an instance of the class
        const dog = new Animal("dog", "black", false, "bark");

        function DogLocation(...props) {
                
            Animal.apply(this, props);
            // adding a new property
            this.location = "city";

        }

        // inheriting the Animal prototype
        DogLocation.prototype = Object.create(Animal.prototype);
        // adding methods to the Child object
        DogLocation.prototype.dogOwner = function () {

            console.log("Steve");

        };

        const dogHabitat = new DogLocation("dog", "brown");
        console.log(dogHabitat);
