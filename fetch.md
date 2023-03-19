## La méthode Fetch en JavaScript

La méthode Fetch est une fonctionnalité JavaScript qui permet d'effectuer des requêtes HTTP asynchrones depuis un navigateur web. Elle permet de récupérer des données depuis des serveurs web.

Fetch utilise une syntaxe simple qui facilite son utilisation. Elle prend comme argument une URL qui pointe vers une ressource à récupérer, et retourne une réponse.

Voici un exemple suivant votre MVC :

Coté back :

Faire une route :

```
$router->map(
    'GET',
    '/api/teachers',
[
    'method' => 'teacher',
    'controller' => TeacherController::class
],
    'teacher_list'
);
```


Créer une fonction qui permet de return un json :
```
public function teacher()
{
    $newteacher = new Teacher();
    $teachers = $newteacher->findAll();

    header('Content-Type: application/json');
    return json_encode(['teachers' => $teachers]);
}

```

Et au niveau du front il nous faut un fetch pour récupérer la donnée

```
fetch('https://monserveur.com/api/teacher')
  .then(response => response.json())
  .then(data => {
    console.log(data);
  })
  .catch(error => {
    console.error(error);
  });
```