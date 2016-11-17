<p></p>
<h1>COMPTE RENDU PROJET WEB GL</h1>
<p></p>
<h2>	1 . Fonctionnement</h2>
<p></p>
<p>L objectif  de  ce  projet  �tait  de  mod�liser  une  boule  qui  se  d�place  dans  un  labyrinthe.  </p>
<p>Le  d�placement  de  la boule se fait � l aide des touches directionnelles. </p>
<p>Il est possible de changer l angle de la cam�ra pour voir o� se d�placer dans le labyrinthe. </p>
<p>Pour ce faire, il suffit de cliquer � l aide de la souris.</p>
<p></p>
<h2>	2 . Explication</h2>
<p></p>
<h3>CREATION DE LA BOULE</h3>
<p></p>
<p>Notre  boule  est  cr�e  simplement  �  partir  d'un  simple  sph�re  sur  laquelle  nous </p>
<p>avons  ajout�  une texture et une illumination.</p>
<p></p>
<h3>CREATION DU LABYRINTHE</h3>
<p></p>
<p>Apres diff�rents essais infructueux qui auraient permis d'importer directer un labyrinthe en format .obj ou format .babylon, </p>
<p>nous avons d�cid� de cr�er notre propre labyrinthe � l aide de plusieurs boxes.</p>
<p>Ainsi, la gestion des collisions se fera au cas par cas selon les boxes rencontr�es et l'angle de la cam�ra.</p>
<p>sous lequel est vu le labyrinthe.</p>
<p></p>
<h3>GESTION DES DEPLACEMENTS DE LA BOULES</h3>
<p></p>
<p>Nos  d�placements  se  font  selon  les  fl�ches  haut,  bas,  droite,  gauche.  Le  deplacement (translation)</p>
<p>et  l'effet  de  roulement  (rotation)  se  font  selon  la  composante  du  temps.  Cette composante  </p>
<p>est  essentiel  afin  de  prendre  en  consid�ration  le  temps  que  la  touche  est  enfonc�e.  </p>
<p>Si on  omet  cette  derni�re,  notre  boule  tournera  qu'une  seule  fois  puis  se  d�placera  uniquement  </p>
<p>par rotation.Pour �viter l'effet de "patinage" nous faisons varier le temps entre 30 et 40.</p>
<p></p>
<h3>GESTION DE LA CAMERA</h3>
<p></p>
<p>Notre cam�ra est une follow cam�ra que nous avons attach� � l'objet sph�re, </p>
<p>c'est � dire la boule. Cela permet � l'utilisateur de suivre la boule en m�me temps que cette derni�re se d�place. </p> 
<p>Nous nous sommes rapidement heurter  � un probl�me : vouloir regarder autour de notre boule.</p> 
<p>Une solution est de switcher entre deux camera : la free lorsqu'on se d�place avec la souris et la follow lorsqu'on se d�place. </p>
<p>Toutefois, cela n�cessite de activer/d�sactiver les deux cam�ras.  Nous  avons  d�cid�  finalement  de  </p>
<p>r�aliser  une  rotation  de  90  �  lorsque  l'on  clique  sur  la  souris  pour permettre  au  joueur  de  </p>
<p>revenir  sur  ses  pas  et  ainsi  de  mieux  coller  avec  l'id�e  de  notre  jeux  :  chercher  une sortie, </p>
<p>se perdre et remonter ses pas.</p>
<p></p>
<h3>GESTION DES COLLISIONS</h3>
<p></p>
<p>Pour la gestion des collisions, nous enregistrons au fur et a mesure la derniere touche appuyee par l utilisateur. Ceci nous permettra de </p>
<p>determiner le cote du mur ou il y a eu collision. Tant qu aucune collision entre la sphere et les murs n a ete enregistre, on peut</p>
<p>faire tous les deplacements. Par contre, si une collision est detectee, on regarde la derniere touche appuyee par l�utilisateur. </p>
<p>Exemple : Si il y a eu collision sur un mur et que la derniere touche appuyee est la gauche alors on a touche le mur sur la droite donc la</p>
<p>sphere peut faire tous les deplacements sauf celui d aller a gauche. Et on reitere pour chaque touche.</p>
<p></p>
<h2>	3 . INTERETS ET BESOINS ADRESSES</h2>
<p></p>
<h3>INTERET DE LA ROTATION</h3>
<p></p>
<p>Lorsque  nous  avons  g�r�  les  d�placements  de  la  boule,  nous  avons  vu  que  cette  derni�re  </p>
<p>ne  subit qu'une  simple  translation.  Par  soucis  de  r�alisme,  nous  avons  �galement  ajout�  </p>
<p>une  rotation  selon  la  bonne coordonn�e dans le m�me temps.</p>
<p></p>
<h3>CHOIX DES COLLISIONS</h3>
<p></p>
<p>Il existe diff�rentes approches pour r�aliser la collisions :  </p>
<p>	-Point d'intersection  </p>
<p>	-Box de collisions</p>
<p></p>
<p>Nous avons choisi la box de collisions car les murs de notre labyrinthe sont des boxs. Par ailleurs, nous avons pense a deux methodes pour bien gerer nos collisions.</p>
<p>Soit :</p>
<p>	- enregistrer la derniere direction de la sphere afin de determiner sur quelle face du mur il y a eu collision.</p>
<p>	- realiser un rebond lors d une collision.</p>
<p>La derniere solution n a pas ete retenu car il aurait fallu faire bon nombre de calculs, dont l epaisseur du mur et recuperer la position du centre de la sphere. </p>
