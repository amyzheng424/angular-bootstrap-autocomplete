# angular-bootstrap-autocomplete
A simple autocomplete component for Angular and Bootstrap

# Getting started
> **NOTE**: Currently, the component is not available on **npm**, but I'll be getting to that soon.

**1.** As of now, you should clone the component from the Github repository:

`git clone http://github.com/DGarvanski/angular-bootstrap-autocomplete.git`

**2.** Import/Include the `BootstrapAutocompleteModule`

<pre>@NgModule({
  declarations: [
    AppComponent
  ],
  imports: [
    BrowserModule,
    BrowserAnimationsModule,
    FormsModule,
    HttpModule,
    RoutingModule,
    BootstrapAutocompleteModule <--//
  ],
  providers: [],
  bootstrap: [AppComponent]
})
export class AppModule {
}</pre>

**3.** Add the component wherever you need it: 

`<bootstrap-autocomplete></bootstrap-autocomplete>`

# Configure it!
The **angular-bootstrap-autocomplete** component has several `@Input()` properties that you need and/or can use:

**1.** `@Input() entries: Array<any>` (required):

The array that will populate the autocomplete options

`<bootstrap-autocomplete [entries]="myAwesomeArrayOfAwesomeStuff"></bootstrap-autocomplete>`


**2.** `@Input() entryProperty: string` (optional): 

Use this if you need to display/filter by a specific property of an object

Example: 

`myAwesomeArrayOfAwesomeStuff = [{name: "Cyborg Duck", powerLevel: "Unlimited" }]`

`<bootstrap-autocomplete [entries]="myAwesomeArrayOfAwesomeStuff" entryProperty="name"></bootstrap-autocomplete>`

This will filter the entries by the `name` property and display the name in the options and input field.


**3.** `@Input() inputPlaceholder: string` (Default: "Search...", optional):

Text for the input field placeholder

`<bootstrap-autocomplete inputPlaceholder="Filter the things!"></bootstrap-autocomplete>`

**4.** `@Input() inputId: string | number` (Default: 0, optional if there's only one instance of the component, required if there are 2 or more):

Modifies the `id` of the input field and dropdown menu. Should be used when having more than one `<bootstrap-autocomplete></bootstrap-autocomplete>` on a page (**TODO**: Should be replaced by an element reference);

`<bootstrap-autocomplete inputId="0"></bootstrap-autocomplete>`

`<bootstrap-autocomplete inputId="1"></bootstrap-autocomplete>`

`<bootstrap-autocomplete inputId="iCouldBeJustARandomString"></bootstrap-autocomplete>`


# Selection event
There is also one event fired on selecting an option from the dropdown menu:

`@Output() onEntrySelected = new EventEmitter();`

`<bootstrap-autocomplete (onEntrySelected)="doSomeStuffWithTheSelection($event)"></bootstrap-autocomplete>`




