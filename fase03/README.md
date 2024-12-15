# Fine Tuning foundation models
Este projeto teve como objetivo realizar o fine-tuning de diferentes foundation models para comparar seu desempenho em diversos aspectos. Os critérios de avaliação utilizados foram:
- Precisão: Capacidade do modelo de fornecer respostas relevantes e corretas no contexto da tarefa.
- Eficiência no treinamento: Tempo e recursos necessários para concluir o processo de fine-tuning.
- Custo operacional: Custos associados ao treinamento e ao uso dos modelos ajustados.
- Flexibilidade: Capacidade do modelo de se adaptar a diferentes cenários e tarefas.

## Estrutura de pastas e conteúdos
- [x] colab: Arquivos fontes para serem utilizados no colab.
- [x] dados: Arquivos de treinamento já no formato do foundation model.
- [x] resultados: Planilha contendo os testes comparativos realizados

## Etapas do Projeto:
### Preparação dos dados
Os resultados dos testes iniciais com os primeiros modelos treinados foram insatisfatórios, apresentando respostas muitas vezes desconexas, chegando a algo próximo do delírio. Para melhorar a qualidade do treinamento, o grupo decidiu explorar mais a fundo os dados e aplicar filtros que priorizassem conteúdos representativos de livros. A seleção foi guiada por palavras-chave como "author" e "copyright", buscando controlar melhor o ambiente de treinamento, seguindo o princípio de "garbage in, garbage out".

A curadoria dos dados foi realizada com base nos seguintes critérios:

- Remoção de Dados Incompletos: Eliminação de linhas com valores nulos nos campos **Title** ou **Content**.
- Filtro por Soma de Tokens: Seleção de linhas onde a soma de tokens entre **Title** e **Content** fosse igual ou superior a 257.
- Filtro por Palavras-Chave: Manutenção de linhas que contivessem as palavras "copyright" ou "author" em **Title** ou **Content**.
- Divisão do Conjunto de Dados: Uso das primeiras 1500 linhas para treinamento e das 500 linhas subsequentes para teste.
- Critérios de Tamanho: Seleção de linhas em que:
  - Title contivesse mais de 40 caracteres.
  - Content contivesse mais de 400 caracteres.

> [!NOTE]
> Em especial para o treinamento do GPT4 foi necessário considerar a quantidade máxima de tokens, por isso o filtro de até 256 tokens.

![](imagens/visao_geral_tokens.png) | ![](imagens/exemplos_max_256_tokens.png)

Com essas melhorias na seleção dos dados, buscou-se criar um conjunto de treinamento mais consistente e representativo, aumentando as chances de sucesso nos modelos subsequentes.




### Comparação das estruturas dos dados de treinamento
### Configuração do fine-tuning
### Resultados