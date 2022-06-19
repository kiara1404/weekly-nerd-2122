### Introduction
During one the visits of the Weekly Mingle, I visited the company Label A. They showed us around the office and explained how they work and what they make. I thought it was cool that they work with a lot of different clients. 
They also had a little assignment for us about TypeScript. Up until that point I had only heard about it and never really looked into it. It was a small but very informative introduction. they also said that it's basically the new standard within the industry and this made me curious to learn more about it.

### What is TypeScript
TypeScript is a superset of JavaScript. This means that it adds features on top of what JavaScript offers. It takes all the functionalities and structures JavaScript provides and adds a few things to that. One of these functionalities is strict types, which means that if you declare a variable a Boolean, you can't change it into something else in your code. This is really helpful when you're working in a team but also to validate your code to see it it's working properly.

JavaScript itself is a loosely typed and dynamic language. Variables are not directly associated with any particular value type and any variable can be assigned and re-assigned values of all types.

#### JavaScript
Look at the example below:
```js
let foo = 42; // foo is now a number
foo = "bar";  // foo is now a string
foo = true;   // foo is now a boolean
```
You can see how you can change the value of the variable into a different type. This was done to be forgiving because it was creat4d to only be used to add certain functionalities to a website. But JavaScript grew a lot and is not only used for functionalities anymore. It's also used to built huge applications, and when building these said applications, dynamic types can lead to bugs in the code.

### TypeScript Basics
There are a few ways to declare types in Typescript. The first one is _inference_, in which you actually don't declare a type but TypeScript infers (guesses) it's for you based on what you typed. 

```js
//string
let string = 'this is a string';
```
When you'd want to change it to a number, it will display an error.

#### Declaring types
Below is an example of how you declare a type to a variable. This will let TypeScript know that variable `a` can only be a string.

```js
  // boolean
  let a: string = 'Kiara;

  //boolean
let b: Boolean
//array
let c: string[] // this will have an array with string values within.
```


#### Interfaces
When working with objects, there's a different syntax for declaring types which is called an interface. It looks a lot like a JS object but we use the interfacce keyword and there are no quotes or commas;

```js
export type Employee = {
  name: string;
  age: number;
  city: string;
  interests: string[];
};

export function exercise0301() {
  const employee: Employee = {
    name: 'Timothy',
    age: 24,
    city: 'Amsterdam',
    interests: ['React', 'Gatsby'],
  };
```
You could make a key conditional, allowign it to be present or not. You need to add a question mark at the end of the key in the interface:

```js
export type Employee = {
  name: string;
  age: number;
  city: string;
  interests?: string[];
};
```

If you have a variable that can be multiple types, you declare them like this:

```js
export type Employee = {
  name: string;
  age: number | string;
  city: string;
  interests: string[];
};
```

When typing functions, you can declare its parameters as wel as its return value:

```js
interface myData {
  name: string;
  city: string;
  age: number;
  printMsg: (message: string) => string;
}
```

### TypeScript compiler
Every time we run our TS file, it compiles our code and checks the data types. If there are any errors, the program will not run. This is a big difference with JavaScript because in JS types are not checked until the program executes.

Browsers do not understand the TypeScript syntax and this is why you'll need to compile your `.ts` file into an `.js` file.

## How to create a TypeScript project
When you want to start a TS project, you'll need Node en NPM installed. Once you are in the right directory,, you'll need to run `npm i typescript --save-dev`. This will install it and save it as a dev dependency.

The next step is to run `npx tsc -init`. This will initializse your project by creating a `tsconfig.json` file. (Just like `npm init`). This file will allow you to configurate and customize but also comes with a set of default options.

After this, you can start creating a file with the `.ts` extention and start wrinting TypeScript code. To compile to JS run the following command `tsc <filename>`. 
Happy coding!


## Sources 
[](https://medium.com/swlh/intro-to-typescript-63bd15c2cd0e)
[](https://www.freecodecamp.org/news/an-introduction-to-typescript/)
[](https://www.typescriptlang.org/)