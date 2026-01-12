# Java - Les bases

## 1. Structure de base d’un programme Java

Tout programme Java s’exécute dans une **classe**.

```java
public class Main {
    public static void main(String[] args) {
        System.out.println("Bonjour");
    }
}
```

* `class` : définit une classe.
* `main` : point d’entrée du programme.
* `System.out.println` : affiche du texte.

## 2. Variables et types

Java est **fortement typé** : chaque variable a un type.

```java
int age = 20;
double prix = 12.5;
boolean actif = true;
char lettre = 'A';
String nom = "Alice";
```

## 3. Opérateurs

### 3.1. Arithmétiques

```java
+ -> addition
- -> soustraction
* -> multiplication
/ -> division
% -> MOD (Reste)
```

### 3.2. Comparaison

```java
== -> égal (a == b)
!= -> pas égal
> -> strictement plus grand
< -> strictement plus petit
>= -> plus grand ou égal
<= -> plus petit ou égal
```

### 3.3. Logiques

```java
&& -> AND (a > 0 && b > 0)
|| -> OR
! -> NOT
```

```markdown
| A    | B    | A && B | A || B | !A   |
| ---- | ---- | ------ | ------ | ---- |
| Vrai | Vrai | Vrai   | Vrai   | Faux |
| Vrai | Faux | Faux   | Vrai   | Faux |
| Faux | Vrai | Faux   | Vrai   | Vrai |
| Faux | Faux | Faux   | Faux   | Vrai |
```

## 4. Conditions

```java
// --- IF seul ---
int age = 20;
if (age >= 18) {
    System.out.println("Majeur");
}

// --- IF / ELSE ---
if (age >= 18) {
    System.out.println("Majeur");
} else {
    System.out.println("Mineur");
}

// --- IF / ELSE IF / ELSE ---
if (age < 13) {
    System.out.println("Enfant");
} else if (age < 18) {
    System.out.println("Adolescent");
} else {
    System.out.println("Adulte");
}

// --- SWITCH ---
int jour = 2;
switch (jour) {
    case 1:
        System.out.println("Lundi");
        break;
    case 2:
        System.out.println("Mardi");
        break;
    case 3:
        System.out.println("Mercredi");
        break;
    default:
        System.out.println("Autre jour");
}
```

## 5. Boucles

```java
// --- FOR ---
for (int i = 0; i < 5; i++) {
    System.out.println("For: " + i);
}

// --- WHILE ---
int j = 0;
while (j < 5) {
    System.out.println("While: " + j);
    j++;
}

// --- DO WHILE ---
int k = 0;
do {
    System.out.println("Do-While: " + k);
    k++;
} while (k < 5);
```

- La différence entre `while` et `do-while` est le fait que `do-while` s'exécute au moins une seule fois puis regarde la condition. Tandis que `while` regarde la condition avant même d'exécuter la première fois.

## 6. Méthodes

Une méthode est une fonction appartenant à une classe.

```java
// -- Fonction --
int addition(int a, int b) {
    return a + b;
}

// -- Procédure --
void afficherMessage(String messages) {
    System.out.println(message);
}
```

Appel :

```java
// -- Fonction --
int resultat = addition(2, 3);

// -- Procédure --
String message = "How are you?";
afficherMessage(message);
```

## 7. Tableaux

Un tableau stocke plusieurs valeurs du **même type**.

### 7.1. Déclaration et initialisation

```java
int[] nombres = new int[3];
nombres[0] = 10;
nombres[1] = 20;
nombres[2] = 30;
```

Ou directement :

```java
int[] nombres = {10, 20, 30};
```

### 7.2. Parcourir un tableau

```java
for (int i = 0; i < nombres.length; i++) {
    System.out.println(nombres[i]);
}
```

Boucle améliorée :

```java
for (int n : nombres) {
    System.out.println(n);
}
```

## 8. Matrices

### 8.1. Déclaration et initialisation

```java
int[][] nombres = new int[3][2];
nombres[0][0] = 10;
nombres[0][1] = 20;
nombres[1][0] = 30;
nombres[1][1] = 40;
nombres[2][0] = 50;
nombres[2][1] = 60;
```

Ou directement :

```java
int[][] nombres = {{10, 20}. {30, 40}, {50, 60}};
```

### 8.2. Parcourir un tableau

```java
for (int i = 0; i < nombres.length; i++) {
    for (int j = 0; j < nombres[i].length; j++) {
        System.out.println(nombres[i][j]);
    }
}
```

Boucle améliorée :

```java
for (int[] ligne : nombres) {
    for (int n : ligne) {
        System.out.println(n);
    }
}
```

## 9. Points essentiels à retenir

* Java = classes + méthodes.
* Tout a un type.
* Indices des tableaux commencent à **0**.
* `length` donne la taille d’un tableau.
