# ☁️ Desafio DIO - Infraestrutura Automatizada com AWS CloudFormation

## 📘 Descrição do Projeto
Este repositório faz parte do desafio proposto pela **Digital Innovation One (DIO)**, com o objetivo de **implementar uma infraestrutura automatizada utilizando o AWS CloudFormation**.  
O projeto visa demonstrar, na prática, o uso de **Infraestrutura como Código (IaC)**, automatizando a criação e o gerenciamento de recursos na AWS.

---

## 🎯 Objetivos de Aprendizagem
Ao concluir este projeto, pude:
- Aplicar os conceitos aprendidos em um ambiente prático;
- Criar e gerenciar stacks utilizando o **AWS CloudFormation**;
- Documentar processos técnicos de forma clara e organizada;
- Utilizar o **GitHub** como ferramenta de documentação e portfólio técnico.

---

## 🧩 Recursos e Serviços Utilizados
- **AWS CloudFormation**
- **Amazon EC2**
- **AWS CLI** (para deploy via linha de comando)
- **Git & GitHub**
- **YAML** (para escrita dos templates)

---

## ⚙️ Estrutura do Template
O arquivo `template.yaml` contém a definição da infraestrutura provisionada.  
O exemplo abaixo cria uma instância **EC2** configurada com tags de identificação:

```yaml
AWSTemplateFormatVersion: '2010-09-09'
Description: Template simples para criar uma instância EC2 com CloudFormation

Resources:
  MinhaInstanciaEC2:
    Type: AWS::EC2::Instance
    Properties:
      InstanceType: t2.micro
      ImageId: ami-0c55b159cbfafe1f0 # Substitua pela AMI da sua região
      Tags:
        - Key: Name
          Value: MinhaInstanciaCF

aws cloudformation create-stack --stack-name MinhaInfra \
--template-body file://template.yaml \
--region us-east-1
