# Khi2 - Exercice 3

L'objectif général va être de regarder si les intentions de vote sont indépendantes de la ville, c.a.d. si les variations d'effectifs dans les intentions de vote sont suffisamment petites pour s'expliquer par des fluctuations d'échantillonage.

La démarche consiste donc à supposer cette indépendance et à calculer les intentions de vote dans chaque ville, sous cette hypothèse. 

Attention, si les intentions de vote théoriques sont les mêmes dans les 3 villes si on exprime ces intentions en probabilité (ou proportion) de voter pour tel ou tel candidat, le *nombre* de personnes qu'on s'attend à indiquer une intention de vote pour tel ou tel candidat va dépendre du nombre de personnes interrogées dans la ville.

Avec l'hypothèse d'indépendance entre intention de vote et ville, on peut constater que dans le pays (supposé être constitué de l'union des 3 villes), il y a 125 intentions de vote pour A, 100 pour B, 85 pour C. Pour estimer les intentions de vote pour chaque candidat dans chaque ville, il faudra répartir ces 3 valeurs (125,100,85) sur les villes, pour chacune au prorata de la population interrogée des villes dans le pays. Le nombre d'intentions de vote pour un candidat dans une ville dépend ainsi d'une intention nationale de vote pour le candidat et de la population interrogée de la ville, mais pas d'une tendance particulière de cette ville favorable ou défavorable à ce candidat.

Pour mener ce calcul, on a besoin de calculer les populations interrogées totales des villes : Kagoul 80, Casinoville 130, Lesplaines 80. Il y a donc 310 personnes interrogées dans le pays.

Sous l'hypothèse d'indépendance discutée plus haut, à Kagoul on devrait s'attendre à 310.125/310.100/310 intentions de vote pour le candidat A soit 40,3 votes. On peut mener ainsi les 9 calculs et aboutir au tableau d'effectifs théoriques suivant :

|   | Kagoul |  Casinoville | Lesplaines  |  Total |
|---|---|---|---|---|
|  A | 40.3  | 52.4  | 32.3  | 125  |
|  B | 32.3  | 41.9  | 25.8  | 100  |
|  C | 27.4  | 35.7  | 21.9  | 85  |
|  Total | 100  | 130  | 80  | 310  |

On peut alors calculer une statistique de $\chi^2$  sur les 9 cases : $$\chi^2 = \sum_{villes} \sum_{candidats} \frac{\text{(effectif théorique - effectif observé)}^2}{\text{effectif théorique}^2}$$
 $$\chi^2 = 10,36$$

 Dans ce problème, il y a (nb lignes -1).(nb colonnes -1)=(3-1).(3-1)=4 degrés de liberté. En effet, les effectifs totaux par ville et par électeurs sont supposés fixes, vis à vis fluctuations d'échantillonage qui nous intéressent dans cet exercice.

 Cherchons dans la tableau du $\chi^2$ le seuil qui ne peut être dépassé qu'avec une probabilité de 5%, sous l'hypothèse d'indépendance. On trouve que ce seuil vaut 9,488. 

 La valeur de $\chi^2$ calculée pour la situation de l'exercice est proche du seuil à 5%. Il est donc difficile de conclure clairement sur l'indépendance.

 La décision de faire une campagne spécifique par ville peut alors dépendre des surcoûts de ces spécificités, qui ne sont pas discutés dans l'exercice.
