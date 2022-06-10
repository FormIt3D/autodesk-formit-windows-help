# Gerar luzes de sequência

_Neste capítulo, vamos dar exemplos de alguns dos plug-ins que vêm com o FormIt para fazer aprimoramentos no arquivo_ _**Encode Campus Sample Model.axm**. Se ainda não tiver feito isso, será possível fazer o download do arquivo do_ [_Conjunto de dados da Parte II do Manual do FormIt_](https://formit-help.s3.amazonaws.com/FormIt+Primer+Part+2+Datasets.zip)__

_Esse plug-in simples permite adicionar rapidamente luzes suspensas ao modelo com base em uma linha ou curva._

1 – Antes de adicionar novas luzes, vamos verificar o resultado pretendido através de uma cena predefinida no modelo.

1. Para ir para a cena que contém as luzes de sequências existentes, abra a **paleta Cenas** e clique duas vezes na cena denominada **Nível dos olhos – Alameda curta**.
2. Observe as luzes de sequências que vieram com esse modelo; é isso que vamos recriar, mas em outro lugar.
3. Na **paleta Camadas**, ative a camada **Geometria auxiliar** para que você possa ver as linhas originais usadas para gerar essas luzes de sequências.

![](<../../.gitbook/assets/3 (10).png>)

2 – Agora, vamos navegar para a outra alameda e adicionar algumas luzes. Na **paleta Cenas**, abra a cena **Nível dos olhos – Alameda longa**. Observe que essa alameda ainda não tem luzes de sequências.

3 – Para criar uma nova sequência de luzes:

1. Abra a paleta recém-instalada **Gerar luzes de sequências**, clicando no ícone de luzes de sequências. Por padrão, os ícones de novos plug-ins aparecem na parte inferior.
2. Altere a opção **Número de luminárias** para **10**.
3. Clique duas vezes em uma das linhas auxiliares para editar o grupo pré-criado **Luzes de sequências – Alameda longa**. Em seguida, clique uma vez em uma das linhas auxiliares pré-desenhadas para selecioná-la.
4. Clique no botão **Gerar luzes de sequências**, na paleta do plug-in, e uma nova sequência de luzes deve aparecer. Observe que cada sequência de luzes é criada como um grupo próprio exclusivo.

![](<../../.gitbook/assets/4 (6) (1).png>)

_**Observação:**_ _Não tem problema se algumas linhas passarem pelo letreiro “Groove Coffee”, pois o plug-in de luzes de sequências cria uma curva de catenária que se ajusta de forma realista por baixo do letreiro._

4 – Tente criar mais algumas luzes de sequências usando a outra linha auxiliar predefinida e/ou criando suas próprias linhas auxiliares. Explore as configurações do plug-in para obter resultados diferentes.

5 – Para ajudar a manter o modelo organizado, quando terminar, recomendamos agrupar todas as linhas auxiliares e colocar esse grupo na camada **Geometria auxiliar**, bem como atribuir todos os grupos de luzes de sequências à camada **Contexto – Iluminação externa**. Isso vai impedir que as linhas auxiliares apareçam em qualquer uma das cenas de “Nível dos olhos” onde não queremos vê-las. Quando estiver concluído, os resultados devem ser semelhantes à próxima captura de tela.

![](<../../.gitbook/assets/5 (3) (1).png>)

_**Observação:**_ _Ao contrário da geometria criada com um script do Dynamo, que pode ser atualizada e regenerada através da_ _**paleta Propriedades**, os objetos criados por um plug-in são (na maioria dos casos) apenas geometria regular do FormIt. Uma vez criados, eles só podem ser editados com as ferramentas de modelagem integradas do FormIt._
