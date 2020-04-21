# Biblioteca - saturn-datepicker

Material range datepicker

NPM: https://www.npmjs.com/package/saturn-datepicker
Git: https://github.com/SaturnTeam/saturn-datepicker#readme
Wiki: 

No módulo: 

```javascript
import { SatDatepickerModule, SatNativeDateModule } from 'saturn-datepicker';
import { MAT_DATE_LOCALE } from '@angular/material';
import { MAT_MOMENT_DATE_FORMATS, MomentDateAdapter } from '@angular/material-moment-adapter';

export const MOMENTJS_DATE_FORMAT = {
  parse: {
    dateInput: 'DD/MM/YYYY',
  },
  display: {
    dateInput: 'DD/MM/YYYY',
    monthYearLabel: 'MMM YYYY',
    dateA11yLabel: 'DD/MM/YYYY',
    monthYearA11yLabel: 'MMMM YYYY',
  },
};

@NgModule({
    imports: [
      ...
      SatDatepickerModule,
      SatNativeDateModule,
      ...
    ],
    providers: [
      {
        provide: DateAdapter,
        useClass: MomentDateAdapter,
        deps: [MAT_DATE_LOCALE]
      },
      // Para configurar o primeiro dia da semana (domingo)
      {
        provide: MAT_DATE_LOCALE,
        useValue: 'pt-br'
      },
      {
        provide: MAT_DATE_FORMATS,
        useValue: MOMENTJS_DATE_FORMAT
      },
    ]
    ...
```