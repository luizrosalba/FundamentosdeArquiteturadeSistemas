
# A arquitetura de aplicações móveis e internet das coisas

## Internet das coisas 
arpanet 
Protocolo MQTT (message queue telemassage transport)  é um protocolo de mensagens assíncronas (machine to machine - M2M) mais utilizado para IOT (linguagem que o smartphone rodando android) para se comunicar com a cloud 
free rtos -> sistema operacional real time 
Modelo publish / subscribe -> modelo de comunicação do MQTT 

 

Publicador/ Publisher:  Quem envia dados para um tópico, emissor.
Subscrito/ Subscriber:  Pessoa que está inscrita no tópico e recebe os dados, receptor.
Broker: Intermédio de comunicação entre Publicador e Subscrito, responsável por receber, enfileirar e enviar as mensagens.
Payload: Conteúdo da mensagem enviada.
Cliente/Client: Elemento capaz de interagir com o Broker, seja para enviar, receber ou os dois.
Mensagem: Pacote de dados trocados entre Clientes e Broker.
Tópico: Endereço para o qual os dados serão encaminhados.
Unsubscribe: Deixar de assinar um tópico.


![](https://github.com/luizrosalba/FundamentosdeArquiteturadeSistemas/blob/master/Capturar2.PNG?raw=true)

pub mqtt://my-tracker.com/identificador_usuario/gps/position{'lat:-23.53,'Ion':-43.81}
topico(ex: /gps/position) : endereço onde se entrega a informação , definido pelo usuario 

mqtt     :// my-tracker.com  /identificador_usuario   /gps      /position            {'lat:-23.53,'Ion':-43.81}
protocolo    broker           identificador           sensor    tipo de informaçao 

mqtt://my-tracker.com/+/gps/position{'lat:-23.53,'Ion':-43.81}
+ é um caractere corigna que faz com que o broker entregue a posição geográfica de todos os usuarios 
pub mqtt://my-tracker.com/identificador_usuario/gps/+
pega todas as informações do gps 
mqtt://my-tracker.com/+/#
# é um caractere corigna que recebe todas as informações de todos os sensores de todos os usuarios 

QOS -> niveis de qualidade de serviço 
QoS 0 (at most once)- A mensagem deve ser recebida no máximo uma vez, podendo ser recebida uma vez ou nenhuma, não há confirmação de recebimento.
QoS 1 (at least once)- A mensagem deve ser recebida pelo menos uma vez, podendo uma mesma mensagem ser recebida uma ou mais vezes, há confirmação de entrega de uma mensagem.
QoS 2 (exactly once)- A mensagem deve ser recebida uma única vez, confirmação de recebimento de uma única mensagem.

- prova de conceito 
app android -> mosquito -> node.js-> banco de dados mysql 
Mosquito -> Broker executável em linux que consegue publicar dados de um android 
-minimo produto viavel 
GPS embarcado -> HiveMq-> akkaScala JVM ->banco de dados nosql 
-Solução 
GPS embarcado -> aws iot core -> aws kinesis firehose -> aws s3 


