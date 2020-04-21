# Material - MatSelect método Change removido

The changed it from change to selectionChange.

```html
<mat-select (change)="doSomething($event)">
```

is now

```html
<mat-select (selectionChange)="doSomething($event)">
```

Link de Referência:

[https://stackoverflow.com/a/50223943/13223495](https://stackoverflow.com/a/50223943/13223495)