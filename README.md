# Questões Teóricas

### 1 - O que é Git?
Git trata-se de um sistema de versionamento, com função de ser usado pelos desenvolvedores para versionamento de códigos, gerando históricos e documentações de melhorias, correções e listas de afazeres de um determinado projeto.

### 2 - O que é a staging area?
Staging Area se refere à arquivos que foram adicionados pelo comando git add, estando estes prontos para serem expostos ao comando git commit.

### 3 - O que é o working directory?
Working Directory trata-se do local onde o git está observando os arquivos e diretórios em busca de mudanças.

### 4 - O que é um commit?
Um commit é um salvamento do seu working directory atual que pode ser usado como ponto de retorno caso seja o desejo do desenvolvedor.

### 5 - O que é uma branch?
Uma branch (galho) trata-se de um ramo criado por um desenvolvedor dentro da árvore, onde ele pode trabalhar sem se preocupar com uma possível danificação do código no repositório principal.

### 6 - O que é o head no Git?
O Head trata-se de um ponteiro que pode estar apontando para um branch ou um commit.

### 7 - O que é um merge?
Merge é um procedimento em que se unem dois branches específicos em um só.

### 8 - Explique os 4 estados de um arquivo no Git.
Untracked significa que o arquivo não está sendo observado pelo git, unmodified significa que ele está sendo observado e está atualizado, modified significa que ele está sendo observado mas não está atualizado, e staged é um estado em que ele está pronto para ser commitado.

### 9 - Explique o comando git init.
Git init inicia um repositório git local.

### 10 - Explique o comando git add.
Git add coloca os arquivos especificados no modo staged.

### 11 - Explique o comando git status.
Git status mostra detalhes dos arquivos do repositório local.

### 12 - Explique o comando git commit.
Git commit realiza o commit do seu branch atual, fazendo uma espécie de snapshot do estado do seu código.

### 13 - Explique o comando git log.
Git log mostra todos os históricos de commits realizados até então.

### 14 - Explique o comando git checkout -b.
Git checkout -b cria uma branch nova e já muda para ela.

### 15 - Explique o comando git reset e suas três opções.

**SOFT:** Move apenas o ponteiro HEAD para um outro commit especificado, não alterando a área de stage ou o working directory.

**MIXED (padrão):** Além de mover o ponteiro HEAD, faz com que a área de stage contenha o mesmo snapshot do commit para o qual o ponteiro HEAD foi movido, porém não afeta o diretório de working. Essa opção de reset é mais drástica que a opção soft, porém, como o diretório de working não é modificado, as versões mais recentes dos arquivos não são perdidas e podem ser adicionadas à área de stage e comitados novamente.

**HARD:** Não apenas descarta as alterações na área de stage como também reverte todas as alterações no diretório de working para o estado do commit que foi especificado no comando. O ponteiro HEAD será movido para o commit anterior e as áreas de stage e working serão revertidas para o mesmo estado do commit apontado pelo HEAD. Como todas as alterações recentes, comitadas ou não, são perdidas, essa opção só deve ser executada se houver um bom motivo para tal.

### 16 - Explique o comando git revert.
O comando git revert pode ser considerado um comando do tipo "desfazer"; no entanto, ele não é uma operação tradicional de desfazer. Em vez de remover o commit do histórico do projeto, ele descobre como inverter as alterações introduzidas pelo commit e anexa um commit novo com o conteúdo resultante. Assim, ele evita que o Git perca o histórico, o que é importante para a integridade do histórico de revisão e para uma colaboração confiável.

### 17 - Explique o comando git clone.
Git clone copia um repositório remoto para o repositório local do usuário.

### 18 - Explique o comando git push.
Git push envia os arquivos que foram commitados do repositório local para o repositório remoto.

### 19 - Explique o comando git pull.
Git pull serve para buscar e baixar conteúdo de repositórios remotos e fazer a atualização imediata ao repositório local para que os conteúdos sejam iguais.

### 20 - Como ignorar o versionamento de arquivos no Git?
Basta criarmos um arquivo de nome .gitignore e especificarmos quais arquivos não serão enviados para o repositório remoto.

### 21 - No terralab utilizamos as branches master ou main, develop e staging. Explique o objetivo de cada uma.
Main seria a branch principal, onde temos o código funcional em alguma proporção, recebendo uma numeração como v 1.0.2. Develop seria a branch de desenvolvimento, onde diversos desenvolvedores incrementam novas funções e corrigem bugs de uma determinada aplicação. Staging trata-se de um estado onde diversos testes serão aplicados nos códigos que estão em fase Develop, para que estes possam ser incrementados na branch main sem problemas.

# Questões Práticas

### 1 - A essa altura, você já deve ter criado a sua conta do GitLab, não é? Crie um repositório público na sua conta, que vai se chamar Atividade Prática e por fim sincronize esse repositório em sua máquina local.

### 2 - Dentro do seu reposotorio, crie um arquivo chamado README.md e leia o artigo como fazer um readme.md bonitão e deixe esse README.md abaixo bem bonitão: README.md onde o trainne irá continuamente responder as perguntas em formas de commit. 

Inserção de código, exemplo de commit de feature. 

### 3 - Crie nesse repositório um arquivo que vai se chamar calculadora.js, abra esse arquivo em seu editor de códigos favoritos e adicione o seguinte código:


const args = process.argv.slice(2);
console.log(parseInt(args[0]) + parseInt(args[1]));

