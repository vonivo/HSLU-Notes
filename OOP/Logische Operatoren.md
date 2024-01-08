## Und
| 1. Argument (a) | 2. Argument (b) | Resultat (a && b) |
| ---- | ---- | ---- |
| $\color{red}false$ | $\color{red}false$ | $\color{red}false$ |
| $\color{red}false$ | $\color{green}true$ | $\color{red}false$ |
| $\color{green}true$ | $\color{red}false$ | $\color{red}false$ |
| $\color{green}true$ | $\color{green}true$ | $\color{green}true$ |
- Der Operator ist **optimiert**: Wenn das erste Argument **false** ist, wird das **zweite** nicht mehr ausgewertet.

## Oder
| 1. Argument (a) | 2. Argument (b) | Resultat (a \|\| b) |
| ---- | ---- | ---- |
| $\color{red}false$ | $\color{red}false$ | $\color{red}false$ |
| $\color{red}false$ | $\color{green}true$ | $\color{green}true$ |
| $\color{green}true$ | $\color{red}false$ | $\color{green}true$ |
| $\color{green}true$ | $\color{green}true$ | $\color{green}true$ |
- Der Operator ist **optimiert**: Wenn das erste Argument **true** ist, wird das **zweite** nicht mehr ausgewertet.
## Exklusiv Oder
| 1. Argument (a) | 2. Argument (b) | Resultat (a \|\| b) |
| ---- | ---- | ---- |
| $\color{red}false$ | $\color{red}false$ | $\color{red}false$ |
| $\color{red}false$ | $\color{green}true$ | $\color{green}true$ |
| $\color{green}true$ | $\color{red}false$ | $\color{green}true$ |
| $\color{green}true$ | $\color{green}true$ | $\color{red}false$ |

## Logisches Nicht
| 1. Argument (a) | Resultat (!a) |
| ---- | ---- |
| $\color{red}flase$ | $\color{green}true$ |
| $\color{green}true$ | $\color{red}false$ |
