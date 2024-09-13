---
layout: essay
type: essay
title: "Smart Questions"
# All dates must be YYYY-MM-DD format!
date: 2024-09-12
published: true
labels:
  - Questions
  - Answers
  - StackOverflow
---

## What is the importance of a smart question?

As a software engineer, it would be very viable to learn the proper way to ask questions so that you can get proper answers in return. When asking questions online in forums such as StackOverflow, for example, we can take a look at Eric Raymond’s essay “How to Ask Questions the Smart Way” for a guideline on how to deliver these questions in a precise way. These guidelines include things such as being specific, providing context, being clear and concise, etc.

## Demonstration of the "smart" way

To demonstrate a “smart way” of asking a question, there is a StackOverflow question submission titled [“Error: `Cannot find module` when npm test using nest typescript”](https://stackoverflow.com/q/78957796), which contains the following: 

```
I’m encountering an error when attempting to execute command npm run. Despite exploring various solutions and troubleshooting steps suggested in other forums and documentation, I haven’t been able to resolve the issue. Could you please provide guidance or suggest a method to address this problem effectively?

the error i get

 FAIL  test/app.e2e-spec.ts
  ● Test suite failed to run

Cannot find module 'src/category/category.module' from '../src/info/info.module.ts'

Require stack:
  D:/astagatra-web/server/src/info/info.module.ts
  D:/astagatra-web/server/src/app.module.ts
  app.e2e-spec.ts

  1 | import { Module } from "@nestjs/common";
  2 | import { DynamooseModule } from "nestjs-dynamoose";
> 3 | import { CategoryModule } from "src/category/category.module";
    | ^
  4 | import { SharedServiceModule } from "src/shared/services/service.module";
  5 | import { UserModule } from "src/user/user.module";
  6 | import { InfoPublicController } from "./controller/info.public.controller";

  at Resolver.resolveModule (../node_modules/jest-resolve/build/resolver.js:324:11)
  at Object.<anonymous> (../src/info/info.module.ts:3:1)
```
The author continues on to provide files for package.json, tsconfig.json, and info.module.ts. This submission follows the guidelines given by Raymond, allowing the community to respond with an equally as smart response to assist them.

```
I got the same error and I solved with this approach:

You need to configure the moduleNameMapper in Jest to match your tsconfig.json paths. Here is how:
Update your tsconfig.json :

"baseUrl": ".",
"paths": {
  "src/*": ["./src/*"]
}

Then update Jest configuration (in package.json) adding a moduleNameMapper:

 "jest": {
  "moduleNameMapper": {
    "^src/(.*)$": "<rootDir>/$1"
  }
 }
```

## The "not smart" way

An example of a “not smart way” of asking a question would be demonstrated in this StackOverflow question submission titled [“JAVASCRIPT Can someone fix my code? [closed]”](https://stackoverflow.com/q/44821329), containing the following:

```
Can someone help me fix my code? The function is like the Eval function but has a √ added but it doesn't work
function Eval(n) {
    var a = n.split("√").length - 1;
    var b = n.split("√").length;
    var c = a.replace("√" + d, e);
    var d = parseFloat(b[1]);
    var e = Math.sqrt(d);
    while (a != 0) {
        b();
        d();
        e();
        c();
        return;
    }
}
document.write(Eval("64+√68+32"));
```
This question reflects a “not smart way” of asking a question because it lacks enough context and doesn’t necessarily prove that the author attempted to fix the errors and instead just asked for help right away. Along with the initial post, some of the comments on it aren’t very respectful or helpful; “Uhh.. Please open the console of your browser, there's a bunch of error messages waiting for you” is a comment that was left in response to the user.

## Conclusion

As a result of this experience, I was able to verify the differences between a smart and not smart way to ask and answer questions. This also helps us to see the need to have a community where there are people that are willing and able to help each other if and when we can. I believe that doing this activity will better prepare me for the future when asking questions, especially regarding software engineering questions.
