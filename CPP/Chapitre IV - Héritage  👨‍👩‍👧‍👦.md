
L’héritage permet de créer des classes dérivées qui réutilisent et étendent le comportement d’une classe de base.  
Ce chapitre montre comment utiliser l’héritage pour :
- Réutiliser du code
- Implémenter le polymorphisme grâce à la virtualisation des méthodes

## Exemple : Classe de Base et Classe Dérivée

### `Base.hpp`
```cpp
#pragma once

#include <iostream>

class Base {
public:
    Base();
    virtual ~Base();

    virtual void afficher() const;
};
```


### `Base.cpp`

```cpp
#include "Base.hpp"

Base::Base() {
    std::cout << "Constructeur Base 🚀" << std::endl;
}

Base::~Base() {
    std::cout << "Destructeur Base 👋" << std::endl;
}

void Base::afficher() const {
    std::cout << "Affichage de Base 🎯" << std::endl;
}
```

### `Derive.hpp`
```cpp
#pragma once

#include "Base.hpp"

class Derive : public Base {
public:
    Derive();
    ~Derive();

    // Redéfinition de la méthode afficher
    void afficher() const;
};
```

### `Derive.cpp`
```cpp
#include "Derive.hpp"

Derive::Derive() {
    std::cout << "Constructeur Derive 🚀" << std::endl;
}

Derive::~Derive() {
    std::cout << "Destructeur Derive 👋" << std::endl;
}

void Derive::afficher() const {
    std::cout << "Affichage de Derive 🎯" << std::endl;
}
```

