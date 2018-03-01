[checkmark]: https://raw.githubusercontent.com/mozgbrasil/mozgbrasil.github.io/master/assets/images/logos/logo_32_32.png "MOZG"
![valid XHTML][checkmark]

[requerimentos]: http://mozgbrasil.github.io/requerimentos/
[getcomposer]: https://getcomposer.org/
[uninstall-mods]: https://getcomposer.org/doc/03-cli.md#remove
[git-releases]: https://github.com/mozgbrasil/magento-base-php_54/releases
[artigo-composer]: http://mozg.com.br/ubuntu/composer
[ioncube-loader]: http://www.ioncube.com/loaders.php
[acordo]: http://mozg.com.br/acordo-licenca-usuario-final/
[tickets]: https://cerebrum.freshdesk.com/support/tickets/new

# Mozg\Base

## Sinopse

Módulo requerido para funcionamento dos demais módulos

## Motivação

Atender o mercado de módulos para Magento oferecendo um excelente suporte

## Suporte / Dúvidas

Para obter o devido suporte [Clique aqui][tickets], relatando o motivo da ocorrência o mais detalhado possível e anexe o print da tela para nosso entendimento

Se preferir, instale o respectivo plugin do Chrome para gravar o seu Screencast

https://chrome.google.com/webstore/detail/loom-video-recorder-scree/liecbddmkiiihnedobmlmillhodjkdmb

## Característica técnica

Uso interno

## Testando na Heroku

Gostaria de apresentar o aplicativo que disponibilizei para a plataforma Heroku

Com apenas 1 clique, o aplicativo cria sua loja virtual usando a plataforma de comércio eletrônico Magento e instala os módulos da MOZG

