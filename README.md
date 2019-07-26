# katex-expression-ng

katex-expression-ng demonstrates how to use the [`<katex-expression>`](https://github.com/navsgh/katex-expression) web component in an Angular 2+ project. This project was generated with [Angular CLI](https://github.com/angular/angular-cli) version 8.1.2.

## Instructions

### Try this demo: 

```bash
git clone https://github.com/navsgh/katex-expression-ng.git
ng serve
```
	
Navigate to `http://localhost:4200/`. 

### Include `<katex-expression>` to an existing Angular 2+ project:

1. **Install `<katex-expression>`**

```bash
npm i --save @navsnpm/katex-expression
```

2. **Include `CUSTOM_ELEMENTS_SCHEMA` in `app.module.ts`**

Refer to the comment _"// for `<katex-expression>` web component"_ for specific lines

```typescript

import { BrowserModule } from '@angular/platform-browser';
import { NgModule } from '@angular/core';

// for <katex-expression> web component
import { CUSTOM_ELEMENTS_SCHEMA } from '@angular/core';

import { AppComponent } from './app.component';

@NgModule({
  declarations: [
    AppComponent
  ],
  imports: [
    BrowserModule
  ],
  providers: [],
  // for <katex-expression> web component
  schemas: [CUSTOM_ELEMENTS_SCHEMA],
  bootstrap: [AppComponent]
})
export class AppModule { }
```

3. Invoke `defineCustomElements` in `main.ts`

Refer to the comment _"// for `<katex-expression>` web component_" for specific lines
	
```typescript
import { enableProdMode } from '@angular/core';
import { platformBrowserDynamic } from '@angular/platform-browser-dynamic';

import { AppModule } from './app/app.module';
import { environment } from './environments/environment';

// for <katex-expression> web component
import { defineCustomElements as defineKatex } from '@navsnpm/katex-expression/loader';

if (environment.production) {
  enableProdMode();
}

platformBrowserDynamic().bootstrapModule(AppModule)
  .catch(err => console.error(err));

// for <katex-expression> web component
defineKatex(window);
```

## License

`katex-expression-ng` is licensed under the [MIT License](http://opensource.org/licenses/MIT).


