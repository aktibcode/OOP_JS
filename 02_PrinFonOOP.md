Chapitre : PRINCIPES FONDAMENTAUX DE LA PROGRAMMATION ORIENTEE OBJET

A-  PF de la programmation orientée objet

    -   Dans cette compétence, nous aborderons ces sujets :

        *   Encapsulation

        *   Abstraction

        *   Héritage

        *   Polymorphisme

B-  Encapsulation

    L'encapsulation est un principe essentiel du Javascript orienté objet. Elle décrit le regroupement de données ou de propriétés et méthodes qui opèrent sur les données ou la propriété dans une unité appeléée objet. Elle permet de masquer l'implémentation interne d'un objet tout en exposant uniquement les détails nécessaires. Son objectif est d'obtenir la modularité, une séparation appropriée des tâches de la maintenabilité. 

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

C-  Abstraction

    L'abstraction est un principe de programmation orientée objet qui implique le processus de simplification de systèmes complexes par la modélisation d'objets basés sur les propriétés et le comportement ou les méthodes nécessaires qu'un objet devrait avoir. Ces propriétés et méthodes sont celles qui sont pertinentes pour le contexte du problème ou de l'objet. Cela aide les développeurs à se concentrer sur les détails de haut niveau, facilitant ainsi la gestion de la complexité du code. Cela rend également notre code réutilisable et évolutif. Ce principe est étroitement lié au principe d'encapsulation.

D-  Héritage

    L'héritage est un concept fondamental de la programmation orientée objet qui permet de créer de nouvelles classes appelées sous-classes ou classes enfants à partir d'une classe existante appelée classe parent ou superclasse .

    La sous-classe ou classe enfant hérite des propriétés et des méthodes de la classe parent ou superclasse . Cela permet de promouvoir la réutilisation du code et l'extension ou la modification des propriétés et des méthodes de la classe parent à l'intérieur de la classe enfant. Cela établit également une relation entre les deux classes.

    Le mot clé extends est utilisé pour créer la classe nouvelle ou étendue (enfant/sous-classe) et le super est utilisé pour hériter des propriétés et des méthodes de la classe parent.

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

    Dans l'exemple de code ci-dessus, nous avons une classe enfant appelée AnimalClassification qui a été créée à partir de la classe Animal, où la classe AnimalClassification est l'enfant ou la sous-classe (parfois également appelée classe de base) et la classe Animal est la classe parent ou super classe.

E-  Polymorphisme

    Le polymorphisme signifie de nombreuses formes . C'est un principe de JavaScript orienté objet qui permet aux sous-classes de créer leur propre implémentation d'une méthode qui existe déjà dans la classe parent. Cela est possible car cela permet aux objets d'être traités comme une instance de leur classe parent. Cela permet aux différentes instances de l'objet parent de répondre à la même méthode afin de renvoyer des valeurs différentes en fonction de ce qui y est stocké.

        class Shape {

            area() {

                console.log("Calculating area of a shape");

            }

        }

        class Circle extends Shape {

            area() {

                console.log("Calculating area of a circle");

            }

        }

        class Square extends Shape {

            area() {

                console.log("Calculating area of a square");

            }

        }

            https://youtu.be/SiBw7os-_zI