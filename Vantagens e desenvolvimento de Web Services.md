
# Web Service

- Soluções para que aplicações se comuniquem independentemente de linguagem, software e hardwares utilizados 

- Inicialmente foram criados para troca de mensagens usando xlm(extensible markup language) sobre o protocolo http sendo identificado por uri (uniform resource identifier) 

- Podemos dizer que serviços web são api's que se comunicam por meio de redes sobre o protocolo http 

- Uma aplicação x acessa um web service que faz troca de  mensagens com a aplicação y usando , xml , json, yaml ... 

SOAP 
REST 
XML 
JSON 

linguagens de marcação -> usadas para comunicação entre aplicações 

## Estrutura Soap 

SOAP = simple object access protocol 

- Baseado em xml para acessar serviços web por http 
- É uma definição de como serviços web se comunicam 
- Desenvolvido para facilitar integrações entre aplicações em diferentes linguagens
- Independe de plataforma e software
- Meio de transporte genérico pode ser usado por outros protocolos além do http 

XML = Extensible Markup Languange 

- criada na décade de 90 pela W3C 
- Facilita a separação de conteúdo 
- Não tem limitação de criação de tags 

Estrutura SOAP 

- O soap message possui uma estrutura unica que deve ser sempre seguida 
- soap envelope (container) -> soap header -> soap body 
- Envelope é usado para encapsular toda a mensagem soap 
- header elemento que possui informações de atributos e metadados da requisição 
- body contem os detalhes da mensagem 

ex : 
```Javascript
<soap:Envelope xmlns:soap="endereço/soap-envelope"> 
<soap:Header> 
</soap:Header> 
<soap:Body>
<m:MetodoEndereco xmlns:m="endereco/endereco"> 
<m:Cidade> nomecidade </m:Cidade>
<m:CEP> numcep </m:CEP>
<m:Numero> num </m:Numero>
<m:Endereco>
</soap:Body>
</soap:Envelope> 
```

## Entendendo o que é WSDL e XSD
WSDL 
- Web Service Description Language 
- Descreve Web Services funciona como um contrado do serviço 
- A descrição é feita em um documento XML, onde é descrito o serviço , especificiações de acesso , portas, métodos ,etc; 

XSD 
- XML Schema Definition 
- É um schema no formato XMl usado para definir a estrutura de dados que será validada no xml 
- Funciona como uma documentação de como deve ser montado o SOAP Message (XML) que será enviado através do Web Service 

- http://www.soapclient.com/xml/soapresponder.wsdl
- https://www.soapui.org/.

documentation => Descrição do que o serviço faz 

Python zeep -> cliente soap para python 

## Aprenda o que são REST, API e JSON
Rest 
- Representational State Transfer 
- É um estilo de arquitetura de software que define a implementação de um serviço web 
- Podem trabalhar com os formatos XML , JSON ou outros 
- utiliza http para definir a operação que está sendo efetuada 
![](https://github.com/luizrosalba/FundamentosdeArquiteturadeSistemas/blob/master/Capturar.PNG?raw=true)

API : 

- Application Programmin Interface
- São conjuntos de rotinas documentadas e disponibilizadas por uma aplicação para que outras aplicações possam consumir suas funcionalidades
- Popular com o aumento dos serviçoes web 
- Facebook , Twitter , Telegram , Wzap , Github ... 
- Apis podem ser rest , json , etc... 


Métodos HTTP : 

- GET  solicita a representação de um recurso ( ex pegar um tweet) 
- POST solicita a criação de um recurso (ex criar um tweet)
- DELETE solicita a exclusão de um recurso 
- PUT  solicita a atualização de um recurso (ex atualiza o texto do twwt)

Para um serviço web ser considerado rest, deve seguir esta arquitetura . get representa, post cria, delete exclui e put atualiza. 

JSON 
- JSON Javascript Object Notation  ( apesar de poder ser usada em qquer linguagem) 
- Formatação leve utilizada para troca de mensagens entre sistemas 
- Usa-se de uma estrutura de chave e valor e também de listas ordenadas 
- Um dos formatos mais populares 

ex: 
```Javascript
{
 "nome": "Os vingadores". 
 "ano": "2019", 
 "personagens":[
 {
  "nome": "Thanos" 
 },
 {
  "nome": "thor" 
 },
 {
  "nome": "Hulk" 
 }
 ]
}
```

## Integração com REST e métodos HTTP na prática

Código de Estado (Status Code) 

Usado pelo servidor para avisar o cliente sobre o estado da operação solicitada 

- 1xx - informativo 
- 2xx sucesso 
- 3xx redirecionamento 
- 4xx erro do cliente 
- 5xx erro do servidor 




