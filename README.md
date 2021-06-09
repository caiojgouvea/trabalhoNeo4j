#Códigos usados para Criar as Entidades e Relaçoes

Faculdades->
  CREATE (n:Faculdade{nome: 'UNIGOIÁS', setor: 'CIDADE JARDIM'})
  CREATE (n:Faculdade{nome: 'FACULDADE OBJETIVO', setor: 'JARDIM PLANALTO'})
  CREATE (n:Faculdade{nome: 'FACULDADE DELTA', setor: 'JARDIM PLANALTO'})

Professores->
  CREATE (n:Professor{nome: 'Jorge Igor', materia: 'LOGICA DE PROGRAMAÇÃO'})
  CREATE (n:Professor{nome: 'RAFAEL CAMARGO', materia: 'SISTEMAS WEB'})
  CREATE (n:Professor{nome: 'PEDRO LUCAS', materia: 'SISTEMAS EMBARCADOS'})
  CREATE (n:Professor{nome: 'FLAVIA NUNES', materia: 'DIREITO CIVIL'})
  
  MATCH(a:Professor), (b:Faculdade) WHERE a.nome = 'JORGE IGOR' AND b.nome = 'FACULDADE DELTA' CREATE (a)-[r:PROFESSOR]->(b) RETURN type(r)
  MATCH(a:Professor), (b:Faculdade) WHERE a.nome = 'FLAVIA NUNES' AND b.nome = 'FACULDADE DELTA' CREATE (a)-[r:PROFESSOR]->(b) RETURN type(r)
  MATCH(a:Professor), (b:Faculdade) WHERE a.nome = 'RAFAEL CAMARGO' AND b.nome = 'FACULDADE DELTA' CREATE (a)-[r:PROFESSOR]->(b) RETURN type(r)
  MATCH(a:Professor), (b:Faculdade) WHERE a.nome = 'RAFAEL CAMARGO' AND b.nome = 'UNIGOIÁS' CREATE (a)-[r:PROFESSOR]->(b) RETURN type(r)
  MATCH(a:Professor), (b:Faculdade) WHERE a.nome = 'PEDRO LUCAS' AND b.nome = 'FACULDADE OBJETIVO' CREATE (a)-[r:PROFESSOR]->(b) RETURN type(r)
  
Alunos->
  CREATE (n:Aluno{nome: 'Thulio Maravilha', idade: 104})
  CREATE (n:Aluno{nome: 'Pedro Paulo', idade: 19})
  CREATE (n:Aluno{nome: 'Marcos Paulo', idade: 20})
  CREATE (n:Aluno{nome: 'Ana Maria', idade: 45})
  CREATE (n:Aluno{nome: 'Júlio Cesar', idade: 24})
  CREATE (n:Aluno{nome: 'Lucas Cabral', idade: 23})
  
  MATCH(a:Aluno), (b:Faculdade) WHERE a.nome = 'Lucas Cabral' AND b.nome = 'FACULDADE OBJETIVO' CREATE (a)-[r:ESTUDA]->(b) RETURN type(r)
  MATCH(a:Aluno), (b:Faculdade) WHERE a.nome = 'Pedro Paulo' AND b.nome = 'FACULDADE OBJETIVO' CREATE (a)-[r:ESTUDA]->(b) RETURN type(r)
  MATCH(a:Aluno), (b:Faculdade) WHERE a.nome = 'Ana Maria' AND b.nome = 'UNIGOIÁS' CREATE (a)-[r:ESTUDA]->(b) RETURN type(r)
  MATCH(a:Aluno), (b:Professor) WHERE a.nome = 'Ana Maria' AND b.nome = 'PEDRO LUCAS' CREATE (a)-[r:ALUNO]->(b) RETURN type(r)
  MATCH(a:Aluno), (b:Faculdade) WHERE a.nome = 'Júlio Cesar' AND b.nome = 'UNIGOIÁS' CREATE (a)-[r:ESTUDA]->(b) RETURN type(r)
  MATCH(a:Aluno), (b:Faculdade) WHERE a.nome = 'Thulio Maravilha' AND b.nome = 'UNIGOIÁS' CREATE (a)-[r:ESTUDA]->(b) RETURN type(r)
  MATCH(a:Aluno), (b:Faculdade) WHERE a.nome = 'Marcos Paulo' AND b.nome = 'FACULDADE DELTA' CREATE (a)-[r:ESTUDA]->(b) RETURN type(r)
  MATCH(a:Aluno), (b:Professor) WHERE a.nome = 'Marcos Paulo' AND b.nome = 'JORGE IGOR' CREATE (a)-[r:ALUNO]->(b) RETURN type(r)
  
  ![capturaNeo4j](https://user-images.githubusercontent.com/44786045/121442330-d22b5d00-c961-11eb-8cf1-c520dbbbc614.PNG)

  
