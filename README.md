# Guia
Esse é um guia simples para rodar o a ferramenta [CYBERSORTx](https://cibersortx.stanford.edu/) via web.

Referência: [NEWMAN, et al. Determining cell type abundance and expression from bulk tissues with digital cytometry. 2019](https://pubmed.ncbi.nlm.nih.gov/31061481/).

## Sobre a ferramenta
O CIBERSORTx é uma ferramenta analítica capaz de imputar perfis de expressão gênica e fornecer uma estimativa das abundâncias dos tipos celulares presentes em uma determinada amostra, utilizando dados de expressão gênica.

## Como posso acessar?
Para fazer análises no [CYBERSORTx](https://cibersortx.stanford.edu/), é necessário criar um login de acesso no site. De forma geral, a liberação do login pode demorar alguns dias.

## Como começo a fazer as análises?
Para iniciar uma análise, basta acessar a página com seu login e escolher a opção **Run CIBERSORTx** na aba **Menu**.

Com isso, três módulos são apresentados a você.
### Módulo 1- Create Signature Matrix
O Módulo 1 corresponde a criação de matrizes de assinatura as quais você pode usar para inferir as frações celulares ou expressão celular nos outros dois módulos.

Para criar a matriz, é preciso informar qual o tipo de dado de expressão (RNAseq, Single-cell RNAseq, Microarray) para qual a matriz será gerada, além de fazer o upload de dois arquivos diferentes:
  1. Arquivo referência: Tabela dos perfis de expressão gênica das populações celulares referência que serão comparadas entre si. É usada para definir as possíveis classes de fenótipo para gerar o arquivo de genes de assinatura personalizado.
  2. Arquivo de fenótipos: Tabela contendo as classes de tipos de células que serão usadas para definir as classes no arquivo de genes de assinatura.

**Para rodar um exemplo, basta escolher a opção** ``` Example``` **e escolher qualquer uma das opções de teste.**

### Módulo 2- Impute Cells fractions
O Módulo 2 nos permite fazer a inferência das frações celulares presentes em uma amostra.

Para fazer esse tipo de análise são necessários dois arquivos:
  1. Matriz de assinatura: A matriz de assinatura é o dado que irá permitir a identificação do perfil celular presente em uma determinada amostra. Neste campo é possível escolher a matriz gerada pelo usário no Módulo 1 ou escolher entre diversas opções pré definidas pela ferramenta (Exemplo: Matriz LM22- 22 tipos imunes celulares).
  2. Arquivo Mixture: Matriz de expressão a qual será utilizada para imputar as frações celulares. A normalização da matriz de expressão deve estar preferencialmente em FPKM (fragments per kilobase of transcript per million reads mapped);

**Para rodar um exemplo, basta escolher a opção** ``` Example``` **e escolher qualquer uma das opções de teste.**

### Módulo 3- Impute Cells Expression
Por fim, o ultímo módulo nos permite identificar quais dos grupos celulares, qual o grau de expressão de cada um, Eles podendo ser agrupados ou serem apresentados a nível amostral.

Para fazer esse tipo de análise são necessários quatro arquivos:
  1. Matriz de assinatura (Explicado a cima)
  2. Arquivo Mixture (Explicado a cima)
  3. Arquivo de classe agrupado- Um arquivo que relabels the phenotypes in your signature matrix according to broader phenotype
  4. Ground truth file (optional)- A file with known gene expression profiles for your cells of interest. Serves for quality control.

**Para rodar um exemplo, basta escolher a opção** ``` Example``` **e escolher qualquer uma das opções de teste.**
