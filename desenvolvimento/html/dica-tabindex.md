# Dica - TabIndex

## Valores

O tabindex aceita valores inteiros. Eles podem ser:

* **Negativo** (geralmente tabindex=”-1”) - o elemento não é acessível pela navegação do teclado.

* **tabindex="0"** - o elemento é acessível pela navegação do teclado, mas o pedido é definido pelo pedido de origem dos documentos.

* **Positivo** - o elemento é acessível pela navegação do teclado e a ordem é definida pelo valor. Por exemplo, tabindex="2" é focável antes tabindex="3", mas depois tabindex="1".

## Uso

* input
* anchor (a)
* textarea
* select
* button

## Exemplo

```html
<body>
  <label>This element will be focused second</label>
  <input name=”field1” type=”email” tabindex=”2” />

   <label>This element will be focused first</label>
  <textarea rows=”4”  cols=”5” tabindex=”1”></textarea>

   <label>The second focused last</label>
  <input name=”field3” type=”text” tabindex=”3”/>
</body>
```

Link de Referência:

[https://kolosek.com/tabindex/](https://kolosek.com/tabindex/)