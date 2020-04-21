# Pipe - Como configurar os pipe para o idioma português?

```javascript
import { NgModule, LOCALE_ID} from '@angular/core';
import { registerLocaleData } from '@angular/common';
import localePt from '@angular/common/locales/pt';
registerLocaleData(localePt, 'pt');

@NgModule({
    providers: [
        {
            provide: LOCALE_ID,
            useValue: 'pt'
        }
    ]
})
```

Link referência: 

[https://www.angularjswiki.com/angular/angular-currency-pipe-formatting-currency-in-angular/](https://www.angularjswiki.com/angular/angular-currency-pipe-formatting-currency-in-angular/)