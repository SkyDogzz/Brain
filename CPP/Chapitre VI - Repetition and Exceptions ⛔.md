Parfait ! Voici une version de l’exemple 100% axée sur les exceptions en C++, avec des std::exception, des throw, et des blocs try / catch, le tout bien structuré et avec plein d’emojis pour bien suivre le flow ! 💥🧯

Dans ce chapitre, nous verrons comment :
- Utiliser try, catch, throw pour gérer les erreurs en C++ 🧱
- Créer nos propres exceptions en dérivant de std::exception 🛠️
- Lancer (throw) et attraper (catch) des erreurs de manière propre et élégante ✨

## Exemple : Exceptions Personnalisées
### `Exception.hpp`
```cpp
  #pragma once

  

#include <iostream>

#include <stdexcept> // Pour std::exception

  

class Exception {

public:

    Exception();

    ~Exception();

  

    void verifierEntier(int n);

    void verifierDiviseur(int diviseur);

  

    class ValeurNegativeException : public std::exception {

    public:

        const char* what() const noexcept override;

    };

  

    class DivisionParZeroException : public std::exception {

    public:

        const char* what() const noexcept override;

    };

};
```

### `Exception.cpp`
  ```cpp

#include "Exception.hpp"


Exception::Exception() {

    std::cout << "Constructeur Exception ⚙️" << std::endl;

}

  

Exception::~Exception() {

    std::cout << "Destructeur Exception 🧹" << std::endl;

}

  

void Exception::verifierEntier(int n) {

    std::cout << "Vérification d’un entier : " << n << std::endl;

    if (n < 0) {

        throw ValeurNegativeException(); // On balance une exception perso 🚀

    }

}

  

void Exception::verifierDiviseur(int diviseur) {

    std::cout << "Vérification du diviseur : " << diviseur << std::endl;

    if (diviseur == 0) {

        throw DivisionParZeroException(); // On balance une autre exception 💣

    }

}

  

const char* Exception::ValeurNegativeException::what() const noexcept {

    return "Erreur : la valeur est négative ❌";

}

  

const char* Exception::DivisionParZeroException::what() const noexcept {

    return "Erreur : division par zéro impossible 🧨";

}
```


### `main.cpp`
```cpp
#include "Exception.hpp"

  

int main() {

    Exception ex;

  

    try {

        ex.verifierEntier(-42); // On test une valeur négative

    } catch (const Exception::ValeurNegativeException &e) {

        std::cerr << "Exception attrapée : " << e.what() << " 🚨" << std::endl;

    }

  

    try {

        ex.verifierDiviseur(0); // On test un diviseur nul

    } catch (const Exception::DivisionParZeroException &e) {

        std::cerr << "Exception attrapée : " << e.what() << " 🚨" << std::endl;

    }

  

    std::cout << "Programme terminé avec grâce et élégance ✅" << std::endl;

    return 0;

}
```
  