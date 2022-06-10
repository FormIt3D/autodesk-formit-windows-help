# Plug-in Mais propriedades

_Esse plug-in é uma versão mais completa da_ _**paleta Propriedades** padrão. Se você selecionar vários grupos e/ou tipos de geometria, esse plug-in fornecerá um detalhamento do que foi selecionado, além de permitir a renomeação em massa de grupos e instâncias de grupos._

1 **–**Primeiro, vamos examinar as propriedades de um grupo de portas do nosso modelo principal. Abra novamente o arquivo **Encode Campus Sample Model.axm** e volte para a cena **Nível dos olhos – Alameda longa**. Para começar a usar o plug-in **Mais Propriedades**:

1. Abra a **paleta Mais propriedades** clicando na propriedade com um ícone do símbolo “mais”.
2. Assegure-se de que a opção **Atualizar na alteração de seleção** esteja marcada.
3. Selecione um dos grupos de portas de vidro duplo, denominado **Porta**, à direita da alameda.
4. Na área **Contagem de seleção**, o **Total de objetos** nos informa que temos um (**1**) objeto selecionado.
5. Logo abaixo, podemos encontrar mais informações sobre quais tipos de objetos foram selecionados. Neste caso, há um (**1**) grupo selecionado, mas esse grupo tem quatro (**4**) instâncias em algum lugar do modelo.

![](<../../.gitbook/assets/10 (2) (1).png>)

_**Observação:**_ _A verificação do número de instâncias do grupo selecionado pode ser muito útil para evitar a alteração acidental de vários elementos quando você realmente só queria alterar o elemento selecionado, mas se esqueceu de torná-lo exclusivo._

2 – Esse plug-in nos permite editar um nome de instância do grupo ou nome do grupo sem ter que entrar no modo de edição de grupos, e renomear várias instâncias de uma só vez. Como mencionamos anteriormente, cada grupo tem um nome, mas cada instância desse grupo também pode ter um nome de “instância” exclusivo. Como provavelmente existem muitos tipos de portas neste modelo, queremos dar a este grupo, e a algumas de suas instâncias, nomes mais específicos.

1. Com o primeiro grupo de **Portas** de vidro ainda selecionado, adicione outro grupo de **Portas** à seleção atual mantendo pressionada a tecla **Shift** ou **Ctrl** e clicando uma vez no outro grupo de **Portas** de vidro duplo, próximo ao primeiro.
2. Observe que, agora, a **paleta Mais propriedades** atualizou sua **Contagem de seleção** para mostrar que existem duas (**2**) instâncias selecionadas, mas somente uma (**1**) **Família** única (também conhecida como grupo) selecionada. (Embora esse plug-in use o termo **Família**, que deve ser conhecido para os usuários do Revit, neste contexto ele significa o mesmo que um grupo do FormIt.)
3. Na área **Família de grupos**, atualize o campo **Nome** para **Portas – Vitrine de vidro duplo**. Isso atualizará o nome do grupo de nomes para todas as instâncias, independentemente de onde estejam localizadas ou se estão selecionadas no momento ou não, sem a necessidade de clicar duas vezes e editar o grupo.
4. Como essas duas instâncias são portas na área do letreiro “Groove Coffee”, vamos renomear apenas essas duas instâncias inserindo **Porta Groove Coffee** no campo **Nome**, na área **Várias instâncias de grupos**.

**Observação:** Na **paleta Propriedades** padrão, não é possível renomear várias instâncias de um grupo de uma só vez. Isso pode ser extremamente útil quando você deseja renomear dezenas ou centenas de instâncias com o mesmo nome de uma só vez.

![](<../../.gitbook/assets/11 (6) (1).png>)

_**Observação:**_ _Se você sair da paleta com o mouse, não poderá mais editar a caixa de texto selecionada. Isso ocorre com todas as paletas, portanto, certifique-se de manter o cursor dentro dos limites da paleta enquanto edita qualquer coisa em uma paleta._

3 – Agora, se você selecionar uma porta de vidro “Groove Coffee” ou uma porta de vidro diferente e observar suas propriedades na **paleta Propriedades**, verá que o nome do **Grupo** foi atualizado para cada instância, mas somente as portas “Groove Coffee” apresentam a propriedade **Nome** de instância atualizada em relação ao valor padrão.

![](<../../.gitbook/assets/12 (3) (1).png>)

4 – Por fim, vamos analisar como esse plug-in classifica diferentes tipos de elementos:

1. Desenhe rapidamente uma **Linha (L)**, um **Retângulo (R)** e um **Cubo (Alt + B)** em qualquer lugar do modelo. Esses desenhos serão temporários, portanto, a localização precisa não é importante.
2. Abra novamente a **paleta Mais propriedades** se ela estiver fechada e, em seguida, pressione **Ctrl + A** para selecionar todos os elementos visíveis no modelo.
3. Vá para a área **Contagem de seleção** e observe que os elementos selecionados estão separados em **Arestas** (linhas), **Faces**, **Corpos**, (formas 3D feitas de faces e arestas, como o cubo)**, ** **Grupos**, entre outros.

![](<../../.gitbook/assets/13 (3) (1).png>)

_**Observação:**_ _Esse plug-in também detecta_ _**Vértices**, que podem ser criados usando outro plug-in chamado_ _**Gerar vértice**. Se você quiser experimentar, instale o __**Plug-in Gerar vértice**__ e repita as etapas acima._
