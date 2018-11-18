# MaterialNg

This article teach how to  use angular material in your angular project. 

The software that I was using as following:

* Angular CLI: 7.0.6
* Node: 10.10.0
* OS: darwin x64
* Angular: 7.0.4
* cnpm@6.0.0 
* npm@6.4.1 

## Create project 

Create project and install some necessary dependency .

```
ng new material-ng --routing --style=scss
cnpm i --save @angular/material@7.0.4 @angular/cdk@7.0.4
cnpm i --save @angular/animations@7.0.4
cnpm i --save hammerjs@2.0.8
```

## import BrowserAnimationsModule to app.module

```
import {BrowserAnimationsModule} from '@angular/platform-browser/animations'
```

## Import material modules

* create file ``/src/app/material.ts`` 

```ts
import {MatButtonModule,MatCheckboxModule} from '@angular/material';
import {NgModule} from '@angular/core'

@NgModule({
  imports: [
    MatButtonModule,
    MatCheckboxModule
  ],
  exports:[
    MatButtonModule,
    MatCheckboxModule
  ],
})

export class MaterialModule{
}
```

* Import MaterialModule to app.module

```ts
...
import {MaterialModule} from './material'

@NgModule({
  declarations: [
    AppComponent
  ],
  imports: [
    ...
    MaterialModule
  ],
  providers: [],
  bootstrap: [AppComponent]
})
export class AppModule { }

```


## add default style to styles.scss

```scss
@import "~@angular/material/prebuilt-themes/indigo-pink.css";
```

To get more information about angular material theming. please acesss [offical web site](https://material.angular.io/guide/theming)


* add icon style to index.html before ``</head>``

```html
  <link href="https://fonts.googleapis.com/icon?family=Material+Icons" rel="stylesheet">
```

> The style file's code as following: 
```css
/* fallback */
@font-face {
  font-family: 'Material Icons';
  font-style: normal;
  font-weight: 400;
  src: url(https://fonts.gstatic.com/s/materialicons/v41/flUhRq6tzZclQEJ-Vdg-IuiaDsNcIhQ8tQ.woff2) format('woff2');
}

.material-icons {
  font-family: 'Material Icons';
  font-weight: normal;
  font-style: normal;
  font-size: 24px;
  line-height: 1;
  letter-spacing: normal;
  text-transform: none;
  display: inline-block;
  white-space: nowrap;
  word-wrap: normal;
  direction: ltr;
  -webkit-font-feature-settings: 'liga';
  -webkit-font-smoothing: antialiased;
}
```

## Add button to app.component.html

```html
<!--The content below is only a placeholder and can be replaced.-->
<button mat-raised-button>Basic</button>
<button mat-raised-button color="primary">Primary</button>
<button mat-raised-button color="accent">Accent</button>
<button mat-raised-button color="warn">Warn</button>
<button mat-raised-button disabled>Disabled</button>

<router-outlet></router-outlet>
```

Change the fontend code. and serve the project``ng serve --open ``


### Add a Toolbar to our poject .

* Add and import and export MatToolbarModule``import {MatToolbarModule} from '@angular/material/toolbar';``

> [More information about MatToolbarModule](https://material.angular.io/components/toolbar/examples)


* Same way to add MatIconModule,``import {MatIconModule} from '@angular/material/icon'; ``

* Change app.component.html

```html
<mat-toolbar color="primary">
  <mat-toolbar-row>
    <span>Third Line</span>
    <span class="example-spacer"></span>
    <mat-icon class="example-icon">menu</mat-icon>
  </mat-toolbar-row>
</mat-toolbar>
<router-outlet></router-outlet>
```

> [More icons](https://material.io/tools/icons/)

* sytle this page app.component.scss

```scss
.example-icon {
  padding: 0 14px;
  cursor: pointer;
}
.example-spacer {
  flex: 1 1 auto;
}
```


## Serve this project and see what happen.

```
ng s --o
```

> We add a menu in the final code. if you want to get he code please visit [the github]().