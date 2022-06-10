# Controle de versão

À medida que você desenvolve e atualiza o plug-in, em algum momento, pode ser necessário criar uma versão do código.

Por exemplo, as APIs do FormIt podem mudar entre versões e, embora você queira que a nova versão do plug-in use novas APIs do FormIt ou do WSM, também gostaria de manter o plug-in funcionando em clientes mais antigos.

A partir do FormIt **v18.0**, é possível implementar o controle de versão para o plug-in em três etapas simples:

* Adicione um arquivo _versions.json_ à raiz do diretório de plug-in
* Especifique cada versão compatível do FormIt e o diretório que contém esses arquivos de plug-in, em _versions.json_
* Use o número de versão interna do FormIt (ou “Número de compilação”), encontrado no FormIt em Informações > Sobre.



### Como organizar o controle de versão para o plug-in

Organize os arquivos de plug-in e diretórios para que correspondam a _versions.json_

O arquivo _versions.json_ deve ter esta aparência:

```
        [
            {
                "version":{
                    "major":18,
                    "minor":0
                },
                "path":"v18_0"
            },
            {
                "version":{
                    "major":19,
                    "minor":1
                },
                "path":"v19_0"
            }
        ]

```

Os caminhos acima _v18\_0_ e _v19\_0_ devem ser subcaminhos válidos da raiz do diretório/repositório.

![](../../../.gitbook/assets/i1.png)

![](../../../.gitbook/assets/i2.png)

![](../../../.gitbook/assets/i3.png)

Uma ótima maneira de lidar com isso é mover o código do plug-in para subdiretórios. Usando o arquivo _versions.json_ acima, uma estrutura de diretórios seria semelhante a esta:

* **versions.json** (arquivo)
* **v18\_0** (diretório)

   * **manifest.json** (arquivo)
   * **plugin.html** (arquivo)
   * **plugin.js** (arquivo)


* **v19\_0** (diretório)
   * **manifest.json** (arquivo)
   * **plugin.html** (arquivo)
   * **plugin.js** (arquivo)

As propriedades opcionais na versão são “exactVersion” e “lastVersion”. “exactVersion” indica que a versão deve coincidir exatamente com a versão do FormIt. “lastVersion” indica a última versão com execução permitida no FormIt.\


```
[
    {
      "version":{
        "major":18,
        "minor":0,
        "exactVersion":true
        },
        "path":"v18_0"
    },
    {
        "version":{
            "major":19,
            "minor":1,
            "lastVersion":true
       },
        "path":"v19_0"
    }
 ]
```

Também é possível usar ramificações/identificadores/confirmações de git para os caminhos.

Se você estiver trabalhando com uma versão de pré-lançamento ou beta do FormIt e desejar testar as alterações em um plug-in que só funciona com a versão de pré-lançamento:

* Siga as etapas acima, exceto usando o nome de arquivo _versions\_prerelease.json_
* Se você confirmar _versions\_prerrelease_ para o repositório, será conveniente removê-lo quando a versão de pré-lançamento do FormIt for liberada
   * Caso contrário, as versões futuras do FormIt de pré-lançamento carregarão o plug-in de um local que pode ser obsoleto ou destinado a uma versão anterior
