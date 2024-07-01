+++
title = 'Rust Cheatsheet'
date = 2024-05-16T14:06:20+02:00
draft = false
summary = 'My personnal cheastsheet while learning Rust'
thumbnail = "images/ferris.jpg"
+++



## 1. Variables :

- Les variables sont définies avec `let`.
- Par défaut, les variables sont **immuables**.
- Utilisez `mut` pour rendre une variable **mutable**.

```rust
let x = 5; // Variable immuable
let mut y = 10; // Variable mutable
```

## 2. Types de données :

- Types de base : `i32, u32, f32, f64, bool, char, &str`.
- Autres types : `tuple, array, vector, struct, enum`.

```rust
let boolean: bool = true;
let character: char = 'a';
let tuple: (i32, f64, &str) = (1, 2.5, "hello");
let array: [i32; 3] = [1, 2, 3];
let vector: Vec<i32> = vec![1, 2, 3];
```
## 3. Contrôle de flux :

`if` pour les conditions.

`for`, `while` et `loop` pour les boucles.

```rust
if x > y {
    println!("x est plus grand que y");
} else {
    println!("y est plus grand ou égal à x");
}

for i in 0..10 {
    println!("i est égal à {}", i);
}

let mut count = 0;
while count < 5 {
    println!("count est égal à {}", count);
    count += 1;
}
```
## 4. Fonctions :

Définition des fonctions avec `fn`.
Type de retour après la flèche `->`.
La denière expression est la valeur de retour (ou utiliser le mot clé `return`)

```rust
fn add(x: i32, y: i32) -> i32 {
    x + y
}

let sum = add(5, 10);
println!("La somme est {}", sum);
```

## 5. Ownership et borrowing :

**Ownership** est un concept clé de Rust pour gérer la mémoire de manière sécurisée.
`&` est utilisé pour emprunter (*borrow*) une valeur.

```rust
fn main() {
    let s1 = String::from("hello");
    let s2 = &s1; // Borrowing s1
    println!("{}", s2); // Utiliser s2 ici est possible
}
```
## 6. Structures et énumérations :

- `struct` définit une **structure**.
- `enum` définit un **type énuméré**.

```rust
struct Person {
    name: String,
    age: u32,
}

let john = Person {
    name: String::from("John"),
    age: 30,
};

enum Color {
    Red,
    Green,
    Blue,
}

let my_color = Color::Red;
```
## 7. Trait :

Les **traits** sont des interfaces que les types doivent implémenter.

```rust

trait Drawable {
    fn draw(&self);
}

struct Circle;
impl Drawable for Circle {
    fn draw(&self) {
        println!("Dessiner un cercle");
    }
}
```