# Tudo que o Zoup pode fazer


# Requisitos funcionais 


# Cadastro
Os usuários devem poder se cadastrar na rede social fornecendo informações básicas como nome, data de nascimento, e-mail, etc.
Deve haver um processo de verificação para garantir a autenticidade das contas.
Login
Os usuários registrados devem poder fazer login utilizando suas credenciais (e-mail/senha ou login social).

# Publicação de Vídeos
Usuários devem poder publicar vídeos, com um limite de tamanho e formatos aceitáveis especificados.

# Publicação de Fotos
Usuários devem poder publicar fotos, com suporte para formatos comuns de imagem e um limite de tamanho especificado.

# Comentários
Os usuários podem comentar em postagens de outros usuários.
Deve ser possível editar e excluir comentários próprios.

# Curtidas
Os usuários podem expressar apreciação por postagens de outros usuários através de curtidas.

# Adicionar Amigos
Os usuários devem poder adicionar outros usuários como amigos para acompanhar suas atividades na rede social.

# Acesso a Comentários
Os usuários podem visualizar todos os comentários feitos em suas próprias postagens e em postagens de amigos.

# Pesquisa de Postagens
Deve ser possível buscar postagens por palavras-chave ou categorias específicas.

# Pesquisa de Perfis
Os usuários podem pesquisar por perfis de outros usuários utilizando critérios como nome, interesses, etc.

# Configurações da Conta
Os usuários têm a capacidade de ajustar configurações de privacidade, notificações e outras preferências da conta.

# Desativar Conta
Os usuários têm a opção de desativar temporariamente suas contas, o que oculta seu perfil e conteúdo da rede social.

# Excluir Conteúdo
Os usuários podem excluir comentários, postagens e conteúdo multimídia que tenham publicado.

# Excluir Perfil
Os usuários têm a opção de excluir permanentemente seus perfis, o que remove todas as informações e conteúdos associados.

# Editar Comentários e Postagens
Os usuários podem editar postagens e comentários após a publicação para corrigir erros ou ajustar o conteúdo.

# Requisitos não funcionais

# Usabilidade
A interface deve ser intuitiva e fácil de usar para usuários idosos, com opções de fonte legível, contraste adequado e elementos de design acessíveis.

# Segurança
A rede social deve garantir a segurança dos dados pessoais dos usuários e proteger contra acesso não autorizado.

# Desempenho
A plataforma deve ser responsiva e suportar um número razoável de usuários simultâneos sem degradação significativa no desempenho.

# Compatibilidade
A aplicação deve ser compatível com uma variedade de dispositivos e navegadores usados por pessoas idosas, como tablets, smartphones e computadores.

# Manutenção
Deve ser fácil realizar atualizações e manutenções na plataforma sem interrupção prolongada dos serviços.

# Suporte
Deve haver um sistema eficaz de suporte ao usuário para ajudar os idosos com problemas técnicos, dúvidas sobre uso da plataforma, entre outros.

# Privacidade
Políticas de privacidade claras e facilmente acessíveis devem ser implementadas para informar os usuários sobre como seus dados são coletados, usados e compartilhados.

# Performance
Os tempos de carregamento de páginas e conteúdos devem ser otimizados para garantir uma experiência rápida e sem frustrações para os usuários idosos.

# Acessibilidade
A plataforma deve seguir diretrizes de acessibilidade web para garantir que todos os usuários, incluindo aqueles com deficiências visuais ou motoras, possam utilizar a rede social sem dificuldades excessivas.


# Visual do Zoup no mobile


![Captura de tela 2024-07-16 152015](https://github.com/user-attachments/assets/042fcfa1-c2a0-4199-8801-827d311002c8)


# Visual do Zoup no Web

![Captura de tela 2024-07-16 152633](https://github.com/user-attachments/assets/35042d86-80e1-4f29-bc03-4654deec0adb)
![Captura de tela 2024-07-16 152720](https://github.com/user-attachments/assets/c35dc46a-f852-467a-be1f-af4c928a6e9f)
![Captura de tela 2024-07-16 152734](https://github.com/user-attachments/assets/0cf4cb05-9d03-49c3-8997-9ccccd4dc3f3)
![Captura de tela 2024-07-16 152759](https://github.com/user-attachments/assets/bf66c759-b346-4dcd-a013-0f77239795cb)

# Estrutura de banco de dados



# Usuários (Users)
user_id: ID único do usuário (Chave primária)
name: Nome do usuário
date_of_birth: Data de nascimento
email: Endereço de e-mail único
password_hash: Hash da senha
verified: Indica se a conta está verificada (booleano)
created_at: Data e hora de criação da conta

# Vídeos (Videos)
video_id: ID único do vídeo (Chave primária)
user_id: ID do usuário que publicou o vídeo (Chave estrangeira referenciando Users)
video_path: Caminho do arquivo de vídeo armazenado
format: Formato do vídeo (e.g., mp4, avi)
size: Tamanho do vídeo em bytes
created_at: Data e hora de publicação do vídeo

# Fotos (Photos)
photo_id: ID único da foto (Chave primária)
user_id: ID do usuário que publicou a foto (Chave estrangeira referenciando Users)
photo_path: Caminho do arquivo de foto armazenado
format: Formato da foto (e.g., jpg, png)
size: Tamanho da foto em bytes
created_at: Data e hora de publicação da foto

# Postagens (Posts)
post_id: ID único da postagem (Chave primária)
user_id: ID do usuário que criou a postagem (Chave estrangeira referenciando Users)
content: Conteúdo textual da postagem
created_at: Data e hora de publicação da postagem
updated_at: Data e hora da última atualização da postagem

# Comentários (Comments)
comment_id: ID único do comentário (Chave primária)
post_id: ID da postagem comentada (Chave estrangeira referenciando Posts)
user_id: ID do usuário que fez o comentário (Chave estrangeira referenciando Users)
content: Conteúdo do comentário
created_at: Data e hora de publicação do comentário
updated_at: Data e hora da última atualização do comentário

# Curtidas (Likes)
like_id: ID único da curtida (Chave primária)
post_id: ID da postagem curtida (Chave estrangeira referenciando Posts)
user_id: ID do usuário que curtiu a postagem (Chave estrangeira referenciando Users)
created_at: Data e hora da curtida

# Amigos (Friends)
user_id: ID do usuário (Chave estrangeira referenciando Users)
friend_id: ID do amigo (Chave estrangeira referenciando Users)
status: Status da amizade (e.g., pendente, aceito)
created_at: Data e hora de criação da relação de amizade

# Configurações da Conta (Settings)
user_id: ID do usuário (Chave estrangeira referenciando Users)
privacy_settings: Configurações de privacidade (armazenadas em JSON)
notification_settings: Configurações de notificações (armazenadas em JSON)
other_preferences: Outras preferências da conta (armazenadas em JSON)
updated_at: Data e hora da última atualização das configurações

# Relacionamentos
Um usuário pode publicar vários vídeos (Users ↔ Videos)
Um usuário pode publicar várias fotos (Users ↔ Photos)
Um usuário pode criar várias postagens (Users ↔ Posts)
Uma postagem pode ter vários comentários (Posts ↔ Comments)
Uma postagem pode ter várias curtidas (Posts ↔ Likes)
Um usuário pode ter vários amigos e ser amigo de vários usuários (Users ↔ Friends)
Um usuário tem uma configuração de conta (Users ↔ Settings)
