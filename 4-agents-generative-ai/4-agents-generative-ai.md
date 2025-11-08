# Oracle Generative AI Agents

## 📌 Introdução

Este laboratório orienta você nas etapas para configurar um agente de IA generativa OCI, incluindo a ingestão de uma base de conhecimento no OCI Object Storage.

<br>

### 📌 **Objetivos**

Descubrar como utilizar de forma prática a funcionalidade de busca vetorial do Oracle Generative AI Agents para otimizar consultas em documentos.

O que você aprenderá:

- Criar um Agent 
- Configure as instruções para o Agent
- Adicionar o RAG Tool no Agent
- Crie um endpoint automaticamente
- Interagir com o Agent criado

<br>


## 1️⃣ Criação do Agente de IA

No menu à esquerda, selecione a opção **Agents**. Em seguida, clique em **Create Agent**

![Agents](images/agents.png)

Nesta tela, siga os seguintes passos:

1. Insira o nome do agente. Recomendamos o nome **agent-ai-demo**.
2. No campo **Description** adicione uma descrição sobre o agente:

    <copy>
    Você responde dúvidas sobre direitos dos consumidores com base no Código de Defesa do Consumidor do Brasil, fornecendo respostas claras e fundamentadas na legislação. Sempre que possível, cite os artigos relevantes do CDC.
    </copy>
<!-- Separador -->

3. No campo **Welcome Message**, insira a mensagem de boas-vindas que será exibida para o usuário ao iniciar a interação com o agente. Exemplo: 

    <copy>
    Bem-vindo! Estou aqui para esclarecer suas dúvidas sobre o Código de Defesa do Consumidor. Como posso ajudar?
    </copy>
<!-- Separador -->

4. Clique em **Next**

![Configuration Agents](images/configuration-agents.png)

Na proxima tela, iremos configurar a o RAG Tool, clique em **Add Tool** e siga os passos abaixo:

![Add Tool](images/add-tool.png)

1. Selecione a opção **RAG**.
2. Insira o nome do RAG. Recomendamos o nome **rag-agent**.
3. No campo **Description** insira uma descrição explicando de forma clara o que o RAG Tool pode recuperar permitindo que o agente de IA faça escolhas mais inteligentes sobre quando usá-la, garantindo respostas mais relevantes e precisas para o usuário.

    <copy>
    Esta ferramenta pode recuperar informações detalhadas sobre os direitos e deveres dos consumidores conforme o Código de Defesa do Consumidor do Brasil, incluindo explicações sobre processos de reclamação, garantias, práticas comerciais, contratos, troca de produtos, reembolsos e orientações sobre como proceder em casos de descumprimento da legislação de defesa do consumidor. Ela oferece acesso a artigos específicos do CDC e interpretações confiáveis para apoiar o usuário em suas dúvidas referentes a relações de consumo no Brasil.
    </copy>
<!-- Separador -->

4. No campo **Custom instructions** adicione instruções específicas para o agente. No exemplo, foi utilizado:

    <copy>
    Você responde dúvidas sobre direitos dos consumidores com base no Código de Defesa do Consumidor do Brasil, fornecendo respostas claras e fundamentadas na legislação. Sempre que possível, cite os artigos relevantes do CDC. Responda sempre de forma clara e exclusivamente em português brasileiro.
    </copy>
<!-- Separador -->

5. Na seção **Add Knowledge Bases**, selecione a base de conhecimento que será vinculada ao agente. Certifique-se de que a base de conhecimento está ativa. **O Lifecycle State deve aparecer como Active.**
6. Clique no botão **Add tool** para adicionar tool.

![RAG Tool Configuration](images/rag-tool-config.png)
![Add KB Tool](images/add-kb-tool.png)

Na próxima seção, **Setup agent endpoint**, certifique-se de que a opção **Automatically create an endpoint for this agent** está marcada. Isso permitirá que o sistema crie automaticamente um endpoint para o agente, facilitando a interação com ele via API com outras aplicações.

![Endpoint Agent](images/setup-agent-endpoint.png)

Clique no botão **Next** e para finalizar a criação do agente clique em **Create agent**.

![Create Agent](images/create-agent.png)

Nesta tela, aceite o Acordo de Licença e Política de Uso do Llama 3, o modelo de inteligência artificial utilizado pelo Agent.

![LLAMA3](images/llama3.png)

No canto superior direito, verifique as mensagens de confirmação. Elas devem indicar que a criação do agente  e do endpoint foram concluídas com sucesso.

O campo **Lifecycle State** exibirá o status como **Creating**, com média de tempo  de **9 minutos** para finalização. Aguarde até que o status mude para **Active**, indicando que o agente está pronto para uso.

![Sucess Messages Agent](images/sucess-messages-agent.png)

