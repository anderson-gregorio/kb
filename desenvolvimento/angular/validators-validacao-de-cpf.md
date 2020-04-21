# Validators - Validação de CPF

```javascript
// angCPFValidator.ts
import { AbstractControl } from '@angular/forms';

export function AnGCFPValidator(control: AbstractControl): any {
    if (!validarCPF(control.value)) {
        return { 'cpfInvalido': true }
    }
    return false;
}

function validarCPF(strCPF: string) {
    let soma: number = 0;
    let resto: number;

    if (!strCPF) { return false; }
    if (strCPF.length < 11) { return false; }
    if (strCPF == "00000000000") { return false };

    for (let i = 1; i <= 9; i++) soma = soma + parseInt(strCPF.substring(i - 1, i)) * (11 - i);
    resto = (soma * 10) % 11;

    if ((resto == 10) || (resto == 11)) resto = 0;
    if (resto != parseInt(strCPF.substring(9, 10))) return false;

    soma = 0;
    for (let i = 1; i <= 10; i++) soma = soma + parseInt(strCPF.substring(i - 1, i)) * (12 - i);
    resto = (soma * 10) % 11;

    if ((resto == 10) || (resto == 11)) resto = 0;
    if (resto != parseInt(strCPF.substring(10, 11))) return false;
    return true;
}
```

```javascript
  ...
  ngOnInit() {
    // Criar o formulario
    this.formulario = this.formBuilder.group({
      ...
      cpf: [null, [Validators.required, AnGCFPValidator]],
  ...
```