# AngularTourOfHeroes

This project was generated with [Angular CLI](https://github.com/angular/angular-cli) version 8.1.0.

## Development server

Run `ng serve` for a dev server. Navigate to `http://localhost:4200/`. The app will automatically reload if you change any of the source files.

## Code scaffolding

Run `ng generate component component-name` to generate a new component. You can also use `ng generate directive|pipe|service|class|guard|interface|enum|module`.

## Build

Run `ng build` to build the project. The build artifacts will be stored in the `dist/` directory. Use the `--prod` flag for a production build.

## Running unit tests

Run `ng test` to execute the unit tests via [Karma](https://karma-runner.github.io).

## Running end-to-end tests

Run `ng e2e` to execute the end-to-end tests via [Protractor](http://www.protractortest.org/).

## Further help

To get more help on the Angular CLI use `ng help` or go check out the [Angular CLI README](https://github.com/angular/angular-cli/blob/master/README.md).

# Notes

```
<h1>{{title}}</h1>
```

The double curly braces are Angular's `interpolation binding` syntax.

The application shell

src/app.component.*
src/heroes/heroes.component.*

The CSS element selector, 'app-heroes', matches the name of the HTML element that identifies this component within a `parent` component's template.

The ngOnInit is a `lifecycle hook`. Angular calls ngOnInit shortly after creating a component. It's a good place to put initialization logic.

`Always` export the component class so you can import it elsewhere ... like in the AppModule.

A non-component heor.ts was created.

```
    <input [(ngModel)]="hero.name" placeholder="name"/>
```

[(ngModel)] is Angular's `two-way data binding` syntax.

Here it binds the hero.name property to the HTML textbox so that data can flow in both directions: from the hero.name property to the textbox, and from the textbox back to the hero.name.

Although `ngModel` is a valid Angular `directive`, it isn't available by default.

It belongs to the optional `FormsModule` and you must opt-in to using it.

Every component must be declared in `exactly one` NgModule.

2 steps:
1. import
2. declare

