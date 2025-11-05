# AWS_CloudFormation
Desafio AWS CloudFormation do Bootcampo Code Girls 2025 

🧱 Implementando sua Primeira Stack com AWS CloudFormation

O AWS CloudFormation é um serviço que permite criar e gerenciar recursos da AWS de forma automatizada, utilizando modelos (templates) em formato YAML ou JSON. Em vez de configurar manualmente cada serviço pela console, o CloudFormation executa o provisionamento de forma padronizada, segura e repetível.

A seguir, estão os passos essenciais para implementar sua primeira stack:

1. Entender o conceito de Stack e Template

Template: é o arquivo que descreve os recursos da sua infraestrutura (como EC2, S3, Lambda, VPC etc.).

Stack: é o conjunto de recursos criados e gerenciados pelo CloudFormation a partir de um template.
Ou seja, você escreve o template, e o CloudFormation cria a stack correspondente.

2. Criar o Template

Você pode criar o template de duas formas:

Manual: escrevendo o arquivo YAML ou JSON em um editor de texto (ex: Visual Studio Code).

Visual: usando o AWS CloudFormation Designer, que oferece uma interface gráfica para montar o diagrama da infraestrutura.

Exemplo simples de template YAML para criar um bucket S3:

AWSTemplateFormatVersion: "2010-09-09"
Description: "Criação de um bucket S3 simples"
Resources:
  MeuBucketS3:
    Type: "AWS::S3::Bucket"
    Properties:
      BucketName: "meu-primeiro-bucket-cloudformation"

3. Fazer o Upload do Template

Acesse o console da AWS → CloudFormation.

Clique em Create stack → With new resources (standard).

Faça o upload do template (arquivo YAML/JSON) ou insira o link de um template salvo no S3.

4. Configurar os Detalhes da Stack

Defina um nome para a stack (ex: MinhaPrimeiraStack).

Se o template tiver parâmetros, insira os valores solicitados (por exemplo, nome do bucket, tipo de instância EC2, etc.).

Clique em Next para revisar as opções avançadas (tags, permissões, rollback, etc.).

5. Criar a Stack

Revise todas as configurações.

Marque a opção de permissão para que o CloudFormation crie recursos em seu nome.

Clique em Create stack.

O CloudFormation iniciará o provisionamento automático. Você pode acompanhar o progresso na aba Events do console.

6. Validar a Criação dos Recursos

Após o status mudar para CREATE_COMPLETE, vá até o serviço correspondente (ex: S3, EC2, etc.) para confirmar que os recursos foram criados com sucesso.

Se algo der errado, verifique a aba Events para ver o motivo da falha.

7. Atualizar ou Excluir a Stack

Se quiser alterar recursos, basta modificar o template e aplicar um update na stack.

Para remover tudo de forma segura, basta excluir a stack, e o CloudFormation apagará todos os recursos criados automaticamente.

✅ Benefícios de usar CloudFormation

Automação: provisionamento rápido e sem erros manuais.

Reprodutibilidade: fácil recriar o mesmo ambiente em outra região ou conta.

Controle de versão: templates podem ser armazenados no GitHub.

Integração: funciona junto com serviços como AWS CodePipeline e AWS Config.
