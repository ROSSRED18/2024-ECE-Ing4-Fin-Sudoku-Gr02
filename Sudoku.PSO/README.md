# R�solution de Sudokupar Optimisation par essaims particulaires (PSO) 

## D�finition

	**L'optimisation par essaim particulaire** (PSO) est une m�thode de r�solution de probl�mes qui s'inspire du comportement social des essaims d'insectes et des bancs de poissons dans la nature. 
	Au c�ur de cette m�thode, un ensemble de solutions potentielles, repr�sent�es par des particules, explore l'espace du probl�me � la recherche de la solution optimale.
	Dans cette approche it�rative, chaque particule de l'essaim repr�sente une solution possible et poss�de deux caract�ristiques principales : sa **position** et sa **vitesse**.
	Les particules se d�placent dans l'espace du probl�me en ajustant leur vitesse en fonction de leur propre exp�rience (la meilleure solution qu'elles ont trouv�e jusqu'� pr�sent) et de l'exp�rience collective de tout l'essaim (la meilleure solution globale).
	Le processus est it�ratif, chaque particule mettant � jour sa trajectoire en fonction des meilleures positions connues.
	Ce m�canisme encourage l'�change d'informations entre les particules, favorisant ainsi l'am�lioration globale de l'ensemble de l'essaim vers la meilleure solution possible.

## Objectif de notre projet

	Notre **but** est de se servir de cette m�thode pour d�velopper des **solveurs de Sudoku** en utilisant le **langage C#**
	
### Pr�requis 

	Environnements : **Visual Studio Community** / **Rider Jet Brains**

	Un d�p�t de code est fourni avec les projets de base facilitant la r�alisation du projet.

	Dans le projet Sudoku.Shared de la solution, on trouve les classes suivantes :

		**- Classe SudokuGrid** : elle repr�sente l'�tat d'un Sudoku � r�soudre ou en cours de r�solution.
			Elle poss�de une **m�thode ToString()** permettant d'afficher l'�tat d'un Sudoku sous forme de
			cha�ne de caract�res, et des **m�thodes Parse()** qui prennent en param�tre un fichier de Sudokus
			ou les lignes de son contenu et renvoie une liste d�objets de la classe nouvellement cr��e
	    **- Interface ISolverSudoku** : elle d�finit les m�thodes � impl�menter par les solvers de Sudoku.
	    **- Classe PythonSolverBase** : Il s�agit d�une classe de base h�ritable pour impl�menter un sol-
			ver en Python utilisant le bridge Python.Net

	Dans le **projet Sudoku.Benchmark** de la solution, on trouve la **classe Program**: elle permet de
	tester les solvers de Sudoku de fa�on individuelle ou dans le cadre d'un benchmark comparatif ;
	Elle utilise la classe **Stopwatch** pour mesu rer les temps d'ex�cution des solvers.

## PSOsolver version 1

	




### Performances

	 **- Easy -**  Time to solution : **33,41 ms**
	 **- Medium -** Time to solution : **57320,34 ms**
	 **- Difficult -** Time to solution : **75722,249 ms**

	 Nous constatons que cette version de solverPSO est **tr�s efficace** pour les grilles de Sudoku de difficult� **Easy**
	 En revanche, elle ne l'est pas pour les difficult�s sup�rieures. Pour obtenir de meilleurs r�sultats, l'id�al est de s'appuyer sur la librairie suivante:
	 https://github.com/yasserglez/metaheuristics

## Metaheuristics

	Afin d'avoir de meilleures performances pour les difficult�s sup�rieures, nous pouvons utiliser la librairie **metaheuristics** gr�ce au d�p�t pr�c�dant.

### Definition 

	Une **m�taheuristique** repr�sente une cat�gorie d'**algorithmes d'optimisation** con�us pour r�soudre des probl�mes difficiles issus de divers domaines tels que la recherche op�rationnelle, l'ing�nierie ou l'intelligence artificielle. 
	Ces probl�mes souvent complexes ne peuvent �tre efficacement r�solus par des m�thodes conventionnelles.
	Les m�taheuristiques sont g�n�ralement des **algorithmes it�ratifs** et **stochastiques**. Ils progressent vers une solution optimale globale, souvent d�sign�e comme l'extremum global d'une fonction, en �chantillonnant une fonction objectif.
	Fonctionnant comme des **algorithmes de recherche**, les m�taheuristiques s'adaptent au probl�me en apprenant ses caract�ristiques afin de converger vers une solution optimale, g�n�ralement une approximation, qui se rapproche de l'optimum global. Cette approche est similaire � celle des algorithmes d'approximation.
	

