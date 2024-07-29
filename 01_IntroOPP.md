Chapitre : Introduction à la programmation orientée objet en JavaScript

A-  Introduction au JavaScript orienté objet

    Dans les compétences précédentes, nous avons appris les bases de JavaScript et du DOM. Dans cette super-compétence, nous travaillerons sur la compréhension du JavaScript orienté objet (OOJ). Presque tout dans JavaScript est considéré comme un objet.

    Les objets de la vie réelle sont un excellent moyen de comprendre les objets en JavaScript. Par exemple, nous avons un objet comme une maison. Cette maison aura des propriétés telles que la couleur, le nombre de pièces, le nombre de portes, etc. La maison peut également être conçue pour faire des choses comme protéger les habitants de la pluie, stocker des objets, etc. En JavaScript, nous avons également des objets avec des propriétés et des choses que les objets peuvent faire. Les propriétés sont comme les caractéristiques de l'objet, elles nous en disent plus sur l'objet. Ce que les objets en JavaScript peuvent faire est connu sous le nom de méthodes.

B-  Valeurs et objets primitifs

    En JavaScript, les valeurs peuvent être des primitives ou des objets. Les valeurs primitives sont des valeurs sans propriétés ni méthodes. Exemples de valeurs primitives : chaîne, nombre, booléen, null, indéfini, symbole et bigint. Les valeurs en JavaScript considérées comme des objets incluent : dates, mathématiques, expressions régulières, tableaux, fonctions et objets.

    Certaines valeurs peuvent être à la fois des primitives et des objets selon la manière dont elles sont définies. Le tableau ci-dessous présente des exemples des deux types de valeurs.

    Primitif

    -   La chaîne peut contenir des valeurs primitives. let name = « John » ;

    -   Les nombres sont considérés comme des valeurs primitives, soit num1 = 6 ;

    -   Les booléens sont des valeurs primitives let isNull = true;

    Objets

    -   Les chaînes peuvent également être un objet lorsqu'elles sont définies avec le mot-clé « new » let name2 = new String(“Jonah”).

    -   Les nombres, tout comme les chaînes de caractères, peuvent également être des objets lorsqu'ils sont définis avec le mot-clé 'new'. Ceci est différent lorsque Number() est utilisé pour convertir un nombre qui est une chaîne de caractères en un nombre. Par exemple : let num3 = “123”; let num4 = Number(num3);

    -   Les booléens, tout comme les types précédents, peuvent également être des objets lorsqu'ils sont définis avec le mot-clé 'new'. Il crée une instance let value = new Boolean(false) Il en va différemment pour Boolean() qui est utilisé pour convertir une valeur en booléen. Par exemple : Let value3 = “true string” Boolean(value3)

        a-  Note:

        Il est important de noter que pour ces valeurs qui ont à la fois des formes primitives et des formes d'objet, vous pouvez les différencier en vérifiant leur type à l'aide du typeof fourni par JavaScript. Vous trouverez ci-dessous des exemples avec des images pour les 3

        b-  Chaîne:

            https://i.imgur.com/ploUT68.png

        c-  Nombre:

            https://i.imgur.com/gg3S7I2.png

        d-  Booléen:

            https://i.imgur.com/xlcu9jl.png

C-  Propriétés et méthodes

    Les propriétés peuvent être considérées comme des caractéristiques de l'objet. Les méthodes sont des fonctions associées à un objet. Pour voir comment fonctionnent les propriétés et les objets, nous allons utiliser l'objet array en créant un tableau de noms de voitures dans la console de notre navigateur. Dans l'exemple ci-dessous, nous voyons la propriété .length , qui nous indique la longueur du tableau. Nous avons des méthodes comme .sort() , qui trie le tableau par ordre alphabétique et .join() , qui joint tout le contenu du tableau en utilisant le caractère ajouté à l'intérieur des parenthèses.

        https://i.imgur.com/YJLsCaD.png

    https://youtu.be/7d9H34ZVRPg?list=PL4cUxeGkcC9i5yvDkJgt60vNVWffpblB7




