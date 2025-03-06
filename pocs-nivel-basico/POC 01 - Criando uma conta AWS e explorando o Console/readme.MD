## **📌 POC 01 - Criando uma conta AWS e explorando o Console**  

### **🎯 Objetivo**  
O objetivo desta POC é criar uma conta AWS do zero, configurar segurança básica (MFA, permissões) e explorar o AWS Management Console para entender os principais serviços e navegação.  

### **🛠️ Pré-requisitos**  
- Um e-mail válido para registro na AWS  
- Um número de telefone ativo  
- Um cartão de crédito ou débito válido (para ativação da conta AWS Free Tier)  
- Acesso à internet  

### **📖 Passo a Passo**  

#### **1️⃣ Criando a Conta AWS**  
1. Acesse [aws.amazon.com](https://aws.amazon.com/) e clique em **"Criar uma conta AWS"**.  
2. Insira o e-mail, senha e nome da conta AWS.  
3. Escolha **"Conta Pessoal"** ou **"Conta Empresarial"**, conforme necessário.  
4. Forneça os detalhes de pagamento (a AWS não cobrará taxas no Free Tier).  
5. Valide sua conta via código SMS ou chamada telefônica.  
6. Escolha um plano (selecione **"Free Tier"** para evitar cobranças).  

#### **2️⃣ Ativando a Autenticação Multi-Fator (MFA) no Usuário Root**  
1. Acesse o AWS Management Console e faça login com a conta root.  
2. No canto superior direito, clique no **seu nome** e vá para **"Minha Conta"**.  
3. No menu esquerdo, clique em **"Configurações de Segurança"**.  
4. Em **"Autenticação Multifator (MFA)"**, clique em **"Ativar MFA"**.  
5. Escolha **"Aplicativo MFA Virtual"** e escaneie o QR Code com um aplicativo autenticador (Google Authenticator, Authy).  
6. Insira os códigos gerados e confirme.  

#### **3️⃣ Criando um Usuário IAM para Acesso Seguro**  
1. No Console AWS, acesse **"IAM"**.  
2. Vá para **"Usuários"** e clique em **"Adicionar usuário"**.  
3. Escolha um nome (ex: `admin-user`) e ative **"Acesso ao Console da AWS"**.  
4. Selecione **"Criar senha personalizada"** e defina uma senha segura.  
5. Atribua a permissão **"Administrador"** (ou crie políticas mais restritas).  
6. Faça login com esse novo usuário em vez do root.  

#### **4️⃣ Explorando o AWS Management Console**  
1. No console, observe a barra superior com **"Serviços", "Recursos Recentes" e "Suporte"**.  
2. Vá até **"Serviços"** e explore os principais grupos:  
   - **Computação** → EC2, Lambda  
   - **Armazenamento** → S3, EBS  
   - **Banco de Dados** → RDS, DynamoDB  
   - **Rede e Segurança** → VPC, IAM  
3. Clique em **"EC2"** e observe as opções de instâncias.  
4. Explore o **"S3"** e crie um bucket de teste.  
5. Acesse **"IAM"** e verifique as permissões do seu usuário.  

### **📌 Conclusão**  
Com essa POC, você criou e configurou uma conta AWS com segurança básica (MFA e IAM) e explorou o Console para se familiarizar com os serviços essenciais.  

### **📚 Dicas para Aprofundamento**  
📌 Leia a documentação da AWS IAM: [AWS Identity and Access Management](https://docs.aws.amazon.com/iam/)  
📌 Explore o AWS Free Tier e teste serviços como EC2 e S3 sem custos: [AWS Free Tier](https://aws.amazon.com/free/)  
📌 Habilite o **AWS Billing Alerts** para evitar cobranças inesperadas: [Configurar Alertas de Custo](https://docs.aws.amazon.com/awsaccountbilling/latest/aboutv2/free-tier-alarms.html)  

---

Se precisar de ajustes, me avise! 🚀