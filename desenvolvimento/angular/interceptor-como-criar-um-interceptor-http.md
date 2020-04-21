# Interceptor - Como criar um interceptor HTTP?

* Gerar um serviços

```bash
ng g s <CAMINHO/NOME_SERVICE>
```

* Atualiza o código para o exemplo abaixo

```javascript
export class AppInterceptorService implements HttpInterceptor {
  intercept(request: HttpRequest<any>, next: HttpHandler): Observable<HttpEvent<any>> {

    const url = request.url;

    if (url.indexOf('/loginSocialLogin') === -1) {
      const customReq = request.clone({
        headers: request.headers.set('Authorization', `Bearer ${this.loginService.getUsuarioLogado.token}`),
      });

      return next.handle(customReq);
    }

    return next.handle(request)
  }
```

* No app.module.ts adiciona ao array providers conforme exemplo abaixo

```javascript
  providers: [
    ...,
    {
      provide: HTTP_INTERCEPTORS,
      useClass: AppInterceptorService,
      multi: true
    }
```