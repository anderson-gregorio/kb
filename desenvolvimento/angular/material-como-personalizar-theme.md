# Material - Como personalizar Theme?

Esta é a maneira como atualmente modifico o theme do Material

* Acessar o site [https://materialtheme.arcsine.dev/](https://materialtheme.arcsine.dev/)

* Clicar em **Copy Angular SCSS**

* Crio o arquivo src/scss/theme.scss

* Copio o contéudo da área de transfefência

* No arquivo src/styles.scss no início do arquivo insiro o seguinto código

```javascript
@import '~@angular/material/theming';

@import './scss/theme.scss';

```