# Angular 8: Bootstrapping
1. main.ts:
	platformBrowserDynamic().bootstrapModule(AppModule)
	    		.catch(err  =>  console.error(err));
2.	This will search for the AppModule in the project. Every Angular project has to contain at least one module for bootstrapping. This module, usually, is called as the root module or app module. It is a TypeScript class decorated with @NgModule decorator.
3.	Inside the @NgModule, we have:
	1.	declarations array (for declarables such as components, directives, pipes, etc)
	2.	imports array (for modules, built-in, third-party, or own feature modules)
	3.	providers array (for providables such as services, mainly used by Angular Dependency Injection framework)
	4.	bootstrap array (which component to bootstrap)
4.	Notice that any Angular app has the default root component called as AppComponent. By default this is bootstrapped. You can also confirm this by looking at index.html file. We see AppComponent's selector, `<app-root>` there.
5.	index.html is the base html file and the whole app is inserted in the DOM at `<app-root></app-root>`
6.	styles.css is the global styles file. If we like to use bootstrap, it will be imported here. Styles defined here are applicable globally
    
