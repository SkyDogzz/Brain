
Dans ce chapitre, nous traitons de :
- **Allocation dynamique** : Utilisation de `new` et `delete`  
- **Pointeurs sur membres** et **références**  
- **Switch Statements** pour gérer les conditions multiples

## Exemple : Gestion de la Mémoire et Utilisation d'un Switch

### `GestionMemoire.hpp`
```cpp
#pragma once

#include <iostream>

class GestionMemoire {
public:
    GestionMemoire(int data);
    ~GestionMemoire();

    // Méthode pour afficher les données
    void afficher() const;

    // Méthode pour mettre à jour la donnée
    void setData(int data);

private:
    int _data;
};
```

### `GestionMemoire.cpp`
```cpp
#include "GestionMemoire.hpp"

GestionMemoire::GestionMemoire(int data) : _data(data) {
    std::cout << "Création de GestionMemoire avec data = " << _data << " 🎉" << std::endl;
}

GestionMemoire::~GestionMemoire() {
    std::cout << "Destruction de GestionMemoire 🚮" << std::endl;
}

void GestionMemoire::afficher() const {
    std::cout << "Data = " << _data << std::endl;
}

void GestionMemoire::setData(int data) {
    _data = data;
    std::cout << "Mise à jour de data à " << _data << " 🔄" << std::endl;
}

Exemple d'utilisation dans main.cpp

#include "GestionMemoire.hpp"
#include <iostream>

int main() {
    // Allocation dynamique de l'objet
    GestionMemoire *obj = new GestionMemoire(10);
    obj->afficher();

    // Utilisation d'un switch statement
    int choix = 2;
    switch(choix) {
        case 1:
            std::cout << "Choix 1 sélectionné 🥇" << std::endl;
            break;
        case 2:
            std::cout << "Choix 2 sélectionné 🥈" << std::endl;
            break;
        default:
            std::cout << "Choix par défaut sélectionné 🎲" << std::endl;
            break;
    }

    // Libération de la mémoire
    delete obj;
    return 0;
}
```


