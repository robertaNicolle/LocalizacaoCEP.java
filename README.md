# Localizacao.java

Este é um projeto Java para consultar um endereço a partir de um CEP utilizando a API ViaCEP e gerar um arquivo JSON com as informações do endereço.

## Funcionalidades

- **Consulta de CEP**: O sistema permite consultar o endereço de um determinado CEP.
- **Geração de arquivo JSON**: Após a consulta, um arquivo `.json` contendo os dados do endereço é gerado automaticamente.

## Estrutura do Projeto

- `ConsultaCep.java`: Classe responsável por realizar a consulta do CEP via API.
- `Endereco.java`: Classe `record` que define o formato de um endereço.
- `GeradorDeArquivo.java`: Classe responsável por gerar um arquivo JSON com os dados do endereço.
- `Principal.java`: Classe principal onde o usuário interage com o sistema para digitar um CEP, realizar a consulta e salvar o arquivo.

## Como Rodar o Projeto

1. Clone este repositório para sua máquina local:
   ```bash
   git clone https://github.com/seu-usuario/localizacao.java.git
   ```

2. Navegue até o diretório do projeto:
   ```bash
   cd localizacao.java
   ```

3. Compile e execute o programa:
   Se você estiver utilizando o `javac` diretamente:
   ```bash
   javac Principal.java
   java Principal
   ```

   Se estiver usando um ambiente como IntelliJ IDEA ou Eclipse, basta rodar a classe `Principal.java`.

## Dependências

Este projeto depende da biblioteca [Gson](https://github.com/google/gson) para manipulação de JSON.

Para adicionar o Gson ao seu projeto, você pode baixar o JAR da [página oficial](https://mvnrepository.com/artifact/com.google.code.gson/gson) ou incluir no seu arquivo `pom.xml` (se estiver usando Maven):

```xml
<dependency>
    <groupId>com.google.code.gson</groupId>
    <artifactId>gson</artifactId>
    <version>2.8.8</version>
</dependency>
```

## Como Funciona

1. O usuário insere um **CEP**.
2. O sistema realiza a consulta à API **ViaCEP** para obter as informações do endereço.
3. O endereço é impresso na tela.
4. O sistema gera um arquivo `.json` com os dados obtidos do endereço, cujo nome será o próprio **CEP**.

### Exemplo de Saída

Se o CEP informado for `01001000`, o sistema pode gerar a seguinte saída:

```json
{
  "cep": "01001-000",
  "logradouro": "Praça da Sé",
  "complemento": "lado ímpar",
  "bairro": "Sé",
  "localidade": "São Paulo",
  "uf": "SP"
}
```

O arquivo gerado será chamado `01001000.json`.

## Erros Comuns

- **Erro de conexão**: Caso a API ViaCEP não esteja acessível, o sistema retornará uma mensagem indicando que não foi possível obter o endereço.
- **CEP inválido**: Se o CEP não for encontrado ou for inválido, uma mensagem de erro será exibida.

## Contribuindo

Se você quiser contribuir com melhorias, correções ou novos recursos, fique à vontade para enviar um **pull request**.

## Licença

Este projeto está licenciado sob a [MIT License](LICENSE).

---
