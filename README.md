<div align="center">
  <h2> Olá, eu sou o Tairik Johnny 👋</h2>
</div>

Atualmente tenho 22 anos e sou Desenvolvedor Full Stack Junior na empresa [Grupo Parque das Flores](https://parquedasflores.com.br/), estou regularmente matriculado no 6° semestre do curso de Banco de Dados pela [FATEC Prof. Jessen Vidal - Faculdade de Tecnologia de São José dos Campos](https://fatecsjc-prd.azurewebsites.net/), tenho formação de Técnico em Informática pela [Etec Prof.ª Ilza Nascimento Pintus](https://www.cps.sp.gov.br/etecs/etec-profa-ilza-nascimento-pintus/) e formação de Técnico em Informática para Internet pelo [Senac EAD](https://www.ead.senac.br/).

<div align="center">
  <a href = "https://api.whatsapp.com/send?phone=5512992333241"><img src="https://img.shields.io/badge/WhatsApp-25D366?style=for-the-badge&logo=whatsapp&logoColor=white" target="_blank"></a>
  <a href="https://www.linkedin.com/in/tairik-nishimura/" target="_blank"><img src="https://img.shields.io/badge/-LinkedIn-%230077B5?style=for-the-badge&logo=linkedin&logoColor=white" target="_blank"></a> 
  <a href = "mailto:tairikjohnny@gmail.com"><img src="https://img.shields.io/badge/-Gmail-%23333?style=for-the-badge&logo=gmail&logoColor=white" target="_blank"></a>
  <a href="https://www.instagram.com/tairikjohnny/" target="_blank"><img src="https://img.shields.io/badge/-Instagram-%23E4405F?style=for-the-badge&logo=instagram&logoColor=white" target="_blank"></a>
</div>

<br>

<div align="center">
  <a href="https://github.com/TairikJohnny">
  <img height="180em" src="https://github-readme-stats.vercel.app/api?username=TairikJohnny&show_icons=true&theme=dracula&include_all_commits=true&count_private=true"/>
  <img height="180em" src="https://github-readme-stats.vercel.app/api/top-langs/?username=TairikJohnny&layout=compact&langs_count=7&theme=dracula"/>
</div>

<br>

<div align="center">
  <img src="https://img.shields.io/badge/Vue.js-35495E?style=for-the-badge&logo=vue.js&logoColor=4FC08D"/>
  <img src="https://img.shields.io/badge/java-ED8B00?style=for-the-badge&logo=java&logoColor=white"/>
  <img src="https://img.shields.io/badge/Spring-6DB33F?style=for-the-badge&logo=spring&logoColor=white"/>
  <img src="https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white"/>
  <img src="https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black"/>
  <img src="https://img.shields.io/badge/MySQL-00000F?style=for-the-badge&logo=mysql&logoColor=white"/>
</div>

<br>
<br>
<br>

<h1 align="center">API 1º SEMESTRE - 2020-1</h1>

<p align="center"> <img src="imagens-1-semestre/logo.png" alt="AgendHouse" class="center" width=150/> </p>

<h2 align="center">
NUNA, sua assistente de voz para viagens
</h2>

<h4 align="center">Resumo 📋</h4>

Uma assistente guiada por comando de voz para auxiliá-lo em sua viagem e estadia.

<h4 align="center">Projeto 🖥</h4>

Projeto proposto pelos professores do 1º semestre da Faculdade de Tecnologia de São José dos Campos Professor Jessen Vidal.

<h4 align="center">Desafio 📈</h4>

O desafio foi criar uma assitente de voz que vai auxiliar o usuário a organizar e planejar a sua viagem e estadia consumindo APIs públicas.

<h3 align="center">Tecnologias adotadas na solução</h3>

<div align="center">

<a href="https://developer.mozilla.org/pt-BR/docs/Web/HTML/Element">
  <img src="https://img.shields.io/static/v1?label=HTML5&message=Front-End&color=E34F26&style=for-the-badge&logo=HTML5"/>
</a>
<a href="https://nodejs.org/en/">
<img src="https://img.shields.io/static/v1?label=CSS3&message=Front-End&color=1572B6&style=for-the-badge&logo=CSS3"/>
</a>
<a href="https://www.javascript.com/">
  <img src="https://img.shields.io/static/v1?label=JavaScript&message=Back-End&color=F7DF1E&style=for-the-badge&logo=JavaScript"/>
</a>

</div>

<h3 align="center">Contribuições individuais/pessoais</h3>

- [x] Trabalhei na tela de clima, ela descobre a localização do usuário e retorna o clima atualizado consumindo uma API pública do site [Weather API](https://openweathermap.org/api).

<p align="center"> Função para descobrir a localização do usuário </p>

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

<p align="center"> Função para consumir a API </p>

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

<h4 align="center">Hard Skills Efetivamente Desenvolvidas</h4>

- [x] Comecei a aprender versionamento de código via GIT.
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

<h1 align="center">API 2º SEMESTRE - 2020-2</h1>

<p align="center"> <img src="imagens-2-semestre/icone_pi.png" alt="AgendHouse" class="center" width=200/> </p>

<h4 align="center">Resumo 📋</h4>

Software desktop para cadastro manual de contas de água e luz que por algum motivo não conseguiram ser automatizadas.

<h4 align="center">Projeto 🖥</h4>

Projeto realizado em parceria com a [Tecsus](https://tecsus.com.br/) uma startup que desenvolve dispositivos, aplicativos e sistemas para a transmissão e recepção de dados, controle de equipamentos remotos e gestão de faturas juntamente com a Faculdade de Tecnologia de São José dos Campos Professor Jessen Vidal.

<h4 align="center">Desafio 📈</h4>

A Tecsus realiza a gestão de contas de utilidades (água e energia) dos seus clientes. Todos os meses milhares de contas devem ser digitadas manualmente no sistema para a realização de análises de contratos e análises de consumo. Desta forma, para facilitar a digitação das contas precisamos de um sistema que permita o cadastro de cada conta de forma rápida e ágil, sem a necessidade de utilização do mouse, apenas por comandos do teclado.

<h3 align="center">Tecnologias adotadas na solução</h3>

<div align="center">

<a href="https://developer.mozilla.org/pt-BR/docs/Web/HTML/Element">
  <img src="https://img.shields.io/static/v1?label=Java&message=Back-End&color=007396&style=for-the-badge&logo=java"/>
</a>
<a href="https://developer.mozilla.org/pt-BR/docs/Web/HTML/Element">
  <img src="https://img.shields.io/static/v1?label=MySQL&message=Banco de Dados&color=4479A1&style=for-the-badge&logo=MySQL"/>
</a>

</div>

<h3 align="center">Contribuições individuais/pessoais</h3>

- [x] Trabalhei na parte de conexão do banco via JDBC e com os CRUDs do sistema.

<p align="center"> Classe para criar o BD </p>

```bash
public class CriarBanco {
	public static void main(String[] args) throws SQLException {
		// TODO Auto-generated method stub

		final String url = "jdbc:mysql://localhost:3306?verifyServerCertificate=false&useSSL=true";
		final String usuario = "root";
		final String senha = "123456789";

		// CRIANDO CONEXAO
		Connection conexao = DriverManager.getConnection(url, usuario, senha);

		Statement stmt = conexao.createStatement();

		// CRIANDO BANCO DE DADOS SE ELE NÃO EXISTIR
		stmt.execute("CREATE DATABASE IF NOT EXISTS projeto_integrador");

		// DELETANDO O BANCO CASO ELE EXISTA
		//stmt.execute("DROP DATABASE IF EXISTS curso_java");

		System.out.println("Banco criado com sucesso!!!");

		conexao.close();
	}
}
```

<p align="center"> Método de update </p>

```bash
public void update() throws SQLException {

  Connection conexao = FabricaConexao.getConexao();

  // Atribuindo oque foi digitado no textField a variavel x
  String x = instalacaoField.getText();

  // String SQL
  String updateSQL = "UPDATE conta_luz SET nomeCliente = ?, vencimento = ?, contaMes = ?, consumo = ?, tarifa = ?, "
      + "pis = ?, confins = ?, icms = ?, totalPagar = ? WHERE instalacao='"+ x + "'";

  // Recebendo o updateSQL
  PreparedStatement stmt = conexao.prepareStatement(updateSQL);		

  // Setando no banco
  stmt.setString(1, nomeClienteField.getText());
  stmt.setString(2, vencimentoField.getText());
  stmt.setString(3, contaMesField.getText());
  stmt.setString(4, consumoField.getText());
  stmt.setString(5, tarifaField.getText());
  stmt.setString(6, pisField.getText());
  stmt.setString(7, cofinsField.getText());
  stmt.setString(8, icmsField.getText());
  stmt.setString(9, totalPagarField.getText());

  stmt.executeUpdate();

  System.out.println("Dados atualizados com sucesso");

  // Fechando conexoes
  stmt.close();
  conexao.close();
  }
```

<h4 align="center">Hard Skills Efetivamente Desenvolvidas</h4>

- [x] Aprofundei os meus conhecimentos com versionamento de código via GIT.
- [x] Aprofundei os meus conhecimentos com metodologias ágeis com Scrum.
- [x] Aprofundei os meus conhecimentos com Java.
- [x] Aprendi a conectar o Java com um banco de dados MySql via JDBC.
- [x] Aprendi a criar interface gráfica com o Java Swing.

<h4 align="center">Soft Skills Efetivamente Desenvolvidas</h4>

- [x] Trabalho em equipe
- [x] Responsabilidade
- [x] Organização
- [x] Gestão do tempo
- [x] Confiança

<h1 align="center">API 3º SEMESTRE - 2021-1</h1>

<p align="center"> <img src="imagens-3-semestre/logo-mom.png" alt="MOM" class="center" width=200/> </p>

<h2 align="center">
MOM - Management of Operational Manuals
</h2>

<h4 align="center">Resumo 📋</h4>

Software para gerenciamento e customização de manuais operacionais da aviação.

<h4 align="center">Projeto 🖥</h4>

Projeto proposto pelo Time de Publicação Operacional da [Embraer](https://embraer.com/br/pt), responsáveis por emitir, aprovar e revisar os manuais operacionais de aviação, destinados a pilotos, tripulação, despatcher de aeronaves e provedores de treinamento juntamente com a Faculdade de Tecnologia de São José dos Campos Professor Jessen Vidal.

<h4 align="center">Desafio 📈</h4>

Desenvolver um sistema que permita customizar, controlar e revisar documentos formados por fragmentos armazenados em arquivos PDF, usando regras específicas para gerar o documento final.

<h3 align="center">Tecnologias adotadas na solução</h3>

<div align="center">

<a href="https://developer.mozilla.org/pt-BR/docs/Web/HTML/Element">
  <img src="https://img.shields.io/static/v1?label=Vue.js&message=Front-End&color=4FC08D&style=for-the-badge&logo=Vue.js"/>
</a>
<a href="https://developer.mozilla.org/pt-BR/docs/Web/HTML/Element">
  <img src="https://img.shields.io/static/v1?label=JavaScript&message=Front-End&color=F7DF1E&style=for-the-badge&logo=JavaScript"/>
</a>
<a href="https://developer.mozilla.org/pt-BR/docs/Web/HTML/Element">
  <img src="https://img.shields.io/static/v1?label=Java&message=Back-End&color=007396&style=for-the-badge&logo=java"/>
</a>
<a href="https://developer.mozilla.org/pt-BR/docs/Web/HTML/Element">
  <img src="https://img.shields.io/static/v1?label=Spring&message=Back-End&color=6DB33F&style=for-the-badge&logo=Spring"/>
</a>
<a href="https://developer.mozilla.org/pt-BR/docs/Web/HTML/Element">
  <img src="https://img.shields.io/static/v1?label=Oracle&message=Banco de Dados&color=F80000&style=for-the-badge&logo=Oracle"/>
</a>

</div>

<h3 align="center">Contribuições individuais/pessoais</h3>

- [x] Trabalhei principalmente no Front-end.
- [x] Ajudei a desenvolver as telas e no consumo dos endpoints.
- [x] Virei Scrum Master no decorrer do projeto.
- [x] Propus o uso do framework JavaScript Vue.js para o front-end.

<p align="center"> Método para buscar um documento no BD </p>

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

<p align="center"> Método para fechar a revisão do documento </p>

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

<h4 align="center">Hard Skills Efetivamente Desenvolvidas</h4>

- [x] Aprofundei os meus conhecimentos com versionamento de código via GIT.
- [x] Aprofundei os meus conhecimentos com metodologias ágeis com Scrum.
- [x] Aprofundei os meus conhecimentos no framework Vue.js.
- [x] Aprofundei os meus conhecimentos em JavaScript.
- [x] Aprendi a consumir endpoints via Axios.

<h4 align="center">Soft Skills Efetivamente Desenvolvidas</h4>

- [x] Trabalho em equipe
- [x] Responsabilidade
- [x] Organização
- [x] Gestão do tempo
- [x] Confiança

<h1 align="center">API 4º SEMESTRE - 2021-2</h1>

<p align="center"> <img src="imagens-4-semestre/logo_agendhouse.png" alt="AgendHouse" class="center" width=600/> </p>

<h2 align="center">
AgendHouse
</h2>

<h4 align="center">Resumo 📋</h4>

O projeto a ser desenvolvido vai ser um sistema para agendamentos de eventos na [Casa Oracle](https://blogs.oracle.com/oracle-brasil/casa-oracle-abre-as-portas-para-a-inovacao-em-sao-paulo) buscando solucionar os obstáculos da pandemia do [Covid-19](https://covid.saude.gov.br/).

<h4 align="center">Projeto 🖥</h4>

Projeto realizado em parceria com a Oracle Corporation uma empresa que atua na área da Computação e Informática juntamente com a Faculdade de Tecnologia de São José dos Campos Professor Jessen Vidal.

<h4 align="center">Desafio 📈</h4>

Desafio proposto pela Oracle Corporation - "No escritório de São Paulo, temos um espaço de inovação aberta chamado Casa Oracle, que é um local para realização de eventos internos/externos, workshops e palestras. Dentro do contexto das restrições sanitárias, nosso desafio é criar uma plataforma para o gerenciamento da utilização do espaço, onde nossos colaboradores poderão fazer a solicitação de agendamento, definindo os convidados e recursos necessários para o evento."

<h3 align="center">Tecnologias adotadas na solução</h3>

<div align="center">

<a href="https://vuejs.org/">
  <img alt="image" src="https://img.shields.io/badge/Vue.js-%23696969?style=for-the-badge&logo=vue.js">
</a>
<a href="https://www.java.com/pt-BR/">
  <img alt="image" src="https://img.shields.io/badge/Java_11-%23696969?style=for-the-badge&logo=Java">
</a>
<a href="https://www.oracle.com/br/cloud/">
  <img alt="image" src="https://img.shields.io/badge/Oracle_Cloud-%23696969?style=for-the-badge&logo=Oracle">
</a>
<a href="https://www.atlassian.com/software/jira">
  <img alt="image" src="https://img.shields.io/badge/Jira_Software-%23696969?style=for-the-badge&logo=jirasoftware">
</a>
<a href="https://git-scm.com/">
  <img alt="image" src="https://img.shields.io/badge/Git-%23696969?style=for-the-badge&logo=Git">
</a>
<a href="https://nodejs.org/en/">
  <img alt="image" src="https://img.shields.io/badge/Node.js-%23696969?style=for-the-badge&logo=Node.js">
</a>
<a href="https://www.npmjs.com/">
  <img alt="image" src="https://img.shields.io/badge/NPM-%23696969?style=for-the-badge&logo=npm">
</a>
<a href="https://maven.apache.org/">
  <img alt="image" src="https://img.shields.io/badge/Maven-%23696969?style=for-the-badge&logo=Apache Maven">
</a>
<a href="https://spring.io/projects/spring-boot">
  <img alt="image" src="https://img.shields.io/badge/Spring_Boot-%23696969?style=for-the-badge&logo=Spring">
</a>

</div>

<h3 align="center">Contribuições individuais/pessoais</h3>

- [x] Nesse projeto do 4º semestre eu assumi o papel de Scrum Master e atuei efetivamente no front-end.
- [x] Trabalhei principalmente no Front-end desenvolvendo as telas e consumindo as API REST, programei cerca de 80% do front-end.
- [x] Dei a ideia de ser utilizado o Vuejs como framework web.
- [x] Ajudei alguns integrantes que não conheciam o framework Vuejs.
- [x] Fiz todo o gerenciamento do GitHub, como acessos ao repositorio e gerenciamento de branchs.
- [x] Exercendo o papel de Scrum Master eu ajudei a gerenciar a equipe e o projeto, marcando as reuniões e seguindo os rituais da metodologia SCRUM.

<p align="center">Telas desenvolvidas por mim</p>

<p align="center"> Tela de Login </p>
<p align="center"> <img src="imagens-4-semestre/tela_login.png" alt="tela de login" class="center" width=800/> </p>

```bash
<v-form
  ref="form"
  v-model="valid"
  lazy-validation
  @submit.prevent="do_login"
>
  <span style="color: white; font-size: 18px">E-mail</span>
  <v-text-field
    label="Email"
    v-model="usuario.email"
    :rules="regra_email"
    single-line
    solo
    required
    dense
    background-color="#A9A9A9"
  ></v-text-field>
  <span style="color: white; font-size: 18px">Senha</span>
  <v-text-field
    label="Senha"
    v-model="usuario.senha"
    :rules="regra_senha"
    background-color="#A9A9A9"
    single-line
    solo
    required
    dense
    password
    :append-icon="show1 ? 'mdi-eye' : 'mdi-eye-off'"
    :type="show1 ? 'text' : 'password'"
    @click:append="show1 = !show1"
  ></v-text-field>
  <v-btn
    id="botao-login"
    block
    color="#C84634"
    type="submit"
    class="white--text"
    :disabled="!valid"
    @click="validate"
    >Login</v-btn
  >
</v-form>
```

<p align="center"> Tela para um usuário externo criar uma conta no sistema </p>
<p align="center"> <img src="imagens-4-semestre/tela_criar_conta.png" alt="tela de criação de conta" class="center" width=800/> </p>

```bash
<v-form
  ref="form"
  v-model="valid"
  lazy-validation
  @submit.prevent="cadastrar_usuario"
>
  <v-container>
    <v-row justify="center">
      <v-col cols="24">
        <span style="color: white; font-size: 18px">Nome</span>
        <v-text-field
          label="Nome"
          v-model="usuario.nome"
          :rules="regra_nome"
          single-line
          solo
          required
          dense
          background-color="#A9A9A9"
        ></v-text-field>
      </v-col>
    </v-row>
    <v-row justify="center">
      <v-col cols="24">
        <span style="color: white; font-size: 18px"
          >E-mail</span
        >
        <v-text-field
          label="E-mail"
          v-model="usuario.email"
          :rules="regra_email"
          single-line
          solo
          required
          dense
          background-color="#A9A9A9"
        ></v-text-field>
      </v-col>
    </v-row>
    <v-row justify="center">
      <v-col cols="24">
        <span style="color: white; font-size: 18px">Senha</span>
        <v-text-field
          label="Senha"
          v-model="usuario.senha"
          :rules="regra_senha"
          background-color="#A9A9A9"
          single-line
          solo
          required
          dense
          password
          :append-icon="show1 ? 'mdi-eye' : 'mdi-eye-off'"
          :type="show1 ? 'text' : 'password'"
          @click:append="show1 = !show1"
        ></v-text-field>
      </v-col>
    </v-row>
    <v-row>
      <v-col></v-col>
      <v-col>
        <v-btn text color="white" :to="{ name: 'Login' }"
          >Cancelar</v-btn
        >
      </v-col>
      <v-col>
        <v-btn
          color="#C84634"
          class="white--text mr-4"
          type="submit"
          :disabled="!valid"
          @click="validate"
        >
          Salvar
        </v-btn>
      </v-col>
    </v-row>
  </v-container>
</v-form>
```

<p align="center"> Tela de gerenciamento de Usuário (CRUD)</p>
<p align="center"> <img src="imagens-4-semestre/tela_usuario_1.png" alt="tela de gerenciamento de usuário" class="center" width=800/> </p>
<p align="center"> <img src="imagens-4-semestre/tela_usuario_2.png" alt="tela de gerenciamento de usuário" class="center" width=800/> </p>

```bash
// Método de cadastro de usuario
cadastrar_usuario() {
  // Se o usuario não tiver um "cod" significa que esse usuario não existe então ele vai pra resquest de cadastro
  if (!this.usuario.cod) {
    Usuario.salvar_usuario(this.usuario)
      .then((resposta_cadastro_usuario) => {
        this.usuario = {};
        Swal.fire(
          "Sucesso",
          "Usuário " +
            resposta_cadastro_usuario.data.nome +
            " cadastrado com sucesso!!!",
          "success"
        );
        this.exibir_usuario();
      })
      .catch((e) => {
        Swal.fire(
          "Oops...",
          "Erro ao cadastrar o usuário! - Erro: " + e.response.data.error,
          "error"
        );
      });
    this.close();
  } else {
    // Método de atualizar usuario
    // Se o usuario já tiver um "cod" ele já existe então ele vai pra request de atualizar
    Usuario.atualizar_usuario(this.usuario)
      .then((resposta_atualizar_usuario) => {
        this.usuario = {};
        Swal.fire(
          "Sucesso",
          "Usuário " +
            resposta_atualizar_usuario.data.nome +
            " atualizado com sucesso!!!",
          "success"
        );
        this.exibir_usuario();
      })
      .catch((e) => {
        Swal.fire(
          "Oops...",
          "Erro ao atualizar o usuário! - Erro: " + e.response.data.error,
          "error"
        );
      });
    this.close();
  }
},
```

<p align="center"> Tela de Fornecedor</p>
<p align="center"> <img src="imagens-4-semestre/tela_fornecedor_1.png" alt="tela de fornecedor" class="center" width=800/> </p>

<p align="center"> Tela de Agendamento de Evento</p>
<p align="center"> <img src="imagens-4-semestre/tela_evento_1.png" alt="tela de agendamento de evento" class="center" width=800/> </p>

```bash
// Método pra exibir os eventos
exibir_evento() {
  Evento.listar_eventos()
    .then((resposta_lista_evento) => {
      this.lista_de_eventos = resposta_lista_evento.data;
    })
    .catch((e) => {
      Swal.fire(
        "Oops...",
        "Erro ao carregar a tabela de eventos! - Erro: " +
          e.response.data.error,
        "error"
      );
    });
},
```

<p align="center"> Tela de Visitante (CRUD)</p>
<p align="center"> <img src="imagens-4-semestre/tela_visitante_1.png" alt="tela de agendamento de visitante" class="center" width=800/> </p>
<p align="center"> <img src="imagens-4-semestre/tela_visitante_2.png" alt="tela de agendamento de visitante" class="center" width=800/> </p>

```bash
// Método pra excluir os visitantes
deletar_visitante(visitante) {
  Visitante.excluir_visitante(visitante)
    .then((resposta_excluir_visitante) => {
      Swal.fire("Sucesso", "Visitante excluido com sucesso!!!", "success");
      resposta_excluir_visitante;
      this.exibir_visitante();
    })
    .catch((e) => {
      Swal.fire(
        "Oops...",
        "Erro ao excluir o visitante! - Erro: " + e.response.data.error,
        "error"
      );
    });
  this.closeDelete();
},
```

<h4 align="center">Hard Skills Efetivamente Desenvolvidas</h4>

- [x] Aprofundei meus conhecimentos no framework Vuejs como um todo.
- [x] Aprendi a trabalhar com API REST no Vuejs.
- [x] Aprendi a trabalhar com gerencimento de Organizações e Repositórios no GitHub.
- [x] Aprendi como é gerenciar uma equipe através do método SCRUM.
- [x] Aprofundei os meus conhecimentos na padrão de projetos MVC, o seu princípio básico é a divisão da aplicação em três camadas: a camada de interação do usuário (view), a camada de manipulação dos dados (model) e a camada de controle (controller).
- [x] Como utilizamos um framework Javascript para facilitar a programação eu aprofundei os meus conhecimentos no padrão de projetos Facade que é um padrão de projeto estrutural que fornece uma interface simplificada para uma biblioteca, um framework, ou qualquer conjunto complexo de classes.
- [x] Como utlizamos o framework Javascript Vuejs aonde temos a estrutura de componentes compondo componentes eu aprofundei os meus conhecimentos no padrão de projetos Composite que é um padrão de projeto estrutural que permite que você componha objetos em estruturas de árvores e então trabalhe com essas estruturas como se elas fossem objetos individuais.

<h4 align="center">Soft Skills Efetivamente Desenvolvidas</h4>

- [x] Trabalho em equipe
- [x] Responsabilidade
- [x] Organização
- [x] Gestão do tempo
- [x] Confiança
