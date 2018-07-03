List of common practices and conventions followed in this project


### The application currently has 3 modules
1. `src/app/app.module`: This is the root module of the application
2. `src/app/core/core.module`: This encapsulates all components that are common to all other modules.
3. `src/app/yande/yande.module`: This encapsulates all components related to Youth and Education 

### Models
* Currently all model classes are created under `src/app/models`. Later these models will be moved under specific modules

### Services
* Most services are created under `arc/app/services`. Module specific services are created under `<module-dir>/services`

### Angular Material and Flexbox
1. Use Material Design and angular flex-layout for User Interface. 
2. Material components are imported/exported in `src/app/material.modules.ts` and this module can be imported into other modules that has use Material Components

### Route Guards
* Use Route Guards (e.g. `src/app/services/auth-guard.service` and `src/app/services/yande-chair-guard.service`) to protect routes from unauthorised and unauthenticated access

### Resolver to pre-fetch data
* Use Resolvers (e.g. `src/app/yande/services/course-list-resolve.service.ts`) to prefetch component data from backend

### Spinners for perceived performance
* Use spinners (`<mat-progress-spinner>`) for perceived performance during API calls

### Test Coverage 
* Make sure test coverage is above 70% or current coverage whichever is greater

### Application state service
* All global application state variables goes into `src/app/services/app.service` (e.g. `loading`, `currentUser`, `isLoggedIn`)
 
### Adding new dependencies
* If any new dependency (other than those already added to package.json) is required for the application, please have a discussion with rest of the team members before adding the dependency to package.json

### Responsive Layouts
* Use angular flex-layout responsive breakpoint alias combined with Static Flex-Layout API to create responsive layouts

```angularjs
fxFlex.md="10px;
fxHide.lt-sm;
xLayout.gt-md="row";
```

### Observables naming convention
* Name observables with a trailing “$” sign. This can be useful when scanning through code and looking for observable values. Also, if you want a property to store the most recent value from an observable, it can be convenient to simply use the same name with or without the “$”.
```angularjs
  stopwatchValue: number;
  stopwatchValue$: Observable<number>;
 
  start() {
    this.stopwatchValue$.subscribe(num =>
      this.stopwatchValue = num
    );
  }
```

### Observable Data Services
This angular application is built around the concept of observable data services. For more details refer this [Angular University blog post](https://blog.angular-university.io/how-to-build-angular2-apps-using-rxjs-observable-data-services-pitfalls-to-avoid/).
 

