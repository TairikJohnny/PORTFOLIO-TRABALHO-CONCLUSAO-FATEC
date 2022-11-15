<h1 align="center">API 2º SEMESTRE - 2020-2</h1>

<p align="center"> <img src="imagens/icone_pi.png" alt="AgendHouse" class="center" width=200/> </p>

<h4 align="center">
Link para o repositório do projeto
</h4>

[Link para o projeto](https://github.com/TairikJohnny/API-2-SEMESTRE)

<h3 align="center">
Resumo
</h3>

Projeto realizado em parceria com a [Tecsus](https://tecsus.com.br/) uma startup que desenvolve dispositivos, aplicativos e sistemas para a transmissão e recepção de dados, controle de equipamentos remotos e gestão de faturas juntamente com a Faculdade de Tecnologia de São José dos Campos Professor Jessen Vidal. A Tecsus realiza a gestão de contas de utilidades (água e energia) dos seus clientes. Todos os meses milhares de contas devem ser digitadas manualmente no sistema para a realização de análises de contratos e análises de consumo. O desafio foi desenvolver um sistema para facilitar a digitação manual das contas, assim, permitindo o cadastro de rápida e ágil, sem a necessidade de utilização do mouse, apenas por comandos do teclado.

<h3 align="center">Tecnologias adotadas na solução</h3>

<div align="center">

<a href="https://www.java.com/pt-BR/">
  <img src="https://img.shields.io/static/v1?label=Java&message=Back-End&color=007396&style=for-the-badge&logo=java"/>
</a>
<a href="https://www.mysql.com/">
  <img src="https://img.shields.io/static/v1?label=MySQL&message=Banco de Dados&color=4479A1&style=for-the-badge&logo=MySQL"/>
</a>
<a href="https://git-scm.com/">
  <img src="https://img.shields.io/static/v1?label=Git&message=Devops&color=F05032&style=for-the-badge&logo=Git"/>
</a>
<a href="https://github.com">
  <img src="https://img.shields.io/static/v1?label=GitHub&message=Devops&color=181717&style=for-the-badge&logo=GitHub"/>
</a>

</div>

<h3 align="center">Contribuições individuais/pessoais</h3>

Trabalhei na parte de conexão do banco de dados via JDBC e com os CRUDs do sistema. Abaixo segue algumas classes e métodos desenvolvidos por mim.

<details>
<summary><b>Classe para criar o banco de dados</b></summary>

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

</details>

<details>
<summary><b>Classe para atualizar os dados do banco de dados</b></summary>

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

</details>

<h4 align="center">Hard Skills Efetivamente Desenvolvidas</h4>

- [x] Aprofundei os meus conhecimentos com versionamento de código via GIT.
- [x] Aprofundei os meus conhecimentos com gerenciamento de projeto no GitHub.
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