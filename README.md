> **Warning**
> 
> [DEPRECATED]  
> A tecnologia em uso neste projeto encontra-se obsoleta e sem viabilidade técnica de execução. Os arquivos estão mantidos neste repositório apenas para fins de demonstração e documentação. 


# Sobre o Projeto WAP-CRT:

Em meados de 1999, coordenei a iniciativa do Núcleo de Informática da Central Alto Petrópolis para a implantação de uma Intranet unificada de todas as centrais telefônicas da CRT, Companhia Riograndense de Telecomunicações.
Optou-se pela tecnologia **WAP/WML** devido às limitações da velocidade da Internet sem fio (GPRS) naquela época (entre 9,6 e 19,2 Kbps), e pelas limitações impostas pelo pequeno tamanho de tela dos dispositivos móveis utilizados pelos colaboradores da companhia (público-alvo da iniciativa).
O objetivo era implementar uma **Intranet WAP** com informações em tempo-real visando otimizar as rotinas operacionais dos colaboradores de atividades externas (cabistas, instaladores, fiscais de rede, entre outros). 


# Coordenação do Projeto:

Fermyno Gutierrez  
**Núcleo de Informática da Central Alto Petrópolis**  
**Diretoria de Operações**

# Sobre a Empresa:

A **CRT (Companhia Riograndense de Telecomunicações)** foi a operadora estatal de telefonia do estado do Rio Grande do Sul, Brasil, e contava na época com aproximadamente 10.000 funcionários e 5 milhões de linhas telefônicas ativas. 
Em 1993, foi considerada pela revista Exame como a melhor empresa de serviços públicos do país. 
Em 1998, foi privatizada e vendida para a **Telefonica de Espanha**. Em 2000, foi repassada para a **Brasil Telecom.** Em 2008, o controle acionário da companhia foi transferido para a operadora de telefonia **Oi**.

# Resumo da Análise de Requisitos (RFP)

## Requisitos Funcionais:

O portal deve permitir o fornecimento de informações em tempo-real, tais como:
- Condições climáticas para a execução de atividades de eletricidade em área exterior,
- Interrupções técnicas programadas e não-programadas que afetam a normalidade dos serviços,
- Telefones de contato para resolução de problemas rotineiros,
- Manuais e procedimentos internos,
- Controle de execução de ordens de serviço,
- Entre outros.

## Requisitos Não-funcionais:

- A Intranet WAP deve rodar nos servidores web já existentes na organização (Apache + PHP4),
- As informações fornecidas no portal devem ser compatíveis com os seguintes aparelhos: Motorola Timeport P7389, Ericsson Model R380, Ericsson Model R320, Nokia 6210, demais aparelhos com função de navegação WAP padrão.
- O desenvolvimento do portal deve ser realizado em linguagem WML e WMLScript.
- O tempo de carregamento de cada página não pode superar os 20 segundos.


# Configuração do Servidor Apache:

O **servidor web Apache** deve estar configurado para reconhecer a linguagem WML (Wireless Markup Language). Para tanto, no caso de servidores apache, o conteúdo a seguir deve ser adicionado ao arquivo **httpd.conf** (sem essas linhas o Apache não reconhecerá o formato WML e tentará enviar o arquivo para download).

Linhas que devem ser adionadas ao httpd.conf:

    # MIME Types for WAP
    # For PHP 4.x, use this:
    AddType application/x-httpd-php .wml
    AddType text/vnd.wap.wml .wml
    AddType image/vnd.wap.wbmp .wbmp 

    
# Implantação do Projeto-Piloto:

Com o objetivo de verificar objetivamente a viabilidade do projeto, foi colocada em prática a implantação de um projeto piloto como esforço temporário para testar a exequibilidade da solução apresentada.
Com a duração aproximada de três meses, o projeto-piloto contou com o apoio do Núcleo de Informática da Central Alto Petrópolis e da Diretoria de Operações da CRT, e envolveu a participação de 14 pessoas nos testes de campo, onde foi possível mensurar os seguintes pontos específicos:
- foi confirmado o correto funcionamento do servidor web Apache como solução de hospedagem das páginas em WML e WMLScript,
- foi confirmado o correto funcionamento dos links das páginas da Intranet WAP,
- foi confirmado que o sistema cumpre com os requisitos (funcionais e não-funcionais) propostos,
- foi constatada uma dificuldade inicial na utilização do navegador wap pelos utilizadores de campo, o que exigiu a realização de um rápido treinamento de aproximadamente cinco minutos. 

Embora o projeto-piloto tenha tido grande aceitação por parte da empresa, com a rápida evolução tecnológica, o wap tornou-se rapidamente obsoleto e optou-se por desenvolver uma nova versão da intranet em HTML/PHP.

Em 2000, com a saída do acionista majoritario (Telefonica de Espanha) e ingresso de novo acionista (Brasil Telecom), o projeto ficou em segundo plano, sendo posteriormente cancelado.
<br />

# Capturas de Tela do Projeto-piloto:

### index.wml
![](https://raw.githubusercontent.com/fermyno/wap-crt/main/screenshots/wap-crt-index.png)
**index.wml**
```xml
<?xml version="1.0"?>
<!DOCTYPE wml PUBLIC "-//WAPFORUM//DTD WML 1.1//EN" "http://www.wapforum.org/DTD/wml_1.1.xml">
<wml>
<template>
	<do name='prev' type='prev' label='Voltar'>
		<prev/>
	</do>
</template>
<card id='index' title='Intranet WAP CRT'>
	<do name='index' type='index' label='About:'>
		<noop/>
	</do>
    <p>
       <img src='images/crt-logo.wbmp' width='79' height='25' alt='CRT'/>
    </p>
	<p>
	   <small>
          Bem-vindo ao portal WAP da Companhia Riograndense de Telecomunica&ccedil;&otilde;es.
       </small>
	</p>
	<p>
	   <small>
          Selecione:
       </small>
	</p>
    <p>
       <a href='crt-avisos.wml'>Avisos &Uacute;teis</a><br/>
       <a href='crt-telefones.wml'>Telefones</a><br/>
       <a href='crt-plantao.wml'>Escala de Plant&atilde;o</a><br/>
       <a href='crt-sobre.wml'>Sobre a Iniciativa</a><br/>
    </p>
</card>
</wml>
```
<br />
<br />

### crt-avisos.wml
![](https://raw.githubusercontent.com/fermyno/wap-crt/main/screenshots/wap-crt-avisos.png)
```xml
code.xml
```
<br />
<br />

### crt-telefones.wml
![](https://raw.githubusercontent.com/fermyno/wap-crt/main/screenshots/wap-crt-telefones.png)
```xml
code.xml
```
<br />
<br />

### crt-plantao.wml
![](https://raw.githubusercontent.com/fermyno/wap-crt/main/screenshots/wap-crt-plantao.png)
```xml
code.xml
```
<br />
<br />

### crt-sobre.wml
![](https://raw.githubusercontent.com/fermyno/wap-crt/main/screenshots/wap-crt-sobre.png)
```xml
code.xml
```
<br />

