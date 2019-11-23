# Angular 8: Structural Directives
1. A directive in Angular is a command to the Angular runtime to accomplish something definite. There are two kinds of directives: structural and attribute directives.
2. A structural directive changes the DOM structure by adding or removing nodes. These structural directives are prefixed with asterix or *
3. For example, if we were to render a list of cities as a HTMl list, we would write the following template:
	`<ul>`
		`<li *ngFor="let city of cities"> {{ city}} </li>`
	`</ul>`
	Please note that, city is initialized to the current item in every iteration ove the cities array. In this case, the `<li>` is called as the host element for `*ngFor` structural directive. Therefore the variable city is available within this element.
4.	The `*ngFor` gives other useful properties which can be used by aliasing. To access these special properties, we need to continue the expression using `;` such as 
	1.	`<li *ngFor="let city of cities; index as i"> {{ i }}. {{ city}} </li>` Please note the index is a built in property of ngFor and as such it cannot be used. It has to be aliased using `as`.
	2.	`<li *ngFor="let city of cities; even as ev; odd as od; first as fr; last as ls"> {{ city}} </li>` Please note, even, odd, first, last are boolean properties. Multiple continuation is possible as in this case.
5.	For conditional rendering of an element, we have `*ngIf="expression"`. Please refer to the `topic1` component in example project `angular-view`.
6.	Please note the use of psuedo selector elements: `<ng-template>` `<ng-container>`. Also, please note the usage of `[ngSwitch]="property"` along with `*ngSwitchCase` and `*ngSwitchDefault`
7.	Any element (including the component) in the template can be referred by a template reference, such as `<h2 #header>This is heading</h2>`. Throughout the template, this h2 is available as the `header` template reference.
8.	Angular encapsulates the browser's native DOM and provides the easier and intuitive abstractions over the native elements. Template reference is one such abstraction. The other useful abstractions are concerning the native DOM events such as click. In the standard web programming, we attach a event handler for a particular known event. Angular provides an easier syntax to achieve this. For example, `<button (click)="clickHandler($event)">Ok</button>`. Here, the `(click)` is the Angular's way of hooking the events. `clickHandler` is the method inside the component class. `$event` is the special and reserved keyword which tunnels the native event args object to the handler. In the template, this has to be exactly `$event`. But in the handler method, it could be named anything.
