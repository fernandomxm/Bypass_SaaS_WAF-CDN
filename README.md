# Bypass_SaaS_WAF-CDN

**O que significa WAF?**

WAF significa Web Application Firewall e é uma coleção de ferramentas de segurança para proteger um site contra diversos ataques e ameaças. Um WAF opera na camada de aplicação do modelo OSI. Analisa solicitações HTTP e aplica um conjunto de regras para identificar e bloquear tráfego suspeito. Quando se trata de web scraping, os WAFs representam um grande obstáculo. Isso ocorre porque as solicitações de scraping geralmente aparecem como um ataque a um WAF, especialmente ao extrair dados em alta taxa ou em grandes volumes.

**É possível ignorar um WAF?**

Sim, o desvio do WAF é possível. Mas como os WAFs usam muitas técnicas de segurança, não existe uma solução única para todos. Estes são vários dos métodos de proteção mais populares que você precisa saber como contornar:

Reputação de endereço IP: Bloqueio de solicitações provenientes de IPs marcados como não confiáveis ​​ou perigosos. Você pode evitar isso com um proxy de web scraping .
CAPTCHAS: Problemas mostrados nas páginas da web que são fáceis de resolver para humanos, mas complexos para bots. Um proxy CAPTCHA irá ajudá-lo a contorná-los.
Honeypots: Armadilhas para bots incorporados em páginas da web que são invisíveis para usuários humanos. Saiba mais sobre como contornar um honeypot .
Análise do comportamento do usuário: Rastreando a atividade do usuário em uma página da web para determinar se é um bot. Evite isso fazendo com que seu scraping bot simule um ser humano com um headless browser.
Device fingerprinting: procura por recursos de hardware e software que normalmente apenas o dispositivo de um usuário real possui. Aprofunde-se na browser fingerprinting e como ultrapassar essa barreira.

**Qual WAF eu preciso ignorar?**

Saber de qual WAF seu site alvo depende é crucial para construir um web scraper eficaz. Siga as etapas abaixo para saber como identificar um WAF:

Explore seu site de destino no navegador . 
Procure métodos de proteção evidentes : os WAFs mais populares informam os usuários sobre o que está acontecendo ao aplicar medidas rigorosas anti-bot. Essas páginas de controle geralmente apresentam o nome do provedor, que é essencial saber.

**WAFs populares que você precisa conhecer**

Os fornecedores de WAF mais populares no mercado são poucos. E como todos adotam diferentes tecnologias de proteção anti-bot e políticas de segurança, criamos guias específicos para ajudá-lo a contornar cada um deles:

Cloudflare: Oferece um conjunto de soluções de segurança para proteger sites de diversos tipos de ataques. Cerca de 20% de todos os sites da Internet o utilizam. Aprenda como contornar o Cloudflare .
Akamai: Aproveita o aprendizado de máquina para bloquear ataques em tempo real. Você descobrirá como ignorar a Akamai aqui.
PerimeterX: explora a análise comportamental para proteger aplicativos da web contra muitas ameaças. Confira nosso guia para encontrar instruções passo a passo sobre como ignorar o PerimeterX .
DataDome: fornece uma tecnologia de detecção de bot para evitar ataques automatizados. Você pode ignorar o DataDome com a ajuda de nosso tutorial detalhado.
Não importa qual tecnologia seu site de destino utilize, você pode ignorar seu WAF com uma API de web scraping completa.

**Técnicas para contornar o WAF**

Vamos ver as melhores dicas e métodos para contornar as defesas do WAF.

1. Use IPs residenciais
Uma solução eficaz para evitar o banimento de IP é fazer solicitações HTTP através de um servidor proxy. Normalmente oferecem:

IPs de data center : endereços provenientes de data centers e não associados a nenhum ISP.
IPs residenciais : endereços atribuídos pelos ISPs a dispositivos reais em um local específico.
IPs móveis : endereços atribuídos pelas operadoras móveis a dispositivos individuais. Eles são úteis para extrair sites que mostram conteúdo diferente para usuários móveis.
Os endereços IP do datacenter são baratos, mas a maioria dos WAFs consegue identificá-los sem esforço. Os IPs residenciais são, em vez disso, muito mais confiáveis. Leia nosso guia dos melhores provedores de proxy para web scraping para ver uma lista de ótimas opções.

2. Execute Fortified Headless Browsers
Navegadores headless são uma ótima ferramenta para raspar sites que precisam de JavaScript. Ainda assim, seu objetivo principal é construir testes automatizados. Assim, eles não tentam se esconder e podem definir cabeçalhos ou variáveis ​​especiais, o que ajuda os WAFs a reconhecer suas solicitações.

Existem algumas bibliotecas para substituir esse comportamento padrão. Por exemplo, undetected_chromedrivercorrige o Selenium para prepará-lo para scraping e puppeteer-extra-plugin-stealthfaz o mesmo para Puppeteer e Playwright. Eles podem ajudá-lo com o desvio do WAF.

3. Web Scraping API
Uma API de scraping é uma ótima alternativa para evitar ser bloqueado por WAFs. Esta tecnologia fornece proxies premium e implementa técnicas anti-bot sofisticadas, eliminando todas as dores de cabeça.

Suponha que você queira criar um script de web scraping em Python para extrair dados da página de revisão G2 do Asana, que é protegida pela Cloudflare: https://www.g2.com/products/asana/reviews

