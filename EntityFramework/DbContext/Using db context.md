Dans un controller, on peut simplement injecter le dbContext comme attribut de classe, car il le contrôleur est scoped.
Cela veut dire que le lifetime du contexte ne dure pas plus longtemps que le traitement de la requête http.
