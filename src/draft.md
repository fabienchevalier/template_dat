##### Groupe de management Azure

| Nom            | ID                | Description                                                           |
| -------------- | ----------------- | --------------------------------------------------------------------- |
| Maléo          | mg-maleo          | Groupe de management principal                                        |
| Sandbox        | mg-sandbox        | Groupe de management de l’env. sandbox                                |
| Projects       | mg-projects       | Groupe de management des env. d’infrastructures                       |
| maleo_website  | mg-maleo_website  | Groupe de management englobant le site web de Maléo                   |
| maleo_intranet | mg-maleo_intranet | Groupe de management englobant l’intranet de Maléo                    |
| Connectivity   | mg-connectivity   | Groupe de management contenant les ressources liées à la connectivité |
| Plateform      | mg-plateform      | Groupe de management contenant les ressources de gestion de l’infra.  |
| Gouvernance    | mg-governance     | Groupe de management content les ressources liées à la gouvernance.   |

##### Abonnements Azure (subscription)

| Nom                 | ID                       | Description                                   |
| ------------------- | ------------------------ | --------------------------------------------- |
| maleo-gouvernance   | xxxx-xxxx-xxxx-xxxx-xxxx | Gestion et facturation gouvernance            |
| maleo-connectivity  | xxxx-xxxx-xxxx-xxxx-xxxx | Gestion et facturation connectivité           |
| maleo-website-prod  | xxxx-xxxx-xxxx-xxxx-xxxx | Environnement de production du projet website |
| maleo-website-pprd  | xxxx-xxxx-xxxx-xxxx-xxxx | Environnement de preprod du projet website    |
| maleo-website-dev   | xxxx-xxxx-xxxx-xxxx-xxxx | Environnement de de dev du projet website     |
| maleo-intranet-prod | xxxx-xxxx-xxxx-xxxx-xxxx | Environnement de prod du projet intranet      |
| maleo-intranet-pprd | xxxx-xxxx-xxxx-xxxx-xxxx | Environnement de preprod du projet intranet   |
| maleo-sandbox       | xxxx-xxxx-xxxx-xxxx-xxxx | Environnement sandbox                         |

#### Bases de données

| Nom             | Type                      | Calcul                            | Stockage | Niveau          |
| --------------- | ------------------------- | --------------------------------- | -------- | --------------- |
| maleo-glpi-prod | Azure Databse for MariaDB | General Purpose (2Vcore, 5GB Ram) | 128GB    | General Purpose |
