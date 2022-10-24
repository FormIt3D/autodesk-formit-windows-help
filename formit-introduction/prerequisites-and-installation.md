# Pré-requisitos e instalação

## Download e instalação

* Faça o download do [FormIt para Windows](https://formit.autodesk.com/page/download) mais recente.
* Use a Autodesk Account para entrar ou [crie uma Autodesk Account gratuita aqui](https://accounts.autodesk.com).
* O complemento do FormIt para Revit está incluído no Revit 2017 e em versões mais recentes. Também é possível pode fazer o download e instalar manualmente o complemento [em nosso site](https://formit.autodesk.com/page/formit-revit).

As configurações a nível do aplicativo para o FormIt estão localizadas em Computer\\HKEY_CURRENT_USER\\SOFTWARE\\Autodesk\\FormIt 360\\

## Configuração recomendada do sistema

| Requisito                    | Detalhes                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
| ------------------------------ | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Sistema operacional**           | <p>Microsoft® Windows® 8, 8.1, 10 ou 11.</p><p><em>Observação: O Parallels Desktop não é oficialmente suportado devido a problemas de desempenho e gráficos degradados nos drivers OpenGL.</em></p>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
| **CPU**                        | <p>Processador Intel® Pentium®, Xeon® ou i-Series ou o AMD® equivalente com tecnologia SSE2.</p><p>É recomendada a maior taxa de velocidade de CPU possível.</p>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
| **Memória**                     | 4 GB de RAM no mínimo, 8 GB ou mais recomendados.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            |
| **Placa de vídeo (GPU)**           | <p>É necessária uma placa de vídeo NVIDIA ou AMD separada que suporte o OpenGL 3.3. O suporte para OpenGL 4.2 é altamente recomendado.</p><p>Para sistemas com placas gráficas comutáveis, siga as instruções do fabricante para garantir que o FormIt sempre use a GPU dedicada a fim de obter o melhor desempenho. Consulte as instruções para <a href="https://www.amd.com/en/support/kb/faq/dh-017">AMD </a>e <a href="http://nvidia.custhelp.com/app/answers/detail/a_id/2615/kw/manage%203d%20settings/related/1">NVIDIA</a>.</p><p>Para obter melhor desempenho e confiabilidade, verifique se os drivers da placa gráfica estão atualizados no site do fabricante ou no Windows Update.</p><p>O FormIt mostrará uma mensagem na inicialização se não for possível usar a placa de vídeo devido a drivers desatualizados ou outros problemas. Se o FormIt não for iniciado após a atualização de drivers, <a href="https://forums.autodesk.com/t5/formit-forum/bd-p/142">entre em contato nos fóruns</a>.</p> |
| **Espaço em disco**                 | 1 GB de espaço livre em disco.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
| **Conectividade e licenciamento** | <p>É necessária uma conexão com a Internet quando o FormIt for iniciado pela primeira vez, para entrar na Autodesk Account.</p><p>Uma conexão com a Internet também é necessária para carregar plug-ins ao iniciar o FormIt. Se não for detectada conexão com a Internet durante a inicialização, o aplicativo será iniciado sem plug-ins.</p><p>Uma Autodesk Account com uma assinatura da nuvem do FormIt Pro é necessária para executar o FormIt Pro no Windows. O FormIt Pro está disponível como parte da <a href="https://www.autodesk.com/collections/architecture-engineering-construction/overview"><strong>Autodesk AEC Collection</strong></a>.</p>                                                                                                                                                                                                                                                                                                   |

## Acesso off-line

Quando você executa o FormIt para Windows pela primeira vez, é necessário estar conectado à Internet para que a licença possa ser validada. Após o primeiro login, será possível usar o aplicativo off-line por 30 dias. Depois disso, você precisará estar on-line para validar a licença novamente.

Ao usar o FormIt para Windows off-line, algumas funcionalidades serão limitadas:

* A ferramenta Configurar localização não funcionará, pois requer uma conexão com a Internet para recuperar dados de satélite e terreno do Bing Maps.
  * No entanto, qualquer satélite e terreno existente que já esteja no modelo de uma sessão on-line anterior permanecerá.
* Os plug-ins, incluindo o Gerenciador de plug-ins, não serão carregados, pois obtêm o código mais recente do GitHub em cada inicialização do aplicativo.
  * Solução alternativa: Se você carregar todos os plug-ins enquanto estiver on-line e mantiver a sessão do FormIt em execução quando estiver off-line, os plug-ins que foram carregados anteriormente permanecerão e funcionarão normalmente.
* Os materiais de amostra não serão carregados, pois eles vêm de um servidor hospedado na nuvem.
  * Solução: Navegue até as pastas de categoria de materiais de amostra enquanto estiver conectado à Internet. As pastas são obtidas por download e armazenadas no computador e podem ser acessadas posteriormente quando off-line.
* Não será possível salvar ou abrir no Autodesk Docs, incluindo da Biblioteca de conteúdo.

## Configurações de DPI recomendadas do Windows

O FormIt para Windows funciona melhor quando a tela de exibição está definida para dimensionamento de DPI de 125% ou menos no Windows.

É possível alterar isso no Windows 10 com o seguinte procedimento:

* Pesquise “Exibir” no menu Iniciar e escolha “Alterar configurações de exibição”
* Selecione o retângulo que representa o monitor que você usará com o FormIt
* Na seção “Escala e layout”, abra o menu suspenso “Tamanho do texto, aplicativos e outros itens” e selecione um valor de 125% ou menos

## Solução de problemas

### Erro de sistema do Windows 10 Pro N

Se você estiver executando o FormIt no Windows 10 Pro N versão 1909 ou posterior, talvez veja esta mensagem de erro:

![FormIt.exe System Error on Windows 10](<../.gitbook/assets/windows 10 error message.png>)

Isso se deve a um problema conhecido com determinadas versões do Windows 10 Pro N. Para evitar esse erro, faça o download do pacote de recursos de mídia da versão do Windows 10 aqui: [Lista de pacotes de recursos de mídia para edições do Windows N](https://support.microsoft.com/en-us/topic/media-feature-pack-list-for-windows-n-editions-c1c6fffa-d052-8338-7a79-a4bb980a700a).

### Não é possível entrar

Quando você tentar entrar na conta no FormIt, a caixa de diálogo de login poderá travar, impedindo que você continue. Se isso ocorrer, talvez seja necessário desbloquear *.autodesk.com no firewall de rede. Entre em contato com o departamento de TI para obter suporte.
