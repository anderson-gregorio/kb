# Directive - Exemplo manipulação do 'colar' no campo de um formulario

```javascript
import { Directive, ElementRef, HostListener } from "@angular/core";
import { NgControl } from "@angular/forms";

@Directive({
  selector: '[someDate]'
})
export class SomeDateDirective{
  constructor(private el: ElementRef, private control : NgControl) {

  }

  @HostListener('paste',['$event']) onEvent($event) {
    $event.preventDefault(); //blocks write to input element
    let data = $event.clipboardData.getData('text');
    setTimeout(() => {
      this.control.control.setValue(data.toUpperCase());
    }, 3000);
  }

}
```

Importante destacar **this.control.control.setValue** que atualiza a informação do controle.

Link de Referência: 

[http://embed.plnkr.co/hsisILvtKErBBOXECt8t/](http://embed.plnkr.co/hsisILvtKErBBOXECt8t/)

[https://stackoverflow.com/questions/42816448/angular2-custom-directive-to-prevent-characters-which-doesnt-match-a-regexp](https://stackoverflow.com/questions/42816448/angular2-custom-directive-to-prevent-characters-which-doesnt-match-a-regexp)

[https://stackoverflow.com/questions/41465542/angular2-input-field-to-accept-only-numbers/41479077](https://stackoverflow.com/questions/41465542/angular2-input-field-to-accept-only-numbers/41479077)