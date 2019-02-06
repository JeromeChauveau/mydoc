# angular-fundamentals-files
This repo contains a few helper files for the Angular Fundamentals course at http://app.pluralsight.com/courses/angular-fundamentals

# General
- Typescript is transpiled to js
- AngularJS = version < 2.
Q: is static typing only for compilation, or does it also generate runtime errors?

Simplification:
`Class Cat {
  private name: string;
  constructor (name) {
    this.name = name;
  }
 }`
 can be simplified into : 
 `Class Cat {
  constructor (private name:string) {
  }
 }`


## Modules 
 - Components can be grouped in modules. 
 - Only files of targeted modules are loaded.
 - Objects from modules are only available in the module where they are registered.

Q : diff between `npm start` & `ng serve`?

## bootstrap
In angular.json, pointeur vers main.ts ("main": "src/main.ts").
In main.ts : 
`platformBrowserDynamic().bootstrapModule(AppModule)` --> shows that application is bootstrap with AppModule.

Q : webpack ?
note : angular.json = webpack config, so when it changes one needs to restart server

## modules
Module declaration file:
 - imports : allows to import other modules to have acess to their services etc..
 - Q : why are components and services declared in two different properties? (declarations and providers)
 - bootstrap: ?
 
 ## Using static assets
 Source folders are defined in angular.json file : "assets" : [] for images, "styles" for css, "scripts" for js
 
# Creating and communicating between components
## Bouding to data & Communication between parent and child components
@Input() event:any;

in child : {{}} refers to object in the component.
in parent : 
event1 = {
    id: 1,
    name: 'Angular connect',
    date:''}
and <event-thumbnail [event]="event1"></event-thumbnail> passer event1 to event object in child (event-thumbnail)

in child :
@Output() eventClick = new EventEmitter(); and <button class='btn btn-primary' (click)='handleClick()'>Click me!</button>
and handleClick(){
    this.eventClick.emit('foo');
  }
  
and in parent:<event-thumbnail [event]="event1" (eventClick)='handleEventClicked($event)'></event-thumbnail> and
handleEventClicked(data) {
    console.log(data);
  }


