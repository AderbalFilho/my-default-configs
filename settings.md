## Atributos do settings.json

Para a formatação dos arquivos costumo usar o `Prettier` (extensão do Code, `Prettier - Code formatter`). Ao selecioná-lo como opção padrão de formatação (feito quando fui formatar um arquivo com o atalho do Code `ctrl + shift+ i`) esse estrutura foi automaticamente colocada no meu arquivo.

```json
{
  "[javascript]": {
    "editor.defaultFormatter": "esbenp.prettier-vscode"
  }
}
```

Entretanto, o prettier só estava sendo usado quando se pedia a formatação ativamente, então também adicionei o comando:

```json
  "editor.formatOnSave": true
```

Logo assim que o arquivo seja salvo, também utilizará a formatação do prettier e economizando tempo com coisas como remoção de espaços em branco e adição de ponto e vírgula no final de comandos.

Outros comandos interessantes são os que ativam o zoom através do `ctrl + scroll` e o que deixa o tamanho padrão de identação para 2 espaços.

```json
  "editor.mouseWheelZoom": true,
  "editor.tabSize": 2
```

Essa configuração ajuda a encontrar as abas em que arquivos ainda não foram salvos.

```json
  "workbench.editor.highlightModifiedTabs": true
```

Está cansado daquela tela chata de boas-vindas do Code? existe uma configuração para eliminá-la.

```json
  "workbench.startupEditor": "none"
```

Como trabalho bastante com React, essa me é útil, na importação automática que normalmente me acontecia como `./component/index.js` agora será importado como `./component` somente. Existe a mesma configuração para TypeScript (só duplicar subsituindo o início por `typescript`).

```json
  "javascript.preferences.importModuleSpecifierEnding": "minimal",
  "typescript.preferences.importModuleSpecifierEnding": "minimal"
```

Já colocou uma declaração na regra CSS como `margin: 12px;`, esqueceu e botou outra mais abaixo `margin: 16px;` e depois ficou pirando vendo 16px de espaçamento na tela por não ter visto que a declaração foi sobreescrita? Adicione essas propriedades e você pelo menos será avisado (existe uma para o `less`, caso você utilize).

```json
  "css.lint.duplicateProperties": "warning",
  "scss.lint.duplicateProperties": "warning"
```

Às vezes é necessário colocar um `!important`, mas é sempre bom ter algo para lembrar de retirar aqueles que você só colocou como teste para poder retirar depois.

```json
  "css.lint.important": "warning",
  "scss.lint.important": "warning"
```

Já que não é necessário colocar a unidade no `0`, é bom ter algo para lembrar quando colocar sem querer.

```json
  "css.lint.zeroUnits": "warning",
  "scss.lint.zeroUnits": "warning"
```

O prettier estava colocando aspas duplas como o default para strings em JavaScript, então adicionei a regra abaixo para trocar por aspas simples.

```json
  "prettier.singleQuote": true,
```

## Formatações interessantes não adicionadas

Existem algumas que gostei bastante, porém nas as utilizei por conta do prettier já tratar delas ou por outras razões. Uma delas foi a abaixo, que formata durante o colar do código. Porém como já tenho a formatação no momento de salvar o arquivo, achei-a desnecessária para meu caso.

```json
  "editor.formatOnPaste": true
```

A adição da última linha em branco, remoção de linhas em branco (com exceção da última), remoção de espaçamentos extras, insersão dos `;` no final das declarações já me são feitas pelo prettier, então não vi necessidade de aplicá-las no VSCode.

```json
  "files.insertFinalNewline": true,
  "files.trimFinalNewlines": true,
  "files.trimTrailingWhitespace": true,
  "javascript.format.semicolons": "insert",
  "typescript.format.semicolons": "insert"
```

Mesmo colocando essas regras, elas seriam substituídas pelo meu `format on save` do prettier, mas caso não esteja usando o prettier e queira que as aspas simples sejam o padrão para strings, use as opções abaixo.

```json
  "javascript.preferences.quoteStyle": "single",
  "typescript.preferences.quoteStyle": "single"
```

Outra opção interessante é o número de abas que podem ficar visíveis no code. Mantive o default no exemplo, 9.

```json
  "explorer.openEditors.visible": 9
```
