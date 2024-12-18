

On lance une vérification pour s'assurer que ça peut potentiellement fonctionner :

```
ansible-playbook -i inventory.yml deploy_pma.yml--check
```

```
ansible-playbook -i inventory.yml deploy_pma.yml --limit "192.168.122.84"
```

Si le test passe, alors tu peux jouer réellement le playbook :

```
ansible-playbook -i inventory.yml deploy_pma.yml
```

To connect to the database. Or others credentials. Modify them
```
mariadb -h 127.0.0.1 -u  user1 rhrejgrjger db1  
```

Et normalement, en te connectant sur la machine ciblée de ton inventaire, tu devrais avoir un serveur http sous Nginx installé et démarré.

Dans le cas où tu te retrouves avec des erreurs, il est nécessaire de bien lire le retour d'erreur fourni par Ansible dans lequel se trouve très probablement l'explication concrète du problème.




Voici la signification de chaque répertoire :

    defaults/ : Contient les valeurs par défaut des variables
    tasks/ : Contient les tâches à exécuter
    files/ : Répertoire pour les fichiers à copier tels quels
    handlers/ : Contient les gestionnaires (handlers) associés aux événements déclenchés par les tâches
    meta/ : Spécifie les dépendances du rôle
    templates/ : Répertoire pour les fichiers de modèles Jinja2
    tests/ : permet aux d'écrire des tests automatisés pour s'assurer que le rôle fonctionne correctement dans différents scénarios
    vars/ : Contient les variables spécifiques au rôle
