
- **Compilation :**  
  Utilisez `-Wall -Wextra -Werror` et le flag `-std=c++98` pour compiler votre code.

- **Organisation des fichiers :**  
  - Chaque module ou exercice doit être placé dans son dossier respectif (ex00, ex01, etc.).  
  - Respectez la séparation entre `.hpp` et `.cpp`.

- **Nommage :**  
  - Utilisez le format **UpperCamelCase** pour les noms de classe (ex. `BrickWall.hpp`).  
  - Les méthodes complètes ne doivent pas être dans les headers (sauf pour les templates).

- **Restrictions :**  
  - **Pas de `namespace` ni de `friend`** pour éviter des pénalités.  
  - Seules les fonctions C++ (et non C) de la bibliothèque standard sont autorisées (pas de `printf()`, `alloc()` ou `free()`).

- **Forme canonique de Coplien :**  
  Implémentez pour chaque classe : constructeur par défaut, constructeur de copie, opérateur d’assignement et destructeur.

- **Gestion de la mémoire :**  
  Assurez-vous de libérer toute mémoire allouée dynamiquement (avec `delete`) pour éviter les fuites mémoire.

- **Lisibilité du code :**  
  Un code bien structuré et commenté est essentiel pour faciliter la compréhension par vos pairs.
