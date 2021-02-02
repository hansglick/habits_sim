# Description

L'objectif de ce repository est l'implémentation d'un simulateur d'habitudes en vue d'éprouver un détecteur d'habitudes.

# Modèlisation

Une habitude est définie de la manière suivante : 
 1. une tranche horaire (heures consécutives, par exemple [7,8,9])
 2. une combinaison de jours de la semaine (par exemple [Lundi,Jeudi])
 3. Une distribution de probabilité sur la tranche horaire (par exemple [0.2,0.1,0.2])


# Paramètres du générateur

 * *Couverture* : Entre 0 et 1. Indique le seuil au dessous duquel, on continue de générer des habitudes
 * *Date_Debut* : date représentant le 1er jour de la simulation
 * *Date_Fin* : date représentant le dernier jour de la simulation
 * *Loi de distribution de la taille de la tranche horaire*
 * *Loi de distribution du nombre de jours de la semaine*

# Processus
 * **Génération d'une habitude** 
   * Tirage du nombre d'heures
   * Tirage du nombre de jours
   * Tirage pmin, pmax, ploc, pdouble
   * Fonction interpolation
   * Mapping des points interpolés
   * => Génération de la distribution horaire
 * **Remplissage du calendrier**
 * **Simulation des événements**


# Génération d'une distribution horaire (input : taille de l'intervalle horaire)

 1. Tirer pmin, pmax, ploc, pdouble, 4 valeurs tirées d'une loi uniforme [0,1]
 2. Interpolation entre 3 points, point gauche, milieu, droit
 3. Mapping des points interpolés vers les tranches horaires
