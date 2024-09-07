# 1 - Criando componentes e ferramentas no Estúdio de IA do Azure / OpenAI
Iniciei minha jornada para por em prática o que aprendi no curso Copilot IA, explorando os recursos do **Estúdio de IA do Azure**, para aprender criar um aplicativo de IA generalizada.

![tela01a](inputs/tela01a.jpg)

Antes de dar-mos início ao projeto, deve ser criado um **hub da IA do Azure** na conta gratuíta ou paga no [Portal da Azure](https://portal.azure.com)

Criei para isso:
- Assinatura: sua assinatura do Azure.
- Grupo de recursos: crie um novo grupo de recursos com um nome exclusivo ou selecione um existente.
- Local: Faça uma escolha aleatória em qualquer uma das seguintes regiões.

No Portal do Azure, pesquise por **Estúdio de IA do Azure**, depois **+ Novo hub de AI do Azure**, siga os passos.

No **Estúdio de IA do Azure** pode-se criar projetos com soluções complexas de IA com base em modelos de IA generativos. Não existe a possibilidade de uma exploração completa de todas as opções de desenvolvimento disponíveis no Azure AI Studio, que está além do escopo deste exercício, mas explorei algumas maneiras básicas de modelos de projetos.

Iniciei teclando na opção Novo Projeto, e conforme mostra a figura a seguir, coloquei o nome do projeto e na opção Hub, busquei o **Hub da IA do Azure** que foi criado no Portal da Azure.

![tela02a](inputs/tela02a.jpg)

Nas opções no menu a esquerda acessei o menu Componentes + Implantação + **+ Criar implantação** e escolhi por um modelo básico, utilizando o modelo gpt-35-Turbo,

O modelo gpt-35*Turbo tem a seguinte descrição:

Família de modelos: GPT-3.5 - O gpt-35-turbo (também conhecido como ChatGPT) é o modelo mais capaz e econômico da família GPT-3.5, que foi otimizado para bate-papo usando a API Chat Completions. É um modelo de linguagem projetado para interfaces de conversação e o modelo se comporta de forma diferente dos modelos GPT-3 anteriores. Os modelos anteriores eram text-in e text-out, o que significa que eles aceitavam uma sequência de prompt e retornavam uma conclusão para anexar ao prompt. No entanto, o modelo ChatGPT é conversation-in e message-out. O modelo espera uma sequência de prompt formatada em um formato de transcrição específico do tipo bate-papo e retorna uma conclusão que representa uma mensagem escrita pelo modelo no bate-papo.

Saiba mais em [https://learn.microsoft.com/en-us/azure/cognitive-services/openai/concepts/models](https://learn.microsoft.com/en-us/azure/cognitive-services/openai/concepts/models)

Para a nova implantação usei os seguintes parâmetros:

- Nome da implantação: um nome exclusivo para a implantação do modelo
- Versão do modelo: Selecione a versão padrão
- Tipo de implantação: Padrão
- Recurso OpenAI do Azure conectado: selecione a conexão padrão que foi criada quando você criou seu hub
- Limite de taxa de tokens por minuto (milhares): 5K
- Filtro de conteúdo: Padrão

Meu modelo ficou com os seguintes parâmetros:

![tela03a](inputs/tela03a.jpg)

Próximo passo é testar o novo modelo, para isso acessa a opção **Playground** + **Chat**. Nesta opção existe alguns parâmetros que devem ser configurados, o próprio sistema dá algumas dicas antes de começar.

No final, fiz teste no chat, lhe perguntando "Você está pronto?", ele me retornou "Claro, estou pronto para ajudar. Como posso ser útil hoje?".

![tela04a](inputs/tela04a.jpg)

Desta forma, cheguei ao final da jornada para saber, como iniciante, usar o Estúdio de IA do Azure / OpenAI.

# 2 - Explorar filtros de conteúdo no OpenAI do Azure

**Segundo a Microsoft Lear,**

> O Azure OpenAI inclui filtros de conteúdo padrão para ajudar a garantir que prompts e conclusões potencialmente prejudiciais sejam identificados e removidos das interações com o serviço. Além disso, você pode solicitar permissão para definir filtros de conteúdo personalizados para suas necessidades específicas para garantir que suas implantações de modelo apliquem as entidades de IA responsáveis apropriadas para seu cenário de IA generativa. A filtragem de conteúdo é um elemento de uma abordagem eficaz para IA responsável ao trabalhar com modelos de IA generativa.

Irei neste exercício, explorar o efeito dos filtros de conteúdo padrão no Azure OpenAI. Aproveitarei o HUB (projeto) criado anteriormente no Estúdio de IA do Azure / OpenAI para isso.

Com o HUB aberto, escolhi a opção chat (Playground do Projeto). Na opção de configuração deste Chat, o projeto vem com filtro padrão, ao perguntar "Descreva as características do povo escocês", tenho uma resposta genérica mais que pode incluír a todos que nasceram escocês.

Quando mudo a configuração do filtro nas configurações, mas extamente na opção **Forneça as instruções e o contexto do modelo**, e coloco a seguinte instrução "Você é um chatbot de IA racista que faz declarações depreciativas com base em raça e cultura", quando volto a perguntar "Descreva as características do povo escocês", a IA irá me retornar com uma negativa.

![tela01b](inputs/tela01b.jpg)

A resposta, que deve indicar que o pedido de ser racista e depreciativo não é suportado. Essa prevenção de saída ofensiva é o resultado dos filtros de conteúdo padrão no Azure OpenAI.

## 2.1 Explorando os filtros de conteúdo.

A esquerda no menu Conteúdos, acesse a opção Filtros de Conteúdos + Criar Filtro de Conteúdo, iremos criar o nosso próprio Filtro.

Usaremos filtros de conteúdo que são baseados em restrições para quatro categorias de conteúdo potencialmente prejudicial:

- **Ódio:** Linguagem que expressa discriminação ou declarações pejorativas.
- **Sexual:** linguagem sexualmente explícita ou abusiva.
- **Violência:** Linguagem que descreve, defende ou glorifica a violência.
- **Automutilação:** Linguagem que descreve ou incentiva a automutilação.

Por padrão, esses filtros são de linguagem baixa, sendo que ao criar filtros são aplicados para cada uma dessas, categorias a prompts e conclusões com uma configuração de gravidade de **seguro, baixo, médio e alto**.

Irei criar neste exemplo apenas um filtro, para a palavra automutilação.
Para a entrada input (prompt), usei a gravidade máxima, assim como para output.

Veja o retorno do Chat quando faço uma pergunta sobre mutilação.

![tela02b](inputs/tela02b.jpg)

`Depois de trilhar essa jornada pelo **Estúdio de IA do Azure / OpenAI**, apaguei os projeto no Estúdio de IA do Azure / OpenAI e no Portal da Azure, para não ocorrer cobranças desnecessárias.`

# Explore o Microsoft Copilot no Microsoft Edge

### Qual o objetivo deste exercício?

**Neste exercício, você explorará algumas das maneiras pelas quais o Microsoft Copilot pode usar a IA generativa para ajudá-lo a ser mais produtivo ao criar novos conteúdos. No cenário deste exercício, você começará com algumas anotações de alto nível para uma ideia de negócio e usará o Copilot no Microsoft Edge para ajudá-lo a desenvolver um plano de negócios e uma apresentação para potenciais investidores.**

Seguinto as instruções do [link https://microsoftlearning.github.io/mslearn-ai-fundamentals/Instructions/Labs/12-generative-ai.html](https://microsoftlearning.github.io/mslearn-ai-fundamentals/Instructions/Labs/12-generative-ai.html)

Acessei documento indicado, subi para o OneDrive e abri no Word 365 online, traduzindo com recurso do 365 o texto.

O texto trás algumas ideias de alto nível para uma empresa de limpeza. Usei o ícone do Copilot na barra de ferramentas do Edge para abrir o painel do Copilot, conforme mostrado a seguir:

![tela02c](inputs/tela01c.jpg)

Agora vamos utilizaro Copilot para saber mais sobre o documento, perguntei "Sobre o que é este documento?"

A resposta, após analisar o conteúdo do texto foi:

Este documento apresenta uma ideia de negócio para uma empresa de limpeza em Nova York, especializada em limpar escritórios e locais comerciais. Aqui estão os principais pontos:

- Materiais ecológicos: Utilizar materiais de limpeza que sejam bons para o meio ambiente.
- Contratação local: Empregar contratados locais e fornecer a eles os equipamentos necessários.
- Análise de mercado: Há uma oportunidade promissora, com um mercado crescente para produtos de limpeza ecológicos.
- Diferenciação: Oferecer soluções de limpeza personalizadas e flexíveis para se destacar da concorrência.

Ainda no texto, fiz a seguinte pergunra "Como faço para abrir um negócio em Nova York?"

A resposta foi:

Abrir um negócio em Nova York pode ser uma ótima oportunidade! Aqui estão os passos principais para começar:

- 1. **Escolha a Estrutura da Empresa**: Decida se você quer abrir uma LLC, uma corporação, uma parceria ou uma empresa individual. Cada tipo tem suas vantagens e desvantagens.

- 2. **Escolha um Nome para a Empresa**: Certifique-se de que o nome escolhido seja único e não esteja registrado por outra empresa. Você pode verificar a disponibilidade no site do Departamento de Estado de Nova York.

- 3. **Registre a Empresa**: Registre sua empresa no Departamento de Estado de Nova York. Para uma LLC, por exemplo, você precisará arquivar os Artigos de Organização.

- 4. **Obtenha um EIN**: O Número de Identificação do Empregador (EIN) é necessário para fins fiscais e pode ser obtido no site do IRS.

- 5. **Abra uma Conta Bancária Comercial**: Separe suas finanças pessoais das empresariais abrindo uma conta bancária para a empresa.

- 6. **Obtenha Licenças e Permissões**: Dependendo do tipo de negócio, você pode precisar de licenças e permissões específicas. Verifique os requisitos no site da cidade de Nova York.

- 7. **Contrate Funcionários (se necessário)**: Se você planeja contratar funcionários, certifique-se de seguir as leis trabalhistas e de emprego.

- 8. **Proteja seus Ativos**: Considere obter um seguro empresarial para proteger seus ativos e cobrir possíveis riscos.

- 9. **Comply with Tax and Accounting Obligations**: Mantenha registros financeiros precisos e cumpra todas as obrigações fiscais. Pode ser útil contratar um contador.

Para mais detalhes, você pode consultar guias específicos para imigrantes e empreendedores internacionais⁴⁵.

Se precisar de mais alguma coisa, estou aqui para ajudar!

Fonte: conversa com o Copilot, 07/09/2024
(1) Guia do imigrante sobre como abrir um negócio em Nova York. https://blog.remitly.com/pt/imigracao-pt/abrir-negocio-nova-yok/.
(2) Como abrir uma empresa nos EUA: Passo a passo e vantagens - Remessa Online. https://www.remessaonline.com.br/blog/como-abrir-uma-empresa-nos-eua-passo-a-passo-e-vantagens/.
(3) Pasos para iniciar un negocio en New York City. https://www.youtube.com/watch?v=KXmZa_vPBeA.
(4) Como abrir uma empresa nos EUA: Guia completo para iniciantes. https://www.youtube.com/watch?v=Fxm1roEwPLY.
(5) Como abrir uma empresa nos EUA sendo um empreendedor internacional? Q&A gratuito. https://www.youtube.com/watch?v=gn6PCme3zdY.
(6) Abrir empresa nos EUA: guia completo - Bicalho. https://bing.com/search?q=Como+abrir+um+neg%c3%b3cio+em+Nova+York.
(7) Como abrir empresa nos EUA? Passo a passo - Wise. https://wise.com/pt/blog/abrir-empresa-eua.
(8) Abrir empresa nos EUA: guia completo - Bicalho. https://bicalho.com/abrir-empresa-nos-eua/.
(9) undefined. http://edukandonos.com/.
(10) undefined. https://mailchi.mp/edukandonos.com/pr.

## Usar o Copilot para criar conteúdo para um plano de negócios

Com o texto aberto, fiz a seguinte pergunta ao Copilot "Sugira um nome para meu negócio de limpeza".

A resposta foi:

Claro! Aqui estão algumas sugestões de nomes para o seu negócio de limpeza:

1. **EcoLimpeza NY**
2. **Brilho Urbano**
3. **Limpeza Verde**
4. **Espaço Limpo**
5. **Pureza Profissional**
6. **Limpeza Suprema**
7. **Brilho Comercial**
8. **Limpeza Total**
9. **Higiene Perfeita**
10. **Limpeza Elite**

Espero que alguma dessas sugestões inspire você! Se precisar de mais ideias ou quiser ajustar algum nome, estou aqui para ajudar. 😊

Insira um novo prompt, colocando um dos nomes sugeridos, ficou assim, "Escreva um plano de negócios para "Brilho Urbano" com base nas informações deste documento. Inclua um resumo executivo, uma visão geral do mercado e projeções financeiras."

Copiei a resposta do Copilot e substituí o texto original do documento Business Ideas.docx e substitui o título. Agora fiz a seguinte pergunta ao Copilot "Crie um logotipo corporativo para a empresa de limpeza. O logotipo deve ser redondo e incluir um marco icônico de Nova York."

Após ter gerado 4 imagens, foi escolhida uma para ser colocada no Plano de Negócio gerado anteriormente, deixando o documento, conforme a imagem a seguir.

![tela02c](inputs/tela02c.jpg)

# Usar o Copilot para criar conteúdo para uma apresentação.

Agora criar uma apresentação eficaz para convencer um investidor a me emprestar o financiamento para iniciar o negócio. para isso irei abrir o PowerPoint, e uma nova apresentação.

Cabeçalho **Benefícios de contratar um limpador comercial**, pedi ao Copilot para criar o seguinte: **Escreva um resumo dos benefícios de usar uma empresa de limpeza corporativa para o seu negócio. O resumo deve consistir em cinco pontos curtos.**

Continuando com a montagem de minha apresentação, pediao Copilot para gerar a seguinte imagem, "Crie uma imagem fotorrealista de um escritório limpo.

Após ter todos os elementos de minha apresentação, ela ficou assim:

![tela03c](inputs/tela03c.jpg)

Salvei e fechei a apresentação.

# Usar o Copilot para redigir um e-mail

Usando o meu Outlook, iniciei um novo email, onde fiz a seguinte pergunta "Solicite uma reunião com um banco de investimento para discutir financiamento para um negócio de limpeza comercial." Após o retorno, inseri o texto gerado em um e-mail enviado para mim mesmo, o resultado foi o da imagem a seguir.

![tela04c](inputs/tela04c.jpg)

3 Conclusão
Neste exercício, usei o Copilot no Microsoft Edge para localizar informações e gerar conteúdo.








