Project developed by Luisa M. G. Mathias and Viviane Stephane P. Novo
Related to the subject Algorithms and Data Structures II - DCA3702 of the Computer Engineering course at UFRN 

# Mapping Collaborations in UFRN's Construction Projects  
 
Contents:
- [Codes](MapeamentoObras.ipynb)
- [Presentation](https://docs.google.com/presentation/d/1DPJ_Fv4ufiEgTYoCXmXclyYn9xEiloEIkCwlD2f7X4Y/edit?slide=id.g381ad9c41c8_0_15#slide=id.g381ad9c41c8_0_15)
- [Database](obras.csv)

## Data Collection and Processing
Based on the project's basic instructions, we used the UFRN [Open Data](https://dados.ufrn.br/) platform to collect information about collaborations between UFRN and companies, and their construction expenses, available in the [‘obras.csv’](obras.csv) file.

We chose to process the data using [Google Colab](https://colab.research.google.com/drive/1oHqfsGKtL39q291jTq_kwXw40K2NQbwQ?usp=sharing#scrollTo=_PaTwJ3MdaGq). Starting with importing the necessary libraries and their respective necessary installations, we imported the csv file and began processing the data, performing the following:

1 - Analyzing the first lines of the dataset and checking the names and types of columns
2 - Evaluating the consistency and standardization of the data
3 - Then, we identified that the file contains 12 well-defined columns, including:

empresa
unidade_responsavel
valor
status_obra
Which will be fundamental for building the graph-based analysis network.
Furthermore, other libraries were also used in the creation of the graph, namely:
aslo
networkx
matplotlib.pyplot
itertools
plotly.graph_object
