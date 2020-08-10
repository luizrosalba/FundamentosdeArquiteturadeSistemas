
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

