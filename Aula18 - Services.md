# Services

- Services
  - Foreground
  - Bind
 
- É um componente de aplicativo capaz de **executar operações de longa duração em segundo plano**

- Não oferece uma interface do usuário

- Pode se **vincular** a um serviço para **interagir** com ele e **até realizar comunicaçõa entre processos (IPC)**

  - Um serviço pode **processar transações de rede, trocar música, executar E/S de arquivos**
 
- **Precisa das permissões**
  - **FOREGROUND SERVICE (>= Android 9(API 28))**
  - **Outros componentes do sistema (GPS, Camera, Wifi etc)**
 
## Service - Primeiro plano

- Primeiro plano
  - Executa alguma **operação perceptível** para o usuário
    - Um app de áudio usaria um **serviço em primeiro plano para tocar uma faixa de áudio**

  - Os serviços em primeiro plano **precisam exibir uma Notificação** para que os usuário estejam **ativamente cientes** de que o serviço está em execução
    - Essa notificação **não pode ser dispensada, a menos que o serviço seja interrompido ou removido do primeiro plano**
      - OBS: No Android 13 usuários podem dispensar a notificação associada a um serviço em primeiro plano por padrão
