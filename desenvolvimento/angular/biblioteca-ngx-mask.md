# Biblioteca - ngx-mask

Cria máscara conforme a configuração repassada

NPM: https://www.npmjs.com/package/ngx-mask
Git: https://github.com/JsDaddy/ngx-mask
Wiki: https://jsdaddy.github.io/ngx-mask-page/

No módulo: 

```javascript
import { NgxMaskModule } from 'ngx-mask'

export const options: Partial<IConfig> | (() => Partial<IConfig>) = {};

@NgModule({
  (...)
  imports: [
    NgxMaskModule.forRoot(options)
  ]
  (...)
})
```

Examplos: 

```
<input matInput type="tel" placeholder="Celular" autocomplete="off" formControlName="celular" mask="(00)00000-0000" required>
<input matInput type="tel" placeholder="CPF" autocomplete="off" formControlName="cpf" mask="000.000.000-00" required>
```

**Utilizando a máscara de telefone**

Para criar uma máscara dinâmica para os padrões de telefone/celulcar

ts
```javascript
  ...
  /**
   * Mascara do telefone
   */
  maskPhoneNumber: string = '(00)0000-00009';
  ...

    // Ao carregar o formulário deve ser configurar a mask
    this.form.patchValue(res.fornecedor[0]);
    this.switchPhoneMask();

  ...

  /**
   * Realiza a seleção da máscara pela quantidade de caracteres digitados
   */
  public switchPhoneMask() {
    const telefone = this.form.get('telefone').value;

    if (telefone) {
      if (telefone.length > 10) {
        return this.maskPhoneNumber = '(00)00000-0000';
      }
    }

    return this.maskPhoneNumber = '(00)0000-00009';
  }
```

html
```html
<input 
  matInput
  type="tel"
  placeholder="Telefone/Celular"
  autocomplete="off"
  formControlName="telefone"
  [mask]="maskPhoneNumber"
  (keyup)="switchPhoneMask()"
>
```
