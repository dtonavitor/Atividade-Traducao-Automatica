# Atividade Tradução Automática

## 9.5.7. Exercícios
**1. Tente valores diferentes do argumento num_examples na funçãoload_data_nmt. Como isso afeta os tamanhos do vocabulário do idioma de origem e do idioma de destino?**

![image](https://github.com/user-attachments/assets/3998da5a-c62c-4b7f-b1ce-4133b58c21a0)
![image](https://github.com/user-attachments/assets/8c693d67-312b-40dd-aeb8-7e03e1ca8546)

Testes foram feitos com valores para num_examples entre 100 e 1000. Foi possível perceber que quanto maior o valor, maior são os tamanhos tanto do vocabulário de origem quanto de destino. Além  disso, conforme os valores aumentavam - principalmente a partir do 500, a diferença entre os vocabulários ficava cada vez maior, com o de destino sempre acima. 

**2. O texto em alguns idiomas, como chinês e japonês, não tem indicadores de limite de palavras (por exemplo, espaço). A tokenização em nível de palavra ainda é uma boa ideia para esses casos? Por que ou por que não?**

A tokenização em nível de palavra pode trazer diversos benefícios [1][2] como:
- Simplificação do Processamento: A tokenização em nível de palavra permite que o texto seja dividido em unidades menores, facilitando o processamento por modelos de tradução automática. Cada palavra é tratada como uma unidade separada, o que reduz a complexidade de lidar com frases completas.
- Preservação do Significado Semântico: Ao utilizar palavras como tokens, o modelo consegue capturar melhor o significado semântico de cada termo. Isso é especialmente útil para preservar o contexto de uma sentença, pois as palavras individuais retêm seus significados completos, em comparação com tokenizações mais finas, como de caracteres ou subpalavras, que podem fragmentar o significado.
- Redução da Ambiguidade: A tokenização em nível de palavra pode reduzir a ambiguidade na tradução, já que palavras inteiras são usadas como tokens. Isso permite ao modelo compreender melhor as nuances entre palavras que podem ter múltiplos significados, pois cada palavra está associada a um contexto.

Apesar do chinês e japonês não terem indicadores de limite de palavras, muitos estudos foram desenvolvidos para segmentação de palavras nestes idiomas. Por exemplo, NAKAGAWA [1] propõe uma abordagem híbrida que combina informações de nível de palavra e de caractere. Enquanto os dados em nível de palavra são eficazes para palavras conhecidas, o nível de caractere ajuda a lidar com palavras desconhecidas, melhorando a precisão da segmentação. Também existem modelos e outras técnicas para realizar esta segmentação, como o Spark NLP [3], segmentação de palavras com base em dicionário e por n-gramas [4]. Assim, ainda pode ser uma boa ideia utilizar a tokenização em nível de palavra mesmo para estes idiomas.

Referências:
[1] NAKAGAWA, Tetsuji. Chinese and Japanese word segmentation using word-level and character-level information. In: **COLING 2004: Proceedings of the 20th International Conference on Computational Linguistics**. 2004. p. 466-472.

[2] CHOI, Key-Sun et al. Word segmentation standard in Chinese, Japanese and Korean. In: **Proceedings of the 7th Workshop on Asian Language Resources (ALR7)**. 2009. p. 179-186.

[3] https://medium.com/john-snow-labs/tokenizing-asian-texts-into-words-with-word-segmentation-models-42e04d8e03da

[4] https://www.ibm.com/docs/pt/i/7.3?topic=processing-chinese-japanese-korean
