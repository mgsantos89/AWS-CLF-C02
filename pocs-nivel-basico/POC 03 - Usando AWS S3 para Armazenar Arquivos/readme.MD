## **📌 POC 03 - Usando AWS S3 para Armazenar Arquivos**  

### **🎯 Objetivo**  
O objetivo desta POC é criar um bucket no Amazon S3, fazer o upload e download de arquivos, além de configurar as permissões públicas e privadas para gerenciar o acesso aos dados armazenados. Essa prática ajudará a entender como o S3 pode ser utilizado para armazenar e gerenciar arquivos na AWS.

### **🛠️ Pré-requisitos**  
- Conta AWS criada e configurada (ver POC 1).  
- Conhecimento básico sobre como interagir com a AWS S3 e o Console AWS.  
- Um arquivo simples para realizar o upload (pode ser uma imagem, PDF ou arquivo de texto).  

### **📖 Passo a Passo**

#### **1️⃣ Criando um Bucket S3**
1. Acesse o [AWS Management Console](https://console.aws.amazon.com/) e pesquise por **S3**.  
2. No painel do S3, clique em **"Create Bucket"**.  
3. Escolha um nome único para o seu bucket (ex: `meu-bucket-poc-aws-123`). O nome deve ser globalmente único, ou seja, não pode existir outro bucket com o mesmo nome.  
4. Escolha a região onde o bucket será criado (por exemplo, **us-east-1**).  
5. Não altere as configurações avançadas de criação do bucket por enquanto (deixe as configurações padrão).  
6. Clique em **"Create"** para criar o bucket.

#### **2️⃣ Enviando Arquivos para o Bucket S3**
1. No painel do S3, clique no nome do bucket recém-criado.  
2. Clique em **"Upload"**.  
3. Clique em **"Add files"** e selecione o arquivo local que você deseja fazer upload (pode ser uma imagem, um documento de texto, etc.).  
4. Clique em **"Upload"** para carregar o arquivo para o seu bucket.  
5. Após o upload, o arquivo estará disponível dentro do seu bucket S3.

#### **3️⃣ Fazendo Download de Arquivos**
1. Navegue até o seu bucket no S3 e clique no arquivo que você deseja baixar.  
2. Clique em **"Download"** para obter o arquivo em seu computador.  
3. O arquivo será baixado e estará disponível para o seu uso local.

#### **4️⃣ Configurando Permissões Públicas/Privadas para o Bucket e Arquivos**
1. **Configurando o Bucket como Privado** (padrão):
   - O bucket será privado por padrão, ou seja, os arquivos não estarão acessíveis publicamente.
   - Verifique se a opção **"Block all public access"** está habilitada. Isso garantirá que apenas você tenha acesso ao conteúdo do bucket.
   
2. **Tornando um Arquivo Público**:
   - Clique no arquivo desejado dentro do bucket.
   - Em **"Permissions"**, habilite a opção **"Public"** para tornar o arquivo acessível via URL pública.  
   - Após habilitar, o link público será exibido na seção de **Object URL**.
   
3. **Retirando a Permissão Pública**:
   - Se você deseja reverter a permissão pública, basta desmarcar a opção **"Public"** nas configurações de permissões do arquivo.  
   - O arquivo não será mais acessível publicamente.

#### **5️⃣ Acessando Arquivos via URL**
1. Após tornar um arquivo público, você pode acessar o arquivo através da URL pública gerada (por exemplo: `https://meu-bucket-poc-aws-123.s3.amazonaws.com/arquivo.txt`).

### **📌 Conclusão**  
Nesta POC, você aprendeu a criar um bucket no Amazon S3, fazer upload e download de arquivos, além de gerenciar permissões de acesso (públicas e privadas). Isso demonstra como o S3 pode ser utilizado como uma solução robusta para armazenar dados e controlar o acesso a esses dados.

### **📚 Dicas para Aprofundamento**  
📌 **Explore o versionamento do S3** para manter várias versões de um arquivo: [S3 Versioning](https://docs.aws.amazon.com/AmazonS3/latest/userguide/Versioning.html).  
📌 Aprenda a usar **S3 Lifecycle Policies** para gerenciar a expiração e transição de objetos entre classes de armazenamento: [S3 Lifecycle Policies](https://docs.aws.amazon.com/AmazonS3/latest/userguide/lifecycle-config-overview.html).  
📌 **Gerenciamento de Custos no S3**: Explore as diferentes **classes de armazenamento do S3** (Standard, Intelligent-Tiering, Glacier, etc.) para otimizar custos conforme as necessidades de acessibilidade dos arquivos: [S3 Storage Classes](https://docs.aws.amazon.com/AmazonS3/latest/userguide/storage-class-intro.html).  
📌 Aprenda sobre o **AWS S3 Transfer Acceleration** para acelerar o upload de grandes arquivos para o S3: [Transfer Acceleration](https://docs.aws.amazon.com/AmazonS3/latest/userguide/transfer-acceleration.html).

---

Esse é um template completo para sua documentação no GitHub. Se precisar de ajustes ou mais detalhes, só avisar! 🚀