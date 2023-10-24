Um dos principais recursos de uma plataforma de identidade é verificar ou autenticar as credenciais quando um usuário entra em um dispositivo, um aplicativo ou um serviço.

## Métodos de autenticação

### Senhas

As senhas são a forma mais comum de autenticação. O uso de senhas deve ser complementado ou substituído por métodos de autenticação mais seguros disponíveis no Microsoft Entra ID.

### Telefone

O Microsoft Entra ID dá suporte a duas opções de autenticação baseada em telefone.

- **Autenticação baseada em SMS**: O usuário insere seu número de telefone celular registrado, recebe uma mensagem de texto com um código de verificação e insere isso na interface de entrada. Pode ser usado como segundo fator de autenticação.

- **Verificação por chamada de voz**:  Somente usado como segundo fator de autenticação. Com a verificação por chamada telefônica, uma chamada de voz automatizada é feita para o número de telefone registrado pelo usuário. Para concluir o processo de entrada, o usuário será solicitado a pressionar # no teclado.

## OATH

OATH (Open Authentication) é um padrão aberto que especifica como os códigos de TOTP (one-time password)  são gerados. Podem ser implementadas usando software ou hardware para gerar os códigos. É usado como segundo fator de autenticação

- **Tokens OATH de software** normalmente são aplicativos. O Microsoft Entra ID gera a chave secreta, ou semente, que é inserida no aplicativo e usada para gerar cada OTP.
    
- **Tokens de hardware OATH TOTP** (preview) são pequenos dispositivos de hardware que se parecem com um chaveiro que exibe um código que é atualizado a cada 30 ou 60 segundos. Os tokens de hardware OATH TOTP normalmente vêm com uma chave secreta, ou semente, pré-programada no token. Essas chaves e outras informações específicas de cada token devem ser inseridas no Microsoft Entra ID e, em seguida, ativadas para serem utilizadas pelos usuários finais.

### Autenticação sem senha

O Microsoft Entra ID fornece maneiras de autenticar nativamente usando métodos sem senha para simplificar a experiência de entrada dos usuários e reduzir o risco de ataques.

- **Windows Hello for Business:** autenticação de dois fatores, é uma combinação de uma chave ou de um certificado vinculado a um dispositivo e de algo que a pessoa saiba (um PIN) ou é (biometria). A entrada do PIN e o gesto biométrico disparam o uso da chave privada para assinar criptograficamente os dados que são enviados ao provedor de identidade. O provedor de identidade verifica a identidade do usuário e autentica o usuário.
- **FIDO2:** (Fast Identity Online) é o padrão mais recente que incorpora o padrão de autenticação da Web (WebAuthn) e tem suporte do Microsoft Entra ID. As chaves de segurança FIDO2 são um método de autenticação de senha baseado em padrões à prova de phishing, que podem usar qualquer fator forma. Essas chaves de segurança FIDO2 normalmente são dispositivos USB, mas também podem ser dispositivos Bluetooth ou dispositivos baseados em NFC. Com um dispositivo de hardware que manipula a autenticação, a segurança de uma conta é aumentada, pois não há senha que possa ser exposta ou adivinhada.
- **Microsoft Authenticator:** Com a conexão sem senha, o aplicativo Authenticator transforma qualquer telefone iOS ou Android em uma credencial forte e sem senha. Para entrar na conta do Microsoft Entra ID, o usuário insere seu nome de usuário, faz a correspondência entre o número exibido na tela e o número do telefone e, em seguida, utiliza a biometria ou o PIN para confirmar.
- **Certificado:** A autenticação baseada em certificado (CBA) do Microsoft Entra Identity habilita os clientes a permitir ou exigir que os usuários se autentiquem diretamente com certificados X.509 em relação ao Microsoft Entra Identity, para aplicativos e entrada no navegador. O CBA tem suporte apenas como forma primária de autenticação sem senha.

## Autenticação primária e secundária

![[autenticacao_metodos.png]]