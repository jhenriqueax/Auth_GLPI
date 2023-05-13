# Como Subir o GLPI com Docker

Este é um guia rápido para ajudá-lo a configurar e executar o GLPI com Docker. Com a utilização do Docker, você pode simplificar o processo de instalação e evitar conflitos de versões.

## Pré-requisitos

Antes de começar, você precisa ter o Docker instalado na sua máquina. Para isso, siga as instruções no [site oficial do Docker](https://docs.docker.com/get-docker/).


## Passo a passo

1. Faça o download do arquivo **docker-compose.yml** deste repositório.
  
        https://github.com/jhenriqueax/Auth_GLPI.git

2. Abra um terminal e navegue até o diretório onde o arquivo **docker-compose.yml** está salvo

3. Execute o comando **docker-compose up -d** para iniciar os containers do GLPI e do banco de dados MariaDB. Esse comando baixará as imagens do Docker Hub e configurará o ambiente. O processo pode levar alguns minutos.

       docker-compose up -d

4. Verifique se os containers estão em execução com o comando **docker ps**. Você deve ver dois containers em execução: `glpi` e `mariadb`.

       docker ps

5. Abra seu navegador e acesse o endereço **localhost:80** . Isso deve abrir a página de instalação do GLPI.

        localhost:80

6. Na página de instalação do GLPI, selecione o idioma desejado e clique em "Próximo".

7. Na página de configuração do banco de dados, digite as credenciais abaixo, Se a conexão for bem-sucedida, clique em "Próximo".

    | Nome do Servidor |   Usuário   |   senha   |
    |------------------|-------------|-----------|
    |      mariadb     |  glpi_user  |    glpi   | 

8. Na página de configuração de contas, defina os usuários e senhas para as contas "Super Administrador", "Conta do Técnico", "Conta do Usuário" e "Conta somente para postar". Clique em "Próximo".

9. Conclua as configurações finais.

Pronto! Agora você tem o GLPI instalado e funcionando com Docker.


## Informações de Login

| Usuário | Senha | Função                |
|---------|-------|-----------------------|
| glpi    | glpi  | Super Administrador   |
| tech    | tech  | Conta do Técnico      |
| normal  | normal| Conta do Usuário      |
| post-only|postonly| Conta somente para postar |


## Dicas adicionais

- Para parar os containers, execute o comando ``docker-compose down``.
- Para reiniciar os containers, execute o comando ``docker-compose restart``.
- Para remover os containers e limpar o ambiente, execute o comando ``docker-compose down -v``.


