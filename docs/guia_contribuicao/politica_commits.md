# Política de _Commits_

## Versionamento

| Versão |    Data    | Modificação                                 | Autor(es)                        |
|:------:|:----------:|---------------------------------------------|----------------------------------|
|   1.0  | 04/10/2023 | Criação do documento de política de commits | Lameque Fernandes e Ariel Vieira |

Os padrões de commits foram definidos pelo time, conforme o padrão [Conventional Commits](https://conventionalcommits.org/).

### Estrutura dos _Commits_

Cada mensagem de commit consiste em um **cabeçalho**, um **corpo** e um **rodapé**.

#### Cabeçalho

Tem um formato pré-definido, que inclui um **tipo** e um **título**:

```bash
  <tipo>(<escopo opcional>): <título>

  <corpo opcional>

  <rodapé opcional>
```

Exemplos:

```bash
  fix(integration-erp): fix error fetching customer data
  improve(app-toolbox): improves data search performance
  docs: add docker project start instructions
```

O **cabeçalho** é obrigatório.

Qualquer linha da mensagem do commit não pode ter mais de 48 caracteres! Assim fica mais fácil para ler no GitHub, Gitlab e outras ferramentas de git.

#### Tipo

Deve ser um dos seguintes:

* **build**: alterações que afetam o sistema de build ou dependências externas
* **static**: alterações no conteúdo de arquivos estáticos (dados .json, imagens, etc)
* **ci**: alterações em nossos arquivos e scripts de configuração de CI
* **cd**: alterações em nossos arquivos e scripts de configuração para CD
* **docs**: somente alterações na documentação
* **feat**: um novo recurso
* **fix**: uma correção de bug da aplicação
* **perf**: alteração de código que melhora o desempenho da aplicação e não altera a forma como o usuário utiliza a aplicação
* **refactor**: alteração de código, que não corrige um bug e nem altera a forma como o usuário utiliza a aplicação
* **improve**: alguma alteração de código que melhore o comportamento de um recurso
* **style**: alterações que não afetam o significado do código (espaço em branco, formatação, ponto e vírgula, etc)
* **test**: adicionando testes ausentes ou corrigindo testes existentes
* **revert**: reverter para um commit anterior

#### Título

O título contém uma descrição sucinta da mudança:

* use o imperativo, tempo presente: "change" ou "changes" não "changed" nem "changeover".
* não capitalize a primeira letra
* sem ponto (.) no final

#### Corpo

Um corpo de mensagem de commit mais longo PODE ser fornecido após o título, fornecendo informações contextuais adicionais sobre as alterações no código.

Configure a mensagem com um wrap de 80 caracteres

Use para explicar "o que" e "porque" foi realizado essa modificação, ao invés de "como".

O corpo DEVE começar depois de uma linha em branco após a descrição.

#### Rodapé

Um rodapé PODE ser fornecido depois de uma linha em branco após o corpo.

Caso possua uma issue vinculada, cria um referência assim: `fix #xxx ` ou `closes #xxx`.

O rodapé também pode ser utilizado quando o commit tiver múltiplos responsáveis com o seguinte formato:
  
```bash
  Co-authored-by: Nome <email@mail.com>
```

#### Reverter um commit

Se o commit reverte um commit anterior, ele deve começar por `revert:`, seguido pelo cabeçalho do commit revertido.

No corpo, ele deve dizer: `This reverts commit <hash>.`, onde o hash é o SHA do commit sendo revertido.

**Observações**

1. O _commits_ deve estar em inglês e ser sucinto e objetivo, representando claramente o que está sendo alterado naquele _commit_.

2. Um link precisa ser adicionado em sua forma mais autêntica, ou seja: sem encurtadores de link e links afiliados

3. O commit deve ser feito com o tipo mais adequado para o tipo de alteração realizada.

4. A descrição do commit deverá ser feitas no imperativo ao invés do pretérito ou gerúndio. Para auxiliar, a frase a seguir pode ajudar a elaborar a descrição do commit: "Se aplicado, esse commit <descrição>"
      1. Em inglês _If applied, this commit will <your subject line here\>_

      2. Aplicando o exemplo de um commit de criação de um novo módulo, a descrição deve ser: “create new module”.

### Pré-commits

Para garantir que os commits sigam o padrão definido, recomenda-se o uso do utilitário [Commitizen](https://commitizen-tools.github.io/commitizen/) como auxílio no processo de criação de commits.

Para instalar o Commitizen, execute o comando abaixo:

```bash
pip install --user -U Commitizen
```

Para utilizar o Commitizen, execute o comando abaixo:

```bash
cz commit
```

Para mais comandos para [integração com pré-commit](https://commitizen-tools.github.io/commitizen/getting_started/#integration-with-pre-commit) ou geração de [changelogs](https://commitizen-tools.github.io/commitizen/changelog/) consulte a documentação do Commitizen.