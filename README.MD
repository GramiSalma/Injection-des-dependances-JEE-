<h1>Compte rendu de l'activité Pratique N° 1 - Injection des dépendances </h1>
Grami salma 
<h3>Introduction</h3>
<p>Plutôt que de créer des instances de dépendances directement dans une classe, l'injection de dépendances permet d'injecter ces dépendances depuis l'extérieur. Cela réduit le couplage(faible) entre les classes, ce qui les rend plus indépendantes et plus réutilisables. </p>
<br>
<h3>Enonce</h3>
1. Créer l'interface IDao avec une méthode getDate
<br>
2. Créer une implémentation de cette interface 
<br>
3. Créer l'interface IMetier avec une méthode calcul
<br>
4. Créer une implémentation de cette interface en utilisant le couplage faible
<br>
5. Faire l'injection des dépendances :

  a. Par instanciation statique

  b. Par instanciation dynamique

  c. En utilisant le Framework Spring

       - Version XML

       - Version annotations
<br>
<h3>Conception</h3>
<img alt="conception" src="captures/conception.png">
<p></p>
<br>

<h3>Captures ecran </h3>
Faire l'injection des dépendances :

<p>a. Par instanciation statique</p>
<img alt="conception" src="captures/instanciation_statique1.jpg">
<br>
<br>
<img alt="conception" src="captures/instanciation_statique2.png">
<p>L'instantiation statique n'est pas une bonne pratique car elle instancie directement les classes plutôt que les interfaces.
Ainsi, si des changements sont nécessaires à l'avenir, les développeurs sont obligés de modifier le code source directement. </p>
<br>
<br>
<p>b. Par instanciation dynamique</p>
<img alt="conception" src="captures/instanciation_dynamique1.jpg">
<br>
<br>
<img alt="conception" src="captures/instanciation_dynamique2.jpg">
<p>L'instanciation dynamique est une bonne pratique qui respecte le couplage faible, où l'on crée un 
fichier texte config.txt : la première ligne contient la couche DAO et la deuxième ligne contient la couche
métier à utiliser. Ensuite, dans la couche présentation, on instancie dynamiquement les classes avec forName() et
.getConstructor().newInstance(), mais comme ça se répète
, on cherche mieux pour automatiser ce flux, d'où l'utilisation du framework Spring qui automatise tout ça. </p>
<br>
<br>
<p>c. En utilisant le Framework Spring</p>
<br>
<br>


       - Version XML
<img alt="conception" src="captures/springxml.jpg">
<br>
<br>
<img alt="conception" src="captures/springxml2.jpg">
<p>Spring lit les interfaces à injecter et les dépendances depuis un fichier de configuration
, généralement nommé config.xml, où il trouve les beans et les propriétés nécessaires.
Ce fichier de configuration est utilisé par la couche de présentation de l'application.
Pour travailler avec cette méthode, il est nécessaire de télécharger trois dépendances principales : 
Spring Framework, Spring Context et Spring Beans.</p>
<br>
<br>

       - Version annotations
<img alt="conception" src="captures/springannotations.png">
<p>Spring utilise les annotations comme alternative aux fichiers XML pour configurer et gérer la partie technique d'un projet, offrant ainsi une approche plus concise et plus facile à maintenir.</p>
<h3>Conclusion</h3>
<p>En résumé, dans ce TP en manipulant différents modes d'injection, nous avons bien compris le principe clé de Spring, et aussi cela renforce nos capacités à développer des applications fermées à la modification et ouvertes à l'extension.</p>