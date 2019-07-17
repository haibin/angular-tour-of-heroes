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

## Two way data binding [()]

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

The `*ngFor` is Angular's repeater `directive`.

## Event binding ()

```
<li *ngFor="let hero of heroes" (click)="onSelect(hero)">
```

This is an example of Angular's `event binding` syntax.

## Class binding []

```
[class.selected]="hero === selectedHero"
```

The Angular `class binding` makes it easy to add and remove a CSS class conditionally.

## Input property @Input()

```
@Input() hero: Hero;
```

The hero property must be an `Input` property, annotated with the @Input() decorator

## Property binding []

```
<app-hero-detail [hero]="selectedHero"></app-hero-detail>
```

[hero]="selectedHero" is an Angular `property binding`.


## Call it in ngOnInit

While you could call getHeroes() in the constructor, that's not the best practice.

Reserve the constructor for simple initialization such as wiring constructor parameters to properties. The constructor shouldn't do anything. It certainly shouldn't call a function that makes HTTP requests to a remote server as a real data service would.


## the RxJS of() function

```
getHeroes(): Observable<Hero[]> {
  return of(HEROES);
}
```

of(HEROES) returns an Observable<Hero[]> that emits a single value, the array of mock heroes.

## Public vs Private

```
    constructor(public messageService: MessageService) {}
```

The messageService property must be public because you're about to bind to it in the template.

Angular only binds to public component properties.

## Routing module

In Angular, the best practice is to load and configure the router in a separate, top-level module that is dedicated to routing and imported by the root AppModule.

```
ng generate module app-routing --flat --module=app
```

--flat puts the file in src/app instead of its own folder.
--module=app tells the CLI to register it in the imports array of the AppModule.

The `RouterOutlet` is one of the router directives

The `routerLink` is the selector for the RouterLink directive that turns user clicks into router navigations. It's another of the public directives in the RouterModule.

## AsyncPipe

```
<li *ngFor="let hero of heroes$ | async" >
```

The $ is a convention that indicates heroes$ is an Observable, not an array.


## RxJS Subject


```
import { Observable, Subject } from 'rxjs';


  private searchTerms = new Subject<string>();

```