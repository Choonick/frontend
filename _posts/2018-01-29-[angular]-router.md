# angular router

### 1. ng generate module app-routing --flat --module=app
--flat은 폴더를 만들지 않고 파일로 생성<br>
--module=app은 모듈에 자동 추가
### 2. /app-routing.module.ts
```
import { NgModule } from '@angular/core';
import { CommonModule } from '@angular/common';
import { RouterModule, Routes } from '@angular/router';
import { LoginComponent } from './components/login/login.component';

const routes: Routes = [
  { path: '', component: LoginComponent }
];

@NgModule({
  imports: [ RouterModule.forRoot(routes)],
  exports: [ RouterModule ]
})
export class AccountRoutingModule { }

```
