# Oracle APEX

## 📌 Introdução

>**O Oracle APEX (Application Express) é uma plataforma de desenvolvimento low-code que permite a criação rápida e fácil de aplicações seguras, escaláveis e altamente responsivas diretamente no Oracle Database, sem a necessidade de infraestrutura complexa.** 

![APEX](images/apex.png)

### ➡️ **Como o Oracle APEX revoluciona o desenvolvimento de aplicações no Oracle Database?**

> Com o Oracle APEX, desenvolvedores podem criar aplicações empresariais modernas por meio de uma interface intuitiva que combina design visual, componentes integrados e funcionalidades avançadas, como gráficos interativos, relatórios dinâmicos e dashboards. O APEX aproveita as capacidades nativas do Oracle Database, como segurança, alta disponibilidade e desempenho, permitindo a criação de workspaces, o upload de aplicações e a integração com serviços externos via credenciais e APIs. Com poucos cliques, é possível importar arquivos SQL, configurar parâmetros de segurança e realizar customizações rápidas e eficientes.

<br>

### 📌 **Objetivos**

  Guiar os participantes na criação e configuração de um ambiente APEX no Oracle Cloud Infrastructure (OCI) para implementar uma aplicação baseada em IA generativa.  

O que você aprenderá:

  - Criar um workspace no APEX.  
  - Importar e instalar uma aplicação.  
  - Ajustar credenciais para integração com serviços do OCI.  
  - Realizar de testes práticos para validar a aplicação.  

<br>
### **Recursos e Suporte**:

