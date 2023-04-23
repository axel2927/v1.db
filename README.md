# v1.db
Devoir info 3ème partie | 23.04.23

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

Table evaluations {
  note integer
  coefficient integer
  rendu_le timestamp
}

Table assistants {
  matricule integer [primary key]
  nom varchar
  prenom varchar
  email varchar
  bureau varchar
}

Table selection_assistants {
  id_etudiant integer
  id_cours integer
}


Ref: inscriptions.student_id > etudiants.matricule
Ref: inscriptions.cours_id > cours.id_cours
Ref: cours.id_cours > professeurs.nom
Ref: evaluations.note > inscriptions.cours_id
Ref: evaluations.note > inscriptions.student_id
Ref: selection_assistants.id_cours > cours.id_cours
Ref: selection_assistants.id_etudiant > assistants.matricule
Ref: selection_assistants.id_etudiant > etudiants.matricule

