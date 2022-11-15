<h1 align="center">API 3º SEMESTRE - 2021-1</h1>

<p align="center"> <img src="imagens/logo-mom.png" alt="MOM" class="center" width=200/> </p>

<h2 align="center">
MOM - Management of Operational Manuals
</h2>

<h4 align="center">
Link para o repositório do projeto
</h4>

[Link para o projeto](https://github.com/TairikJohnny/API-3-SEMESTRE)

<h3 align="center">
Resumo
</h3>

Projeto proposto pelo Time de Publicação Operacional da [Embraer](https://embraer.com/br/pt), responsáveis por emitir, aprovar e revisar os manuais operacionais de aviação, destinados a pilotos, tripulação, despatcher de aeronaves e provedores de treinamento juntamente com a Faculdade de Tecnologia de São José dos Campos Professor Jessen Vidal. O objetivo foi desenvolver um sistema que permita customizar, controlar e revisar documentos formados por fragmentos armazenados em arquivos PDF, usando regras de negócio específicas para gerar o documento final.

<h3 align="center">Tecnologias adotadas na solução</h3>

<div align="center">

<a href="https://vuejs.org/">
  <img src="https://img.shields.io/static/v1?label=Vue.js&message=Front-End&color=4FC08D&style=for-the-badge&logo=Vue.js"/>
</a>
<a href="https://www.javascript.com/">
  <img src="https://img.shields.io/static/v1?label=JavaScript&message=Front-End&color=F7DF1E&style=for-the-badge&logo=JavaScript"/>
</a>
<a href="https://www.npmjs.com/">
  <img src="https://img.shields.io/static/v1?label=NPM&message=Front-end&color=CB3837&style=for-the-badge&logo=NPM"/>
</a>
<a href="https://www.java.com/pt-BR/">
  <img src="https://img.shields.io/static/v1?label=Java&message=Back-End&color=007396&style=for-the-badge&logo=java"/>
</a>
<a href="https://spring.io/projects/spring-boot">
  <img src="https://img.shields.io/static/v1?label=Spring Boot&message=Back-end&color=6DB33F&style=for-the-badge&logo=Spring"/>
</a>
<a href="https://maven.apache.org/">
  <img src="https://img.shields.io/static/v1?label=Apache Maven&message=Back-end&color=C71A36&style=for-the-badge&logo=Apache Maven"/>
</a>
<a href="https://www.oracle.com/br/">
  <img src="https://img.shields.io/static/v1?label=Oracle&message=Banco de Dados&color=F80000&style=for-the-badge&logo=Oracle"/>
</a>
<a href="https://git-scm.com/">
  <img src="https://img.shields.io/static/v1?label=Git&message=Devops&color=F05032&style=for-the-badge&logo=Git"/>
</a>
<a href="https://github.com">
  <img src="https://img.shields.io/static/v1?label=GitHub&message=Devops&color=181717&style=for-the-badge&logo=GitHub"/>
</a>

</div>

<h3 align="center">Contribuições individuais/pessoais</h3>

Fiquei responsável por desenvolver o Front-end da aplicação, devido o grau de complexidade propus de utilizarmos o framework JavaScript Vue.js para desenvolver o front-end e virei Scrum Master no decorrer do projeto. Abaixo segue alguns métodos desenvolvidos por mim. 

<details>
<summary><b>Método para buscar um documento no BD</b></summary>

```bash
getDocument() {
  http.get(DocumentsEndpoints.FIND_ALL_BY, {
      params: {
          document_name: this.name,
          part_number: this.partNumber
      }
  })
      .then(response => {
          this.document = response.data;
          let documentId = response.data.id;
          this.allReviews = this.document.revisions;
          this.getOpenedReview(documentId);
          console.log(this.openedReview);
          console.log(this.allReviews);
      }).catch(error => {
      console.log(error);
      //alert('Não foi possível obter o documento')
      swal("Erro!", "Não foi possível obter o documento", "error");
  });
},
```

</details>

<details>
<summary><b>Método para fechar a revisão do documento</b></summary>

```bash
closeReview() {
  http.put(`/revision/close?document_id=${this.document.id}`)
      .then(response => {
          this.closedReview = response.data;
          //alert('Revisão fechada com sucesso!!')
          swal("Sucesso!", "Revisão fechada com sucesso!", "success");
      })
      .catch(error => {
          console.error(error);
          //alert('Não foi possível fechar a revisão')
          swal("Erro!", "Não foi possível fechar a revisão", "error");
      })
},
```

</details>

<h4 align="center">Hard Skills Efetivamente Desenvolvidas</h4>

- [x] <b>GIT e GitHub</b>
    - Aprofundei os meus conhecimentos em versionamento de código via GIT e gerenciamento de projetos no GitHub.
    - Sei fazer com autonomia.
  
- [x] <b>SCRUM</b>
    - Me tornei Scrum Master no decorrer do projeto então aprofundei os meus conhecimento na metodologia e nos seus rituais.
    - Sei fazer com autonomia.

- [x] <b>Vue.js</b>
    - Aprofundei os meus conhecimentos em Vue.js, foi o meu primeiro projeto real utilizando o framework JavaScript.
    - Estava utilizando o Vue.js no estágio e resolvi propor de utilizarmos no projeto devido o sua facilidade de aprendizagem.
    - Aprendi a consumir APIs utilizando JavaScript e Axios.
    - Sei fazer com ajuda.

<h4 align="center">Soft Skills Efetivamente Desenvolvidas</h4>

- [x] <b>Superação</b>
    - Tivemos que superar diversos obstáculos no decorrer do projeto com a saída de alguns membros do grupo.
    - Sei fazer com autonomia.

- [x] <b>Responsabilidade</b>
    - Precise assumir a responsabilidade do cargo de Scrum Master devido a saída do mesmo.
    - Sei fazer com autonomia.

- [x] <b>Trabalho em Equipe</b>
    - O trabalho em equipe mais do que nunca foi fundamental para superarmos as adversidades e conseguimos dar continuidade no projeto mesmo com a saída de alguns integrantes.
    - Sei fazer com autonomia.

- [x] <b>Comunicação</b>
    - A comunicação entre os membros da equipe foi essencial para o bom andamento do projeto
    - Sei fazer com autonomia.