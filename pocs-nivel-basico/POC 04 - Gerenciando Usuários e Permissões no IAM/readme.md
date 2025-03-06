Aqui está o **README.md** para documentar sua POC no GitHub:

---

## **📌 POC 04 - Gerenciando Usuários e Permissões no IAM**

### **🎯 Objetivo**  
O objetivo desta POC é aprender a criar usuários no AWS IAM (Identity and Access Management), aplicar políticas de segurança para restringir acessos e simular permissões de usuários. Essa prática é essencial para entender como gerenciar e controlar o acesso a recursos AWS de forma segura e eficiente.

### **🛠️ Pré-requisitos**  
- Conta AWS configurada e com permissões administrativas.  
- Conhecimento básico sobre o serviço **IAM** e **AWS Management Console**.  
- Familiaridade com a criação e aplicação de políticas de acesso.

### **📖 Passo a Passo**

#### **1️⃣ Criando um Usuário IAM**
1. Acesse o [AWS Management Console](https://console.aws.amazon.com/).
2. No painel de serviços, pesquise por **IAM** e clique sobre o serviço.
3. No painel esquerdo, clique em **"Users"** e depois em **"Add user"**.
4. Insira um nome de usuário (por exemplo, `usuario-poc`).
5. Selecione o tipo de acesso desejado para o usuário:
   - **Access key**: Permite o acesso via API/CLI.
   - **Password**: Permite o acesso via Console Web.
6. Clique em **Next: Permissions** para avançar.

#### **2️⃣ Atribuindo Permissões ao Usuário**
1. Escolha entre **Attach existing policies directly** ou **Add user to group** para definir as permissões:
   - **Attach existing policies directly**: Você pode selecionar políticas predefinidas, como **AdministratorAccess** (acesso total) ou **ReadOnlyAccess** (acesso somente leitura).
   - **Create a new group**: Crie um grupo de usuários e adicione permissões específicas a ele.
2. Para este exercício, escolha a política **ReadOnlyAccess** para restringir o usuário a apenas visualizar os recursos da AWS.
3. Clique em **Next: Tags** para continuar (opcionalmente, adicione tags para organização).
4. Clique em **Next: Review** para revisar a configuração.
5. Clique em **Create user** para finalizar a criação do usuário.

#### **3️⃣ Simulando o Acesso com o IAM Policy Simulator**
1. No painel do IAM, clique em **"IAM Policy Simulator"** no menu lateral esquerdo.
2. Selecione o usuário ou grupo de usuários para o qual você deseja testar as permissões.
3. Escolha uma ação e um serviço para simular. Por exemplo, você pode tentar acessar o serviço **S3** ou **EC2** e simular as permissões.
4. O simulador irá informar se o acesso foi permitido ou negado com base nas políticas aplicadas ao usuário.

#### **4️⃣ Testando o Acesso com o Novo Usuário**
1. Para testar as permissões no console, faça logout da sua conta de administrador.
2. Tente fazer login usando as credenciais do novo usuário (você receberá um nome de usuário e senha ou chave de acesso ao final da criação).
3. Após o login, verifique se as permissões do usuário estão restritas, conforme esperado. O usuário com a política **ReadOnlyAccess** não poderá realizar ações de modificação, como iniciar instâncias EC2.

#### **5️⃣ Modificando Permissões do Usuário**
1. Caso precise ajustar as permissões, volte ao painel IAM e clique sobre o nome do usuário.
2. Em **Permissions**, clique em **Add permissions** para adicionar ou modificar as políticas do usuário.
3. Você pode adicionar permissões específicas, como criar buckets no S3 ou administrar instâncias EC2, ou mesmo associar o usuário a um novo grupo com diferentes permissões.

### **📌 Conclusão**  
Nesta POC, você aprendeu como criar e gerenciar usuários IAM na AWS, aplicando políticas de segurança para controlar acessos. O IAM é fundamental para garantir que apenas usuários autorizados possam acessar e gerenciar recursos na AWS, respeitando os princípios de menor privilégio.

### **📚 Dicas para Aprofundamento**  
📌 **Políticas IAM e Controle Granular de Acesso**: Aprenda a escrever suas próprias **políticas IAM** para fornecer controle preciso sobre os recursos da AWS. Consulte a documentação sobre como criar políticas personalizadas: [AWS IAM Policies](https://docs.aws.amazon.com/IAM/latest/UserGuide/access_policies.html).  
📌 **Princípio do Menor Privilégio**: Sempre atribua apenas as permissões necessárias para a função de cada usuário. Isso reduz o risco de acesso indevido aos recursos da AWS.  
📌 Explore as permissões **IAM Conditions** para restringir acessos com base em condições específicas, como origem do IP ou hora do dia: [IAM Conditions](https://docs.aws.amazon.com/IAM/latest/UserGuide/reference_policies_elements_condition.html).  
📌 Aprenda a usar **Roles IAM** para fornecer permissões temporárias a recursos da AWS, como uma instância EC2 ou função Lambda: [IAM Roles](https://docs.aws.amazon.com/IAM/latest/UserGuide/id_roles.html).  
📌 **Auditoria de Acesso**: Utilize o **AWS CloudTrail** para auditar todas as ações realizadas pelos usuários na sua conta AWS. Isso é essencial para garantir segurança e conformidade: [AWS CloudTrail](https://docs.aws.amazon.com/awscloudtrail/latest/userguide/cloudtrail-user-guide.html).

---

Esse é um modelo detalhado para documentar sua POC sobre gerenciamento de usuários e permissões no IAM. Se precisar de ajustes ou informações adicionais, é só avisar! 🚀