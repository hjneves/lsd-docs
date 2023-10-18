TWITTER
-------

Using widgets created in the twitter account.

1\. create widget on twitter

2\. copy the code

3\. insert into the webpage



INSTAGRAM
---------

Using a library <https://lightwidget.com>

1\. Configure widget

2\. generate code

3\. inserto into the webpage

Desafio - Formatação
--------------------

Formatar posicionamento e dimensão dos widgets

Colocar os feeds lado a lado.

Usando table:

```html
 <table>
    <tr>
      <td>
            <a class="twitter-timeline" href="https://twitter.com/DisneyPixar" data-widget-id="713778492454805505">Tweets by @DisneyPixar</a> <script>!function(d,s,id){var js,fjs=d.getElementsByTagName(s)[0],p=/^http:/.test(d.location)?'http':'https';if(!d.getElementById(id)){js=d.createElement(s);js.id=id;js.src=p+"://platform.twitter.com/widgets.js";fjs.parentNode.insertBefore(js,fjs);}}(document,"script","twitter-wjs");</script>
      </td>     
      <td>
        <!-- LightWidget WIDGET --><script src="http://lightwidget.com/widgets/lightwidget.js"></script><iframe src="http://lightwidget.com/widgets/cade34c261a75b6ba0d7072d31b9cba1.html" id="lightwidget_cade34c261" name="lightwidget_cade34c261"  scrolling="no" allowtransparency="true" class="lightwidget-widget" style="width: 100%; border: 0; overflow: hidden;"></iframe>


      </td>

    </tr>
</table>

```

```css

 /* -------------- Feeds -------------*/
    table {
      width: 100%;
    }

    td {
      display: table-cell;
      vertical-align: top;
      width: 50%;
    }
```

Facebook
--------

<https://developers.facebook.com/docs/plugins/page-plugin>

[](https://developers.facebook.com/docs/plugins/page-plugin)