- **Download da Aplicação**: [f102.sql](https://objectstorage.us-ashburn-1.oraclecloud.com/p/rYsZFM9_XUMb7t92b6jFH3B-5oB78j3URY3xlrK1LHXlVAjs_C1uD6xWoV-qtfpW/n/idi1o0a010nx/b/bucket-dataprev/o/f102.sql)

- **Download do PDF**: [Normas Internas Dataprev](https://www.dataprev.gov.br/governanca/normativos/normasinternas). Para o nosso exemplo, utilizaremos o arquivo **Viagem a Serviço Nacional**.
- **Documentação da Oracle Cloud**: [Getting started with vectors in 23ai](https://blogs.oracle.com/coretec/post/getting-started-with-vectors-in-23ai)
- **Tutoriais**: [Oracle Database 23ai - Oracle AI Vector Search & Retrieval Augmented Generation (RAG) with Oracle APEX](https://www.linkedin.com/pulse/oracle-database-23ai-ai-vector-search-retrieval-augmented-rao-bqkcf/)


### _**Aproveite sua experiência na Oracle Cloud!**_


## 1️⃣ Criação de Workspace e Import de aplicação em ambiente APEX

Para acessar a URL da instância APEX na Console do Oracle Cloud Infrastructure (OCI), siga os passos a seguir. 

Inicialmente, retorne ao console da OCI. Em seguida, navegue até a página do seu Autonomous Database. Dentro da página da instância do banco de dados, localize e clique na opção **"Tool Configuration"**. Lá, você encontrará a URL da instância APEX. **Copie essa URL e abra em seu navegador.**

   ![Tool Configuration](images/tool-config.png)

Na página que será aberta ao acessar a URL da instância APEX, **insira a senha de acesso ao workspace admin**, criada na etapa anterior (**WORKSHOPsec2019##**).
<br>

   ![Apex Password](images/apex-password.png)

Em seguida, clique na opção **Create Workspace**. Na tela seguinte, escolha a opção **Existing Schema** para continuar com a criação do workspace utilizando um schema já existente.

   ![Existing Schema](images/existing-schema.png)

Na sequência, preencha o formulário como o exemplo abaixo (recomendamos a senha **WORKSHOPsec2019##**). E clique em **Create Workspace** para finalizar.

   ![Create Workspace](images/create-workspace.png)

Clique na aba superior **Manage Instance** e, em seguida, selecione **Security**.

   ![Manage Instance](images/manage-instance.png)

Altere o parâmetro **Allow Public File Upload** para **Yes** e clique em **Apply Changes** para salvar as alterações.

   ![File Upload](images/file-upload.png)

Encerre a sessão do usuário **ADMIN** clicando em **Sign Out**, localizado na região superior direita da tela.

   ![Sign Out](images/sign-out.png)

Faça o login no usuário **DEMO** criado nas etapas anteriores utilizando as credenciais de acesso indicadas abaixo.

   ![Login](images/login.png)

Clique em **App Builder** e, em seguida, selecione **Import**.

   ![Import](images/import.png)

Na página que será aberta, faça o upload do arquivo **f102.sql** utilizando o seguinte link: [f102.sql](https://objectstorage.us-ashburn-1.oraclecloud.com/p/rYsZFM9_XUMb7t92b6jFH3B-5oB78j3URY3xlrK1LHXlVAjs_C1uD6xWoV-qtfpW/n/idi1o0a010nx/b/bucket-dataprev/o/f102.sql).

   ![Aplicação f102](images/f102.png)

Aceite as configurações padrão e clique em **Install Application** para prosseguir com a instalação.

   ![Install](images/install.png)

Clique em **Install Supporting Objects** para concluir a instalação dos objetos de suporte necessários.

   ![Supporting Objects](images/supporting-objects.png)

Por fim, clique na aba **App Builder** para retornar à interface principal de desenvolvimento de aplicações.

   ![App Builder](images/app-builder.png)

## 2️⃣ Configuração de Credenciais para RAG (Retrieval-Augmented Generation)

Na aba **App Builder**, clique em **Workspace Utilities** para acessar as ferramentas utilitárias do workspace.

   ![Workspace Utilities](images/workspace-utilities.png)

Em seguida, selecione **Web Credentials** e clique na credencial existente chamada **apex\_ai\_cred**.

   ![Web Credentials](images/web-credentials.png)
   ![Apex AI Cred](images/apex-ai-cred.png)

Para preencher corretamente essa credencial, é necessário obter algumas informações sobre o usuário no ambiente OCI. Na guia do navegador onde o OCI está aberto, clique no avatar no canto superior direito e selecione **User Settings**.

   ![User Settings](images/user-settings.png)

Na tela **User Settings**, localize a guia **API Keys** no canto inferior esquerdo. Clique nela e siga as instruções do assistente (wizard) para criar um par de chaves de API. 

> **ATENÇÃO: Certifique-se de salvar as seguintes informações em um local seguro, pois será necessária para configurar a credencial na próxima etapa:** <br></br>
> - **OCI User ID**
> - **OCI Private Key**
> - **OCI Public Key Fingerprint**

   ![API Keys](images/api-keys.png)

O preenchimento do formulário no APEX exigirá informações específicas que podem ser obtidas na tela do OCI. Para facilitar, **utilize as seguintes correspondências de cores** entre os dois sistemas. Preencha as seguintes informações:
- OCI User ID
- OCI Private Key 
- OCI Public Key Fingerprint

   ![OCID API OCI](images/ocid-api-oci.png)
   ![OCID API APEX](images/ocid-api-apex.png)

O OCI Tenancy ID pode ser coletado no OCI na página **Tenancy Details**, que pode ser acessada clicando no nome do seu Tenancy na página inicial do Console ou na seção Tenancy Information dentro de User Settings.

   ![Tenancy Details](images/tenancy-details.png)
   ![Tenancy OCID](images/tenancy-ocid.png)

Retorne à página do APEX e insira o **OCI Tenancy ID** no campo correspondente, utilizando o valor coletado na página Tenancy Details do OCI.

Por fim, clique em **Apply Changes** para salvar as configurações e concluir o ajuste da credencial.

## 3️⃣ Configuração no Payload da API de Requisição

Para concluir este processo, será necessário realizar uma alteração no **payload da API de requisição**.

Acesse o **App Builder** e clique na aplicação que você instalou recentemente.

   ![APP Builder API](images/app-builder-api.png)

Selecione em **Shared Components -> REST Data Resources**

   ![Shared Components](images/shared-components.png)
   ![Rest Data Resources](images/rest-data-resources.png)

Clique em **cohere-chat** e, em seguida, no **ícone de lápis ao lado do método POST**.

   ![Cohere Chat](images/cohere-chat.png)

**Altere o Compartment ID para a variável OCI Tenancy ID coletada na etapa 2 deste laboratório.**
Por fim, clique em **Apply Changes** para salvar as alterações.

   ![alt text](images/ocid-compartment.png)

## 4️⃣ Teste da Aplicação

Com a configuração da credencial concluída, podemos testar a aplicação. Para isso, clique em **App Builder** e, em seguida, no ícone **Run** para executar a aplicação e verificar seu funcionamento.

   ![Run Application](images/run-application.png)

Clique em **Arquivos e Normas**.

   ![Assistente AI](images/assistente-ai.png)

Seguiremos com o upload de um arquivo PDF para dentro da aplicação. Qualquer PDF pode ser utilizado, mas, para fins didáticos deste workshop, recomendamos as normas disponíveis no link: [Normas Internas Dataprev](https://www.dataprev.gov.br/governanca/normativos/normasinternas). Para o nosso exemplo, utilizaremos o arquivo **Viagem a Serviço Nacional**.

   ![Dataprev Site](images/dataprev-site.png)

Clique em **Upload** e preencha o formulário seguindo o exemplo fornecido. O **JSON** utilizado para o preenchimento está disponível logo abaixo da imagem de referência.

   ![Uploader](images/uploader.png)


    <copy>  
    {
        "by" : "words",
        "max" : "50",
        "overlap" : "0",
        "split": "sentence",
        "language" : "ptb",
        "normalize": "none"
    }

    </copy>

Se o upload for concluído com sucesso, sua tela deverá se assemelhar ao exemplo exibido, mostrando a confirmação do arquivo enviado e os detalhes preenchidos no formulário.

   ![Row Created](images/row-created.png)

Clique em Assistente AI e faça uma pergunta relacionada ao documento carregado. Por exemplo, você pode perguntar: **"COMO FAZER ALTERAÇÃO DE VIAGEM"**.

   ![Question](images/question.png)


**Se não houver erro, você terá concluído com sucesso o workshop.** Sinta-se à vontade para fazer o upload de outros arquivos ou explorar realizando novas perguntas ao Assistente AI.


## 👥 Agradecimentos

- **Autores** - Caio Oliveira
- **Autores Contribuintes** - Isabelle Anjos, Gabriela Miyazima, Aristotelles Serra
- **Última Atualização Por/Data** - Janeiro 2025

## 🛡️ Declaração de Porto Seguro (Safe Harbor)

O tutorial apresentado tem como objetivo traçar a orientação dos nossos produtos em geral. É destinado somente a fins informativos e não pode ser incorporado a um contrato. Ele não representa um compromisso de entrega de qualquer tipo de material, código ou funcionalidade e não deve ser considerado em decisões de compra. O desenvolvimento, a liberação, a data de disponibilidade e a precificação de quaisquer funcionalidades ou recursos descritos para produtos da Oracle estão sujeitos a mudanças e são de critério exclusivo da Oracle Corporation.

Esta é a tradução de uma apresentação em inglês preparada para a sede da Oracle nos Estados Unidos. A tradução é realizada como cortesia e não está isenta de erros. Os recursos e funcionalidades podem não estar disponíveis em todos os países e idiomas. Caso tenha dúvidas, entre em contato com o representante de vendas da Oracle. 