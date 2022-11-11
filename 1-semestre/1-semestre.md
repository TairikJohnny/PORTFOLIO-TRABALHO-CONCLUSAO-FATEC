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

O projeto foi proposto pelos professores do 1º semestre da Faculdade de Tecnologia de São José dos Campos Professor Jessen Vidal, o desafio foi criar uma assitente de voz que vai auxiliar o usuário a organizar e planejar a sua viagem e estadia consumindo APIs públicas.

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

- [x] Comecei a aprender versionamento de código via GIT.
- [x] Comecei a aprender a gerenciar projetos no GitHub.
- [x] Comecei a aprender metodologias ágeis com Scrum.
- [x] Comecei a aprender JavaScript.
- [x] Comecei a aprender a consumir APIs.
- [x] Aprofundei os meus conhecimentos em HTML e CSS.

<h4 align="center">Soft Skills Efetivamente Desenvolvidas</h4>

- [x] Trabalho em equipe
- [x] Responsabilidade
- [x] Organização
- [x] Gestão do tempo
- [x] Confiança