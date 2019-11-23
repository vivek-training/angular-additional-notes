# Angular 8: Services
1. Services are used in Angular for state management. They make the data communication between the components really easy and straight-forward, thanks to Angular's built-in dependency-injection framework.
2. We create a service with  `ng g s xyz`
3. Services are used by Angular for dependency injection. That means whoever that wants a service, would ask for it in the constructor. Angular would then inject the service to those components or directives. Therefore, the services are decorated with @Injectible({...})
4. There is an important property in @Injectible configuration `providedIn: 'root'`
5. This property makes the service as a singleton. Throughout the app's lifetime, there is going to be only one instance of this service. This is why all the interested parties (components and directives) can communicate via the service.
6. The power of the services is further strengtheneed by RxJS and Observables