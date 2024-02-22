## Dans un contrôleur

- Dans un controller, on peut simplement injecter le dbContext comme attribut de classe, car il le contrôleur est scoped.
  Cela veut dire que le lifetime du contexte ne dure pas plus longtemps que le traitement de la requête http.

- Il est aussi possible d'aller modifier la class de base "ControllerBase" pour qu'un certain dbContext soit injecté dans tous les contrôleur.
