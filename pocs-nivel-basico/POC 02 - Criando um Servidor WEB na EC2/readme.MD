## **📌 POC 02 - Criando um Servidor Web na EC2**  

### **🎯 Objetivo**  
O objetivo desta POC é criar uma instância EC2 Linux, configurar as regras de segurança para permitir o tráfego HTTP/HTTPS e hospedar um site simples na instância, a fim de aprender os principais conceitos de computação na AWS.

### **🛠️ Pré-requisitos**  
- Uma conta AWS criada e configurada (ver POC 1).  
- Conhecimento básico sobre servidores web e instâncias EC2.  
- Uma chave SSH gerada para acesso seguro à instância EC2.  
- Um arquivo HTML simples para hospedar como página web.

### **📖 Passo a Passo**

#### **1️⃣ Criando uma Instância EC2**
1. Acesse o [AWS Management Console](https://console.aws.amazon.com/).  
2. Na barra de pesquisa, procure por **"EC2"** e clique em **"Instâncias EC2"**.  
3. Clique em **"Launch Instance"** para criar uma nova instância.  
4. Escolha a **Amazon Linux 2 AMI** (ou qualquer distribuição Linux de sua preferência).  
5. Selecione o tipo de instância, como **t2.micro** (que é elegível para o Free Tier).  
6. Na **configuração de instância**, você pode deixar os parâmetros padrão.  
7. Configure o armazenamento, deixando o padrão (8GB de EBS).  
8. Na **configuração de rede**, selecione a VPC padrão.  
9. Clique em **"Next: Configure Security Group"**.  

#### **2️⃣ Configurando o Security Group**  
1. Crie um novo **Security Group** ou use um existente.  
2. Adicione as seguintes regras de entrada para permitir acesso à instância:
   - **HTTP (porta 80)**: Para acesso via navegador.  
   - **SSH (porta 22)**: Para acesso remoto à instância (certifique-se de restringir o acesso a seu IP).  
   - **HTTPS (porta 443)**: Caso deseje suportar HTTPS no futuro.  
3. Finalize a criação da instância e anote o **IP público** da EC2.  

#### **3️⃣ Acessando a Instância EC2 via SSH**  
1. Localize a chave SSH criada no momento de criação da instância.  
2. Acesse a instância usando o comando SSH no terminal (substitua os valores de IP e caminho da chave SSH):
   ```bash
   ssh -i /caminho/para/sua-chave.pem ec2-user@<IP-da-instância>
   ```
3. Após conectar, você estará dentro da instância EC2 e poderá configurar o servidor web.

#### **4️⃣ Instalando o Apache (ou Nginx) na Instância EC2**  
1. Instale o **Apache** com o seguinte comando:
   ```bash
   sudo yum update -y
   sudo yum install httpd -y
   ```
2. Inicie o serviço Apache:
   ```bash
   sudo systemctl start httpd
   ```
3. Habilite o Apache para iniciar automaticamente após reinicializações:
   ```bash
   sudo systemctl enable httpd
   ```

#### **5️⃣ Carregando o Conteúdo do Site**  
1. Crie um arquivo **index.html** simples com conteúdo como:
   ```html
   <html>
       <head><title>Meu Primeiro Site na AWS</title></head>
       <body><h1>Olá, este é um site hospedado na AWS EC2!</h1></body>
   </html>
   ```
2. Carregue esse arquivo no diretório padrão do Apache:
   ```bash
   sudo echo "<html><head><title>Meu Primeiro Site na AWS</title></head><body><h1>Olá, este é um site hospedado na AWS EC2!</h1></body></html>" > /var/www/html/index.html
   ```

#### **6️⃣ Testando o Site**  
1. Abra um navegador e acesse o **IP público** da instância EC2:  
   ```http
   http://<IP-da-instância>
   ```
2. Se tudo estiver correto, você verá a página com a mensagem configurada no **index.html**.  

### **📌 Conclusão**  
Essa POC permitiu criar uma instância EC2, configurar as regras de segurança necessárias, instalar um servidor web e hospedar um site simples. Com isso, você aprendeu a gerenciar instâncias EC2, utilizar o Amazon Linux, configurar a segurança e realizar deploy básico de uma aplicação web.

### **📚 Dicas para Aprofundamento**  
📌 Explore o **Amazon EC2 Auto Scaling** para aumentar ou diminuir o número de instâncias conforme a demanda de tráfego: [EC2 Auto Scaling](https://docs.aws.amazon.com/autoscaling/)  
📌 Configure um **Elastic Load Balancer (ELB)** para distribuir tráfego entre múltiplas instâncias EC2: [Elastic Load Balancing](https://docs.aws.amazon.com/elasticloadbalancing/latest/userguide/)  
📌 Aprenda sobre a configuração de **Elastic IPs** para instâncias EC2 e como associá-las para manter um IP fixo: [Elastic IPs](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/elastic-ip-addresses.html)  

---

Caso precise de ajustes ou adições, só avisar! 🚀