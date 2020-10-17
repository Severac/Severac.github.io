# L'Intelligence Artificielle existe-t-elle ?

J'ai lu le livre "L'intelligence artificielle n'existe pas" de Luc JULIA.   
Ce livre est en grande partie (un peu plus de la moitié) une biographie de l'auteur 
(une personne brillante et pragmatique à l'origine de concepts comme Siri, les imprimantes connectées, des concepts très utiles mais assez éloignés des techniques de "Deep learning", et donc assez éloignés de l' "Intelligence Artificielle", puisque c'est au deep learning qu'on associe souvent l'intelligence artificielle) 
ainsi qu'une description des usages liés aux objets connectés du futur.  

Mais je souhaitais réagir à la partie du livre qui concerne son titre : "L'intelligence artificielle n'existe pas"  
L'auteur expose un point de vue très tranché : celui que les machines ne disposeraient absolument pas d'une intelligence : 
celle qui permet d'innover, de s'adapter à de nouvelles situations.  
Seul l'humain disposerait de cette intelligence : les algorithmes utilisés par les machines n'auraient rien à voir avec cela, 
ce ne seraient que de vulgaires techniques "mathématiques et statistiques"  

Or certes, l'état actuel de l'IA n'est pas au niveau humain, mais contrairement à ce qu'affirme l'auteur, on peut bien selon moi parler d'intelligence.

Voici pourquoi, et voici ma réponse aux principaux arguments fournis par l'auteur pour affirmer que l'IA n'existerait pas :

> D'après l'auteur, Siri n'est pas intelligent

Il y a eu beaucoup de marketing autour de Siri en vue de nous faire croire que c'était un système intelligent.  
Or dans la première version de Siri il n'y avait en réalité aucune technique avancée d'intelligence artificielle à ma connaissance (de type deep learning).  
Siri n'est pas une référence en matière d'intelligence artificielle, il est donc abusif de l'utiliser en exemple pour indiquer que l'IA n'existe pas.  
Pour s'en convaincre on pourra aller voir le rapport [https://www.stateof.ai/](State of AI) 2020 qui indique que d'autres assistants vocaux sont capables de réaliser des tâches avancées :  
AI dialogue assistants are live and **handling calls from UK customers today**  
PolyAI has rolled out its voice assistant for hospitality in the UK. **The system is actively answering reservation calls and assisting diners with special dietary requirements and providing COVID-19 guidance.**  
Powered by the company's latest deep learning technology, **the system can understand noisy speech from telephone lines and has a success rate of >90% for an average 8-turn conversation."**

> Les machines seraient incapables de reconnaître des objets dans des contextes qu'ils n'ont jamais vus  
> Je cite l'auteur : "Les machines sont incapables de contextualiser. Si lors de la phase d'apprentissage, on n'a pas fourni d'images de chat prises la nuit, il y a peu de chances que le système reconnaisse un chat dans la nuit"  

Pourtant, voici un contre exemple : j'ai réalisé l'entraînement d'un réseau de neuronnes convolutif qui est capable de reconnaître un chien de nuit. Voici ce que détecte le modèle :  
<img src="https://blog.analysons.com/images/Screenshot_20201008-231908.jpg" width="200">

Ce chien aux yeux rouges un peu surnaturels est reconnu à juste titre comme un Eskimo dog à 87% de probabilité et comme un Siberian Husky (une race qui ressemble beaucoup à l'Eskimo dog) à 12%.  
Les données utilisées pour entraîner ce réseau de neuronnes proviennent de la banque d'images ImageNet et du stanford dogs dataset : aucune de ces banques d'images ne comportent d'images de Siberian Husky ou d'Eskimo dog prises dans ce contexte de nuit.  
Le deep learning a donc ici permis à la machine de généraliser ce qu'elle connait à une situation nouvelle.  
Cela est possible grâce à la technique du "transfer learning" qui a révolutionné le domaine de la reconnaisance d'images: en partant d'un modèle qui n'a vu que des images très générales, on peut le spécialiser à un domaine particulier en ne lui montrant que quelques dizaines d'exemples.

Le code source du réseau de neuronnes que j'ai construit pour générer cette reconnaissance [https://www.kaggle.com/franoisboyer/openclassrooms-pj7-modelisation-part-6](est disponible ici) :  

> Les enfants auraient besoin de beaucoup moins d'exemples que la machine pour reconnaître une image  
> "Si on interroge les psychologues, ils nous disent que les enfants n'ont besoin que de deux instances d'images de chat pour les reconnaître à vie"  

L'auteur oublie la partie immergée de l'iceberg : l'élément le plus important qui permet cette compétence.  
Arrivé à l'âge de 2 ans, combien d'images d'objets, d'animaux, l'enfant a-t-il déjà vues ? Mieux que des images, il est exposé à un flux vidéo constant d'objets à différents niveau de zoom, de rotation, de couleurs, etc... Citez moi une seule IA connue qui a été entraînée sur autant de données ?   
Pourquoi l'humain reconnait-il si facilement des objets avec peu d'exemples ? Parce que la perception repose largement sur des mécanismes qui ne sont pas purement conscients: on dépend très largement d'informations venant d'organes visuels, auditifs,... spécialisés, et aussi de zones de notre cerveaux spécialisées dans cela.  
Quand vous voyez un chaton, vous ne pouvez pas *choisir* de ne pas voir le chaton: vous n'avez pas le choix, l'information est déjà passée par le cortex visuel cérébral, qui a fait le travail pour vous. Est-ce que vous pouvez expliquer comment vous avez fait pour reconnaître que c'est un chaton ? Non, et pourtant, cette partie de votre subconscient qui reconnaît immédiatement le chaton fait bien partie de votre intelligence : et les réseaux de neuronnes convolutifs qui font le succès de l'IA en reconnaissance d'images jouent justement ce rôle, ils sont issus de l'étude du cortex visuel cérébral, ils fournissent justement l'équivalent de ces fonctionnalités "bas niveau" de reconnaissance de formes, et sont même capables de performances meilleures que les humains dans certains domaines.  

Pourquoi a-t-on besoin de fournir à une IA des images avec différents niveaux de zoom, de luminosité, de rotation, ....  
<img src="https://blog.analysons.com/images/Data augmentation.png" width="600">

C'est parce que l'IA n'est pas plongée dans le monde physique réel comme nous le sommes : elle n'a pas toutes nos connaissances.  
Mais si l'IA a besoin de ce type d'exemples contextuels, ce n'est pas parce que *l'intelligence artificielle n'existerait pas* comment l'auteur semble le croire ; c'est parce qu'elle part avec un handicap : celui du manque de connaissance a priori sur le monde physique (auquel on pallie en partie en fournissant beaucoup d' exemples).  

Bien sûr cela ne veut pas dire que les IA ont atteint le niveau humain, nous en sommes encore loin.  
Ce papier de recherche permet d'aller plus loin sur la question et creuse d'autres aspects comme la différence entre les connaissances acquises et innées : [https://arxiv.org/abs/1911.01547](https://arxiv.org/abs/1911.01547)  

> Les IA d'échecs ne seraient douées d'aucune intelligence ni créativité  

Je m'intéresse aux échecs et je peux affirmer que l'IA Alpha Zero de deep mind est époustouflante de créativité et d'initiative.  
Posez la question à n'importe quel joueur d'échecs ayant visionné quelques parties. Il vous répondra qu'Alpha Zero dispose d'un sens positionnel extrêmement développé. Or aux échecs, on oppose souvent le sens positionnel (le côté stratégique, qui a longtemps été réservé aux humains) et le sens tactique (le côté calcul pur) : dans les années 80, pour battre un programme d'échecs, il fallait jouer des coups "positionnels" de long terme que le programme ne pouvait pas comprendre.  De nos jours, c'est Alpha Zero qui joue des coups positionnels parfois très inattendus, qui sont en apparence faux (et que les anciens programmes d'échecs ne comprennent pas non plus), mais qui s'avèrent gagnants sur le long terme.  
Je ne détaillerai pas cela ici car le sujet a déjà largement été traité, mais Alpha Zero est le contre exemple absolu de ce qu'indique l'auteur.

De plus, Alpha Zero a vaincu Stockfish (qui était jusqu'alors le meilleur moteur d'échecs existant) en utilisant beaucoup moins de puissance de calcul que ce dernier.  
Voici quelques vidéos de parties d'alpha zero :  
[https://www.youtube.com/watch?v=PH06mEOVVyY&t=187s](https://www.youtube.com/watch?v=PH06mEOVVyY&t=187s)  
[https://www.youtube.com/watch?v=lFXJWPhDsSY](https://www.youtube.com/watch?v=lFXJWPhDsSY)

Un autre domaine où l'IA a énormément progressé ces dernières années, c'est celui de la gestion du texte.
Avec GPT 3, qui est un modèle capable de générer du texte, on obtient des résultats que je trouve très impressionnants.
Sous certaines conditions, il est possible de poser des questions à GPT 3, et de converser avec lui.

On pourra voir certains exemples ici :
[https://medium.com/@kirkouimet/turing-test-2669daffae38](https://medium.com/@kirkouimet/turing-test-2669daffae38)  
[https://lacker.io/ai/2020/07/06/giving-gpt-3-a-turing-test.html](https://lacker.io/ai/2020/07/06/giving-gpt-3-a-turing-test.html)  

Même si GPT 3 n'est clairement pas une intelligence de niveau humain, en lisant certains textes qu'il formule, on se rend compte qu'il dispose de certaines capacités de déduction et de logique.  

En conclusion: selon moi on peut déjà dire aujourd'hui que l'IA existe, lorsqu'on regarde les progrès réalisés en détection d'images, gestion du texte, et jeu, dont j'ai fourni quelques éléments dans cet article.    
En revanche, ce qui n'existe pas encore, c'est une IA de type AGI (Artificial General Intelligence) : une IA suffisamment généraliste pour maîtriser ces différentes disciplines en même temps.  






