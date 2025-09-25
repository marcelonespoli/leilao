
Projeto - Leilão
---

### Contexto:
- A rotina de criação de leilão e lances já está implementada.
- A validação de leilão fechado ou aberto durante a criação de novos lances (bids) já está implementada.

---


## Configuração e Execução 

### 1. Configurar o Tempo de Fechamento 
No arquivo `.env`, ajuste o valor do campo `AUCTION_DURATION` para definir o tempo que um leilão permanecerá ativo antes de ser fechado automaticamente.

### 2. Iniciar os Serviços 
Execute o comando abaixo para iniciar a aplicação:
```bash
make up
```
Aguarde até que todos os serviços estejam completamente inicializados.

---

## Testando o Fechamento Automático 

### 1. Criar um Novo Leilão 
Use o comando abaixo para criar um leilão utilizando um exemplo de requisição POST:
```bash
sudo make create
```

### 2. Listar Leilões Ativos 
Use o comando abaixo para listar os leilões com o status ativo (status = 0):
```bash
sudo make list
```
O campo status dos leilões retornados será 0, indicando que estão ativos.

### 3. Verificar o Fechamento 
Aguarde o tempo configurado em `AUCTION_DURATION` no `.env`. Após o período, use o comando abaixo para verificar os leilões fechados:
```bash
sudo make check
```
Agora, o campo status dos leilões será 1, indicando que foram fechados automaticamente.

---

## Rodar os Testes Automatizados 
Para executar os testes do projeto e verificar o comportamento do fechamento automático, use o comando:
```bash
sudo make test
```
---

