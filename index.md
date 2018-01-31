## Welcome to GitHub Pages

You can use the [editor on GitHub](https://github.com/on-digitalstudio/how-works/edit/master/index.md) to maintain and preview the content for your website in Markdown files.

Whenever you commit to this repository, GitHub Pages will run [Jekyll](https://jekyllrb.com/) to rebuild the pages in your site, from the content in your Markdown files.

### Markdown

Markdown is a lightweight and easy-to-use syntax for styling your writing. It includes conventions for

```markdown
Syntax highlighted code block

# Header 1
## Header 2
### Header 3

- Bulleted
- List

1. Numbered
2. List
ESTRUTURA DO SITE

  - NOME DA EMPRESA
  - CATEGORIA
  - TELEFONE
  - SITE
  - EMAIL
  -ENDEREÇO
                        - PÁGINA INICIAL
                        - PARCEIROS
                        - SOBRE
                        - SERVIÇOS
                        - CONTATO
                        - RODAPÉ
                        - SLIDER
                    - INTEGRAÇÃO C/ INSTAGRAM
                        - INSTAFEED GALERIA
                        - FACEBOOK
                    - INTEGRAÇÃO C/ DETALHES DO GOOGLE
                      - ENVIAR UM COMENTÁRIO
                      - ENVIAR UMA PERGUNTA
                      - ENVIAR FOTOS
                          - COMPARTILHADAS COMIGO
                      - HORÁRIO
                      - BREVE DESCRIÇÃO
                      - BLOG
                          - POSTAGEM GOOGLE
                        -MENSAGEM GOOGLE ALLO
                        
                        PAGESPEED
                        SITEMAP
                        ROBOT
                        WEBMASTER
                        SSL
                        
                        WEBMAIL
                        PAGAMENTO
                        CONTRATO
                        
                        
                        GOOGLE SUITE
                          AGENDA
                          EMAIL
                          DRIVE
                          
                          
                      - ANALITYCS
                      - TAGMANAGER
                      - ADWORDS
                      - MAPS
                      
                      - FACEBOOK
                        - SERVIÇOS
                        - LOJAS
                        - FOTO/VIDEO CAPA
                        - FOTO/VIDEO PROFILE
                      - INSTAGRAM
                      
                      
                      ---- ADVOGADO / ESCRITÓRIO
                      - EXPLORAR COTAÇÕES
                      
                      - PROPOSTAS
                        - ENVIADAS
                        - ACEITAS
                        - ENCERRADAS
                        
                      - SOLICITAÇÕES
                        - SOLICITAÇÃO
                          - CADASTRO
                          - LISTA DE COTAÇÕES
                        
                      - RELATÓRIOS
                      
                      - MEU ESCRITÓRIO
                        - SITE
                        - ENDEREÇO
                        
                      - MINHAS INFORMAÇÕES (ADVOGADO - OAB) TYPE_USER: 1
                        - CADASTRO DE ÁREAS
                          - SERVIÇOS - VALOR MÉDIO
                        
                      - CONFIGURAÇÕES
                        - NOTIFICAÇÕES
                        
                      - AJUDA
                      
                      ---- CLIENTE
                      - EXPLORAR ADVOGADO / ESCRITÓRIO 
                      
                      - SOLICITAÇÕES
                        - SOLICITAÇÃO
                          - CADASTRO
                          - LISTA DE COTAÇÕES
                        
                      - MINHAS INFORMAÇÕES (CLIENTE) TYPE_USER: 2
                        - INFORMAÇÕES PESSOAIS
                        
                      - CONFIGURAÇÕES
                        - NOTIFICAÇÕES
                        
                      - AJUDA
                        
                        
                        ------
                        Solicite Propostas
                        Simples e rápido, leva apenas 2 minutos

                        Negocie
                        Esclareça detalhes e receba propostas

                        Escolha
                        Escolha o melhor fornecedor e contrate sem intermediários
                        
                        Blog
                        Perguntas frequentes
                        planos e preços
                        Política de Privacidade
                        Termos de Uso
                        Facebook
                        Instagram
                        Ajuda - Tutorial
                        Integrar com Jivochat
                        
-- SELECT PARA LOCALIZAR TODAS AS QUESTÕES DE UMA PROVA E INSERIR NA TABELA
INSERT INTO couser.on_exam_user_question (NEW.id_exam_user, id_exam_user_question) SELECT id_exam_user_question FROM couser.on_exam_question WHERE id_exam = NEW.id_exam;

-- FUNCTION PARA CALCULAR SE O ALUNO FOI:
--	0 - REPROVADO
--	1 - APROVADO
--	2 - PENDENTE
--		SE FOI APROVADO: INSERT INTO TABLE_CERTIFICADO ID_COURSE AND ID_USER - GERA CERTIFICADO  
-- se for 0 - botão para limpar as respostas
-- se for 1 - botão para pegar o certificado
-- se for 2 - botão para fazer a prova
-- se não tiver registro - botão para fazer a prova

 FOR v_i IN SELECT unnest(string_to_array(REPLACE(REPLACE(p_conteudo_remessa, CHR(13), ';'), CHR(10), ''), ';')) LOOP             
            v_loop := v_loop+1;	            
            -- VERIFICA SE É O BANCO DO BRASIL NO LAYOUT CNAB400
            --IF (substr(v_i.unnest::text, 12, 8) <> 'COBRANCA'::text OR substr(v_i.unnest::text, 77, 18) <> '001BANCO DO BRASIL'::text or length(cast (v_i.unnest::text as text)) <> '400') AND v_loop = 1  THEN																		
            IF (substr(v_i.unnest::text, 12, 8) <> 'COBRANCA'::text OR substr(v_i.unnest::text, 77, 18) <> '001BANCO DO BRASIL'::text) AND v_loop = 1  THEN
               RAISE EXCEPTION '0001';   


        try {
            if ($_FILES['file']['type'] != 'text/xml') {
                $result = array(status => 'error', error => $this->errorApplication(00001), file => $file);
            } else {
                $result = $this->errorPermission($file);
            }
        } catch (Exception $exc) {   
            $result = array(status => 'error', error => $this->errorException($exc->getCode(), $exc->getMessage()), file => $file);
        }



    public function errorException($code = null, $message = null) {
        $result = array(message => 'Erro: Desconhecido', button => true);
        
        switch ($code) {
            case 2200:
                $result = array(message => 'Erro: Estrutura do arquivo inválida', button => true);
                break;

            case 22004:
                $result = array(message => 'Erro: A estrutura do arquivo não possui todas as informações necessárias para completar está ação', button => true);
                break;

            case 23505:
                $result = array(message => 'Erro: O arquivo não foi enviado, pois já foi armazenado em sua nuvem', button => false);
                break;

            default:
                $result = $this->errorDB($message);
                break;
        }
        
        return $result;
    }
    
    public function errorDB($message = null) {
        $result = array(message => 'Erro: Desconhecido', button => true);
        
        switch (intval(substr($message, 44, 4))) {
            case 0003:
                $result = array(message => 'Erro: O arquivo não foi enviado, pois o <b>CNPJ/CPF</b> encontrado no <b>XML</b>, não representa nenhum <b>CNPJ/CPF</b> desta conta', button => false);  
                break;

            default:
                $result = array(message => 'Erro: Não foi possível encontrar o problema', button => true);
                break;
        }
        
        return $result;
    }
    

**Bold** and _Italic_ and `Code` text

[Link](url) and ![Image](src)
```

For more details see [GitHub Flavored Markdown](https://guides.github.com/features/mastering-markdown/).

### Jekyll Themes

Your Pages site will use the layout and styles from the Jekyll theme you have selected in your [repository settings](https://github.com/on-digitalstudio/how-works/settings). The name of this theme is saved in the Jekyll `_config.yml` configuration file.

### Support or Contact

Having trouble with Pages? Check out our [documentation](https://help.github.com/categories/github-pages-basics/) or [contact support](https://github.com/contact) and we’ll help you sort it out.
