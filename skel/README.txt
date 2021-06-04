Ciobanu Alin-Matei 335CB

R = A x B x Bt + At x A

neopt:
- varianta "de mana", tin cont ca A este superior triunghiulara, deci nu mai inmultesc cu 0
- calculez C1 = B x Bt; C1 este matrice simetrica; calculez doar diagonala principala si elementele
  de deasupra ei apoi completez prin simetrie
- calculez C2 = A x Bt; A superior triunghiulara, nu inmultesc cu 0
- tin cont ca At x A este matrice simetrica, astfel calculez doar elementele de deasupra diagonalei
  principale

opt_m:
- folosesc hint-ul pt compilator register
- utilizez pointeri pt acceserarea elementelor matricelor pentru sporirea vitezei
- B x Bt matrice simetrica
- A x (B x Bt) - tin cont ca A matrice superior triunghiulara
- At x A - matrice simetrica; A superior triunghiulara, At inferior triunghiulara

blas:
- calculez B x Bt cu cblas_dgemm si salvez rezultatul in C
- calculez A X C cu cblas_dtrmm si salvez rezultatul in C
- calculez At x A cu cblas_dtrmm si salvez rezultatul in A


- timpii de rulare de pe coada nehalem se gasesc in fisierul script.sh.o, iar graficul aferent
acestor timpi se gasesc in performance_graphic.png