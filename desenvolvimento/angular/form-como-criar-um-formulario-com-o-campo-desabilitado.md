# Form - Como criar um formulário com o campo desabilitado?

```javascript
this.form = this.formBuilder.group({
  ...
  datapag: [{ value: null, disabled: true }],
  ...
});
```