# L'Intelligence Artificielle existe-t-elle ?

J'ai lu le livre "L'intelligence artificielle n'existe pas" de Luc JULIA.   
Ce livre est en grande partie (un peu plus de la moitié) une biographie de l'auteur 
(une personne brillante et pragmatique à l'origine de plusieurs concepts ayant eu des applications pratiques comme Siri, les imprimantes connectées. 
Des concepts très utiles mais assez éloignés des techniques de "Deep learning", qu'on associe souvent à la notion d' "Intelligence Artificielle", d'après ce que j'en sais) 
ainsi qu'une description des usages liés aux objets connectés du futur.  

Mais je souhaitais réagir à la partie du livre qui concerne son titre : "L'intelligence artificielle n'existe pas"  
L'auteur expose un point de vue très tranché : celui que les machines ne disposeraient absolument pas d'une intelligence : 
celle qui permet d'innover, de s'adapter à de nouvelles situations.  
Seul l'humain disposerait de cette intelligence : les algorithmes utilisés par les machines n'auraient rien à voir avec cela, 
ce ne seraient que de vulgaires techniques "mathématiques et statistiques"  

Or certes, l'état actuel de l'IA n'est pas au niveau humain, mais je suis en désaccord avec l'affirmation "haut et fort" de l'auteur qu'elle n'a rien à voir.  
Voici ma réponse aux principaux arguments fournis :

> Sur l'intelligence de Siri  

Il y a eu beaucoup de marketing autour de Siri en vue de nous faire croire que c'était un système intelligent.  
Or dans la première version de Siri il n'y avait en réalité aucune technique avancée d'intelligence artificielle à ma connaissance (de type deep learning).  
Siri n'est pas une référence en matière d'intelligence artificielle, il est donc abusif de l'utiliser en exemple pour indiquer que l'IA n'existe pas.
Pour s'en convaincre on pourra aller voir le rapport [https://www.stateof.ai/](State of AI) 2020 qui indique :  
"AI dialogue assistants are live and **handling calls from UK customers today**"
"PolyAI has rolled out its voice assistant for hospitality in the UK. The system is actively answering reservation calls and assisting diners with special dietary requirements and providing COVID-19 guidance."  

> Les machines seraient incapables de reconnaître des objets dans des contextes qu'ils n'ont jamais vus  
> Je cite l'auteur : "Les machines sont incapables de contextualiser. Si lors de la phase d'apprentissage, on n'a pas fourni d'images de chat prises la nuit, il y a peu de chances que le système reconnaisse un chat dans la nuit"  

Pourtant, j'ai réalisé l'entraînement d'un réseau de neuronnes convolutif qui est capable de reconnaître un chien de nuit, en voici un exemple :  
<img src="Screenshot_20201008-231908.jpg" width="200">

Ce chien aux yeux rouges un peu surnaturels est reconnu à juste titre comme un Eskimo dog à 87% de probabilité et comme un Siberian Husky (une race qui ressemble beaucoup à l'Eskimo dog) à 12%.  
Les données utilisées pour entraîner ce réseau de neuronnes proviennent de la banque d'images ImageNet et du stanford dogs dataset : aucune de ces banques d'images ne comportent d'images de Siberian Husky prises de manière sombre, dans ce contexte de nuit un peu surnaturel.  
Le deep learning a-t-il donc permis à la machine de généraliser ce qu'elle connait à une situation nouvelle ?  

Le code source du réseau de neuronnes que j'ai construit pour générer cette reconnaissance [https://www.kaggle.com/franoisboyer/openclassrooms-pj7-modelisation-part-6](est disponible ici) :  






