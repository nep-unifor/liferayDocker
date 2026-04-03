## Liferay com Docker

Este repositório fornece um ambiente simples para execução do Liferay utilizando Docker. O objetivo é facilitar o desenvolvimento local sem necessidade de configuração manual complexa.

## Visão Geral

O ambiente está configurado para rodar o Liferay diretamente a partir de uma imagem oficial, com foco exclusivo em desenvolvimento. Qualquer pessoa pode clonar este repositório e iniciar a aplicação rapidamente.

## Como executar

### Pré-requisitos

* Docker instalado
* Docker Compose instalado

### Passos

```bash
docker compose up -d
```

Após a inicialização, acesse no navegador:

```
http://localhost:8080
```

Acesso inicial

Para acessar o sistema pela primeira vez, utilize:

```
Email: test@liferay.com
Senha: test
```

## Configuração atual

O ambiente foi configurado com as seguintes características:

* Utiliza uma imagem pública oficial do Liferay Portal
* Porta 8080 exposta para acesso via navegador
* Setup wizard desativado para evitar configuração inicial manual
* Senha padrão de administrador definida como `test`
* Cache desativado para facilitar o desenvolvimento e testes

### Sem persistência de dados

Não há volumes configurados no Docker. Isso significa:

* Todos os dados são armazenados apenas dentro do container
* Ao remover o container, todos os dados são perdidos
* Comandos como `docker compose down -v` irão apagar completamente o ambiente

### Consequências

* Usuários criados serão perdidos após reinicialização completa
* Configurações feitas no portal não são persistidas
* Conteúdo criado no sistema será apagado

## Possíveis problemas

### Porta 8080 em uso

Caso a porta 8080 já esteja sendo utilizada, altere no `docker-compose.yml`:

```yaml
ports:
  - "8081:8080"
```

E acesse via:

```
http://localhost:8081
```


---

Este setup foi projetado para simplicidade e rapidez no desenvolvimento local. Para uso mais robusto, recomenda-se evoluir a configuração conforme as necessidades do projeto.
