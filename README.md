## Criando meu próprio repositório e aumentando ainda mais meu portfólio de projetos no GitHub.

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






