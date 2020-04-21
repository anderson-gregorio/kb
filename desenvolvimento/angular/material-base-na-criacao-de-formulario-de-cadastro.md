# Material - Base na criação de formulário de Cadastro

```html
<app-processando [processando]="processando" ></app-processando>

<div *ngIf="!processando">
  <mat-card style="margin-bottom: 10px;">
    <form [formGroup]="form">
      <mat-card-content>

        <!-- Nome do Cliente -->
        <mat-form-field class="width100">
          <input matInput formControlName="nome_cliente" autocomplete="off" placeholder="Nome do Cliente">
        </mat-form-field>

        ...

        <!-- Tabela de Preço -->
        <!-- <mat-form-field class="width100">
          <mat-select placeholder="Tabela de Preço" formControlName="id_preco" cdkFocusInitial>
            <mat-option *ngFor="let precos of listTabelaPreco" [value]="precos.id_preco">
              {{ precos.descricao }}
            </mat-option>
          </mat-select>
        </mat-form-field> -->

      </mat-card-content>
    </form>
  </mat-card>
```

```javascript
  /**
   * form: Formulário do Cadastro
   */
  form: FormGroup;

  ...

  constructor(
    private formBuilder: FormBuilder,
  ) { }

  ...

  ngOnInit() {
    ...
    // Criar o formulário
    this.form = this.formBuilder.group({
      id_cliente: [null],
      nome_cliente: [null, [Validators.required, Validators.minLength(3)]],
      id_tipo_cliente: [null, [Validators.required, Validators.minLength(1)]],
      id_preco: [null, [Validators.required]],
      telefone: [null],
      porc_troca: [null],
      endereco: [null]
    });
    ...
  }
```