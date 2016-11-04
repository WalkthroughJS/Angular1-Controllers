# Angular1-part2-ngModel

In [Part 1](https://github.com/WalkthroughJS/Angular1-part1-GettingStarted), we built a running app with an `index.html` and `app.js` with our app declaration and a controller with a scope variable that connected the controller to the view.

In this lesson (Part 2), we're going to talk about ng-model and a bit about how it works. Let's start by talking a little bit about scope variables. We've established that scope variables have a connection to the view, which we proved by setting our `scope.hello` variable to `world` and getting it to show up when we put `{{hello}}` inside the body that we assigned to the `myFirstController` controller. I also mentioned the idea of two-way binding in the last lesson, but how does that connect to scope variables. Well, let's see. 

Let's start by making a copy the same project we had last time around and making sure that it works. Once we do that, let's open up `index.html`. Inisde the body tag, let's add a text box above the `{{hello}}`. Inside the input element, make it a type of text and add this attribute: `ng-model="hello"`. Now, let's go into the controller and remove the `$scope.hello` variable.

```text
<!DOCTYPE html>
<html ng-app="myFirstNgApp">
  <head>
    <meta charset="utf-8">
    <title></title>
  </head>
  <body ng-controller="myFirstController">
    <input type="text" ng-model="hello">
    <p>{{hello}}</p>
    
    <script src="https://cdnjs.cloudflare.com/ajax/libs/angular.js/1.5.8/angular.js" charset="utf-8"></script>
    <script src="app.js" charset="utf-8"></script>
  </body>
</html>
```

After you save it, open up `index.html`. Now, let's type something into the text box. Crazy enough, the same thing that you type into the text box is the thing that's showing up below it where that `{{hello}}` we have is. Even though we don't have a scope variable declared in the controller, when we add that `ng-model` attribute to the input element in `index.html`, a scope variable of that name is declared and assigned in memory. How it updates itself after it changes is another thing inside Angular called the "digest cycle", but that's nothing you need to worry about until later on. The short explanation is that Angular has a "watcher" for all the scope variables and every time one of them changes, the app refreshes itself and applies the changes. It's a pretty cool system the've got, but alas, let's move on to more applicable things.

Let's go back to that thing we mentioned in part 1 called "dependency injection". One of the cool things about Angular is that you can extend the functionality of the controller by "injecting" services into the controller's callback function's arguments. What do I mean by "services", though? Basically, Angular has a lot of built-in functionality that it lets you inject it whenever you need it. For example, if you need to make an API call to get info from your database or you want to get some JSON from a public API, there's a service called `$http` that you can use. If you want to access the window object for some crazy reason, Angular gives you `$window`. There's a huge list of services they have built in, BUT you can also create services yourself and that's something that we'll talk about in part 3. I know this lesson seems so short, given how much of a staple of Angular that controllers may seem like, but the truth is that what makes controllers so useful are the services you can inject into it to extend the functionality. 

So, let's review briefly what we went over in part 2. Controllers