[https://github.com/mozgbrasil/heroku-magento#descrição](https://github.com/mozgbrasil/heroku-magento#descrição)

## Instalação - Atualização - Desinstalação - Desativação

--

Sugiro "printar" as telas com todos os procedimentos executados

Envie para nós as imagens das telas na eventualidade de quaisquer dificuldades

--

Este módulo destina-se a ser instalado usando o [Composer][getcomposer]

Execute o seguinte comando no terminal, para visualizar a existencia do Composer e sua versão

	composer --version

Caso não tenha o Composer em seu ambiente, sugiro ler o seguinte artigo [Clique aqui][artigo-composer]

--

É necessário que o servidor tenha o suporte a extensão [ionCube PHP Loader][ioncube-loader]

Execute o seguinte comando no terminal, para visualizar a existencia da extensão nesse ambiente denominado PHP CLI

	php -v

Para visualizar se essa extensão está ativa em seu servidor no ambiente denominado PHP WEB

Certique se da presença do arquivo phpinfo.php na raiz do seu projeto

	<?php phpinfo(); ?>

Caso não exista o arquivo phpinfo.php na raiz do projeto Magento, crie o mesmo adicionado o conteúdo acima

Acesse o arquivo pelo browser

Em seguida pesquise pelo termo "ionCube PHP Loader"

Caso o seu servidor não tenha o suporte a extensão, entre em contato com sua empresa de hospedagem e peça para que eles ativem a extensão

Caso tenha a permissão e queira ativar a extensão, [Clique aqui][ioncube-loader]

Em "Loader Downloads API", efetue download do pacote compatível com o seu servidor

Descompacte o pacote e faça upload do arquivo "loader-wizard.php" para seu servidor, onde será demonstrado o passo a passo para a ativação da extensão

[Clique aqui](https://youtu.be/GZ2J6MLkko4) para ver os processos executados

--

Na presença do "ionCube PHP Loader" efetue o download do seguinte arquivo e coloque na raiz do seu servidor e acesse, se funcionar quer dizer que o "ionCube" está lendo esse tipo de encriptação

https://raw.githubusercontent.com/mozgbrasil/heroku-magento/master/phpinfo-ioncube-encoder10-x86-64-php_54.php

--

Para utilizar o(s) módulo(s) da MOZG é necessário aceitar o [Acordo de licença do usuário final][acordo]

--

Sugiro manter um ambiente de testes para efeito de testes e somente após os devidos testes aplicar os devidos procedimento no ambiente de produção

--

Sugiro efetuar backup da plataforma Magento e do banco de dados

--

Antes de efetuar qualquer atualização no Magento sempre mantenha o Compiler e o Cache desativado

--

Certique se da presença do arquivo composer.json na raiz do seu projeto Magento e que o mesmo tenha os parâmetros semelhantes ao modelo JSON abaixo

	{
	  "minimum-stability": "dev",
	  "prefer-stable": true,
	  "license": [
	    "proprietary"
	  ],
	  "repositories": [
	    {
	      "type": "composer",
	      "url": "https://packages.firegento.com"
	    }
	  ],
	  "extra": {
	    "magento-root-dir": "./",
	    "magento-deploystrategy": "copy",
	    "magento-force": true
	  }
	}

Caso não exista o arquivo composer.json na raiz do projeto Magento, crie o mesmo adicionado o conteúdo acima

### Para instalar o módulo execute o comando a seguir no terminal do seu servidor no diretório do seu projeto

	composer require mozgbrasil/magento-base-php_54:dev-master

Você pode verificar se o módulo está instalado, indo ao backend em:

	STORES -> Configuration -> ADVANCED/Advanced -> Disable Modules Output

--

### Para atualizar o módulo execute o comando a seguir no terminal do seu servidor no diretório do seu projeto

Antes de efetuar qualquer processo que envolva atualização no Magento é recomendado manter o Compiler e Cache desativado

	composer update

Na ocorrência de erro, renomeie a pasta /vendor/mozgbrasil e execute novamente

Para checar a data do módulo execute o seguinte comando

	grep -ri --include=*.json 'time": "' ./vendor/mozgbrasil

### Para usar uma versão especifica do módulo

Primeiro acesse as versões disponibilizadas acessando os [releases][git-releases]https://github.com/mozgbrasil/magento-base-php_54/releases

Utilize a versão que atenda a data correspondente a seu arquivo de licença

Para isso altere no arquivo composer.json para a devida versão

    "require" : {
        "mozgbrasil/magento-base-php_54": "1.0.0"

Em seguida execute o comando a seguir no terminal do seu servidor

	composer update

--

### Para [desinstalar][uninstall-mods] o módulo execute o comando a seguir no terminal do seu servidor

	composer remove mozgbrasil/magento-base-php_54

--

### Para desativar o módulo

1. Antes de efetuar qualquer processo que envolva atualização sobre o Magento é necessário manter o Compiler e Cache desativado

2. Caso queira desativar os módulos da MOZG renomeie a seguinte pasta app/code/local/Mozg

A desativação do módulo pode ser usado para detectar se determinada ocorrência tem relação com o módulo

## Como configurar o método

Para configurar o método, acesse no backend em:

	STORES -> Configuration -> MOZG -> Geral

Você terá os campos a seguir

### Configurações Padrão

#### Recursos

##### • **Ativar estilo ao IWD_Opc**

Ativa o recurso

##### • **Ativar barra de progresso no painel de controle da loja virtual**

Ativa o recurso

##### • **Ativar barra de progresso na finalização do pedido**

Ativa o recurso

##### • **Ativar botão "Dump" na visualização do pedido**

Usado para analise de dados

##### • **Ativar botão "Trajeto" na visualização do pedido**

Mostra o trajeto entre o endereço da loja e do cliente

#### Debugar

##### • **Exibir nomes dos blocos**

Usado para debug

## Perguntas mais frequentes "FAQ"

### Sugestões importante

* Antes de efetuar qualquer atualização no Magento sempre mantenha o Compiler e o Cache desativado

* Sugiro efetuar backup da plataforma Magento e do banco de dados

* Sugiro "printar" as telas com todos os procedimentos executados e se necessário me envie as imagens das telas na eventualidade de quaisquer dificuldades

* Sugiro manter um ambiente de testes para efeito de testes e somente após os devidos testes aplicar os devidos procedimento no ambiente de produção

### Sobre exibição de parcelas para o produto

--

Devido a diversidade de praticas para a exibição de parcelas na visualização do produto, sugiro adotar uma das pratica a seguir

--

O seguinte módulo exibe o valor das parcelas com base em um valor para a parcela minima sendo exibido a descrição da parcela abaixo do preço do produto e na pagina do produto pode ser exibido a tabela das parcelas

https://github.com/franciscoprado/magentoprecoparcelado

Que pode ser instalado via composer

Para instalar o módulo via composer execute o seguinte comando na raiz do projeto

	composer require connect20/FranciscoPrado_PrecoParcelado

Conforme documentação do módulo, deve ser aplicado o suporte ao arquivo

	nano app/design/frontend/base/default/template/catalog/product/price.phtml

		<?php
		$modules = Mage::getConfig()->getNode('modules')->children();
		$modulesArray = (array)$modules;

		if (isset($modulesArray['FranciscoPrado_PrecoParcelado'])) {
		echo Mage::helper('franciscoprado_precoparcelado')->getPrice($this->getProduct()->getFinalPrice());
		}
		?>

--

Na necessidade de exibição de parcela na página de produto "somente", talvez o seguinte módulo deva atender sua necessidade, o mesmo usa o recurso de parcela minima, contando com algumas configurações

https://github.com/contardi/installments

Que pode ser instalado via terminal

	mkdir _temporario

	cd _temporario

	wget https://github.com/contardi/installments/archive/master.zip

	unzip master.zip

	cp -fr installments-master/* ../magento/

Conforme documentação do módulo, deve ser aplicado o suporte ao arquivo de catálogo (listagem e view)

	nano app/design/frontend/base/default/template/catalog/product/view.phtml

	nano app/design/frontend/smartwave/porto/template/catalog/product/view.phtml

	^W = price

		<?php echo $this->getChildHtml('preco_parcelado'); ?>
	    <?php echo $this->getChildHtml('preco_avista'); ?>
	    <?php echo $this->getChildHtml('installments'); ?>

--

# Como alterar o status do pedido

Devido o pedido estar com o status como "Revisão de pagamento" o Magento não permite "Cancelar" nessa etapa

Mas com o uso de módulo de terceiros ou desenvolvendo uma rotina você consegue alterar o status do Magento

Sugiro pesquisar na NET por "Magento Change Order"

Exemplos

https://marketplace.magento.com/xtento-advanced-order-status.html

https://amasty.com/order-status.html

### Como aplicar taxa de forma condicional

Provavelmente o seguinte módulo atenderá essa necessidade

https://github.com/yvoronoy/magento-extension-extra-fee

Vemos que o mesmo funciona sobre o recurso "Regras de promoção" nativo do Magento

### Reexecutar os scripts de setup do módulo

Execute o comando a seguir no MySQL para reexecutar os scripts de setup

    -- add table prefix if you have one
    DROP TABLE IF EXISTS mozg_boxpacker_packing_comment_store;
    DROP TABLE IF EXISTS mozg_boxpacker_packing_comment;
    DROP TABLE IF EXISTS mozg_boxpacker_packing_store;
    DROP TABLE IF EXISTS mozg_boxpacker_packing;
    DROP TABLE IF EXISTS mozg_api_debug;
    DROP TABLE IF EXISTS mozg_event_data;
    DROP TABLE IF EXISTS mozg_event_data_queue;
    DROP TABLE IF EXISTS mozg_order_payment;
    SELECT * FROM `core_resource` WHERE `code` like '%mozg%';
    DELETE FROM core_resource WHERE code like '%mozg%';
    SELECT * FROM `core_config_data` WHERE `path` like '%mozg%';
    DELETE FROM core_config_data WHERE path like '%mozg%';

### Como alterar as dimensões de produto(s)
### Como alterar atributo(s) de produto(s)

É nativo do Magento a possibilidade de selecionar registros na grade de dados de produto(s), podendo selecionar a ação de "atualizar atributos", em seguida será exibido a possibilidade de atualizar atributos em lote

### Como resgatar o código da transação do pedido

A referência do pagamento é armazenada na seguinte hierarquia do Magento

    order
         payment
                mozg_psp_reference

A seguir temos um exemplo

	$order_id = '1';
	$order = Mage::getModel('sales/order')->load($order_id);
	$payment = $order->getPayment();
	$psp_reference = $payment->getData('mozg_psp_reference');

### Onde os atributos de clientes ficam armazenadaos ?

É nativo do Magento que na tabela `eav_attribute` esteja registrado atributos e na tabela `eav_attribute_option_value` os registros para valores do tipo option "select"

    SELECT * FROM `eav_attribute` WHERE `attribute_code` = 'rg';

    SELECT * FROM `customer_eav_attribute` WHERE `attribute_id` = 218;

    SELECT * FROM `customer_entity_varchar` WHERE `attribute_id` = 218;

### Modificando a tradução do módulo para o template

Cada módulo tem o seu arquivo de tradução com a mesma nomenclatura do módulo

Os arquivos de tradução para português do Brasil no Magento é armazenado no diretório  

    /app/locale/pt_BR/

Recomendo não editar os arquivos nesse diretório pois em uma nova atualização de módulo esse arquivo deve ser atualizado com as informações do módulo

Na necessidade de trocar algum item

Edite o arquivo translate.csv presente no diretório do seu template para ser exibido um novo resultado

    /app/design/frontend/default/default/locale/pt_BR/translate.csv

Caso não exista a estrutura "/locale/pt_BR/translate.csv" em seu template apenas crie o arquivo nessa estrutura de diretório

Obs.

No Windows ou Mac sugiro usar o programa UltraEdit para edição do arquivo, dessa forma será mantido a codificação do arquivo em UTF-8

### Mage_Core_Exception: The requested Payment Method is not available. in /app/Mage.php:603
### ERRO: A forma de pagamento selecionada não está disponível

Esse erro é ocasionado caso o módulo relacionado ao método de pagamento esteja ausente no projeto

em

http://magento.stackexchange.com/questions/24307/the-requested-payment-method-is-not-available-on-order-details-page

vemos  que temos 2 opções:

- usar o módulo relacionado ao método de pagamento
- alterar o relacionamento do método a um módulo via banco de dados

Simulei um exemplo em meu ambiente local, pois não pretendo usar o módulo Cerebrum_Telencephalon e quero usar somente o novo pacote Mozg

Abaixo temos 2 instruções SQL a primeira retorna os métodos, a segunda executa a alteração do relacionamento

    SELECT * FROM `sales_flat_order_payment` WHERE `method` like '%cerebrum%' ;

    UPDATE `sales_flat_order_payment` SET `method`= 'mozg_cielo_api_cc'  WHERE `method` = 'cerebrum_cielo';

Abaixo temos os ID dos métodos

	# Telencephalon

	cerebrum_americanexpress
	cerebrum_banrisul_banricompras
	cerebrum_bancodobrasil
	cerebrum_bcash
	cerebrum_boleto_bradesco
	cerebrum_boleto_hsbc
	cerebrum_boleto_itau
	cerebrum_boleto_santander_banespa
	cerebrum_boleto_banespa
	cerebrum_boleto_bb
	cerebrum_boleto_bancoob
	cerebrum_banrisul_boleto
	cerebrum_boleto_cef
	cerebrum_boleto_cef_sigcb
	cerebrum_bradesco
	cerebrum_cielo
	cerebrum_meucheckout
	cerebrum_itaushopline
	cerebrum_mercadopago
	cerebrum_moip
	cerebrum_pagseguro
	cerebrum_pagador
	cerebrum_redecard

	# Mozg

	mozg_bancodobrasil_comercioeletronico_bb
	mozg_bancodobrasil_comercioeletronico_boleto
	mozg_bancodobrasil_comercioeletronico_eletronictransfer
	mozg_braspag_api_cc
	mozg_braspag_api_dc
	mozg_braspag_api_boleto
	mozg_braspag_api_eletronictransfer
	mozg_cielo_api_cc
	mozg_cielo_api_dc
	mozg_cielo_api_boleto
	mozg_cielo_api_eletronictransfer
	mozg_cielo_checkout_hpp
	mozg_bradesco_shopfacil_boleto
	mozg_bradesco_shopfacil_eletronictransfer
	mozg_redecard_komerci_cc
	mozg_itau_shopline_bankline
	mozg_itau_shopline_boleto
	mozg_pagseguro_api_lightbox
	mozg_pagseguro_api_padrao
	mozg_pagseguro_api_cc
	mozg_pagseguro_api_boleto
	mozg_pagseguro_api_eletronictransfer

### Sobre checkout(s)

Sugiro usar o checkout nativo do Magento

ou

Usar o seguinte checkout de compra em 1 passo

https://github.com/mozgbrasil/magento-iwd-opc#iwdopc

### Sobre o módulo "Inovarti_Onestepcheckout 2.0.3" - "One Step Checkout Brasil 6 Pro"

Disponibibilizado em https://github.com/deivisonarthur/OSC-Magento-Brasil-6-Pro

### Sobre o módulo "Ideasa_IdeCheckoutvm 1.8.0" - "Checkout Venda Mais"

Disponibibilizado em http://www.ipagare.com/

Conforme imagem

Veja que o módulo não deve funcionar corretamente quando ativado mais de 1 método de pagamento que tenha formulário como é o caso dos métodos de cartão de crédito ou débito, veja que o módulo ao invés de enviar somente os parâmetros do formulário relativo ao método de pagamento selecionado está sendo enviado todos os parâmetros de todos os formulários

https://drive.google.com/open?id=1qwNiJlS8JOz3s2JIYEOOLCDZZln3-188

https://drive.google.com/open?id=1PaBK_AdRTSzR_gYl7iTMy_AyaPYoTtAP

### Sobre a janela DHTML http://prototype-window.xilinus.com/

Foi detectado que no GoogleChrome não é exibido o Scroll da janela DHTML nativa do Magento, por isso do uso do Popup

### Como exibir as colunas "ID do Método de Pagamento" e "Status da Transacão"
### Sobre as colunas "ID do Método de Pagamento" e "Status da Transacão"

[![Clique para visualizar o vídeo](https://img.youtube.com/vi/FO7X3lvqLrQ/0.jpg)](https://youtu.be/FO7X3lvqLrQ "Clique para visualizar o vídeo")

Essas colunas foram adicionadas para uso interno do programador da MOZG, se tratando de recurso experimental

Essas colunas devem ser exibida caso exista registro que o módulo "husseycoding_customordergrid" esteja ativado

O módulo "husseycoding_customordergrid" permite adicionar colunas na grade de dados de pedidos

Como o módulo não exibe o ID do método de pagamento, o módulo da MOZG está adicionado essa nova coluna estendendo a funcionalidade do módulo "husseycoding_customordergrid"

É possível efetuar pesquisa na nova coluna "ID do Método de Pagamento"

Na grade de dados de pedidos foi colocado condição que ao pesquisar na coluna "ID do Método de Pagamento" pelos seguintes identificadores: "mozg_cielo" ou "mozg_braspag" é exibido na coluna "Status da Transacão" o status da transação de cada pedido na grade de dados

É recomendado a instalação do módulo via composer executando o seguinte comando no terminal

    composer require husseycoding/customordergrid

Abaixo temos as URLs relativa ao repositório do módulo e o vídeo demonstrativo

https://github.com/husseycoding/customordergrid

https://www.youtube.com/watch?v=dxIUntG6M2A

--

Fui reportado de ocorrência de erro no uso do módulo "husseycoding/customordergrid"

	PHP Fatal error: Call to a member function addData() on boolean in /app/code/community/HusseyCoding/CustomOrderGrid/Model/Observer.php on line 49

--

Assuntos relativo a módulos de terceiros, sugiro entrar em contato com o desenvolvedor do módulo

--

Vemos no repositório desse módulo um caso reportado recentemente em "01/09" sobre esse erro que mencionado

https://github.com/husseycoding/customordergrid/issues/14

Onde o desenvolvedor informa que deve analisar em uma próxima versão

--

Por se tratar de módulo Open-Source, qualquer programador pode aplicar uma possível correção e até contribuir para a melhoria desse módulo

--

### Como remover arquivos do projeto

A seguir é efetuado pesquisa nos diretórios pelas nomenclaturas

	find /home/marcio/dados/public_html/application-dev39/FLOX/flox_public_html/ -type d -name 'Mozg*'

	find /home/marcio/dados/public_html/application-dev39/FLOX/flox_public_html/ -type d -name 'mozg*'

	find /home/marcio/dados/public_html/application-dev39/FLOX/flox_public_html/ -type l -name 'Mozg*'

	find /home/marcio/dados/public_html/application-dev39/FLOX/flox_public_html/ -type l -name 'mozg*'

Como vemos que são retornado somente as pastas vinculada a MOZG, podemos excluir os diretório

	find /home/marcio/dados/public_html/application-dev39/FLOX/flox_public_html/ -type d -name 'Mozg*' | xargs rm -rf

	find /home/marcio/dados/public_html/application-dev39/FLOX/flox_public_html/ -type d -name 'mozg*' | xargs rm -rf

	find /home/marcio/dados/public_html/application-dev39/FLOX/flox_public_html/ -type l -name 'Mozg*' | xargs rm -rf

	find /home/marcio/dados/public_html/application-dev39/FLOX/flox_public_html/ -type l -name 'mozg*' | xargs rm -rf

Execute a primeira instrução somente para efeito de conferencia

Em seguida exclua a pasta vendor na raiz do projeto e se necessário atualize os requerimentos do Composer

## No modo "Personalizado" escolhendo as seções desejadas para não permitir acesso, apresenta sempre "Acesso Negado"

Na editação do nível de acesso em permissões de acesso

Deve ser selecionado o nó "configuração" em "sistema"

## Porque não está sendo exibido o pedido em /sales/order/history/

O pedido com o status "pagamento pendente" não deve ser exibido nesse ambiente

É exibido os pedidos com os status a seguir

[✓] new
[x] pending_payment
[✓] processing
[✓] complete
[✓] closed
[✓] canceled
[✓] holded
[✓] payment_review

## Estatística

Pacote | Downloads Total | Downloads Mensal | Downloads Diário
--- | --- | --- | ---
[IWD_Opc](https://packagist.org/packages/mozgbrasil/magento-iwd-opc/stats) | [![Total Downloads](https://poser.pugx.org/mozgbrasil/magento-iwd-opc/downloads)](https://packagist.org/packages/mozgbrasil/magento-iwd-opc) | [![Monthly Downloads](https://poser.pugx.org/mozgbrasil/magento-iwd-opc/d/monthly)](https://packagist.org/packages/mozgbrasil/magento-iwd-opc)| [![Daily Downloads](https://poser.pugx.org/mozgbrasil/magento-iwd-opc/d/daily)](https://packagist.org/packages/mozgbrasil/magento-iwd-opc)
[Regiões Brasil](https://packagist.org/packages/mozgbrasil/magento-brasil-regions/stats) | [![Total Downloads](https://poser.pugx.org/mozgbrasil/magento-brasil-regions/downloads)](https://packagist.org/packages/mozgbrasil/magento-brasil-regions) | [![Monthly Downloads](https://poser.pugx.org/mozgbrasil/magento-brasil-regions/d/monthly)](https://packagist.org/packages/mozgbrasil/magento-brasil-regions)| [![Daily Downloads](https://poser.pugx.org/mozgbrasil/magento-brasil-regions/d/daily)](https://packagist.org/packages/mozgbrasil/magento-brasil-regions)
[Tradução Brasil](https://packagist.org/packages/mozgbrasil/magento-locale-pt_br/stats) | [![Total Downloads](https://poser.pugx.org/mozgbrasil/magento-locale-pt_br/downloads)](https://packagist.org/packages/mozgbrasil/magento-locale-pt_br) | [![Monthly Downloads](https://poser.pugx.org/mozgbrasil/magento-locale-pt_br/d/monthly)](https://packagist.org/packages/mozgbrasil/magento-locale-pt_br)| [![Daily Downloads](https://poser.pugx.org/mozgbrasil/magento-locale-pt_br/d/daily)](https://packagist.org/packages/mozgbrasil/magento-locale-pt_br)
[Framework](https://packagist.org/packages/mozgbrasil/php-framework-php_54/stats) | [![Total Downloads](https://poser.pugx.org/mozgbrasil/php-framework-php_54/downloads)](https://packagist.org/packages/mozgbrasil/php-framework-php_54) | [![Monthly Downloads](https://poser.pugx.org/mozgbrasil/php-framework-php_54/d/monthly)](https://packagist.org/packages/mozgbrasil/php-framework-php_54)| [![Daily Downloads](https://poser.pugx.org/mozgbrasil/php-framework-php_54/d/daily)](https://packagist.org/packages/mozgbrasil/php-framework-php_54)
[Base](https://packagist.org/packages/mozgbrasil/magento-base-php_54/stats) | [![Total Downloads](https://poser.pugx.org/mozgbrasil/magento-base-php_54/downloads)](https://packagist.org/packages/mozgbrasil/magento-base-php_54) | [![Monthly Downloads](https://poser.pugx.org/mozgbrasil/magento-base-php_54/d/monthly)](https://packagist.org/packages/mozgbrasil/magento-base-php_54)| [![Daily Downloads](https://poser.pugx.org/mozgbrasil/magento-base-php_54/d/daily)](https://packagist.org/packages/mozgbrasil/magento-base-php_54)
[Correios](https://packagist.org/packages/mozgbrasil/magento-correios-php_54/stats) | [![Total Downloads](https://poser.pugx.org/mozgbrasil/magento-correios-php_54/downloads)](https://packagist.org/packages/mozgbrasil/magento-correios-php_54) | [![Monthly Downloads](https://poser.pugx.org/mozgbrasil/magento-correios-php_54/d/monthly)](https://packagist.org/packages/mozgbrasil/magento-correios-php_54)| [![Daily Downloads](https://poser.pugx.org/mozgbrasil/magento-correios-php_54/d/daily)](https://packagist.org/packages/mozgbrasil/magento-correios-php_54)
[Cielo](https://packagist.org/packages/mozgbrasil/magento-cielo-php_54/stats) | [![Total Downloads](https://poser.pugx.org/mozgbrasil/magento-cielo-php_54/downloads)](https://packagist.org/packages/mozgbrasil/magento-cielo-php_54) | [![Monthly Downloads](https://poser.pugx.org/mozgbrasil/magento-cielo-php_54/d/monthly)](https://packagist.org/packages/mozgbrasil/magento-cielo-php_54)| [![Daily Downloads](https://poser.pugx.org/mozgbrasil/magento-cielo-php_54/d/daily)](https://packagist.org/packages/mozgbrasil/magento-cielo-php_54)
[Clientes](https://packagist.org/packages/mozgbrasil/magento-customer-php_54/stats) | [![Total Downloads](https://poser.pugx.org/mozgbrasil/magento-customer-php_54/downloads)](https://packagist.org/packages/mozgbrasil/magento-customer-php_54) | [![Monthly Downloads](https://poser.pugx.org/mozgbrasil/magento-customer-php_54/d/monthly)](https://packagist.org/packages/mozgbrasil/magento-customer-php_54)| [![Daily Downloads](https://poser.pugx.org/mozgbrasil/magento-customer-php_54/d/daily)](https://packagist.org/packages/mozgbrasil/magento-customer-php_54)
[Redecard](https://packagist.org/packages/mozgbrasil/magento-redecard-php_54/stats) | [![Total Downloads](https://poser.pugx.org/mozgbrasil/magento-redecard-php_54/downloads)](https://packagist.org/packages/mozgbrasil/magento-redecard-php_54) | [![Monthly Downloads](https://poser.pugx.org/mozgbrasil/magento-redecard-php_54/d/monthly)](https://packagist.org/packages/mozgbrasil/magento-redecard-php_54)| [![Daily Downloads](https://poser.pugx.org/mozgbrasil/magento-redecard-php_54/d/daily)](https://packagist.org/packages/mozgbrasil/magento-redecard-php_54)
[Itaú](https://packagist.org/packages/mozgbrasil/magento-itau-php_54/stats) | [![Total Downloads](https://poser.pugx.org/mozgbrasil/magento-itau-php_54/downloads)](https://packagist.org/packages/mozgbrasil/magento-itau-php_54) | [![Monthly Downloads](https://poser.pugx.org/mozgbrasil/magento-itau-php_54/d/monthly)](https://packagist.org/packages/mozgbrasil/magento-itau-php_54)| [![Daily Downloads](https://poser.pugx.org/mozgbrasil/magento-itau-php_54/d/daily)](https://packagist.org/packages/mozgbrasil/magento-itau-php_54)
[Braspag](https://packagist.org/packages/mozgbrasil/magento-braspag-php_54/stats) | [![Total Downloads](https://poser.pugx.org/mozgbrasil/magento-braspag-php_54/downloads)](https://packagist.org/packages/mozgbrasil/magento-braspag-php_54) | [![Monthly Downloads](https://poser.pugx.org/mozgbrasil/magento-braspag-php_54/d/monthly)](https://packagist.org/packages/mozgbrasil/magento-braspag-php_54)| [![Daily Downloads](https://poser.pugx.org/mozgbrasil/magento-braspag-php_54/d/daily)](https://packagist.org/packages/mozgbrasil/magento-braspag-php_54)
[PagSeguro](https://packagist.org/packages/mozgbrasil/magento-pagseguro-php_54/stats) | [![Total Downloads](https://poser.pugx.org/mozgbrasil/magento-pagseguro-php_54/downloads)](https://packagist.org/packages/mozgbrasil/magento-pagseguro-php_54) | [![Monthly Downloads](https://poser.pugx.org/mozgbrasil/magento-pagseguro-php_54/d/monthly)](https://packagist.org/packages/mozgbrasil/magento-pagseguro-php_54)| [![Daily Downloads](https://poser.pugx.org/mozgbrasil/magento-pagseguro-php_54/d/daily)](https://packagist.org/packages/mozgbrasil/magento-pagseguro-php_54)
[Clearsale](https://packagist.org/packages/mozgbrasil/magento-clearsale-php_54/stats) | [![Total Downloads](https://poser.pugx.org/mozgbrasil/magento-clearsale-php_54/downloads)](https://packagist.org/packages/mozgbrasil/magento-clearsale-php_54) | [![Monthly Downloads](https://poser.pugx.org/mozgbrasil/magento-clearsale-php_54/d/monthly)](https://packagist.org/packages/mozgbrasil/magento-clearsale-php_54)| [![Daily Downloads](https://poser.pugx.org/mozgbrasil/magento-clearsale-php_54/d/daily)](https://packagist.org/packages/mozgbrasil/magento-clearsale-php_54)
[Banco do Brasil](https://packagist.org/packages/mozgbrasil/magento-bancodobrasil-php_54/stats) | [![Total Downloads](https://poser.pugx.org/mozgbrasil/magento-bancodobrasil-php_54/downloads)](https://packagist.org/packages/mozgbrasil/magento-bancodobrasil-php_54) | [![Monthly Downloads](https://poser.pugx.org/mozgbrasil/magento-bancodobrasil-php_54/d/monthly)](https://packagist.org/packages/mozgbrasil/magento-bancodobrasil-php_54)| [![Daily Downloads](https://poser.pugx.org/mozgbrasil/magento-bancodobrasil-php_54/d/daily)](https://packagist.org/packages/mozgbrasil/magento-bancodobrasil-php_54)
[Bradesco](https://packagist.org/packages/mozgbrasil/magento-bradesco-php_54/stats) | [![Total Downloads](https://poser.pugx.org/mozgbrasil/magento-bradesco-php_54/downloads)](https://packagist.org/packages/mozgbrasil/magento-bradesco-php_54) | [![Monthly Downloads](https://poser.pugx.org/mozgbrasil/magento-bradesco-php_54/d/monthly)](https://packagist.org/packages/mozgbrasil/magento-bradesco-php_54)| [![Daily Downloads](https://poser.pugx.org/mozgbrasil/magento-bradesco-php_54/d/daily)](https://packagist.org/packages/mozgbrasil/magento-bradesco-php_54)
[Jadlog](https://packagist.org/packages/mozgbrasil/magento-jadlog-php_54/stats) | [![Total Downloads](https://poser.pugx.org/mozgbrasil/magento-jadlog-php_54/downloads)](https://packagist.org/packages/mozgbrasil/magento-jadlog-php_54) | [![Monthly Downloads](https://poser.pugx.org/mozgbrasil/magento-jadlog-php_54/d/monthly)](https://packagist.org/packages/mozgbrasil/magento-jadlog-php_54)| [![Daily Downloads](https://poser.pugx.org/mozgbrasil/magento-jadlog-php_54/d/daily)](https://packagist.org/packages/mozgbrasil/magento-jadlog-php_54)
[Jamef](https://packagist.org/packages/mozgbrasil/magento-jamef-php_54/stats) | [![Total Downloads](https://poser.pugx.org/mozgbrasil/magento-jamef-php_54/downloads)](https://packagist.org/packages/mozgbrasil/magento-jamef-php_54) | [![Monthly Downloads](https://poser.pugx.org/mozgbrasil/magento-jamef-php_54/d/monthly)](https://packagist.org/packages/mozgbrasil/magento-jamef-php_54)| [![Daily Downloads](https://poser.pugx.org/mozgbrasil/magento-jamef-php_54/d/daily)](https://packagist.org/packages/mozgbrasil/magento-jamef-php_54)
[Loggi](https://packagist.org/packages/mozgbrasil/magento-loggi-php_54/stats) | [![Total Downloads](https://poser.pugx.org/mozgbrasil/magento-loggi-php_54/downloads)](https://packagist.org/packages/mozgbrasil/magento-loggi-php_54) | [![Monthly Downloads](https://poser.pugx.org/mozgbrasil/magento-loggi-php_54/d/monthly)](https://packagist.org/packages/mozgbrasil/magento-loggi-php_54)| [![Daily Downloads](https://poser.pugx.org/mozgbrasil/magento-loggi-php_54/d/daily)](https://packagist.org/packages/mozgbrasil/magento-loggi-php_54)

## Contribuintes

Equipe Mozg

## License

[Comercial License](LICENSE.txt)

## Badges

[![Join the chat at https://gitter.im/mozgbrasil](https://badges.gitter.im/Join%20Chat.svg)](https://gitter.im/mozgbrasil/)
[![Latest Stable Version](https://poser.pugx.org/mozgbrasil/magento-base-php_54/v/stable)](https://packagist.org/packages/mozgbrasil/magento-base-php_54)
[![Total Downloads](https://poser.pugx.org/mozgbrasil/magento-base-php_54/downloads)](https://packagist.org/packages/mozgbrasil/magento-base-php_54)
[![Latest Unstable Version](https://poser.pugx.org/mozgbrasil/magento-base-php_54/v/unstable)](https://packagist.org/packages/mozgbrasil/magento-base-php_54)
[![License](https://poser.pugx.org/mozgbrasil/magento-base-php_54/license)](https://packagist.org/packages/mozgbrasil/magento-base-php_54)
[![Monthly Downloads](https://poser.pugx.org/mozgbrasil/magento-base-php_54/d/monthly)](https://packagist.org/packages/mozgbrasil/magento-base-php_54)
[![Daily Downloads](https://poser.pugx.org/mozgbrasil/magento-base-php_54/d/daily)](https://packagist.org/packages/mozgbrasil/magento-base-php_54)
[![Reference Status](https://www.versioneye.com/php/mozgbrasil:magento-base-php_54/reference_badge.svg?style=flat-square)](https://www.versioneye.com/php/mozgbrasil:magento-base-php_54/references)
[![Dependency Status](https://www.versioneye.com/php/mozgbrasil:magento-base-php_54/1.0.0/badge?style=flat-square)](https://www.versioneye.com/php/mozgbrasil:magento-base-php_54/1.0.0)

:cat2: