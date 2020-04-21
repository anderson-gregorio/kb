# Snippet - Routes

```javascript
const routes: Routes = [
    {
        path: '',
        redirectTo: 'n/dashboard',
        pathMatch: 'full'
    },
    {
        path: 'n',
        component: NavComponent,
        children: [
            {
                path: 'dashboard',
                canActivate: [
                    AppGuardGuard
                ],
                component: DashboardComponent,
                data: {
                    animation: 'right'
                }
            },
        ]
    },
    ....
```