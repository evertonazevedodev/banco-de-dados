# Desafio DIO - Criação e Configuração de Banco de Dados SQL no Azure

## 📌 Objetivo
Este repositório documenta o processo de criação e configuração de um **Banco de Dados SQL no Microsoft Azure** como parte do desafio prático da DIO.  
O objetivo foi aplicar os conceitos aprendidos nas aulas para provisionar um banco de dados na nuvem, configurá-lo para acesso seguro e testar sua conectividade.

---

## 🛠️ Tecnologias e Ferramentas Utilizadas
- **Microsoft Azure** (portal.azure.com)
- **Azure SQL Database**
- **SQL Server Management Studio (SSMS)**
- **Git e GitHub**
- **Markdown** para documentação

---

## 📋 Passo a Passo

### 1️⃣ Criando o Banco de Dados no Azure
1. Acesse o [Portal do Azure](https://portal.azure.com/).
2. No menu lateral, clique em **Criar um recurso** → **Bancos de dados** → **Banco de Dados SQL**.  
   ![Passo 1 - Criar banco de dados](./images/passo1-criar-banco.png)
3. Configure as opções:
   - **Assinatura**: Assinatura Padrão
   - **Grupo de Recursos**: `rg-desafio-dio`
   - **Nome do Banco de Dados**: `db-dio-azure`
   - **Servidor**: Criar novo
     - **Nome do servidor**: `srv-dio-azure`
     - **Login do administrador**: `adminsql`
     - **Senha**: (senha definida e anotada)
     - **Localização**: Brasil Sul
4. **Computação e Armazenamento**:
   - **Nível de serviço**: Basic
   - **Tamanho máximo**: 2 GB
5. Clique em **Revisar + Criar** e depois em **Criar**.

---

### 2️⃣ Configurando o Firewall e Permissões
1. Acesse o servidor criado (`srv-dio-azure`) no portal.
2. Em **Configurações de Firewall e Redes Virtuais**, adicione:
   - **Permitir serviços e recursos do Azure** ✔️
   - **Adicionar endereço IP do cliente** para permitir conexão da sua máquina.  
     ![Passo 2 - Configuração firewall](./images/passo2-firewall.png)
3. Salve as alterações.

---

### 3️⃣ Conectando ao Banco de Dados
1. Abra o **SQL Server Management Studio (SSMS)** no seu computador.
2. Em **Nome do servidor**, insira: `srv-dio-azure.database.windows.net`
3. **Autenticação**: SQL Server Authentication
4. Usuário: `adminsql`
5. Senha: (senha definida)
6. Clique em **Conectar**.  
   ![Passo 3 - Conexão SSMS](./images/passo3-conexao-ssms.png)

---

### 4️⃣ Criando uma Tabela de Teste
Dentro do SSMS, execute o seguinte comando:


CREATE TABLE Alunos (
    Id INT PRIMARY KEY IDENTITY(1,1),
    Nome NVARCHAR(100) NOT NULL,
    Curso NVARCHAR(100) NOT NULL,
    DataCadastro DATETIME DEFAULT GETDATE()
);



📚 Aprendizados
Durante este desafio, aprendi a:
Criar e configurar um banco de dados SQL no Azure.
Configurar regras de firewall para acesso seguro.
Conectar ao banco usando o SQL Server Management Studio.
Criar tabelas, inserir e consultar dados em um ambiente na nuvem.
Documentar processos técnicos usando GitHub e Markdown.

🔗 Recursos
Documentação oficial do Azure SQL Database
Guia de conexão via SSMS

👩‍💻 Autor
Everton Azevedo
