# Angular 8: Routing
1.	Angular uses component based routing. To use the routing, import `RouterModule` in the `app.module.ts`. This cannot be used as such. We need to use the factory method `forRoot(...)` which takes an array of routes. Usually we create the routes array as a const in a file and pass this to the `AppModule` imports array as `RouterModule.forRoot(routes)`
2.	In the routes array, the basic route is a simple mapping between path and the component. `**` acts as the match-all, which is obviously kept at the bottom. Most specific routes are at top and most general ones are at the bottom. If a route uses route parameters (such as `route/param/id/x/y`), use the path as: `res/:param1/:param2`.
3.	Once we have the router, it needs a outlet to output the matched component. This is done by using `<router-outlet></router-outlet>` (usually in app.component.html.
4.	There are 3 ways to achieve the navigation in Angular:
	1.	Through `[routerLink]="['/path', 'param1', 'param2']" [queryParams]="{qparam: true}"  fragment="frg"`
	2.	Through code based navigation using Router (a service from RouterModule) as: `this.router.navigate(['/path', 'param'], navigationExtras);` Please take a close look at angular-router project. Know more about navigationExtras in  **topic01.component.ts** line 17-21
	3.	Hard navigation by directly entering the url in the browser. This actually reloads the page, but works neverthelsess
5.	Do not use href property in the a tags, as this reloads the page and defeats the purpose of the SPA.
6.	To get the route paramaeters and query parameters and fragments in the destination component, we use ActivatedRoute. Please refer to  **topic02.component.ts** line 13-14 in angular-router project.