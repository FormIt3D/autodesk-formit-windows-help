# Plug-in Gerenciar câmeras

_Neste capítulo, vamos dar exemplos de alguns dos plug-ins que vêm com o FormIt para fazer aprimoramentos no arquivo_ _**Encode Campus Sample Model.axm**. Se ainda não tiver feito isso, será possível fazer o download do arquivo do_ [_Conjunto de dados da Parte II do Manual do FormIt_](https://formit-help.s3.amazonaws.com/FormIt+Primer+Part+2+Datasets.zip)__

Ao longo do manual, usamos cenas como ferramentas valiosas para navegar e controlar a visibilidade em todo o modelo. Esse plug-in nos permite ver e editar a elevação da nossa câmera atual, exportar câmeras para cada cena como objetos 3D e copiar essas cenas entre modelos.

1 – Primeiro, vamos ajustar a cena **Nível dos olhos – Alameda longa** para que a câmera esteja realmente ao nível dos olhos:

1. Se ainda não estiver, volte para a cena **Nível dos olhos – Alameda longa** clicando duas vezes nela dentro da **paleta Cenas**.
2. Abra a **paleta Gerenciar câmeras** clicando na câmera com um ícone de engrenagem.
3. Altere a **Altura acima do solo** para **5’-8"**.

![](<../../.gitbook/assets/6 (6) (1).png>)

_**Observação:**_ _Se o modelo tiver níveis, esse plug-in também mostrará a altura acima do nível mais próximo abaixo da_ _**Câmera principal**._

2 – Em seguida:

1. Volte para a **paleta Cenas**.
2. Assegure-se de que a cena **Nível dos olhos – Alameda longa** ainda esteja selecionada (caso contrário, clique uma vez para selecioná-la).
3. Clique no botão **Atualizar cena** para salvar a nova altura da câmera nessa cena.

![](<../../.gitbook/assets/7 (1) (1).png>)

_**Observação:**_ _Também é possível ajustar o ângulo e a posição da câmera de uma cena alternando o botão_ _**Editar câmeras de cena**_ _na parte superior da_ _**paleta Cenas**_ _(entre os botões atualizar e reproduzir)._

3 – Em seguida, vamos exportar as nossas cenas para um novo modelo. Primeiro, temos que criar objetos de câmera para todas as cenas que usam o plug-in **Gerenciar câmeras**:

1. Abra novamente a **paleta Gerenciar câmeras**.
2. Verifique se a opção **Copiar câmeras para a área de transferência** está marcada.
3. Clique no botão **Exportar cenas para câmeras**. Isso pode demorar alguns segundos.
4. Se toda a tela ficou branca, é porque a **Câmera principal** foi alinhada com uma das câmeras da cena. **Diminua o zoom (Z)** até que você possa ver os três edifícios principais e os objetos de câmera recém-criados. Observe que os objetos de câmera são automaticamente colocados em um grupo grande denominado **Câmeras**. Dentro desse grupo, cada câmera individual é colocada em seu próprio grupo com o mesmo nome da cena com base na qual foi criada.

![](<../../.gitbook/assets/8 (7) (1).png>)

4 – Vamos copiar essas cenas para um novo modelo. Como os dados das câmeras foram salvos na área de transferência, não há muito a fazer:

1. **Salve** **(Ctrl + S)** o modelo atual e feche-o.
2. Inicie um novo esboço vazio selecionando **Novo esboço (Ctrl + N)** no menu suspenso **Arquivo**, na barra do **Menu principal**.
3. Abra o plug-in **Gerenciar câmeras**, se ele ainda não estiver aberto, e assegure-se de que a opção **Procurar câmeras na área de transferência** esteja marcada.
4. Clique no botão **Importar cenas de câmeras**, perto da parte inferior do plug-in, e as cenas do nosso outro modelo serão importadas. Para verificar, abra a **paleta Cenas** e/ou ative a camada **Câmera**. Você verá que todas as cenas e os objetos de câmera 3D foram importados para esse modelo.

![](<../../.gitbook/assets/9 (7) (1).png>)