Clique no nome do agente e, em seguida, selecione a opção **Launch Chat** para iniciar a interação com o agente.

![Launch Chat](images/launch-chat.png)

> **ATENÇÃO: Caso o agente esteja ativo e o botão não esteja disponível, acesse o menu à esquerda inferior e selecione Endpoints. Verifique se o Lifecycle State do endpoint está como Active. Se o status estiver como Creating, aguarde a finalização e atualize a página.**

## 2️⃣ Interface de Interação com o Assistente Virtual

### 🔵 **Agente e Endpoint (destacado em azul)**

> - **Agent:** Neste campo você seleciona o agente configurado para responder às suas perguntas. No exemplo, o agente selecionado é o **ai-agent**.
> <br>
> - **Agent Endpoint:** O endpoint associado ao agente. Este é o ponto de acesso que conecta o assistente às bases de conhecimento.

### 🔴 **Área de Chat (destacada em vermelho)**

Esta é a área principal onde você pode interagir com o agente. Aqui, o assistente exibe a mensagem de saudação que configuramos e as respostas às suas perguntas.

> -  O campo **Type a message...** é onde você insere suas perguntas. Após digitar, clique em **Submit** para enviar a mensagem.
> -  O botão **Reset chat session** permite reiniciar a sessão de chat, apagando o histórico atual de interação.

### 🟠 **Traces (destacado em laranja)**

> O painel Traces mostra detalhes técnicos de cada interação com o agente, como as **consultas realizadas, os resultados gerados e os detalhes da página e parágrafo cujas informações foram obtidas**. Este recurso é útil para analisar como o assistente processa as perguntas e recupera informações da base de conhecimento.

![Interface Agent](images/interface-agent.png)

Na imagem abaixo, você pode observar o funcionamento do assistente virtual ao responder perguntas baseadas em diferentes documentos previamente carregados na base de conhecimento.

![Chat Agent](images/chat-agent.png)

Exemplos de perguntas para fazer os testes:

    <copy>
    Não gostei do produto. Posso cancelar a compra?
    </copy>
<!-- Separador -->

    <copy>
    Ao abrir uma conta bancária, fui informado de que era obrigatório contratar um seguro de vida. Gostaria de saber se essa exigência por parte do banco está correta.  
    </copy>
<!-- Separador -->

    <copy>
    O cinema da minha cidade proíbe a entrada de produtos adquiridos no supermercado, obrigando os clientes a comprarem apenas os itens vendidos no local. Essa prática está correta? 
    </copy>
<!-- Separador -->

    <copy>
    A escola da minha filha está solicitando diversos materiais. Gostaria de saber quais itens podem ser incluídos legalmente na lista de material escolar.
    </copy>
<!-- Separador -->

Ao clicar em **View Citations**, você expande as referências utilizadas pelo assistente para gerar a resposta. 

![View Citations](images/view-citations.png)

Cada citação apresenta as seguintes informações:

> - **Title:** O nome do arquivo de onde a informação foi extraída.
> - **Object storage path:** O caminho do arquivo no armazenamento do OCI.
> - **Document ID:** Um identificador único do documento.
> - **Page numbers:** Indica o número da página no documento de onde a informação foi retirada.
> - **Source text:** Exibe o trecho exato do documento utilizado para compor a resposta do assistente.


🎉 Laboratório finalizado! Parabéns por concluir todas as etapas. Fique à vontade para criar novas perguntas, explorar a sua aplicação e descobrir ainda mais possibilidades com o seu assistente virtual.

Você poderá seguir para o próximo laboratório.

## 👥 Agradecimentos

- **Autores** - Victória Rodrigues
- **Autores Contribuintes** - Isabelle Anjos, Caio Oliveira, Gabriela Miyazima, Aristotelles Serra
- **Última Atualização Por/Data** - Novembro 2025

## 🛡️ Declaração de Porto Seguro (Safe Harbor)

O tutorial apresentado tem como objetivo traçar a orientação dos nossos produtos em geral. É destinado somente a fins informativos e não pode ser incorporado a um contrato. Ele não representa um compromisso de entrega de qualquer tipo de material, código ou funcionalidade e não deve ser considerado em decisões de compra. O desenvolvimento, a liberação, a data de disponibilidade e a precificação de quaisquer funcionalidades ou recursos descritos para produtos da Oracle estão sujeitos a mudanças e são de critério exclusivo da Oracle Corporation.

Esta é a tradução de uma apresentação em inglês preparada para a sede da Oracle nos Estados Unidos. A tradução é realizada como cortesia e não está isenta de erros. Os recursos e funcionalidades podem não estar disponíveis em todos os países e idiomas. Caso tenha dúvidas, entre em contato com o representante de vendas da Oracle. 
