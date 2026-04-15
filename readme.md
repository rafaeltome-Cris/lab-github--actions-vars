As secrets aparecem como *** nos logs porque o GitHub aplica mascaramento automático para proteger dados sensíveis, como tokens, senhas e chaves de acesso. Isso impede o vazamento dessas informações durante a execução do workflow.

Já as variables (vars) não são consideradas sensíveis e, por isso, seus valores são exibidos normalmente nos logs.

Um job não consegue acessar diretamente variáveis criadas em outro job. Isso ocorre porque cada job é executado em um ambiente isolado dentro do GitHub Actions.

Por exemplo, uma variável como BUILD_VERSION, criada no build_app utilizando $GITHUB_ENV, não estará disponível no deploy_app.