4. Acesso para o servidor Origin
A ideia por trás de um WAF é criar uma rede de firewall e proteger o conteúdo dentro dela. Mas e se você pudesse passar por ele e entrar em contato diretamente com o servidor de origem para contornar todas as defesas?

Primeiro, use serviços como Shodan ou ferramentas como CloudFlair para obter o endereço IP do servidor host. Em seguida, forje algumas solicitações para que pareçam vir de um nome de domínio válido e entre em contato com o servidor.

Tenha em mente que esta técnica nem sempre é possível porque encontrar o IP do servidor de origem é difícil para a maioria dos alvos. Além disso, falsificar as solicitações certas exige tempo e esforço.

5. Use solucionadores WAF
Estas são ferramentas ou serviços que afirmam ser capazes de contornar os desafios do WAF. Eles funcionam analisando os métodos de proteção e modificando o tráfego HTTP de acordo. Alguns solucionadores WAF populares são:

BypassWAF: tenta superar firewalls procurando registros DNS A antigos e verificando se o servidor de origem responde a esse domínio.
Cfscrape: um módulo Python de código aberto que permite contornar a proteção Cloudflare. 
Cloudscraper: Uma biblioteca Python para evitar a sala de espera do Cloudflare, também conhecida como " I'm Under Attack Mode " (IUAM).
A maioria dessas soluções funciona por um tempo limitado, pois não são mantidas ou atualizadas.

6. Faça engenharia reversa do desafio JavaScript
Os desafios de JavaScript envolvem código injetado na página pelo WAF. O navegador executa o snippet e o supera de forma transparente. Se o raspador não conseguir resolver o teste, ele será marcado como bot e bloqueado.

Essa é uma das proteções mais comuns usadas pelos WAFs. Veja por que você precisa saber como contorná-lo. A única maneira de fazer isso é analisar o snippet injetado, fazer engenharia reversa do código JavaScript e estudar como o desafio funciona.

Para obter um exemplo do mundo real, confira nosso guia sobre como enfrentar o desafio da “sala de espera” da Cloudflare .

7. Contorne os CAPTCHAs
CAPTCHAs são uma ferramenta comum que os sites usam para impedir que bots acessem seu conteúdo. Para contorná-los, você tem duas soluções:

Serviços de resolução de CAPTCHA : geralmente são caros e sujeitos a falhas. 
Evite que eles apareçam : Proxies oferece ferramentas para ajudá-lo a evitá-los em primeiro lugar.
Na maioria dos casos, a segunda opção é a solução mais eficaz. Consulte nosso guia sobre os melhores proxies CAPTCHA para saber mais.

8. Não caia nas armadilhas do Honeypot
As armadilhas do Honeypot envolvem páginas, links ou formulários falsos que os usuários humanos não podem ver, mas são visíveis para os bots. Quando um visitante automatizado interage com eles, o site pode detectá-los e bani-los.

Torne seu bot inteligente para evitar cair nessas armadilhas. Não clique em links não visíveis nem preencha campos ocultos do formulário. Ignore a interação com display: noneelementos HTML e certifique-se de que sua página de destino seja real.

Para obter mais informações, leia nosso artigo sobre o que é uma armadilha honeypot e como contorná-la .

9. Bypass Browser Fingerprinting
A impressão digital do navegador trata da coleta de informações no navegador de um usuário. A ideia é aproveitar esses dados para identificar exclusivamente um usuário e limitar o número de solicitações permitidas. Visite nosso artigo sobre impressão digital do navegador para saber mais sobre como funciona.

Uma abordagem específica para este método WAF é a impressão digital da tela . Um script força o navegador a gerar uma imagem usando as especificações do navegador do usuário como parâmetros. Diferentes computadores renderizarão diferentes imagens de tela, facilitando a identificação do usuário com base nisso.

10. Contorne a impressão digital TLS
A impressão digital TLS é um método para reconhecer um usuário estudando os parâmetros trocados durante o handshake TLS entre cliente e servidor.

Os WAFs observam e registram todas as conexões TLS. Eles rastreiam quem inicia uma conversa com o servidor e decidem se bloqueiam ou permitem a solicitação. Explore como contornar o WAF usando essa tecnologia em nosso guia sobre impressão digital TLS .

11. Entenda o rastreamento de eventos
Os WAFs continuam coletando dados sobre o usuário. Eles observam quando, como e com quais elementos você interage. Ao procurar padrões conhecidos, eles podem dizer se você é humano.

Uma forma de impedir essa proteção é programar seu bot para se comportar da maneira mais natural possível com a ajuda de um headless browser.

**Conclusão**

Você aprendeu um pouco sobre como contornar a proteção WAF:

O que é WAF e quais são os provedores mais comuns.

Se é possível contornar isso.

Quais são as defesas mais comuns utilizadas por essas tecnologias.

As técnicas aqui apresentadas são apenas parte de todo o arsenal disponível aos WAFs. 

Além disso, estas medidas de proteção continuam a evoluir e contorná-las torna-se cada dia mais difícil. 

Encontrar soluções alternativas e mantê-las atualizadas exige muito tempo e esforço.

**MUITO IMPORTANTE SEMPRE FECHAR ESSE BYPASS**
