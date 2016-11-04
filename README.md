# Angular1-Controllers

In [Part 1](https://github.com/WalkthroughJS/Angular1-part1-GettingStarted), we built a running app with an `index.html` and `app.js` with our app declaration and a controller with a scope variable that connected the controller to the view.

In this lesson (Part 2), we're going to talk about controllers and a bit about how they work. Let's start by talking a little bit about scope variables. We've established that scope variables have a connection to the view, which we proved by setting our `scope.hello` variable to `world` and getting it to show up when we put `{{hello}}` inside the body that we assigned to the `myFirstController` controller. I also mentioned the idea of two-way binding in the last lesson, but how does that connect to scope variables. Well, let's see. 

Let's start by making a copy the same project we had last time around and making sure that it works. Once we do that, let's open up `index.html`. Inisde the body tag, let's add a text box above the `{{hello}}`.

```text
<!DOCTYPE html>
<html ng-app="myFirstNgApp">
  <head>
    <meta charset="utf-8">
    <title></title>
  </head>
  <body ng-controller="myFirstController">
    <input type="text" ng-model="hello">
    {{hello}}
    
    <script src="https://cdnjs.cloudflare.com/ajax/libs/angular.js/1.5.8/angular.js" charset="utf-8"></script>
    <script src="app.js" charset="utf-8"></script>
  </body>
</html>
```
