# Appliquer


<b>Conception</b>

Une bibliothèque veut gérer son stock de livre, leur classement en catégories (roman, essai, guide, etc) et leur emprunt par des usagers. On doit aussi pouvoir éditer une ficher personnalisée par auteur (avec par exemple les dates de naissance et de décès).

Proposez un schéma Entité Association pour représenter la situation. Ce schéma devra comporter un nom et quelques champs pour chaque entité, et chaque relation devra indiquer un verbe et une cardinalité. (PS: il y a au minimum trois entités).

Dans un second temps, transformez ce schéma en modèle relationnel pour remplacer les liens N-M par des tables de liaison et en indiquant bien dans les champs les clés primaires et les clés étrangères.


<b>Exploitation</b>

Implémenter la base dans phpmysql. et la remplir avec des exemples.

Donner les requêtes SQL pour extraire:

    la liste des livre dont le titre comprends “renard”
    SELECT Titre FROM `Livres` WHERE Titre LIKE '%renard%' ;
    
    la liste de livres de la catégorie roman
    SELECT Titre FROM `Livres` WHERE Ctagorie = 'Roman' ;
    
    la liste des livres en cours d’emprunt
    SELECT Titre FROM `Livres` INNER JOIN `Emprunt` ON Livres_id_Livre = id_Livre ;
    
    La liste des usagers en retard pour leur retour
    SELECT Nom, Prenom FROM `Usagers` INNER JOIN `Emprunt` ON Usagers_id_Usagers = id_Usagers 
    WHERE Date_retour IS NULL 
    AND (TIMESTAMP(Date_emprunt) +(21*60*60*24)) < CURRENT_TIMESTAMP() ;
    

