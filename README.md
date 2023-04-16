# pokedox
<p align="center">
<img src="https://user-images.githubusercontent.com/85010162/150538692-6323d2fd-437e-45b0-946f-690a8ec5e829.png"/>
</p>

<h1 align="center">Pokemon - PokeAPI</h1>



<p align="center">  
⚔️ ϞϞ (๑⚈ ․̫ ⚈๑)∩ Le développement du projet avec ViewBinding, ViewModel avec LiveData, Dagger2, Retrofit2 avec RxJava3, Room Database, MaterialCardView avec ShapeableOverlay Style et ProgressView basé sur l'architecture MVVM.
</p>
</br>

<p align="center">
<img src="https://user-images.githubusercontent.com/85010162/150537968-23b0f9fb-066b-4170-b1f6-5a76e0fd6d12.png"/>
</p>



## Pile technologique et bibliothèques open-source
Architectures et composants
Architecture MVVM (Modèle - Vue - ViewModel)
Patron de conception Repository
ViewModel - Permet aux données de survivre aux changements de configuration tels que les rotations d'écran.
LiveData - Une classe de conteneur de données observable.
ViewBinding - Une fonctionnalité qui vous permet d'écrire plus facilement du code qui interagit avec les vues.
SwipeRefreshLayout - Implémenter le modèle d'interface utilisateur "Swipe-to-Refresh".
La persistance Room - Fournit une couche d'abstraction sur SQLite pour permettre un accès à la base de données plus robuste tout en exploitant toute la puissance de SQLite.
- [Retrofit2 & OkHttp3](https://github.com/square/retrofit) - Un client HTTP de type sécurisé pour Android et la JVM.

- [Dagger](https://github.com/google/dagger) - Un injecteur de dépendances rapide pour Android et Java.

- [Glide](https://github.com/bumptech/glide), [GlidePalette](https://github.com/florent37/GlidePalette) - Chargement des images à partir du réseau.
- [Material-Components](https://github.com/material-components/material-components-android) - Composants de design matériel pour la construction de CardView.
- [ProgressView](https://github.com/skydoves/progressview) - Une vue de progression polie et flexible, entièrement personnalisable avec des animations.

Ce code représente une activité dans une application Android qui affiche des détails sur un élément sélectionné. Voici une explication détaillée du code : 
La classe DetailActivity étend la classe AppCompatActivity, qui est une classe de base pour les activités de l'application Android.
 La méthode onCreate est appelée lorsque l'activité est créée. Dans cette méthode, l'interface utilisateur est définie en utilisant le fichier de disposition ActivityDetailBinding. 
La méthode setContentView est utilisée pour définir la vue principale de l'activité en utilisant la méthode getRoot de l'objet activityDetailBinding. 
La méthodegetWindow().getDecorView().setSystemUiVisibility(View.SYSTEM_UI_FLAG_HIDE_NAVIGATION); est utilisée pour cacher la barre de navigation Android en bas de l'écran. 
La méthode setUpDetailFragment est appelée pour initialiser le fragment de détails. Cette méthode utilise le FragmentManager pour remplacer le conteneur de fragment par le DetailFragment. 
La méthode onWindowFocusChanged est appelée lorsque la fenêtre gagne ou perd le focus. Dans cette méthode, l'interface utilisateur est mise à jour pour cacher les barres de navigation et les barres d'état.
 La méthode getWindow().getDecorView().setSystemUiVisibility est utilisée pour cacher la barre de navigation et la barre d'état et pour rendre l'interface utilisateur en mode plein écran. 
En résumé, ce code initialise une activité pour afficher les détails d'un élément sélectionné et masque les barres de navigation et les barres d'état pour une expérience utilisateur améliorée.

Ce code est une implémentation d'un adaptateur pour une RecyclerView qui sera utilisé pour afficher une liste de Pokémon.

La classe PokemonRecyclerViewListAdapter étend la classe ListAdapter, qui est fournie dans la bibliothèque Android Jetpack, et qui est une extension de RecyclerView.Adapter. Cette classe utilise la méthode DiffUtil pour calculer les différences entre deux listes et mettre à jour la vue uniquement pour les éléments qui ont été modifiés. Elle prend également en compte les interactions avec les utilisateurs via OnItemClickListener.

La classe a un constructeur qui prend un contexte, un OnItemClickListener et un objet DiffUtil.ItemCallback en paramètres. Elle utilise également une liste de type ArrayList pour stocker les données.

La méthode onCreateViewHolder() est appelée lorsque la RecyclerView a besoin d'un nouveau ViewHolder pour afficher un élément. Cette méthode crée une instance de la classe RecyclerViewViewHolder en utilisant PokemonItemBinding pour inflater la vue.

La méthode onBindViewHolder() est appelée pour remplir les données dans la vue du ViewHolder. Elle récupère l'élément à la position donnée dans la liste de Pokémon, met à jour les données dans la vue en fonction de cet élément et définit un écouteur de clic sur l'élément.

La méthode getItemCount() renvoie le nombre d'éléments dans la liste de Pokémon.

La méthode refreshPokemonList() ajoute des données à la liste de Pokémon et met à jour la vue. La méthode clearAllOldData() vide la liste de Pokémon et met à jour la vue.

La classe RecyclerViewViewHolder est une classe interne statique qui contient la vue de chaque élément de la liste de Pokémon.

La classe PokemonDiff est une classe interne statique qui définit comment la méthode DiffUtil doit comparer les éléments de la liste de Pokémon.

L'interface OnItemClickListener définit une méthode onClick() qui est appelée lorsque l'utilisateur clique sur un élément de la liste de Pokémon. Cette méthode prend le nom et l'image du Pokémon en tant que paramètres.



Ce code contient une classe appelée "Converters" qui contient deux méthodes de conversion utilisées par la bibliothèque de persistance de données Room. Room est une bibliothèque Android qui fournit une couche d'abstraction sur SQLite pour simplifier la gestion de la base de données.

Les deux méthodes dans la classe Converters sont utilisées pour convertir une liste d'objets de type "TypesResponse" en format JSON et vice versa.

La première méthode, "listToJson", prend une liste d'objets "TypesResponse" et la convertit en une chaîne JSON à l'aide de la bibliothèque Gson. Gson est une bibliothèque Java qui permet de convertir des objets Java en chaînes JSON et vice versa.

La deuxième méthode, "jsonToList", prend une chaîne JSON et la convertit en une liste d'objets "TypesResponse" à l'aide de la bibliothèque Gson. La méthode utilise également un objet de type "TypeToken" pour permettre à Gson de savoir quelle est la structure de l'objet JSON à convertir en une liste d'objets "TypesResponse".

Ces méthodes sont utilisées par Room pour stocker et récupérer des listes d'objets "TypesResponse" dans la base de données SQLite.



Ce code définit un module Dagger pour la création d'objets liés au réseau.

La classe NetworkModule contient plusieurs méthodes annotées avec @Provides, qui indiquent à Dagger comment créer et fournir des objets à d'autres classes.

La méthode provideOkHttpClient fournit un objet OkHttpClient, qui est configuré pour inclure un HttpLoggingInterceptor pour la journalisation des requêtes et des réponses HTTP.

La méthode provideRetrofit fournit un objet Retrofit, qui est utilisé pour configurer la base de l'URL de l'API, l'objet OkHttpClient, et les convertisseurs de type pour les réponses (GsonConverterFactory) et les observables (RxJava3CallAdapterFactory).

La méthode provideAPIService fournit une interface APIService, qui est créée à partir de l'objet Retrofit.

La méthode provideAPIClient fournit un objet APIClient, qui est créé en utilisant l'objet APIService.

Dans l'ensemble, ce module permet de créer des objets liés au réseau, notamment l'objet APIClient qui est utilisé pour interagir avec l'API PokeAPI.
 






## Architecture
<p align="center">
Le projet est basé sur l'architecture MVVM.
</p>

<p align="center">
<img src="C:\Users\sboul\OneDrive\Bureau\PokeAPI-Java-master\Cap.png"/>
</p>

## Open API
<img src="https://user-images.githubusercontent.com/85010162/150532477-e758e4db-6261-47da-81da-815139a0be8d.png" align="right" width="20%"/>

Le projet utilise PokeAPI pour construire une API RESTful.<br>
PokeAPI fournit une interface API RESTful vers des objets hautement détaillés construits à partir de milliers de lignes de données liées à Pokémon.
