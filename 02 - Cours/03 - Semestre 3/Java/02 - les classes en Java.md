# Java - Les classes

- [Java - Les classes](#java---les-classes)
  - [1. Classe](#1-classe)
  - [2. Attributs](#2-attributs)
  - [3. Constructeur](#3-constructeur)
    - [Pourquoi this ?](#pourquoi-this-)
      - [1. Changer le nom du paramètre](#1-changer-le-nom-du-paramètre)
      - [2. Utiliser this](#2-utiliser-this)
  - [4. Utiliser le constructeur](#4-utiliser-le-constructeur)
  - [5. Méthodes](#5-méthodes)

## 1. Classe

- Une classe est un **modèle** pour créer des objets.
- Prenons un **animal**. Un animal est comme un **plan général ou un moule** : *il décrit ce que tous les animaux peuvent avoir ou faire, et les animaux spécifiques comme le chien, le chat ou le lion sont des versions concrètes avec leurs propres caractéristiques.*

- On peut dire que l'***animal*** est une `classe`.
- Dans Java, on peut la représenter ainsi:
```java
class Animal {

}
```

- ***NOTEZ QUE LE NOM DE LA CLASSE COMMENCE TOUJOURS PAR UNE MAJUSCULE, ET N'A PAS D'ESPACES.***

## 2. Attributs

- L'animal a plusieurs caractéristiques: ***nom, couleur de peau, age, sauvage ou domestique, carnivore, herbivore etc...***
- Ces caractéristiques définissent un animal précis. Par exemple: Un lion de 2 ans, couleur dorée, carnivore etc..
- Dans Java, on peut représenter ces caractéristiques avec des `attributs`, ou en d'autres termes, `variables`.
- On aura donc la suite de notre classe d'avant:
```java
class Animal {
    String nom;
    int age;
    String type;
    String couleur;
}
```

## 3. Constructeur

- Vous voyez avant que nos attributs n'ont pas de valeurs. alors comment peut-on définir un lion ?
- On utilise un `constructeur`, une ***méthode du même nom que la classe qui nous permet de donner des valeurs initiales***.

```java
class Animal {
    String nom;
    int age;
    String type;
    String couleur;

    Animal(String nom, int age, String type, String couleur) {
        this.nom = nom;
        this.age = age;
        this.type = type;
        this.couleur = couleur;
    }
}
```

### Pourquoi this ?

- Vous voyez que notre attribut s'appelle `nom`, et que dans le constructeur on a aussi le paramètre `nom`.
- Ceci peut nous causer des problèmes vu qu'ils ont le même. Deux solutions s'offrent à nous.

#### 1. Changer le nom du paramètre

- Dans le constructeur, on peut faire ça:
```java
Animal(String nom1, int age1, String type1, String couleur1) {
    nom = nom1;
    age = age1;
    type = type1;
    couleur = couleur1;
}
```

#### 2. Utiliser this

- La solution 1 est ***moche*** (nom1, age1, **sérieux?**)
- Faisons les trucs convenablement.
- `this` est facile à comprendre, regardez:
```java
class Animal {
    String nom;
    int age;
    String type;
    String couleur;

    Animal(String nom, int age, String type, String couleur) {
        this.nom = nom; // this.nom veut dire, utilise l'attribut du paramètre, et c'est correct
        this.age = age;
        this.type = type;
        this.couleur = couleur;
    }
}
```

## 4. Utiliser le constructeur

- Vous vous rappelez de `main` ?
- `main` nous permet d'exécuter le programme principal.
- C'est donc dans la classe `Main` qu'on va créer notre premier lion.
```java
public class Main {
    public static void main(String[] args) {
        Animal lion = new Animal("Lion", 2, "Sauvage", "Or");
    }
}
```

- On peut diviser ça:
- `Animal` -> Ce premier est le type (comme int), pour dire que notre lion est un animal (et non pas un nombre, ***bien évidemment***).
- `lion` -> Ceci est le nom de notre variable.
- `new Animal()` -> Ceci va dire au programme de nous créer un lion.
  
- ***Maintenant, comment ce lion aura ses propres caractéristiques ?***
- En utilisant les paramètres du constructeur `Animal`.
```java
new Animal(String nom, int age, String type, String couleur);

// Ceci devient donc:
new Animal('Lion', 2, 'Carnivore', 'Or');

// On a donc un lion, 2 ans, carnivore avec une peau dorée.
```

## 5. Méthodes

- Vous réalisez qu'on a un lion qui ne fait rien ? Il ne bouge pas, il ne crie pas, il ne mange pas.
- On peut régler ça avec les `méthodes`, ou comme on les appelle dans d'autres langages, `fonctions et procèdures`.
- On va ajouter ces méthodes vers `Animal`:

```java
class Animal {
    String nom;
    int age;
    String type;
    String couleur;

    Animal(String nom, int age, String type, String couleur) {
        this.nom = nom;
        this.age = age;
        this.type = type;
        this.couleur = couleur;
    }

    void bouger() {
        System.out.println("Je peux enfin bouger");
    }

    String nourriturePreferee() {
        return "la viande";
    }
}
```

- Si on revient vers `main`:
```java
public class Main {
    public static void main(String[] args) {
        Animal lion = new Animal("Lion", 2, "Sauvage", "Or");

        lion.bouger(); // On affiche à l'écran: Je peux enfin bouger

        String nourriture = lion.nourriturePreferee();

        System.out.print("Notre lion aime " + nourriture); // Ceci affiche: Notre lion aime la viande.
    }
}
```