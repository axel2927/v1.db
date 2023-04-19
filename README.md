# v1.db
Devoir info 1ère partie | 19.04.23
Table etudiants {
  matricule integer [primary key]
  nom varchar
  prenom varchar
  email varchar
  natel varchar
}

Table cours {
  nom varchar
  id_cours integer [primary key]
}

Table professeurs {
  nom varchar [primary key]
  prenom varchar
  email varchar
  bureau varchar
}

Table inscriptions {
  student_id integer
  cours_id integer
}

Ref: inscriptions.student_id > etudiants.matricule
Ref: inscriptions.cours_id > cours.id_cours
Ref: cours.id_cours > professeurs.nom
