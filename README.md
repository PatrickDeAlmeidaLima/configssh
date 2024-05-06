# Como configurar um acesso ssh no github no seu pc:

1. Verifique se você já tem uma chave SSH: Primeiro, vamos verificar se você já possui uma chave SSH. No terminal (ou prompt de comando), digite o seguinte comando:
ls -al ~/.ssh
Isso listará todos os arquivos na sua pasta .ssh. Se houver arquivos com nomes como id_rsa ou id_rsa.pub, você já tem uma chave SSH configurada.

2. Gere uma nova chave SSH (se necessário): Se você não encontrou uma chave SSH, ou deseja criar uma nova, use o seguinte comando:
ssh-keygen -t rsa -b 4096 -C "seu_email@example.com"
Substitua "seu_email@example.com" pelo seu endereço de e-mail associado à sua conta do GitHub. Isso criará uma nova chave SSH com o algoritmo RSA e um comprimento de chave de 4096 bits.

3. Escolha um nome de arquivo para sua chave SSH: O comando ssh-keygen perguntará onde você deseja salvar a chave. O local padrão é ~/.ssh/id_rsa. Se você deseja usar um nome diferente, pode especificar um caminho diferente.
4. Proteja sua chave com uma senha (opcional): Você pode adicionar uma senha à sua chave para fornecer uma camada adicional de segurança. Isso é opcional, mas altamente recomendado.
5. Adicione sua chave SSH à sua conta do GitHub:
* Copie o conteúdo da sua chave pública. Você pode fazer isso com o comando:
cat ~/.ssh/id_rsa.pub

* Copie a saída completa.
* Faça login na sua conta do GitHub.
* No canto superior direito, clique na sua foto de perfil e vá para "Settings".
* No menu lateral esquerdo, clique em "SSH and GPG keys".
* Clique em "New SSH key" (ou "Add SSH key").
* Cole a chave SSH pública no campo apropriado e dê um título significativo à chave.
* Clique em "Add SSH key".

6. Teste sua conexão SSH: Para verificar se a sua chave SSH foi configurada corretamente, você pode tentar se conectar ao GitHub usando SSH:
ssh -T git@github.com

Se tudo estiver configurado corretamente, você receberá uma mensagem de confirmação.
