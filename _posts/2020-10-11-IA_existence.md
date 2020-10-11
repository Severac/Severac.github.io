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

Pourtant, voici un contre exemple : j'ai réalisé l'entraînement d'un réseau de neuronnes convolutif qui est capable de reconnaître un chien de nuit, en voici un exemple :  
<img src="../images/Screenshot_20201008-231908.jpg" width="200">

Ce chien aux yeux rouges un peu surnaturels est reconnu à juste titre comme un Eskimo dog à 87% de probabilité et comme un Siberian Husky (une race qui ressemble beaucoup à l'Eskimo dog) à 12%.  
Les données utilisées pour entraîner ce réseau de neuronnes proviennent de la banque d'images ImageNet et du stanford dogs dataset : aucune de ces banques d'images ne comportent d'images de Siberian Husky prises dans ce contexte de nuit un peu surnaturel.  
Le deep learning a-t-il donc permis à la machine de généraliser ce qu'elle connait à une situation nouvelle ?  
La technique du "transfer learning" a révolutionné le domaine de la reconnaisance d'images: en partant d'un modèle qui n'a vu que des images très générales, on peut le spécialiser à un domaine particulier en ne lui montrant que quelques dizaines d'exemples.  

Le code source du réseau de neuronnes que j'ai construit pour générer cette reconnaissance [https://www.kaggle.com/franoisboyer/openclassrooms-pj7-modelisation-part-6](est disponible ici) :  

> Les enfants auraient besoin de beaucoup moins d'exemples que la machine pour reconnaître une image  
> "Si on interroge les psychologues, ils nous disent que les enfants n'ont besoin que de deux instances d'images de chat pour les reconnaître à vie"  

L'auteur oublie la partie immergée de l'iceberg : l'élément le plus important qui permet cette compétence.  
Arrivé à l'âge de 2 ans, combien d'images d'objets, d'animaux, l'enfant a-t-il déjà vues ? Mieux que des images, il est exposé à un flux vidéo constant d'objets à différents niveau de zoom, de rotation, de couleurs, etc... Citez moi une seule IA connue qui a été entraînée sur autant de données ?   
Pourquoi l'humain reconnait-il si facilement des objets avec peu d'exemples ? Parce que la perception repose largement en dehors de ce qui est purement conscient: on dépend très largement d'informations venant d'organes visuels, auditifs,... spécialisés, et aussi de zones de notre cerveaux spécialisées dans cela.  
Quand vous voyez un chaton, vous ne pouvez pas *choisir* de ne pas voir le chaton: vous n'avez pas le choix, l'information est déjà passée par des zones plus "bas niveau" de votre corps et de votre cerveau qui ont fait le travail pour vous. Est-ce que vous pouvez expliquer comment vous avez fait pour reconnaître que c'est un chaton ? Est-ce que cette partie de votre subconscient qui reconnaît immédiatement le chaton est intelligente ?  
Les réseaux de neuronnes convolutifs qui font le succès de l'IA en reconnaissance d'images sont justement issus de l'étude du cortex visuel cérébral, ils fournissent justement l'équivalent de ces fonctionnalités "bas niveau" de reconnaissance de formes, et sont capables de performances meilleures que les humains dans certains domaines.  

Pourquoi a-t-on besoin de fournir à une IA des images avec différents niveaux de zoom, de luminosité, de rotation, ....  
<img src="https://github.com/Severac/Severac.github.io/blob/master/_posts/Data augmentation.png" width="600">

Serait-ce parce que l'IA n'est pas plongée dans le monde physique réel comme nous le sommes : elle n'a pas toutes nos connaissances.  
Mais si l'IA a besoin de ce type d'exemples contextuels, est-ce que c'est parce que *l'intelligence artificielle n'existerait pas* comment l'auteur semble le croire ? Ou bien est-ce davantage une question de manque de connaissance a priori de l'IA sur le monde (auquel on pallie en partie en fournissant des exemples) ?  

Bien sûr cela ne veut pas dire que les IA ont atteint le niveau humain, nous en sommes encore loin.  
Ce papier de recherche permet d'aller plus loin sur la question et creuse d'autres aspects comme la différence entre les connaissances acquises et innées : [https://arxiv.org/abs/1911.01547](https://arxiv.org/abs/1911.01547)  

> Les IA d'échecs ne seraient douées d'aucune intelligence ni créativité  

Je m'intéresse aux échecs et je peux affirmer que l'IA Alpha Zero de deep mind est époustouflante de créativité, d'initiative, de prise de risque.  
Posez la question à n'importe quel joueur d'échecs ayant visionné quelques parties.  
Je ne détaillerai pas cela ici car le sujet a déjà largement été traité, mais Alpha Zero est le contre exemple absolu de ce qu'indique l'auteur.

De plus, Alpha Zero a vaincu Stockfish (qui était jusqu'alors le meilleur moteur d'échecs existant) en utilisant beaucoup moins de puissance de calcul que ce dernier.  
Voici quelques vidéos de parties d'alpha zero :  
[https://www.youtube.com/watch?v=PH06mEOVVyY&t=187s](https://www.youtube.com/watch?v=PH06mEOVVyY&t=187s)
[https://www.youtube.com/watch?v=lFXJWPhDsSY](https://www.youtube.com/watch?v=lFXJWPhDsSY)








