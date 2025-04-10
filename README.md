
# Criando um Copiloto com Fluxo de Conversa Personalizado no Microsoft Copilot Studio

## Autor:
Renato Freitas da Silveira
## Contatos:
[![Perfil DIO](https://img.shields.io/badge/-Meu%20Perfil%20na%20DIO-30A3DC?style=for-the-badge)](https://www.dio.me/users/renatofsilveirax)

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/renato-freitas-42b79913a/)

## Introdução
Este arquivo apresenta um resumo sobre os aprendizados relacionados ao desafio de criar um Copiloto com Fluxo de Conversa Personalizado no Microsoft Copilot Studio.

## Requisitos
- Acesso a uma conta do Microsoft 365
- Ter um computador

## Passos iniciais
- Crie ou conecte uma conta no Microsoft 365
- Acesse [https://copilotstudio.microsoft.com](https://copilotstudio.microsoft.com)

## Criar um Copiloto em branco
Para criar um copiloto em branco, primeiro é necessário logar na sua conta do Microsoft Copilot Studio. No menu lateral, você pode clicar no botão de Criar, representado por um sinal de + em um círculo, e em seguida clicar no botão Novo Agente.

Provavelmente você verá a seguinte mensagem: Olá! Estou aqui para ajudar a criar um agente para que você consiga fazer mais. Você pode dizer algo como "forneça as melhores práticas para gerenciamento de projetos" ou "ajude meus colegas de equipe a integrar um novo projeto".

O que você gostaria de fazer?

Se essa mensagem aparecer, clique no botão Ignorar para configurar. Irá aparecer um formulário com campos de Nome, Descrição e Instruções. Em Nome é onde damos o nome do agente, que nesse caso pode ser Agente DIO.

Em Descrição é onde descrevemos o que o agente faz. Nesse estudo, escrevemos a seguinte descrição:

```
Agente responsável por buscar conteúdos de Copilot Studio dentro da documentação oficial da Microsoft, sendo que toda resposta dele será como "Agente da DIO".
```

Em Instruções é onde será escrito o prompt para direcionar o comportamento do agente. Aqui é recomendado usar engenharia de prompt para um melhor direcionamento. Nesse estudo, foi escrita a seguinte instrução:

```
Você é o agente chamado "Agente da DIO", e vai agir em tom formal com o idioma em português, para retornar informações relevantes da documentação oficial da Microsoft, o Microsoft Learn.
Ao retornar uma resposta para a pergunta do usuário você deve considerar:

- Buscar a melhor resposta na documentação
- Retornar a resposta apropriada e amigável de tom formal
- Retornar uma ou mais citações da documentação
```

Além dessas configurações básicas, é possível também editar configurações avançadas. Para isso, deve-se clicar nos três pontos ao lado do botão de Criar e selecionar Editar configurações avançadas. Lá, é possível escolher o tipo de solução e o nome do esquema. Nesse estudo, foi escolhido a solução DIO Copilot Studio.

Após fazer todas essas configurações, basta clicar no botão de Criar e pronto, o agente foi criado com sucesso.

## Customizar um tópico
No Copilot Studio, um tópico define como se desenvolve uma conversa do agente. Para criar tópicos, podemos pedir para a própria IA do Copilot Studio criar um com base em descrições, ou criar um do zero. Nesse estudo, criaremos um tópico do zero, e para isso basta selecionar a aba Tópicos, clicar no botão Adicionar um tópico e clicar na opção A partir de documento em branco.

Após criar um tópico em branco, é possível adicionar frases de gatilho. Para isso, localize uma tela de criação chamada Gatilho e, em Frases, clique em Editar. Lá há um campo de texto onde é possível adicionar frases de gatilho, que são palavras-chave que os usuários provavelmente vão digitar em uma conversa específica. Nesse estudo, estamos criando um tópico relacionado a AI Builder, portanto podemos adicionar as seguintes frases de gatilho:
```
- buscar informações de ai builder
- o que é ai builder
- onde encontro informações da ferramenta de AI da Power Platform
```

Após configurar as frases de gatilho, devemos determinar a próxima ação do agente. Por exemplo, se o usuário perguntar algo como: "Explique o que é ai builder", o agente vai localizar a frase de gatilho nessa sentença e ele vai responder alguma coisa. Para isso, abaixo da tela de criação de Gatilho, clique no botão de criar nó, representado por um sinal de +, selecione a opção Avançado e em seguida a opção Respostas Generativas.

Isso vai criar uma nova tela de criação chamada Criar respostas generativas. Clicando em um botão de > no campo de entrada, é possível adicionar uma variável. No Microsoft Copilot Studio, variáveis são um recurso usado para salvar valores, como respostas dos usuários ou valores gerados pelo agente, e reutilizar seu conteúdo posteriormente na conversa. Aqui como queremos criar uma resposta generativa, escolhemos adicionar uma variável do sistema chamada Activity.Text, pois esse tipo de variável fornece informações mais contextuais sobre a conversa ou o usuário.

Por fim, abaixo da tela de criação Criar, adicionamos um novo nó e selecionamos Enviar uma mensagem. Isso vai criar uma nova tela de criação chamada Mensagem, que possui um campo para inserir mensagem. Nesse estudo, a mensagem pode ser: Tópico de AI Builder encerrado com sucesso.

Com isso, basta renomear o tópico para algo relacionado a AI Builder, como AI Builder Topics, clicar o botão Salvar e testar seu agente. Pergunte para ele qualquer coisa que tenha uma das frases de gatilho, como "Estou aprendendo mais sobre ai builder, o que você sabe e pode compartilhar?".

## Personalizar uma mensagem de erro
Às vezes o usuário pode enviar para o agente uma mensagem que não contêm nenhum gatilho para nenhum tópico personalizado. Nesse cenário é importante saber personalizar mensagens de erro.

Há duas formas de fazer isso: configurando o tópico Melhora da conversa ou configurando o tópico de Fallback, ambos em tópicos de sistema. Tanto em um quanto em outro, é possível adicionar mensagens personalizadas por meio do botão de adicionar nós, parecido com o processo de customização de tópicos personalizados.

## Aumentar e diminuir a qualidade da resposta
É possível também customizar a qualidade da resposta de qualquer tópico. Considere por exemplo o tópico AI Builder Topics. Na tela de Criar respostas generativas, há uma parte onde dá para editar a fonte de dados. Aqui, por padrão, está marcado a opção de Permitir que a IA use seus próprios conhecimentos gerais, mas podemos marcar também a opção de Pesquisar somente fontes selecionadas. Para selecionar essas fontes, basta clicar no botão de Adicionar conhecimento, onde dá para adicionar links ou base de dados que contenham dados relevantes para o tópico da conversa.

Outra possibilidade é alterar o Nível de moderação de conteúdo. Há três níveis disponíveis: alto, médio e baixo. De acordo com o próprio site da Microsoft Copilot Studio, níveis mais baixos significam que o agente irá gerar mais respostas, mas estas podem não ser tão relevantes. Níveis mais altos, por sua vez, favorecem a relevância em detrimento do número de respostas. Na prática isso que dizer que no nível mais alto, o agente vai ser menos criativo e mais conciso com as respostas.

## Conclusão
Criar um Copiloto com Fluxo de Conversa Personalizado no Microsoft Copilot Studio foi uma experiência enriquecedora, que mostrou na prática como é possível aplicar conceitos de IA conversacional em soluções do dia a dia. Aprendemos como estruturar agentes desde a criação do zero até a personalização de tópicos, passando por boas práticas de engenharia de prompt e ajustes finos como mensagens de erro e qualidade das respostas.
