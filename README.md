# TGP-Correction

### Résumé de The Gossip Project :

TGP est une application web permettant de créer et consulter des potins. 

* Sur la page d'accueil l'ensemble des potins,
  * avec le nombre de like et la posibilité de liker le potin
  * avec le nombre de commentaires associés
  
* En détail, en cliquant sur un potin :
  * sur la page du potin, il verra le contenu intégral du potin (titre et contenu) ainsi que le nom de la personne qui l'a créé, sa ville, et la date de création/modification. 
  * Il pourra cliquer sur le nom de l'utilisateur et ainsi voir son profil 
  * Il pourra cliquer sur le nom de la ville et voir l'ensemble des potins associés à cette ville 
  * Il pourra liker le potin 
  * Il pourra commenter le potin 
  
* Pour créer un potin, l'utilisateur doit impérativement être inscrit et connecté.
  * Il pourra créer un compte 
  * Il pourra de logger 
  * Il pourra se délogger

### Les énoncés  : 

##### 1) La création des models  

https://www.thehackingproject.org/dashboard/courses/1/projects/23?locale=fr

##### 2) Les views

https://www.thehackingproject.org/dashboard/courses/1/projects/14?locale=fr

##### 3) Créer un potin ( form_tag)

https://www.thehackingproject.org/dashboard/courses/1/projects/17?locale=fr

##### 3) Full CRUD 

https://www.thehackingproject.org/dashboard/courses/1/projects/18?locale=fr
- Une page par potin 
- Une page profil du user 
- Une page ville permettant de visualiser l'ensemble des potins d'une même ville
- Permettre la modification d'un potin 
- Permettre la suppression d'un potin 
- Permettre de commenter un potin, modifier et supprimer un commentaire
- Ajout d'alertes pour informer l'utilisateur du bon déroulement du process ou de son echec 

##### 4) Facebook style 

https://www.thehackingproject.org/dashboard/courses/1/projects/90?locale=fr

- Création d'un utilisateur (sign in) 
- Login
- Logout
- Un potin ne peut pas être créé sans être inscrit et loggé 
- Un user connecté peut créer, modifier et supprimer ses propres potins 
- Permettre de liker/déliker un potin sur la page d'accueil, la page ville et la page détail d'un potin 

### Les détails des routes-controller-views

##### USER
* Route : users
* Controller : users_controller.rb
  * Méthode new
  * Méthode create
  * Méthode show
* Views : 
  * new.html.erb *permet de créer un nouveau user*
  * show.html.erb *permet de voir le profil d'un user*

##### GOSSIP
* Route : gossips
* Controller : gossips_controller.rb
  * Méthode index
  * Méthode show
  * Méthode new
  * Méthode create *Si la création d'un potin est ok, on redirige vers la page du potin avec message de succes, sinon on reste sur la page de création*
  * Méthode edit
  * Méthode update *Si la modif d'un potin est ok, on redirige vers la page du potin avec message de succes, sinon on revient sur la page de modif*
  * Méthode destroy *Si le potin a été bien supprimé, on redirige vers la page d'accueil avec message de succes*
* Views : 
  * index.html.erb *définit comme l'accueil du site root_path avec l'ensemble des potins*
  * new.html.erb *permet de créer un nouveau gossip*
  * show.html.erb *permet de voir le détail d'un gossip, commenter et liker*
  * edit.html.erb *permet de modifier un potin*

##### LIKE
* Route : likes => cette route est dépendante de la route gossip
* Controller : likes.controller.rb
  * Méthode new
  * Méthode create
  * Méthode destroy
* Aucune view !

##### CITY
* Route : cities 
* Controller : 
  * Méthode show 
* Views : 
  * show.html.erb *permet de visualiser les potins de la ville concernée*
  
##### SESSION
* Route : sessions
* Controller : 
  * Méthode new
  * Méthode create *permet de se connecter avec l'adresse email - Si le couple email/password est ok, on envoi un message de bienvenue avec une redirection vers la page d'accueil, sinon on renvoi un message d'alerte et un renvoi vers la page de login*
  * Méthode destroy *permet de se déconnecter* 
* Views : 
  * new.html.erb *permet la connecter a son compte*
 
  

