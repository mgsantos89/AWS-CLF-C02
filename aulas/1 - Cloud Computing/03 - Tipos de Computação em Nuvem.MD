# Introdução à Computação em Nuvem

### **1. Tipos de Computação em Nuvem**
A computação em nuvem possui diferentes modelos de serviço, sendo os principais:

#### **1.1 Infraestrutura como Serviço (IaaS)**
- Fornece os blocos básicos de TI na nuvem: rede, computação e armazenamento.
- Oferece alta flexibilidade e facilita a migração da TI tradicional para a nuvem.
- Exemplos:
  - **AWS:** Amazon EC2
  - **Outros provedores:** Google Cloud, Azure, Rackspace, Digital Ocean, Linode.

#### **1.2 Plataforma como Serviço (PaaS)**
- Elimina a necessidade de gerenciar infraestrutura subjacente.
- Foca apenas na implementação e gestão de aplicativos.
- Exemplos:
  - **AWS:** Elastic Beanstalk
  - **Outros provedores:** Heroku, Google App Engine, Windows Azure.

#### **1.3 Software como Serviço (SaaS)**
- Produto completo gerenciado pelo provedor de serviço.
- Exemplos:
  - **AWS:** Rekognition (aprendizado de máquina)
  - **Outros serviços comuns:** Gmail, Dropbox, Zoom.

### **2. Comparando os Modelos de Nuvem**
| Modelo  | Responsabilidade do Usuário | Responsabilidade do Provedor |
|---------|-----------------------------|-----------------------------|
| On-Premises | Tudo (aplicações, dados, servidores, rede) | Nada |
| IaaS | Aplicações, dados, SO | Virtualização, servidores, rede |
| PaaS | Aplicações, dados | Todo o resto (infraestrutura e execução) |
| SaaS | Nada | Tudo |

### **3. Modelo de Preços na AWS**
A AWS segue o modelo de **pay-as-you-go**, ou seja, pagamos apenas pelo que usamos. Existem três principais categorias de cobrança:

- **Computação:** Pagamento pelo tempo exato de uso da infraestrutura.
- **Armazenamento:** Pagamento pela quantidade de dados armazenados.
- **Rede:** Pagamento apenas pelos dados que saem da nuvem (entrada gratuita).

Este modelo reduz significativamente os custos em comparação com a TI tradicional.

