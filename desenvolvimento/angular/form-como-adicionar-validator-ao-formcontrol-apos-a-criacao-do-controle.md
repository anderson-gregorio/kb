# Form - Como adicionar Validator ao FormControl após a criação do controle?

Defina um validador para um controle no FormGroup: 

```javascript
this.myForm.controls['controlName'].setValidators([Validators.required])
```

Remova o validador do controle no FormGroup: 

```javascript
this.myForm.controls['controlName'].clearValidators()
```

Atualize o FormGroup depois de executar uma das linhas acima. 

```javascript
this.myForm.controls['controlName'].updateValueAndValidity()
```

Link de Referência:

[https://stackoverflow.com/a/47751840/13223495](https://stackoverflow.com/a/47751840/13223495)