### D�finition TSP (Travelling Salesman Problem)

	Le **TSP (Travelling Salesman Problem)** est un probl�me de **combinatoire** qui constitue un d�fi d'optimisation.
	Il consiste � trouver le parcours le plus court qui relie un ensemble donn� de villes en les visitant chacune exactement une fois.
	Ce probl�me est embl�matique en informatique, suscitant un grand int�r�t de recherche et servant souvent d'introduction � l'algorithmique et � la th�orie de la complexit�.
	Il trouve de nombreuses applications pratiques, notamment dans la planification, la logistique et des domaines plus �loign�s tels que la g�n�tique, o� les villes repr�sentent des g�nes et la distance entre elles refl�te leur similarit�.


## PSOsolver version 2




### Performances globales 

	**Coloration Graph Solver** easy 1 :  65,1349 ms 
	**CSPchoco** easy 1 :  53,8512 ms 
	**Simulatedannealing** easy 1 : 27,2353 ms
	**Backtrackingdotnet** easy 1 : 2,4842 ms

## Difficult�s g�n�rales rencontr�es

	- Difficult�s pour Pull pour avoir les ajouts des autres solvers des autres groupes quand on est dans la partie Choose a solver.
	- Conflits lors des fusions avec les modifications pr�c�dentes du professeur qu'on n'avait pas r�cup�r�.
    - Choix des fichiers utils pour notre cas car il y a plusieurs fichiers PSO diff�rents (Best, First). On les a regard� mais on a eu du mal � retranscrire le probl�me TSP en probl�me Sudoku.


## Journal de bord

	R�sum� de ce qu'on a r�alis� **en temps r�el**

### Premier Pull-Request (PR) : Ajout projet PSO

	� **Fork** du repository principal sur Github et attribu� les droits d��dition sur le fork � l��quipe en charge du projet dans l�onglet settings de notre d�p�t
	� Clonage local du fork sur chacune des machines des membres du groupe
	� Chargement de la solution existante *.sln 
	� D�finition du projet **Sudoku.Benchmark** comme **projet de d�marrage**
	� Ex�cution du projet **Benchmark** pour v�rifier que l�application est fonctionnelle
	� Cr�ation d'un nouveau projet de type biblioth�que de classe de pr�f�rence 
	� Dans le nouveau projet r�f�renciation du projet noyau **Sudoku.Shared** contenant la d�finition d�un Sudoku et de l�interface de solver
	

### Deuxi�me PR : PSO Premi�re Tentative 

#### Liste des classes 

	**1- PSOSolver** 
	**2- Particle** (avec ses constructeurs)

#### Liste des m�thodes 

	**1- UpdatePosition**, qui nous permet de mettre � jour les positions des particules
    **2- SudokuGrid Solve**, qui nous permet de r�soudre la grille de Sudoku
	  - En derni�re partie du code de la classe **Particle** en commentaire, on a cherch� � impl�menter une m�thode **UpdateVelocity** pour calculer la mise � jour des vitesses des particules

#### Difficult�s 

	- Comprendre la **th�orie** de la m�thode PSO
	- Quand nous lan�ons la premi�re version de notre code, il y a des **erreurs** sur **Sudoku.Benchmark**

### Troisi�me PR : PSOsolver de base fonctionnel 

#### Liste des nouvelles classes du d�p�t SudokuCombinatorialEvolutionSolver 

	**3- MatrixHelper**
	**4- Organism**
	**5- OrganismType**
	**6- Sudoku**

	Notre premier solver r�sout les Sudoku de niveau - Easy - mais il prend plus de temps (environ 1min) pour r�soudre les Sudoku de difficult�s sup�rieures. 
	Maintenant, on se penche sur la librairie Heuristiclab afin d'utiliser metaheuristics. On regarde �galement l'adaptation TSP / PSO pour optimiser notre Solver.
	
### Quatri�me PR (Partiel) : Avancement solver PSO avec metaheuristics 

	Il nous faut concevoir la traduction du Sudoku en probl�me compatible gr�ce au PSO discr�tis� (DiscretePSO), qui est impl�ment� dans le d�p�t **metaheuristics**. 
	On s'est inspir� de ce qui a �t� fait pour le **TSP** (cf d�finition plus haut)
	L'adaptation TSP/PSO a �t� effectu�e dans ce d�p�t et pr�sente de bons r�sultats. 

    Pour comprendre cela, nous avons clon� et test� le code du d�pot en question. Comme il y a beaucoup de tests effectu�s, nous avons fait le m�nage en commentant ce qui n'est pas utile, c'est � dire que nous avons comment� tout dans le fichier **Main** � l'exception par exemple de la ligne 

	```
	new PSO2OptBest4TSP(),

	```
    






