
### Instalação

Os plugins trazem extensões ao site que permitem adicionar novas funcionalidades, optimizar e simplificar processos, como por exemplo ao nível de SEO, forms de contacto.

Para adicionar um plugin vamos à secção plugins no dashboard.

![[Pasted image 20231113214109.png]]
Podemos instalar um novo plugin através da opção `Add New Plugin` ou gerir os plugins já previamente instalados.
Podemos navegar nas categorias de plugins ou então pesquisar por um. Depois de encontrado o plugin na lista podemos instalá-lo e ativá-lo de seguida.
Conforme o plugin podem ser adicionadas mais opções ao menu do dashboard, com é o caso do plugin Yost SEO que cria uma entrada própria no dashboard.

![[Pasted image 20231113214729.png]]
### Woocommerce

É um plugin open source de eCommerce quer permite adicionar a um site a capacidade de gerir vendas de produtos e serviços. Baseado em templates e designs que ofereçam diversas funcionalidades, umas gratuitas outras pagas.
Por sua vez o woocommerce tem a flexibilidade de poder ser também alterado e extendido com recurso a add-ons (por ex. reservas, envios).
Os pagamentos são também um ponto importante porque normalmente trazem uma complexidade de integrações acrescida, o woocommerce suporte por defeito paypal e stripe, mas podem ser adicionadas outras *gateways* de pagamento

#### Instalação 

A instalação do woocommerce é semelhante à de qualquer plugin no wordpress, vamos a plugins e escolhemos adicionar um novo plugin. Procuramos por woocommerce, instalamos e ativamos o plugin.

![[Pasted image 20231114092122.png]]
O processo de ativação tem um wizard para recolha de algumas informações.
No final temos o dashboard do woocommerce disponível para configurar a loja:
![[Pasted image 20231114115544.png]]
Vamos adicionar um produto, indicando o nome e preço de listagem, podemos também opcionalmente defiinir um preço promocional (sales), uma categoria para o produto.

A escolha do tema é opcional, mas podemos escoher um tema que apresente por exemplo o carrinho de compras por defeito.

Na configuração dos pagamentos, o woo payments é o sistema por defeito, mas podem ser instalados outros addons de pagamento, como por exemplo paypal. Para instalar vamsos aos plugin e adicionamos um novo `WooCommerce PayPal Payments` .

Na definição das taxas, após a definição da localização da loja, podemos indicar qual a taxa aplicada aos produtos. Por exemplo IVA a 23%.


#### Erros na instalação
Se a instalação falhar será necessário validar os seguintes pontos:

1. Aumentar o limite de memória a usar pelo wordpress
`wp-config.php`

```php
/* Add any custom values between this line and the "stop editing" line. */

define( 'WP_MEMORY_LIMIT', '256M' );

/* That's all, stop editing! Happy publishing. */

```

2. Aumentar o limite do tempo de execução dos scripts php
`MAMP/bin/php/[php_version]/conf/php.ini`

```php
; Maximum execution time of each script, in seconds
; http://php.net/max-execution-time
; Note: This directive is hardcoded to 0 for the CLI SAPI

max_execution_time = 300
```

3. Instalar o plugin `All In One WP Security` e na sua secção file system security validar que as permissões das directorias estão ok 

![[Pasted image 20231114114817.png]]



