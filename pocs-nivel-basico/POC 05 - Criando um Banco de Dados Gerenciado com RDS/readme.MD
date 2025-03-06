## **📌 POC 05 - Criando um Banco de Dados Gerenciado com RDS**

### **🎯 Objetivo**  
O objetivo desta POC é provisionar um banco de dados gerenciado no Amazon RDS (MySQL ou PostgreSQL) e conectar a uma aplicação local para interagir com o banco. Ao realizar essa tarefa, você aprenderá a utilizar o Amazon RDS, que oferece bancos de dados escaláveis e de alta disponibilidade, sem a necessidade de gerenciar a infraestrutura subjacente.

### **🛠️ Pré-requisitos**  
- Conta AWS configurada com permissões administrativas.
- Familiaridade com a AWS Management Console.
- Conhecimento básico de bancos de dados relacionais (MySQL ou PostgreSQL).
- Aplicação local para conectar-se ao banco de dados RDS (exemplo: uma aplicação Java, Python ou PHP).

### **📖 Passo a Passo**

#### **1️⃣ Criando uma Instância RDS**
1. Acesse o [AWS Management Console](https://console.aws.amazon.com/).
2. No painel de serviços, pesquise por **RDS** e clique sobre o serviço.
3. No painel esquerdo, clique em **Databases** e depois em **Create database**.
4. Selecione o **Banco de Dados Engine**: Escolha **MySQL** ou **PostgreSQL**.
5. Selecione a opção **Standard Create** para um controle completo sobre a configuração da instância.
6. Preencha as informações de configuração da instância:
   - **DB Instance Identifier**: Defina um nome para sua instância (ex: `mydb-instance`).
   - **Master Username**: Defina um nome de usuário administrador (ex: `admin`).
   - **Master Password**: Defina a senha do administrador.
7. Em **DB Instance Size**, escolha uma instância de acordo com suas necessidades. Para fins de teste, uma instância **db.t2.micro** pode ser suficiente.
8. Em **Storage**, deixe o padrão, ou configure a quantidade de armazenamento desejada.
9. Em **VPC & Security Groups**, configure a VPC para garantir que sua instância RDS tenha conectividade adequada com os recursos da sua rede.
10. Em **Public Accessibility**, selecione **Yes**, se quiser que sua instância seja acessível publicamente.
11. Clique em **Create database**.

#### **2️⃣ Configurando o Security Group**
1. Após a criação da instância RDS, vá até o **Security Groups** da VPC onde sua instância está.
2. Adicione uma regra de entrada para permitir o acesso ao banco de dados. Para MySQL, a porta padrão é **3306**, e para PostgreSQL é **5432**.
3. Adicione uma regra permitindo o acesso de seu IP local para testar a conexão.
4. Clique em **Save rules**.

#### **3️⃣ Conectando a Aplicação Local ao Banco RDS**
1. Verifique o **Endpoint** da sua instância RDS na página de detalhes da instância no Console da AWS.
2. Na sua aplicação local, configure a string de conexão com o banco de dados, utilizando o **Endpoint**, o **nome de usuário** e a **senha** definidos anteriormente.
   - Exemplo para MySQL (em PHP):
     ```php
     $servername = "mydb-instance.c9akciq32.rds.amazonaws.com";
     $username = "admin";
     $password = "yourpassword";
     $dbname = "yourdbname";
     
     $conn = new mysqli($servername, $username, $password, $dbname);
     
     if ($conn->connect_error) {
         die("Connection failed: " . $conn->connect_error);
     }
     echo "Connected successfully";
     ```
   - Exemplo para PostgreSQL (em Python):
     ```python
     import psycopg2
     
     conn = psycopg2.connect(
         host="mydb-instance.c9akciq32.rds.amazonaws.com",
         database="yourdbname",
         user="admin",
         password="yourpassword"
     )
     print("Connected successfully")
     ```
3. Teste a conexão executando a aplicação localmente.

#### **4️⃣ Configurando Backup e Manutenção**
1. No painel de configuração da instância RDS, vá até **Backup** e configure o **backup automatizado** para garantir que seus dados sejam protegidos.
2. Configure o **Maintenance window** para especificar quando a instância pode ser atualizada automaticamente.

#### **5️⃣ Monitoramento com CloudWatch**
1. Acesse o **CloudWatch** no Console AWS.
2. Verifique as métricas relacionadas à sua instância RDS, como **CPU utilization**, **Disk space usage** e **Read/Write operations**.
3. Crie alarmes para monitorar essas métricas e receber notificações caso algum limite seja ultrapassado.

### **📌 Conclusão**  
Nesta POC, você aprendeu como provisionar um banco de dados gerenciado com Amazon RDS, configurar a conexão de uma aplicação local ao banco e realizar configurações essenciais de segurança e backup. O Amazon RDS simplifica o processo de gerenciar bancos de dados, permitindo que você se concentre mais no desenvolvimento da sua aplicação e menos na administração da infraestrutura.

### **📚 Dicas para Aprofundamento**  
📌 **Configuração de Multi-AZ para Alta Disponibilidade**: Explore como criar uma instância RDS com Multi-AZ para garantir alta disponibilidade. Isso pode ser feito ao criar a instância, selecionando a opção **Multi-AZ** para replicação síncrona.  
📌 **Escalabilidade Horizontal com Read Replicas**: Aprenda a configurar **Read Replicas** para escalar a leitura do banco de dados e distribuir a carga de trabalho.  
📌 **IAM Authentication**: Em vez de usar credenciais de banco de dados tradicionais, você pode configurar **IAM Database Authentication** para gerenciar autenticação de usuários no banco via IAM. Isso oferece uma abordagem mais segura. [IAM Authentication para RDS](https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/UsingWithRDS.IAMDBAuth.html).  
📌 **RDS Proxy**: Use o **RDS Proxy** para melhorar a escalabilidade e a segurança das conexões com o banco de dados. O RDS Proxy gerencia as conexões para garantir que sua aplicação seja mais eficiente.  
📌 **Otimização de Performance**: Explore opções de otimização de desempenho, como o uso de **Provisioned IOPS** para uma latência de disco mais baixa, ou o ajuste de parâmetros no **Parameter Group** do RDS para melhorar a performance de consultas.  

---

Esse é um modelo completo de README para documentar sua POC sobre a criação de um banco de dados no RDS. Se precisar de mais detalhes ou ajustes, fico à disposição! 🚀