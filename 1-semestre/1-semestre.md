<h1 align="center">API 1º SEMESTRE - 2020-1</h1>

<p align="center"> <img src="imagens/logo.png" alt="AgendHouse" class="center" width=150/> </p>

<h2 align="center">
NUNA, sua assistente de voz para viagens
</h2>

<h4 align="center">
Link para o repositório do projeto
</h4>

[Link para o projeto](https://github.com/TairikJohnny/API-1-SEMESTRE)

<h3 align="center">
Resumo
</h3>

O projeto foi proposto pelos professores do 1º semestre da Faculdade de Tecnologia de São José dos Campos Professor Jessen Vidal, o desafio foi criar uma assistente de voz que vai auxiliar o usuário a organizar e planejar a sua viagem e estadia consumindo APIs públicas. Este projeto beneficiou o meu aprendizado e minha autonomia como aluno, pois, pude estudar diversas tecnologias que nunca havia trabalhado e como consequência também tive dificuldades em estudar essas tecnologias e aplicá-las de forma eficiente trazendo o melhor resultado para o projeto. 

<h3 align="center">Tecnologias adotadas na solução</h3>

<div align="center">

<a href="https://developer.mozilla.org/en-US/docs/Glossary/HTML5">
  <img src="https://img.shields.io/static/v1?label=HTML5&message=Front-End&color=E34F26&style=for-the-badge&logo=HTML5"/>
</a>
<a href="https://developer.mozilla.org/en-US/docs/Web/CSS">
<img src="https://img.shields.io/static/v1?label=CSS3&message=Front-End&color=1572B6&style=for-the-badge&logo=CSS3"/>
</a>
<a href="https://www.javascript.com/">
  <img src="https://img.shields.io/static/v1?label=JavaScript&message=Back-End&color=F7DF1E&style=for-the-badge&logo=JavaScript"/>
</a>
<a href="https://git-scm.com/">
  <img src="https://img.shields.io/static/v1?label=Git&message=Devops&color=F05032&style=for-the-badge&logo=Git"/>
</a>
<a href="https://github.com">
  <img src="https://img.shields.io/static/v1?label=GitHub&message=Devops&color=181717&style=for-the-badge&logo=GitHub"/>
</a>

</div>

<h3 align="center">Contribuições individuais/pessoais</h3>

Fiquei responsável pelo desenvolvimento da tela de clima, a mesma descobre a localização do usuário e retorna o clima atualizado consumindo uma API pública do site [Weather API](https://openweathermap.org/api). Segue abaixo alguns métodos desenvolvidos por mim.

<details>
<summary><b>Função para descobrir a localização do usuário</b></summary>

```bash
// Função para descobrir a localização do usuário
function getUserPosition() {
  let url;
  navigator.geolocation.getCurrentPosition((pos) => {
    // Latitude informada pelo navegador sendo armazenada em uma variavel
    let lat = pos.coords.latitude;
    // Longitude informada pelo navegador sendo armazenada em uma variavel
    let long = pos.coords.longitude;
    // Inserindo a URL do site e adicionando a chave da API gerada no site
    url = `https://api.openweathermap.org/data/2.5/weather?lat=${lat}&lon=${long}&units=imperial&APPID=0ed1849b155148f92803761f3cb5b7ce`;
    // Chamando o método fetchApi e passando a URL
    fetchApi(url);
  });
}
```

</details>

<details>
<summary><b>Função para consumir a API</b></summary>

```bash
// Salvando os retornos da API
function fetchApi(url) {
  // Salvando a localização do usuario informado pela API (cidade)
  let city = document.querySelector('.city');
  // Salvando a temperarura da cidade informada pela API 
  let temp = document.querySelector('span');
  // A função solicita os dados para a URL inserida a cima (requisição HTTP)
  fetch(url)
    .then((data) => {
      // Retorno dos dados convertidos em JSON
      return data.json();
    })
    .then((data) => {
      // Convertendo a temperatura fornecida pela API para Celsius
      let tempInCelsius = ((5 / 9) * (data.main.temp - 32)).toFixed(1);
      // Retornando para o HTML a cidade e a temperatura convertida
      city.innerText = `Hoje a temperatura em ${data.name} é:`;
      temp.innerText = tempInCelsius;
    })
    // Tratamento de erros
    .catch((err) => {
      city.innerText = `Impossível executar a função. Verifique a sua conexão.`;
      temp.innerText = `-`;
    })
}
```

</details>

<h4 align="center">Hard Skills Efetivamente Desenvolvidas</h4>

- [x] <b>GIT</b>
    - Foi o meu primeiro contato com versionamento e GIT, aprendi a importância da ferramenta no dia-a-dia de um desenvolvedor e aprendi a utilizar e implemetar em projetos.
    - Sei fazer com ajuda.

- [x] <b>GitHub</b>
    - Foi o meu primeiro contato com o GitHub, aprendi a importância da ferramenta no gerenciamento de projetos e aprendi a utilizar e implemetar em projetos.
    - Sei fazer com ajuda.

- [x] <b>SCRUM</b>
    - Foi o meu primeiro contato com o SCRUM, aprendi a importância da metodologia no gerenciamento de projetos e aprendi os rituais do SCRUM.
    - Sei fazer com ajuda.

- [x] <b>JavaScript</b>
    - Foi o meu primeiro contato com o JavaScript, aprendi a consumir APIs públicas e mostrar as informações para o usuário.
    - Sei fazer com ajuda.

- [x] <b>APIs</b>
    - Foi o meu primeiro contato com APIs, aprendi a consumir APIs públicas e aprendi a importância de uma API no mundo do desenvolvimento.
    - Sei fazer com ajuda.

- [x] <b>HTML e CSS</b>
    - Apronfundei os meus conhecimentos em HTML e CSS, aprendi a mostrar para o usuário o retorno de uma API.
    - Sei fazer com ajuda.

<h4 align="center">Soft Skills Efetivamente Desenvolvidas</h4>

- [x] <b>Trabalho em equipe</b>
    - O trabalho em equipe é sem dúvidas um dos pontos mais importantes no desenvolvimento do projeto como um todo.
    - Sei fazer com autonomia.

- [x] <b>Gerenciamento</b>
    - Devido a metodologia SCRUM o gerenciamento de tempo e das tarefas é fundamental para o bom desenvolvimento do projeto.
    - Sei fazer com autonomia.

- [x] <b>Organização</b>
    - A organização é essencial para um bom fluxo de trabalho no projeto.
    - Sei fazer com autonomia.

- [x] <b>Responsabilidade</b>
    - A responsabilidade é essencial dentro do SCRUM para a realização das tasks de maneira correta e no tempo certo.
    - Sei fazer com autonomia.

- [x] <b>Confiança</b>
    - A confiança em si mesmo e no grupo é fundamental, é necessario confiar no grupo para a boa realização do projeto.
    - Sei fazer com autonomia.