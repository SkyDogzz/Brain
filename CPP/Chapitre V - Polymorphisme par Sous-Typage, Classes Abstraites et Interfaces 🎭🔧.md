
Ce chapitre traite du polymorphisme par sous-typage en C++ :  
- **Classes abstraites** qui ne peuvent être instanciées directement  
- **Interfaces** via classes abstraites pour garantir l’implémentation de certaines méthodes  
- Utilisation de pointeurs vers la classe de base pour manipuler différentes implémentations

## Exemple : Interface et Implémentation

### `IAnimal.hpp`
```cpp
#pragma once

#include <iostream>

class IAnimal {
public:
    virtual ~IAnimal() {}
    // Méthode virtuelle pure, l’interface oblige la redéfinition
    virtual void faireDuBruit() const = 0;
};
```

### `Chien.hpp`
```cpp
#pragma once

#include "IAnimal.hpp"

class Chien : public IAnimal {
public:
    Chien();
    ~Chien();

    // Implémentation de l’interface
    void faireDuBruit() const;
};

#endif // CHIEN_HPP

Chien.cpp

#include "Chien.hpp"

Chien::Chien() {
    std::cout << "Un chien est né 🐶" << std::endl;
}

Chien::~Chien() {
    std::cout << "Le chien s'en va 👋" << std::endl;
}

void Chien::faireDuBruit() const {
    std::cout << "Woof Woof! 🐾" << std::endl;
}
```
