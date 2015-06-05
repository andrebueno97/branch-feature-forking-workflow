# branch-feature-forking-workflow

Branch Feature Forking Workflow é uma mistura de Branch Feature Workflow com Forking Workflow.

Nova funcionalidade 

1. Primeira coisa devemos tirar um branch a partir da master no repositório oficial, isso pode ser feito inclusive pelo GitHub
![creating feature-1 branch](http://sc-cdn.scaleengine.net/i/a4338424388fdb37687dbf968097939f1.png)

2. Forke o projeto (caso você não tenha) 
![forking](http://sc-cdn.scaleengine.net/i/7da9034fb0a31dec0ef0b5c5c5e71dee.png)
![forkingTo](http://sc-cdn.scaleengine.net/i/321e1eb548cbd155f75ca969bf99ecbc.png)

3. Dado fork do projeto sob o seu usuário, você deve clonar seu o repositorio
```
git clone https://github.com/lfreneda/sample-bffw/
```

![clonning](http://sc-cdn.scaleengine.net/i/27a95a396b54a66fbc628e248d90560d.png)

4. é necessário também adicionar também uma referência para o repositorio official

```
git remote add official (endereco_repositorio_official)
```
![remoting](http://sc-cdn.scaleengine.net/i/91862c232dd14bc9b665376d1d2a4dc9.png)

5. Depois disso, voce deve criar sua branch de trabalho a partir da branch da funcionalidade (feature-1), vamos supor que uma das tasks para entregar a feature-1 é criar uma modelagem de classes, você então pode criar a branch feature-1-modelo-de-classes

![branching](http://sc-cdn.scaleengine.net/i/120af7bb5bf2668404b6bc335c4ad081.png)

Nesse momento nossas branchs estão com o ponteiro para o mesmo commit:

![graph-on-branching](http://sc-cdn.scaleengine.net/i/8e4fafeac8daff39819c2089dd57c638.png)

Vamos dizer que voce trabalhou nesse modelo de classes e após dois commits, voce já pode "integrar" essa task

git log

![history](http://sc-cdn.scaleengine.net/i/066996d969bf27788be46bb6d32aa88b.png)
![history-graph](http://sc-cdn.scaleengine.net/i/67bbdae1343a1a9a9e81317389b587a7.png)

Dado uma pequena contribuição "pronta", já é possível criar um pull request para o repositorio oficial. Para fazer isso é necessário empurrar suas alterações para seu repositorio

![1asdassda](http://sc-cdn.scaleengine.net/i/588eda2f950d81ebbf3040561a81110d.png)

Automaticamente ao acessar o repositorio do projeto voce vera ~Compare & pull request~

![compare-and-pull-request](http://sc-cdn.scaleengine.net/i/716240153e5b5d75564fc6dd52254434.png)

Importante lembrar que você deve selecionar como base fork a branch feature, no caso feature-1

![open-pull-request](http://sc-cdn.scaleengine.net/i/7bd847c3793d3bb34e9b0ad48126fd79.png)

Pull request criado, será avaliado pelo time.

Caso seja rejeitado, é necessário fechar o pull request, basicamente o que você tem que fazer é implementar as correções e criar outro pull request posteriormente.

Quando aceitar um pull request, aproveitar e deletar a branch remota com a alteração, isso é feito pelo botão "Delete branch"

![delete-branch](http://sc-cdn.scaleengine.net/i/ec4e5b2155d715702bb158d1a41b1b3f1.png)

Caso seja aceito, é necessário atualizar sua branch com as novas contribuções, na verdade, essa prática deve ser frequentemente feita pelos membros da equipe em suas branchs "interessadas". 

Grafico localmente antes de atualizar com as alteracoes do servidor

![graph-antes-atualizacao](http://sc-cdn.scaleengine.net/i/53ee710e0608dc430f1c4bad82ab3729.png)


(falar do prune)

![ci](http://sc-cdn.scaleengine.net/i/2d6e97349b042ccd48d2b33f6d529a20.png)

TA-DA :tada:

![graph](http://sc-cdn.scaleengine.net/i/917d3fd475bc4cf2cd582ba80599a86c.png)

Você também pode/deve limpar localmente as branchs que você ja integrou.

![branch-d](http://sc-cdn.scaleengine.net/i/b8089b83d3cd56f439393e685abe81c9.png)

Novas contribuições/pull requests serão feitos assim como o anterior, gerando uma arvore parecida com a seguinte:

![graph-2](http://sc-cdn.scaleengine.net/i/9ab852bdd2f3358e733ad41e3b1fad14.png)

Então, foram feitos 2 pull request para conclusão da feature-1, Dado que a feature já está pronta para ser coloca em produção, é possível fazer isso diretamente pelo GitHub

(efeito cascata)

![master-feature-1-pr](http://sc-cdn.scaleengine.net/i/c00a173a81e7bd1174d4a0ce690ffa57.png)

Done :)




