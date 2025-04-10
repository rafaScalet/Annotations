## Problema

Um problema muito comum, e que diversas pessoas já documentaram na internet, é ao enviar notificações aos usuários do seu sistema, por exemplo, muitos devs fazem o sistema de notificação muito acoplado ao resto do sistema, e quando é necessário adicionar outro meio de notificação, acaba sendo uma tarefa muito complexa. Vamos supor que um sistema envie notificações de atualizações por e-mail, e o dono do sistema quer poder deixar o usuário escolher entre SMS, WhatsApp entre outros, este é o problema que vamos resolver com padrões de projetos

## Padrões Escolhidos

Foi usado principalmente o padrão `Factory Method` para resolver o problema por diversos motivos, mas também foi usado o `Strategy` e o `Observer` para tornar mais fácil a manutenibilidade do código.

## Justificativa do Uso

- ***Factory Method ->*** O `factory` talvez seja o padrão mais óbvio de se aplicar a esta situação, pois resolve a maioria dos problemas, que era adicionar novos métodos de notificações. A ideia é criar uma interface para a criação de objetos, mas deixar que as subclasses decidam qual classe instanciar. Neste caso, uma classe base de `NotificationFactory` é criada, e subclasses como `EmailNotificationFactory`, `SMSNotificationFactory`, e `WhatsAppNotificationFactory` se tornam responsáveis pela criação dos tipos específicos de notificação, desta forma já foi resolvido o problema de notificações.


- ***[[Strategy]] ->*** O `strategy` aqui, pode ser usado para substituir o `factory`, mas também pode ser usado em conjunto ao mesmo, ele pode ser aplicado aqui para definir diferentes algoritmos de envio de notificações, permitindo que a lógica de envio (por exemplo, envio de SMS, envio de email) seja desacoplada da classe de notificação. Isso permite que novos métodos de envio sejam adicionados sem afetar o resto do código, facilitando a extensão do sistema com novos tipos de notificação sem alterar a estrutura de classes existentes.

- ***Observer ->*** O `Observer` (pelo menos no caso em que estou me inspirando) foi usado somente como um facilitador para integração a outros sistemas, como `logs e monitoramento`, ele não teve um papel realmente crucial para a resolução do problema, mas pode ser usado para evitar mais problemas futuros, por permitir uma integração mais rápida e melhor a outros sistemas.