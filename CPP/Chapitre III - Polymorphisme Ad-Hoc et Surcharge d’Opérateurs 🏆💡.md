
Dans ce chapitre, nous verrons comment :
- Surcharger des opérateurs (ex. `+`, `==`)  
- Implémenter la **forme canonique de Coplien** (constructeur par défaut, constructeur de copie, opérateur d’assignement et destructeur)

## Exemple : Surcharge d’Opérateurs

### `Operateur.hpp`
```cpp
#pragma once

#include <iostream>

class Operateur {
public:
    Operateur(int valeur);
    ~Operateur();

    // Forme canonique
    Operateur(const Operateur &other);
    Operateur &operator=(const Operateur &other);

    // Surcharge de l’opérateur d’addition
    Operateur operator+(const Operateur &other) const;

    // Surcharge de l’opérateur de comparaison (égalité)
    bool operator==(const Operateur &other) const;

    // Méthode pour afficher la valeur
    void afficher() const;

private:
    int _valeur;
};
```

### `Operateur.cpp`
```cpp
#include "Operateur.hpp"

Operateur::Operateur(int valeur) : _valeur(valeur) {
    std::cout << "Constructeur Operateur avec valeur " << _valeur << " 🚀" << std::endl;
}

Operateur::~Operateur() {
    std::cout << "Destructeur Operateur pour valeur " << _valeur << " 👋" << std::endl;
}

Operateur::Operateur(const Operateur &other) : _valeur(other._valeur) {
    std::cout << "Constructeur de copie Operateur 🔄" << std::endl;
}

Operateur &Operateur::operator=(const Operateur &other) {
    if (this != &other) {
        _valeur = other._valeur;
        std::cout << "Assignation Operateur 🔁" << std::endl;
    }
    return *this;
}

Operateur Operateur::operator+(const Operateur &other) const {
    std::cout << "Surcharge de l’opérateur + utilisée ➕" << std::endl;
    return Operateur(this->_valeur + other._valeur);
}

bool Operateur::operator==(const Operateur &other) const {
    std::cout << "Surcharge de l’opérateur == utilisée 🤝" << std::endl;
    return (this->_valeur == other._valeur);
}

void Operateur::afficher() const {
    std::cout << "Valeur = " << _valeur << std::endl;
}
```
