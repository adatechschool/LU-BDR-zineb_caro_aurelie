# Pratiquer

https://sql.sh/exercices-sql/villes-de-france

-> Configuration serveur et PHPMyAdmin


Veuillez trouver les requêtes SQL permettant d’effectuer chacune des demandes suivantes :

    Obtenir la liste des 10 villes les plus peuplées en 2012
    SELECT ville_nom, ville_population_2021 FROM `villes_france_free` ORDER BY ville_population_2012 DESC LIMIT 10;
    
    Obtenir la liste des 50 villes ayant la plus faible superficie
    SELECT ville_nom, ville_surface FROM `villes_france_free` ORDER BY ville_surface ASC LIMIT 50;
    
    Obtenir la liste des départements d’outres-mer, c’est-à-dire ceux dont le numéro de département commencent par “97”
    SELECT departement_nom, departement_code FROM `departement` WHERE departement_code LIKE '97%';
    
    Obtenir le nom des 10 villes les plus peuplées en 2012, ainsi que le nom du département associé
    SELECT ville_nom, departement_nom FROM `villes_france_free` INNER JOIN `departement` 
    ON ville_departement = departement_code
    ORDER BY ville_population_2012 DESC LIMIT 10;
    
    Compter le nombre de villes dont le nom commence par “Saint”
    SELECT COUNT (ville_nom) FROM `villes_france_free` WHERE ville_nom LIKE `Saint%`

    Remplacez les tirets par un espace vide, pour toutes les villes commençant par “SAINT-” 
    (dans la colonne qui contient les noms en majuscule)
    UPDATE `villes_france_free` SET ville_nom = REPLACE (ville_nom, '-', ' ')
    WHERE ville_nom LIKE 'SAINT-%' 