Descubra o que esse código faz através de pesquisas na internet, também descubra como executar um código em javascript e dado que o nome do nosso arquivo é calculadora.js e você entendeu o que o código faz, escreva abaixo como executar esse código em seu terminal:

**RESPOSTA:** O código em questão recebe 2 números a partir de uma command line e os soma. A forma como precisei fazer para ele funcionar foi o seguinte:
1- Instalar o NodeJS.
2- No Visual Code (minha IDE de escolha), instalar a extensão Code Run.
3- Na aba de TERMINAL do Visual Code, você irá executar a ação de soma com o seguinte comando: node calculadora.js 3 9
O resultado será a soma dos 2 argumentos, ou seja a soma de 3 e 9 que é igual a 12.

### 4 - Agora que você já tem um código feito e a resposta aqui, você precisa subir isso para seu repositório. Sem usar git add . descubra como adicionar apenas um arquivo ao seu histórico de commit e adicione calculadora.js a ele.	

**RESPOSTA:** Basta adicionarmos o nome do arquivo individualmente em vez de usar add ponto; dessa forma: git add calculadora.js

### 5 - Copie e cole o código abaixo em sua calculadora.js:

```js
const soma = () => {
    console.log(parseInt(args[0]) + parseInt(args[1]));
};

const args = process.argv.slice(2);

soma();
```

Descubra o que essa mudança representa em relação ao conventional commit e faça o devido commit dessa mudança. 

**RESPOSTA**: Trata-se de um commit refactor. Ele ocorre quando quaisquer mudanças que atinjam o código, porém não alterem sua funcionalidade.

### 6 - João entrou em seu repositório e o deixou da seguinte maneira:

```js
const soma = () => {
    console.log(parseInt(args[0]) + parseInt(args[1]));
};

const sub = () => {
    console.log(parseInt(args[0]) - parseInt(args[1]));  
}

const args = process.argv.slice(2);

switch (args[0]) {
    case 'soma':
        soma();
    break;

    case 'sub':
        sub();
    break;

    default:
        console.log('does not support', arg[0]);
}
```
Depois disso, realizou um git add . 
e um commit com a mensagem: "Feature: added subtraction"
faça como ele e descubra como executar o seu novo código.

Nesse código, temos um pequeno erro, encontre-o e corrija 
para que a soma e subtração funcionem.

Por fim, commit sua mudança.

**RESPOSTA**: O código foi corrigido na calculadora.js; o erro estava na numeração dos args das funções de soma e sub, além de na linha 21 estar escrito arg[0] em vez de args[0].
Exemplo de execução por terminal: node .\calculadora.js sub 19 10
OUTPUT: 9
O commit **feature** foi realizado com a nova funcionalidade.

### 7 - Por causa de joãozinho, você foi obrigado a fazer correções na sua branch principal! O produto foi pro saco e a empresa perdeu muito dinheiro porque não conseguiu fazer as suas contas, graças a isso o seu chefe ficou bem bravo e mandou você dar um jeito disso nunca acontecer. Aprenda a criar uma branch, e desenvolva a feature de divisão nessa branch. 

**RESPOSTA:** Para criar uma branch nova (e já mudar para ela imediatamente), podemos usar o comando: git checkout -b dev1
Isso irá criar uma branch nova de nome dev1.
Foi adicionado o commit com a feature no repositório remoto.

### 8 - Agora que a sua divisão está funcionando e você garantiu que não afetou as outras funções, você está apto a fazer um merge request. Em seu gitlab, descubra como realizá-lo de acordo com o gitflow.

**RESPOSTA:** Basta acessarmos a aba de BRANCHES, selecionar a branch dev1, onde um botão de MERGE REQUEST estará disponível. A branch dev1 será deletado por padrão, e ela se unirá com a main, trazendo suas atualizações para a main.

### 9 - João quis se redimir dos pecados e fez uma melhoria em seu código, mas ainda assim, continuou fazendo um push na master, faça a seguinte alteração no código e fez o commit com a mensagem: "refactor: calculator abstraction"

var x = args[0];
var y = args[2];
var operator = args[1];

function evaluate(param1, param2, operator) {
  return eval(param1 + operator + param2);
}

if ( console.log( evaluate(x, y, operator) ) ) {}

Para piorar a situação, joão não te contou como executar esse novo código, enquanto você não descobre como executá-lo lendo o código, 
e seu chefe não descobriu que tudo está comprometido, faça um revert 
através do seu gitlab para que o produto volte ao normal o quanto antes!

**RESPOSTA:** Revert feito com sucesso. Joãozinho doido das ideia.

### 10 - Descubra como executar esse novo código e que operações ele é capaz de realizar. Deixe sua resposta aqui, e explique o que essas funções javascript fazem.

**RESPOSTA:** O novo código deixa a operação mais intuitiva, agora no terminal é preciso escrever, por exemplo: node .\calculadora.js 8 - 3
OUTPUT: 5
Ele faz a operação de acordo com o sinal digitado entre os números.

Foi usado eval. A função eval converte uma string em código javascript. Ou seja, ela convereterá a expressão matemática que foi passada através do args para código.

### COMENTÁRIOS DO USUÁRIO:
Eu depois acabei percebendo que cometi o mesmo erro de João e desenvolvi o código através da branch main, em vez de criar a minha própria como foi feito em um dos exercícios. Beginner's mistake. 🤡