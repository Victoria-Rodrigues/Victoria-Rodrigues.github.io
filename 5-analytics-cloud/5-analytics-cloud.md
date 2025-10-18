# Oracle Analytics Cloud

## Introdução

>**O Oracle Analytics Cloud - OAC aprimora as análises dos seus dados através das funcionalidades estatísticas e IA, com sugestões de visualizações que enriquecem o seu Painel Analítico.** 

O OAC complementa a plataforma de Self-Service Analytics e conta com o motor de Business Intelligence proveniente do OBIEE, que permite construção de Modelos Dimensionais, Hierarquias e outras estruturas que otimizam o consumo dos dados, em Relatórios e Dashboards.

A filosofia da solução gira ao redor dos conceitos de Augmented Analytics, tema muito recorrente em análises de companhias especializadas, como o Gartner. Ele se resume em enriquecer as análises com conceitos de Inteligência Artificial e Machine Learning, dando acesso a abordagens estatísticas avançadas para qualquer perfil de usuário e não apenas aos que possuem vasto conhecimento sobre o tema. Nossa solução é classificada como **‘Líder’ no Quadrante Mágico do Gartner**, principal referência para avaliação e comparação de tecnologias hoje em dia.

<br>
### **Objetivos**

O objetivo deste workshop é demonstrar de forma prática como utilizar a ferramenta do Oracle Analytics Cloud e algumas funcionalidade de AI&ML embarcadas no OAC. Durante o workshop, você aprenderá a criar visualizações, adicionar estatísticas nas análises em um cenário que dados abertos da Marinha Brasileira (https://dados.gov.br/dados/conjuntos-dados/embarcacoes).

<br>
### **Recursos e Suporte**:

- **Documentação da Oracle Cloud**: [Getting started with Oracle Analytics Cloud](https://docs.oracle.com/en/cloud/paas/analytics-cloud/index.html)
- **Tutoriais**: [Oracle Analytics Cloud - Explore Funcionalidades com Tutoriais](https://docs.oracle.com/en/cloud/paas/analytics-cloud/tutorials.html)


### _**Aproveite sua experiência na Oracle Cloud!**_


## 1️⃣ Acessar OAC 

1. Clique no menu de hambúrger do canto superior esquerdo da tela, na sequência navegue até a página de gestão do Oracle Analytics Cloud.
   ![Analytics Cloud Acess](images/AcessoOAC.png)

2. Selecione a instância do OAC criada anteriormente. Verifique se a Região e o Compartimento estão certos.
   ![Analytics Cloud Homepage](images/OCI-Analytics.png)

3. Agora abra o ambiente clique no botão **Analytics Homepage**.
   ![Analytics Cloud Homepage](images/AcessoOAC1.png)
   ![Analytics Cloud Homepage](images/AcessoOAC2.png)


<br>

4. Após o acesso da Homepage do OAC, **faça o download do arquivo .dva** com o material do laboratório: [Painel das Embarcações Brasileiras](https://objectstorage.us-ashburn-1.oraclecloud.com/n/idi1o0a010nx/b/Fast_Track/o/Lab%20Analytics%20-%20Embarca%C3%A7%C3%B5es%20Brasil.dva)

5. Em seguida, clique nos 3 pontos, ao lado do ícone do perfil. Selecione **'Import Workbook'**.
   ![Import do Arquivo](images/Import1.png)

6. Escolha o arquivo .dva que acabou de baixar no passo 3, para importar.
   ![Import do Arquivo](images/Import2.png)
   ![Import do Arquivo](images/Import3.png)

7. Altere o idioma da ferramenta, clique no Ícone do Perfil, selecione Perfil. Depois só escolher o Idioma e a Configuração Regional do OAC para o desejado. 
   ![Perfil - Idioma](images/Perfil.png)
   ![Perfil - Idioma](images/Perfil2.png)

8. (OPCIONAL) Após a importação você terá acesso ao dataset (Conjunto de Dados) **Brasil-Embarcações** e ao workbook que vamos fazer, se quiser dar uma olhada como ele vai ficar no final só entrar nele **Lab Analytics - Embarcações Brasil**. 
   ![Homepage depois do import](images/Import4.png)

## 2️⃣ Criação do Dashboard - Visualizações

1. Na Homepage do OAC, selecione o Menu de Hamburguer (Canto Superior Esquerdo), Selecione Dados e a Aba Conjunto de Dados (Dataset).
![Homepage - Conjunto de Dados](images/Dataset.png)

2. Selcione **Brasil-Embarcações**. Irá abrir o workbook (Pasta de Trabalho), uma tele em branco para montar o Painel com análises e visualizações. 
![Painel com Conjunto de Dados selecionado](images/Workbook2.png)

3. Na tela em branco do painel, selecione os dados da primeira coluna da esquerda, segurando o **_CTRL+Clique_  Quantidade, Latitude, Longitude**. Agora, **arraste** os itens selecionados **para a Tela** e como sugestão o OAC já sugere que a visualização seja um Mapa.
![Visualização Mapa](images/Workbook3.png)

4. Dentro da Segunda Coluna, na gramática da visualização coloque o campo **QUANTIDADE** na caixa 'Tamanho'. E selecione o campo **ESTADO** e arraste ele ele dentro da caixa 'Cor'.
![Visualização Mapa](images/Workbook4.png)

5. (OPCIONAL) Altere a propriedade para personalizar o mapa. Na segunda coluna onde fica a gramática e a propriedade do gráfico, selecione o ícone superior de propriedades e vá até ícone de mapa na segunda linha. Altere a propriedade do Mapa, em cada ícone da segunda linha tem acesso a um tipo de personalização da visualização. 
![Propriedades Visualização](images/Workbook5.png)

6. (OPCIONAL) Deixe no modo que achar mais agradável, para continuar vou deixar no modo Dark/Escuro do Mapa.
![Propriedades Visualização](images/Workbook6.png)

7. Crie um gráfico de Barras. Selecione o campos desejados na coluna da esquerda onde fica os dados, segurando o _CTRL+Clique_  **Estado e Quantidade**. Agora, arraste os itens selecionados para a Tela, ao lado do Mapa, aparece uma faixa verde na posição onde a visualização vai ficar. 
![Gráfico de Barra](images/Barra1.png)

8. Para ordenar os dados do gráfico selecione o ícone com uma seta para cima e outra para baixo, como mostrado na imagem. E então selecione a forma que deseja ordenar os dados. 
![Ordenar Dados](images/Ordenar1.png)
![Ordenar Dados](images/Ordenar2.png)
![Ordenar Dados](images/Ordenar3.png)

9. Salve seu trabalho até agora. Selecione o ícone do disquete no campo direito superior. Dê um nome para o seu Painel e salve. 
![Salvar Painel](images/Save.png)

## 3️⃣ Adição de Estatística nas Visualizações

1. Adicione estatísticas como: _Previsão, Linha de Tendência, Linha de Referência, Outliers ou Cluster_. 
<br> Selecione a visualização que deseja adiconar estatística. Clique com o _botão direito_, selecione **Adionar Estatísticas**. E escolha a opção **Outliers**, trará os pontos que destoam do grupo. 
   ![Estatística - Outliers](images/Outliers.png)
   ![Estatística - Outliers](images/Outliers2.png)

2. Deixe uma visualização mais personalizada, adicionando um filtro para trazer os _**10 maiores valores**_. Na segunda coluna, selecione o ícone da Gramática da Visualização.
   ![Filtro na Visualização](images/Filtro.png)

3. Selecione o dado **Quantidade** na primeira coluna e traga para segunda coluna, na gramática do painel para adionar **Quantidade** em **Filtros**. 
<br> Personalize o filtro, definindo _N Mais Altos_ e Contragem _10_. 

   ![Filtro na Visualização](images/Filtro1.png)

4. Ao adicionar mais algumas métricas de estatística, como Linha de Referência. 
<br> Selecione a visualização desejada. Clique com o _botão direito_, selecione **Adionar Estatísticas**. E escolha a opção **Linha de Referência**. Deixe na Função Média. 

   ![Linha de Referência](images/Referencia1.png)
   ![Linha de Referência](images/Referencia2.png)

5. Repita o passo anterior. 
<br> Selecione a visualização desejada. Clique com o _botão direito_, selecione **Adionar Estatísticas**. E escolha a opção **Linha de Referência**. Deixe na Função Mediana, alterando a cor da linha para ficar diferente.   

   ![Linha de Referência](images/Referencia3.png)
   ![Linha de Referência](images/Referencia4.png)

## 4️⃣ One-Click Explain & Autoinsights
1. Adicione mais uma tela. No canto inferior tem um símbolo de '+', ao lado da aba 'Tela 1' ou 'Geral'. Clique nele para adicionar uma segunda Tela.
   ![Tela 2](images/Tela2.png) 

2. Renomeie o nome da Tela 2 para **'Autoinsights'**, Abas no canto inferior do Painel. 

3. Selecione a **Lâmpada Laranja** no canto superior direito próximo ao Ícone do Perfil. Irá abrir uma aba com várias sugestões de gráficos e visualizações.
   ![Autoinsights](images/Autoinsight1.png)
   ![Autoinsights](images/Autoinsight2.png)  

4. Aproveite para selecionar algumas visualizações, como o Mapa **Geographical Density of Records**, clique no símbolo '+' ou arraste e solte na tela do Painel. 
   ![Autoinsights](images/Autoinsight3.png) 

5. Repita a mesma ação para o gráfico de Barras **Top 10 SIGLA by QUANTIDADE**.
   ![Autoinsights](images/Autoinsight4.png) 

6. Sua tela de Autoinsights ficará dessa forma: 
   ![Autoinsights](images/Autoinsight5.png) 

7. Agora, a funcionalidade que explica seu dado. Clique com o _botão direito_ em cima do dado **ESTADO**. E selecione **'Explicar ESTADO'**
   ![One-Click Explain](images/Explain10.png)

8. Vai abrir um pop up, com __Fatos Básicos, Drivers Chave, Segmentos e Anomalias__ sobre o dado selecionado.
   ![One-Click Explain](images/Explain11.png)

9. Navegue pelas Abas do Explain para ver quais visualizações e quais tipos de análises são disponibilizadas com 1-Clique.
   ![One-Click Explain](images/Explain12.png)
   ![One-Click Explain](images/Explain13.png)
   ![One-Click Explain](images/Explain14.png)

10. Repita para o dado **EMBARCAÇÃO**, clique com o _botão direito_ em cima do dado **EMBARCAÇÃO**. E selecione **'Explicar EMBARCAÇÃO'**
   ![One-Click Explain](images/Explain1.png)
   ![One-Click Explain](images/Explain2.png)
   ![One-Click Explain](images/Explain3.png)
   ![One-Click Explain](images/Explain4.png)

11. Adicione algumas das visualizações disponibilizadas no seu Painel, selecione o **'Check Verde'**, no canto superior das visualizações. 
   ![One-Click Explain](images/Explain5.png)
   ![One-Click Explain](images/Explain6.png)

12. Agora selecione o botão **'Adicionar Selecionado'** e veja as visualizações disponíveis no seu Painel.
   ![One-Click Explain](images/Explain7.png)

13. Salve seu trabalho. Selecione o ícone do disquete no campo direito superior. E volte a Homepage.
![Salvar Painel](images/Save2.png)
![Voltar a Homepage](images/Save3.png)

14. Navegue pelo Painel pronto que foi importado na primeira tarefa. O Workbook (Pasta de Trabalho) **Lab Analytics - Embarcações Brasil**. 
   ![Homepage depois do import](images/Import4.png)


<br>

🎉🎉 Parabéns, você terminou os Laboratórios de **OAC - Oracle Analytics Cloud com sucesso!!** 🎉🎉

<br>

## 5️⃣ [EXTRA] Adição de Previsão, Campo Calculado, Filtros e Personalização do Dashboard

1. Adiocione mais uma tela. No canto inferior em um símbolo de '+', ao lado da aba 'Tela 1' ou 'Geral'. Clique nele para adicionar uma segunda Tela.
   ![Tela 4](images/Tela2.png) 

<br>

### **Estatística - Previsão (Forecast)**
2. Segure **_CTRL+Clique_** nos campos **ANO e QUANTIDADE** na primeira coluna no primeiro ícone (Dados), e arraste os dois para a tela em branco. Verifique que é um gráfico de **Linha**.
   ![Previsão](images/Previsao.png) 

3. Selecione a visualização que deseja adiconar estatística. Clique com o _botão direito_, selecione **Adionar Estatísticas**. E escolha a opção **Previsão**.
   ![Previsão](images/Previsao2.png) 
   ![Previsão](images/Previsao3.png) 
   ![Previsão](images/Previsao4.png) 

4. (OPCIONAL) Personalizar a propriedade do gráfico, deixando o valor e o ponto no gráfico visível. 
   ![Propriedades da Visualização](images/Prop1.png) 
   ![Propriedades da Visualização](images/Prop2.png) 

5. Outra forma de analisar a mudança períodica da quantidade de embarcações, é pelo gráfico de . Por isso, segure _CTRL+Clique_ nos campos **ANO e QUANTIDADE** na primeira coluna no primeiro ícone (Dados), e arraste os dois para a tela ao lado do gráfico de linha. 
   ![Cascata](images/Cascata.png) 
   ![Cascata](images/Cascata2.png) 

<br>

### **Campos Calculados**

6. Agora, Vamos criar um campo Calculado para sempre trazer o valor de **QUANTIDADE** do ano anterior ao ano que se refere o dado que está se utilizando agora. Clique com o _botão direito do mouse em cima do **'Meus Cálculos'**_. Selecione **Criar Cálculo ...**
   ![Campo Calculado](images/Calc1.png)

7. Escreva a função no corpo do Novo Cálculo.  

   ```
   AGO(QUANTIDADE, YEAR, 1)
   ```
8. Verifique se o cálculo está referenciado, ele está referenciado, quando as variáveis ficam coloridas, sendo a função verde (AGO), campo azul (QUANTIDADE).
   ![Campo Calculado](images/Calc2.png)
   ![Campo Calculado](images/Calc3.png)

9. Adicione o nome do cálculo: **'Quantidade do Ano Anterior'**, clique no botão **Validar** para verificar que está tudo certo. E pode Salvar.
   ![Campo Calculado](images/Calc4.png)

10. Agora, crie um cálculo para ver a variação da Frota de Naval do Brasil, ano a ano.  Clique com o _botão direito do mouse em cima do **'Meus Cálculos'**_. Selecione **Criar Cálculo ...**
   ![Campo Calculado](images/Calc1.png)

11. Escreva a função no corpo do Novo Cálculo.  
   ```
   (QUANTIDADE - Quantidade do Ano Anterior)/Quantidade do Ano Anterior
   ```

12. Verifique se o cálculo está referenciado. Ele está referenciado, quando as variáveis ficam coloridas, sendo a função verde, campo azul.
   ![Campo Calculado](images/Calc6.png)
   ![Campo Calculado](images/Calc7.png)

13. Crie uma visualização com a variação em porcentagem do aumento ou diminuição da frota naval por Estado no decorrer dos Anos. Para isso, segure _CTRL+Clique_ nos campos **ANO (ANO)** e **Quantidade do Ano Anterior** (Meus Cálculos) na primeira coluna no primeiro ícone (Dados), e arraste os dois para a tela ao lado do gráfico de linha. 

   ![Frota de Embarcação Ano a Ano](images/Calc10.png)

14. Adicione o campo **ESTADO** dentro da caixa Cor do gráfico, como indicado na imagem. 
   ![Frota de Embarcação Ano a Ano](images/Calc11.png)

15. Se tem o estado GO - Goiás, com uma variação bem grande comparada com os demais, assim como RR - Roraima.  Portanto, será adicionado um filtro desconsiderando os 2 estados. Para isso, adicione o campo **ESTADO** dentro da caixa Filtro do gráfico,
   ![Frota de Embarcação Ano a Ano](images/Calc12.png)
   ![Frota de Embarcação Ano a Ano](images/Calc14.png)
   ![Frota de Embarcação Ano a Ano](images/Calc15.png)

16. Clique com o _botão direito_, selecione **Adionar Estatísticas**. E escolha a opção **Linha de Referência**. Deixe na Função Média. 
   ![Frota de Embarcação Ano a Ano](images/Calc13.png)
   ![Frota de Embarcação Ano a Ano](images/Calc16.png)

<br>

### **Filtros**

5. Criar uma visualização de Nuvem de Palavras e utilizá-la como filtro. 
Selecione os campos desejados **Embarção e Quantidade**. _Clique com o botão direito_ e escolhe a opção **Selecionar Visualização**, agora selecione o ícone da nuvem de palavras, como na imagem a seguir. 
   ![Nuvem de Palavras](images/Tag1.png)
   ![Nuvem de Palavras](images/Tag2.png)

6. Use uma visualização para filtrar os dados. Ao lado do título da visualização existe um filtro, selecione para o **filtro ficar verde**, isso significa que a **visualização está sendo utilizada como filtro**
   ![Nuvem de Palavras como Filtro](images/Tag3.png)

7. Selecione algum item da Nuvem de Palavras e perceba que todas as visualizações vão ser filtradas a partir dela. Como exemplo foi selecionado **Outros**.
   ![Nuvem de Palavras como Filtro](images/Tag4.png)

8. Adicione Título na primeira página do Painel. Na primeira Coluna selecione o segundo ícone do gráfico (Visualizações). Escolha **Caixa de Texto** segure e arraste para a Tela no canto superior da tela. 
   ![Título do Painel](images/Titulo.png)

9. Personalize o Título mudando as propriedades, na segunda coluna segundo ícone, adicione uma cor ao fundo, deixe o texto centralizado e outras personalizações como mostra na imagem a seguir.
   ![Título do Painel](images/Titulo2.png)

<br>

### **Variedade de Filtros**
10. Adicione uma Caixa de Filtro na Tela, selecione o campo **Ano** para utilizar como Filtro, arraste e solte até ficar ao lado do Título, canto direito superior.  
   ![Filtro Seletor](images/Filtro10.png)

11. Na gramática do Painel, selecione o tipo de visualização que quer **Filtros do Painel de Controle**. E selecione um Ano do Filtro.
   ![Filtro Seletor](images/Filtro11.png)
   ![Filtro Seletor](images/Filtro12.png)

12. Personalize o nome do Filtro, selecione na segunda coluna no segundo ícone (Propriedades). Atualize o Label para **Personalizado** e deixe como **ANO**.
   ![Filtro Seletor](images/Filtro13.png)   

13. Também existe a possibilidade de utilizar filtros no cabeçalho do Painel. Selecione o campo **ESTADO** na primeira coluna no primeiro ícone (Dado). Segure e arraste para o campo superior da tela onde há um '+' com Clique aqui ou arraste os dados para adicionar um filtro".
   ![Filtro Seletor](images/Filtro15.png)   

14. Faça o mesmo com o campo **EMBARCAÇÃO**, adicionando ele na barra de filtro superior do Painel. 
   ![Filtro Seletor](images/Filtro16.png)  

15. Renomeie o nome da Tela 1 para **'Geral'**, Abas no canto inferior do Painel. 
   ![Tela 1 para Geral](images/Geral.png)  

<br>

🎉🎉 Parabéns, você terminou os Laboratórios e Material EXTRA de **OAC - Oracle Analytics Cloud com sucesso!!** 🎉🎉

<br>

## 👥 Agradecimentos

- **Autores** - Gabriela Miyazima
- **Autor Contribuinte** - Caio Oliveira, Isabelle Anjos
- **Última Atualização Por/Data** - Janeiro 2025

## 🛡️ Declaração de Porto Seguro (Safe Harbor)

O texto a seguir tem como objetivo traçar a orientação dos nossos produtos em geral. É destinado somente a fins informativos e não pode ser incorporado a um contrato. Ele não representa um compromisso de entrega de qualquer tipo de material, código ou funcionalidade e não deve ser considerado em decisões de compra. O desenvolvimento, a liberação, a data de disponibilidade e a precificação de quaisquer funcionalidades ou recursos descritos para produtos da Oracle estão sujeitos a mudanças e são de critério exclusivo da Oracle Corporation.

Esta é a tradução de uma apresentação em inglês preparada para a sede da Oracle nos Estados Unidos. A tradução é realizada como cortesia e não está isenta de erros. Os recursos e funcionalidades podem não estar disponíveis em todos os países e idiomas. Caso tenha dúvidas, entre em contato com o representante de vendas da Oracle. 
