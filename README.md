Project developed by Luisa M. G. Mathias and Viviane Stephane P. Novo
Related to the subject Algorithms and Data Structures II - DCA3702 of the Computer Engineering course at UFRN 

# Mapping Collaborations in UFRN's Construction Projects  
 
Contents:
- [Codes](MapeamentoObras.ipynb)
- [Presentation](https://docs.google.com/presentation/d/1DPJ_Fv4ufiEgTYoCXmXclyYn9xEiloEIkCwlD2f7X4Y/edit?slide=id.g381ad9c41c8_0_15#slide=id.g381ad9c41c8_0_15)
- [Database](obras.csv)

## Data Collection and Processing
Based on the project's basic instructions, we used the UFRN [Open Data](https://dados.ufrn.br/) platform to collect information about collaborations between UFRN and companies, and their construction expenses, available in the [‘obras.csv’](obras.csv) file.

We chose to process the data using [Google Colab](https://colab.research.google.com/drive/1oHqfsGKtL39q291jTq_kwXw40K2NQbwQ?usp=sharing#scrollTo=_PaTwJ3MdaGq). 
Starting with importing the necessary libraries and their respective necessary installations, we imported the csv file and began processing the data, performing the following:

1 - Analyzing the first lines of the dataset and checking the names and types of columns

2 - Evaluating the consistency and standardization of the data

3 - Then, we identified that the file contains 12 well-defined columns, including:

   - empresa
   - unidade_responsavel
   - valor
   - status_obra

This will be fundamental for building the graph-based analysis network.

Furthermore, some of the libraries used in the creation of the graph were:
   
   - networkx
   - plotly
   - itertools
   - matplotlib.pyplot

## The archive's head 
```
id_obra                                          descricao  \
0      478  CONSTRUÇÃO DO BLOCO H DO SETOR DE AULAS TEÓRIC...   
1      521  CONSTRUÇÃO DO BLOCO A1 DO SETOR DE AULAS TEÓRI...   
2      925  Complementação da 2ª Etapa e Realização da 3ª ...   
3      493  CONSTRUÇÃO DO BLOCO H DO SETOR DE AULAS TEÓRIC...   
4      848  CONSTRUÇÃO DO SETOR DE ANTIBIÓTICOS PRODUÇÃO D...   

                   periodo  qtd_dias status_obra licitacao  \
0  23/03/2005 - 19/11/2005       240  FINALIZADA    5/2004   
1  04/05/2005 - 30/12/2005       240  FINALIZADA    7/2004   
2  28/01/2005 - 22/01/2006       360  FINALIZADA    2/2004   
3  23/03/2005 - 19/11/2005       240  FINALIZADA    6/2004   
4  02/06/2005 - 29/01/2006       240  FINALIZADA    4/2004   

                                             empresa    modalidade  \
0   03.166.687/0001-28 - CRS-CONSTRUÇÕES E EMPREE...  CONCORRÊNCIA   
1   03.166.687/0001-28 - CRS-CONSTRUÇÕES E EMPREE...  CONCORRÊNCIA   
2   40.761.454/0001-08 - AR PROJETOS & CONSTRUÇÕE...  CONCORRÊNCIA   
3   03.166.687/0001-28 - CRS-CONSTRUÇÕES E EMPREE...  CONCORRÊNCIA   
4        03.722.669/0001-85 - CONSTRUTORA CAGEO LTDA  CONCORRÊNCIA   

                 valor                        fonte_recurso  \
0  R$       847.582,26  APLICACOES FINANCEIRAS (0280154215)   
1  R$       833.702,12                                  NaN   
2  R$       814.550,74                                  NaN   
3  R$       829.454,21                                  NaN   
4  R$     1.561.230,93      TESOURO - EDUCAÇÃO (0112000000)   

          vigencia_projeto                           projeto  \
0                      NaN                               NaN   
1  20/04/2005 - 20/11/2005          19O ENECIC/2005 (852005)   
2  20/12/2002 - 31/07/2007  UFRN/CONV.133/02 - HUOL (862003)   
3                      NaN                               NaN   
4                      NaN                               NaN   

   id_unidade_responsavel                             unidade_responsavel  
0                     NaN                                             NaN  
1                     NaN                                             NaN  
2                   446.0             HOSPITAL UNIVERSITÁRIO ONOFRE LOPES  
3                     NaN                                             NaN  
4                   252.0  NUCLEO DE PESQUISA EM ALIMENTOS E MEDICAMENTOS
```
```
Colunas:
Index(['id_obra', 'descricao', 'periodo', 'qtd_dias', 'status_obra',
       'licitacao', 'empresa', 'modalidade', 'valor', 'fonte_recurso',
       'vigencia_projeto', 'projeto', 'id_unidade_responsavel',
       'unidade_responsavel', 'valor_float'], dtype='object')
```

## Problem definition
> How can we understand the complex network of collaboration between construction companies and UFRN units in the execution of its projects?

