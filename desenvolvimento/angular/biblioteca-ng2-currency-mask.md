# Biblioteca - ng2-currency-mask

Cria máscara para a digitação de valores em dinheiro

NPM: https://www.npmjs.com/package/ng2-currency-mask
Git: https://github.com/cesarrew/ng2-currency-mask
Wiki: 

No módulo: 

```javascript
import { CurrencyMaskModule } from 'ng2-currency-mask';
import { CurrencyMaskConfig, CURRENCY_MASK_CONFIG } from 'ng2-currency-mask/src/currency-mask.config';

// Configuração da Mask
export const CustomCurrencyMaskConfig: CurrencyMaskConfig = {
    align: 'left',
    allowNegative: false,
    decimal: ',',
    precision: 2,
    prefix: '',
    suffix: '',
    thousands: '.'
};

@NgModule({
    imports: [
      ...
      CurrencyMaskModule,
      ...
    ],
    providers: [
        {
            provide: CURRENCY_MASK_CONFIG,
            useValue: CustomCurrencyMaskConfig
        },
    ],
```

html
```html
<!-- Valor -->
<mat-form-field class="width100">
    <input type="tel" matInput currencyMask formControlName="valormov" autocomplete="off"
        placeholder="Valor" required>
</mat-form-field>
```