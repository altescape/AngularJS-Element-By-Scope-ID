AngularJS: Get HTML elements by scope ID
========================================

AngularJS Get an element by inputting the Scope ID (which can be found from AngularJS Batarang)

### SET-UP 

1. Create a favourite in Chrome (it can be of anything, this page for instance) and add it to the bookmark bar.
2. Now edit it and rename it to something helpful, I've called mine AngularJS Scope ID
3. While editing copy the contents from script.txt or below and place it in the url field.

### USAGE

When you are developing with AngularJS Batarang you get a tree view of all current scopes, eg:

~~~
< Scope (001)
  < Scope (002)
    < Scope (003)
~~~

It doesn't give any detail about what or where in the HTML those scopes are.

Now if you click the newly created bookmark and go to Chrome's developer console you now have access to the function ```getElementByScopeId(scopeId)```

In the console type this function ( ```getElementByScopeId('002')``` ) and the console will print out the HTML element. Hovering over the print out will highlight it in the browser window, eg:


``` > <div class="wrap" ng-controller="MyCtrl">...</div> ```

---

### CODE

#### PUT IN BOOKMARK:URL FIELD

~~~
javascript:console.info("Script ready, now use getElementByScopeId('id')");function getElementByScopeId(scopeId) {var i; var scopesInDom = angular.element('.ng-scope'); for (i=0; i < scopesInDom.length; i++) {if (angular.element(scopesInDom[i]).scope().$id === scopeId) { return scopesInDom[i]; } } };
~~~

#### PUT IN CHROME DEV CONSOLE

~~~
getElementByScopeId('002')
~~~


#### WILL OUTPUT

~~~
> <div class="wrap" ng-controller="MyCtrl">...</div>
~~~

---

##### PRETIFIED VERSION

~~~
javascript: console.info("Script ready, now use getElementByScopeId('id')");

function getElementByScopeId(scopeId) {
    var i;
    var scopesInDom = angular.element('.ng-scope');
    for (i = 0; i < scopesInDom.length; i++) {
        if (angular.element(scopesInDom[i]).scope().$id === scopeId) {
            return scopesInDom[i];
        }
    }
};
~~~
