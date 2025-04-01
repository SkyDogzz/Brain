
Dans ce chapitre, nous abordons les notions de base du C++ :  
- **Classes** et **fonctions membres**  
- **Streams** pour la gestion des entrées/sorties  
- **Listes d’initialisation**, **static** et **const**  
- Séparation en fichiers `.hpp` et `.cpp` (sans méthode complète dans le header)  
- **Aucune utilisation de namespace**

## Exemple : Classe Basique "Exemple" 📘

### `Exemple.hpp`
```cpp
#pragma once
#include <iostream>

// Déclaration de la classe Exemple
class Exemple {
public:
    // Constructeur par défaut 😃
    Exemple();

    // Constructeur avec paramètres 🎯
    Exemple(int valeur);

    // Destructeur 🗑️
    ~Exemple();

    // Constructeur de copie (forme canonique) 🔄
    Exemple(const Exemple &other);

    // Opérateur d’assignement (forme canonique) 🔁
    Exemple &operator=(const Exemple &other);

    // Méthode membre pour afficher la valeur 📢
    void afficher() const;

private:
    int _valeur; // attribut privé
};
```

### `Exemple.cpp`
```cpp
#include "Exemple.hpp"

// Initialisation de la valeur par défaut
Exemple::Exemple() : _valeur(0) {
    std::cout << "Constructeur par défaut appelé 😊" << std::endl;
}

// Constructeur avec paramètres
Exemple::Exemple(int valeur) : _valeur(valeur) {
    std::cout << "Constructeur avec paramètre appelé 🚀" << std::endl;
}

// Destructeur
Exemple::~Exemple() {
    std::cout << "Destructeur appelé 👋" << std::endl;
}

// Constructeur de copie
Exemple::Exemple(const Exemple &other) : _valeur(other._valeur) {
    std::cout << "Constructeur de copie appelé 🔄" << std::endl;
}

// Opérateur d’assignement
Exemple &Exemple::operator=(const Exemple &other) {
    if (this != &other) {
        _valeur = other._valeur;
        std::cout << "Opérateur d’assignement appelé 🔁" << std::endl;
    }
    return *this;
}

// Méthode pour afficher la valeur
void Exemple::afficher() const {
    std::cout << "Valeur : " << _valeur << std::endl;
}
```
