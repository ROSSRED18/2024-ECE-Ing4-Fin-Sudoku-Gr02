# Sudoku Solver - Backtracking Algorithm

Ce projet est une impl�mentation d'un solveur de Sudoku en C# utilisant l'algorithme de backtracking.

## Fonctionnalit�s

- R�solution de grilles de Sudoku � l'aide de l'algorithme de backtracking.
- Int�gration facile dans d'autres applications ou projets utilisant le langage C#.

## Structure du Projet

- `Sudoku.Shared` : Contient les interfaces et les types partag�s pour le projet.
- `Sudoku.Backtracking2` : Impl�mentation du solveur de Sudoku utilisant l'algorithme de backtracking.
- `README.md` : Ce fichier. Fournit des informations sur le projet, son utilisation et sa structure.

## M�thodes

### `SudokuGrid Solve(SudokuGrid s)`

Cette m�thode est utilis�e pour r�soudre une grille de Sudoku en utilisant l'algorithme de backtracking.

Param�tres :
- `s` : La grille de Sudoku � r�soudre.

Retour :
- La grille de Sudoku r�solue.

### `int[,] Conversion(SudokuGrid s)`

Cette m�thode convertit une grille de Sudoku au format utilis� par l'algorithme de backtracking.

Param�tres :
- `s` : La grille de Sudoku � convertir.

Retour :
- La grille de Sudoku convertie au format `int[,]`.

### `bool IsSafe(int[,] grid, int row, int col, int num)`

Cette m�thode v�rifie si la valeur donn�e peut �tre plac�e dans la case sp�cifi�e sans violer les r�gles du Sudoku.
Elle v�rifie si la valeur est d�j� pr�sente dans la m�me ligne, la m�me colonne ou le m�me bloc.

Param�tres :
- `grid` : La grille de Sudoku.
- `row` : L'indice de ligne de la case.
- `col` : L'indice de colonne de la case.
- `num` : La valeur � v�rifier.

Retour :
- True si la valeur peut �tre plac�e en toute s�curit� dans la case sp�cifi�e, False sinon.

### `bool SolverBacktracking(int[,] grid, int row, int col)`

Cette m�thode r�cursive est utilis�e pour r�soudre une grille de Sudoku en utilisant l'algorithme de backtracking.
Elle parcourt la grille case par case en essayant diff�rentes valeurs et v�rifie si chaque valeur est valide.

Param�tres :
- `grid` : La grille de Sudoku � r�soudre.
- `row` : L'indice de ligne actuel.
- `col` : L'indice de colonne actuel.

Retour :
- True si la grille a �t� r�solue avec succ�s, False sinon.

## Difficult�s Rencontr�es

    -** Git et VSCode :  La configuration du projet, la synchronisation et l'utilisation de GitHub ont pr�sent� des d�fis initiaux.
    -** Une des autres difficult�s a �t� de trouver une solution pour repr�senter la grille de Sudoku de mani�re efficace pour l'algorithme de backtracking.   
     Nous avons d� mettre en place une conversion entre le format utilis� par le solveur et celui utilis� par l'interface utilisateur.
    -** De plus la logique impliqu�e dans le processus de backtracking est complexe donc nous avons pris du temps
     pour le comprendre parfaitement pour povoir l'impl�menter de mani�re efficace dans le code.

## Performance 

    -** Facile : 0.0204 ms 
    -** Medium : 117,766 ms    
    -** Hard : 3804.4044 ms      

puzzle index 1

## Exemple d'utilisation

```C#
// Exemple d'utilisation dans votre propre application
SudokuGrid grid = new SudokuGrid(/* Ins�rez votre grille de Sudoku ici */);
Backtracking2Solver solver = new Backtracking2Solver();
SudokuGrid solution = solver.Solve(grid);
// Utilisez la grille solution pour afficher ou traiter le r�sultat.


