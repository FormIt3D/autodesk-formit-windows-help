---
description: >-
  Start a BIM workflow by evaluating the performance of elements from the
  beginning of the design process.
---

# Análise solar + de energia

![](<../.gitbook/assets/20220317 Solar Analysis.png>)

## Análise de energia no FormIt

Analise o modelo de construção para obter eficiência energética no início do processo de projeto.

[Visualizar os projetos do Insight](https://gbs.autodesk.com/OneEnergy/Insight)

## Análise de energia com o Insight

Com uma assinatura do **FormIt Pro** por meio da [AEC Collection](https://www.autodesk.com.br/collections/architecture-engineering-construction/overview), você tem acesso à Análise de energia com o **Insight**:

* Analise os modelos de projeto nos estágios iniciais com o mecanismo de análise do Green Building Studio
* Conecte-se a uma vista de painel dos resultados da análise para comparar as opções do projeto
* Ajuste os widgets do fator de análise de energia, como proporção da janela para a parede, orientação do edifício e outros
* Resuma o impacto da energia da construção com um único número calculado como um custo de resultado final por área
* Salve os resultados da análise de energia para revisão futura com clientes e outras partes interessadas

## Novidades do FormIt + Insight <a href="#insight-what-s-new" id="insight-what-s-new"></a>

### **Aprimoramentos na confiabilidade do Insight** <a href="#improvements-to-insight-reliability" id="improvements-to-insight-reliability"></a>

* O [FormIt 2021](https://formit.autodesk.com/blog/post/introducing-formit-2021) agora verifica o modelo para identificar problemas comuns antes de iniciar as execuções do Insight e corrige falhas comuns do Insight para oferecer uma experiência mais confiável.
* O FormIt 2021 também melhora de forma geral a confiabilidade da conexão FormIt + Insight, resolvendo muitas falhas conhecidas e melhorando as taxas de sucesso de execução.

## Guia de Introdução <a href="#insight-getting-started" id="insight-getting-started"></a>

### **Funcionamento** <a href="#how-it-works" id="how-it-works"></a>

* A análise de energia do Insight carrega os dados do modelo do FormIt e executa várias centenas de análises na nuvem para determinar várias pontuações de energia
* A análise de energia usa o Revit para analisar o modelo. Quando você envia dados do FormIt para o Revit, é necessário [garantir que o modelo do FormIt seja vedado e múltiplo](https://formit.autodesk.com/blog/post/repairing-solid-models)

### **Preparar o modelo do FormIt** <a href="#preparing-your-formit-model" id="preparing-your-formit-model"></a>

* O Insight usa qualquer geometria visível no esboço do FormIt
   * Assegure-se de que a casca da construção que você deseja analisar seja a única geometria visível
   * Coloque a geometria de suporte, como o ambiente, o mobiliário e os elementos do terreno em uma [Camada](../tool-library/layers.md) separada e desative a Camada
* O Insight funciona melhor com um modelo de construção simples e sólido
   * Assegure-se de que a massa da construção seja [sólida e vedada](https://formit.autodesk.com/blog/post/repairing-solid-models)
   * Se o projeto de construção já tiver aberturas para janelas e portas, será melhor criar uma nova massa sem aberturas específicas para a Análise de energia e ocultar a versão mais detalhada usando Camadas
* A massa de construção simples precisa ter [Níveis](../tool-library/levels-and-area.md) aplicados
* O modelo do FormIt precisa ter uma [Localização](../tool-library/setting-location.md) definida

![](../.gitbook/assets/insight.png)

### **Iniciar a análise de energia** <a href="#starting-energy-analysis" id="starting-energy-analysis"></a>

* Procure o botão Análise de energia na barra de ferramentas

![](../.gitbook/assets/generate\_insight.png)

* Clique em “Gerar Insight” para iniciar o processo
* Isso carregará os dados do modelo visíveis e executará várias centenas de simulações na nuvem
* Quando o processo estiver concluído, uma mensagem será exibida na parte superior da tela e o menu será atualizado para indicar que um novo Insight está pronto para ser visualizado
   * Clique em “Visualizar Insight” para visualizar a análise no navegador da Web
   * Também é possível encontrar todas as análises do Insight no [Autodesk Insight](https://gbs.autodesk.com/OneEnergy/Insight).

## Solução de problemas <a href="#insight-troubleshooting" id="insight-troubleshooting"></a>

### **Erros comuns** <a href="#common-errors" id="common-errors"></a>

* “Não foi possível criar o projeto do Insight. Tente novamente mais tarde.”
   * Faça login no [painel do Green Building Studio](https://gbs.autodesk.com/GBS/Project) e reinicie o FormIt
      * Se você não conseguir efetuar login ou se aparecer uma página de “acesso negado”, talvez seja necessário [adquirir uma assinatura do Green Building Studio](https://knowledge.autodesk.com/search-result/caas/CloudHelp/cloudhelp/ENU/BPA-Help/files/GUID-7FCFF904-F943-4020-BF7F-53AA7148673D-htm.html)
   * Verifique se o modelo é [sólido e vedado](https://formit.autodesk.com/blog/post/repairing-solid-models)
   * Verifique se há problemas com os serviços do FormIt no [Autodesk Health Dashboard](https://health.autodesk.com/)
* Para verificar se o Green Building Studio executou com êxito a Análise de energia para este projeto, consulte o [painel do Green Building Studio](https://gbs.autodesk.com/GBS/Project)
   * O projeto mais recente deve aparecer na parte superior da lista e deve exibir 248 execuções
   * Se for exibido 0 execuções, [informe-nos nos fóruns do FormIt](https://forums.autodesk.com/t5/formit-forum/bd-p/142) para podermos ajudar a solucionar os problemas

### **Registros detalhados** <a href="#detailed-logs" id="detailed-logs"></a>

* O FormIt para Web fornece detalhes adicionais quando a análise de energia falha:
   * Acesse [FormIt para Web](https://formit.autodesk.com/app)
   * Abra o modelo que apresenta problemas com a análise de energia
   * Execute análise de energia
   * Abra as Ferramentas do desenvolvedor (pressione F12 no Google Chrome ou no Firefox)
   * Consulte a guia Console
   * Copie ou faça uma captura de tela de qualquer erro para [informar sobre o problema nos fóruns do FormIt](https://forums.autodesk.com/t5/formit-forum/bd-p/142)

## Análise de luz solar

Com uma assinatura do **FormIt Pro** por meio do [AEC Collection](https://www.autodesk.com.br/collections/architecture-engineering-construction/overview), é possível visualizar o impacto solar em sua construção:

* Especifique faces relevantes a serem analisadas quanto ao impacto solar
* Visualize os resultados em segundos na tela do aplicativo
* Passe o mouse sobre um ponto de entrada para ver os valores calculados específicos do impacto solar
* Escolha visualizar os resultados como um estudo de vidraça mensal ou como um estudo de viabilidade anual do painel solar

Saiba mais sobre a [Análise solar](../tool-library/solar-analysis.md) no FormIt Pro.
