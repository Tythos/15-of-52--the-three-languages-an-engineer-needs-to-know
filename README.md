We're going to revert to type, just a little bit, for today. I want to develop an idea that has been developing for a while in software engineering. Specifically, I want to tackle the idea that, in order to be a successful software engineer "YOU NEED TO LEARN LANGUAGE XYZ".

What I've found is, instead, it's less about specific languages and more about specific "slots" in your toolbelt. There are specific roles that different languages will provide, largely categorized by how they are used. So, today we're going to break down the three "levels" of programming languages that you will want to learn and use.

Let's start with a specific example of such a "stack", based on languages I've used a lot of in my own experience.

![an example "stack" of languages](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/7zx0rh5uggp9bnn878y0.png)

After a while what you'll realize (regardless of what your selections are) that different languages are good at different things. It can be fun to flame this-language-vs-that-language, etc. But there may be different trades with a new project that go into your decision of what language to use. C++ gets a lot of hate! Python gets a lot of hate! Javascript gets a lot of hate! But regardless, there are specific situations where you would choose each of these languages, and there are different roles for which they will be better suited.

## The Three Layers

One of the most interesting books I've read is "Masterminds of Programming" (though now that I think of it, this is probably due for an update with the amazing array of new languages modern developers can choose from!)

[Masterminds of Programming](https://www.amazon.com/Masterminds-Programming-Conversations-Creators-Languages/dp/0596515170)

It's a great collection of interviews with different programming language designers, and (in addition to fun quotes of GvR trash-talking Java, and Java designers trash-talking C++ and Bjarne Stroustrup, etc.) it illuminates just how strongly the design of different languages are shaped by:

* Personalities, preferences, heuristics

* Original design purposes

* Problems/objectives to solve

* Constraints of the time

![cover of text](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/dkou3o2egh9eepnwz69l.png)

Javascript was created in a handful of days at Netscape, for example! It would be a very different language if it was designed by committee over the process of several years. But it's been very successful because it solves a specific problem with great integration, very minimal syntax, and good libraries for DOM manipulation and asynchronous programming.

### Lower-Level Languages

Let's start with the "bottom" level. We'll assume that we don't necessarily need to learn assembly or machine language. Instead, what makes a language "low level" is typically something like this:

* It builds to a platform-specific set of instructions

* It is compiled (and possibly linked)

* There is no garbage collection or similar "guards"; you are directly allocating and manipulating memory 

C and C++ are obvious examples here. (The third bullet from above precludes a language like Go, but it does blur the lines a little bit.) Other good examples include Zig, Rust, or even Fortran. There are similar candidates but, in general, it's very useful to have working knowledge of at least one "low-level" programming language.

One caveat: You lose a lot of quality-of-life features at the lower level. One thing that C and C++ don't have is a modern package manager, for example! How are you identifying specific bundles of code and symbols? How are dependencies being resolved and combined? How do you conduct build and meta-operations (like documentation and testing)? Some languages have modern solutions for these, like Rust, but it isn't always easy.

### General-Purpose Language

This is not a domain-specific language--quite the contrary. Languages living here are going to come with a degree of garbage collection and other resource/performance automation features. You will also have a variety of platform-agnostic tools for key OS interactions like path resolution, file input/output, threading, etc.

One key feature of a general-purpose language is just how quickly and easily you can address a specific arbitrary problem, particularly at the prototyping stage. This is often enabled and characterized by a healthy package ecosystem, which makes it easy to reuse your own code, and to leverage code that other people have written. Another distinguishing feature at this level is the availability of bindings to other languages--being able to wrap a static library from C, for example.

This is a great place to do side projects and other experiments. It's also a great place to develop comfort without needing to look up documentation for specific syntax and other subtle variations. Other examples (beyond Python) include Ruby and Go. You'll also find a lot of small teams built around these languages because they're commonly fluent and easy to recruit for.

### UI Scripting

At our "highest" level, we have a set of more elementary languages that (while not necessarily domain-specific) are commonly used for binding things like UI events, glue between systems or applications, and other automation capabilities. There is probably some kind of embedded context or interpreter here, which is one of the defining characteristics (compared to general-purpose languages that are more likely to be running on an intermediate byte-code representation).

Other examples of higher-level UI scripting languages, beyond Javascript, include things like Lua or (arguably) Swift. I would even put React (let the debate begin!) in this category as its own unique quasi-language (mixed syntax aside, this isn't obvious). And of course TypeScript qualifies as well.

## BUT WAIT THERE'S MORE!

There are a few other languages that will be useful for you to learn in your career. These don't really correspond as well to specific "levels" as the first three. But for context let's consider a model of game engine organization I put together in an earlier article.

https://dev.to/tythos/engines-evolution-10gk

In particular, let's consider the following diagram that defines an engine evolution that represents the boundary between beginner-intermediate game development efforts and intermediate-advanced.

![one model of intermediate game engine design patterns](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/vbizib45i8lonbzeqflx.png)

There are several "layers" to game development. The "engine"--which is largely a way to scaffold event loops, window management, shared interfaces, and libraries of reusable software elements--isn't actually most of the game.

![the three layers as they apply to game development](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/3rvtqkzvum7dpatp8kal.png)

The engine is focused on performance and reusability, but it is *not* focused on implementing the mechanics of a specific game. The game logic, specific models, and other things that are developed to realize a specific game publication, are probably written "on top of" (or at least in conjunction with) the lower-level engine code.

But, there's another level beyond this. If you've ever written add-ons in World of Warcraft, for example, you know that there's an interpreter embedded within the game mechanics (with specific events you can subscribe to and assets you can extend or customize). Lua is a great example of this higher-level "scripting" usecase that can be used by the community to customize and extend different behaviors.

If you only know languages that quality for each of these three layers, you're going to do pretty well. But there are at least three other languages that will come in handy. This will be true regardless of what your "tech stack" selection of languages looks like from the first three "layers", whether it's C++/Python/Javascript, or Zig/Go/Lua, or anything else.

![a few other categories, beyond the layers](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/rrye869bgq25pw6da845.png)

### Shell Scripting

Purely for the sake of "getting around" your development systems, you will likely need to learn some degree of shell scripting. If you're on Linux, for example, learn to write a `.sh` script. On Windows, learn how to write a `.bat` file. Automating system actions (including basic variable assignment, pipe manipulation/integration, and control flow statements) is an invaluable way to save time and headache. Many, *MANY* tasks you will need to function will greatly benefit from the ability to automate it with a small shell script.

![the classic thinkgeek tshirt, rip](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/xg9s5nhfcjok3ub3mp02.jpg)

Interestingly, Python started out as a cross-platform scripting language for the scientific computing community! While it's since grown into a GPL (a lot of languages do this, much like Zig is growing into a GPL having started out as a systems-programming language), it still has very potent capacity as a scripting language for automation (think about the `os`, `sys`, and `subprocess` core modules, for example). Bonus points for crossing off two categories with the same language, of course!

### Domain-Specific Languages

In contrast to "general-purpose" programming languages, there are "domain-specific" languages that are uniquely suited (and designed around) the defining usecase of a specific domain. MATLAB is a good example here, which you will likely need to learn to perform heavy lifting in numerical algorithms and tensor manipulation.

Tensorflow is also an example of a DSL, even though it's used and manipulated in other languages, because there's a specific grammar and syntax to the manner in which neural networks are constructed, configured, and trained/utilized. You could learn Terraform as a DSL for large-scale static infrastructure-as-code (IAC) automation, for example, if you do a lot of cloud engineering. If you like crypto/blockchain, you'll likely pick up something like Solidity at some point.

But by definition your DSL will likely be a function of what specific domain you find yourself. Just be aware that you're probably going go benefit from picking up a DSL at some point.

### Structured Query Language

The way you interact with (and understand) data, data-oriented development, and data-driven engineering is largely facilitated by learning SQL.

No other category in this article requires you to choose a specific language. There are many candidates for scripting languages, general-purpose languages, etc.

But you need to learn SQL. Because it rewires your brain in an incredibly helpful way.

You need to understand how queries work; how data is sorted and filtered; how tables and schemas are structured; how relational references work; how different "JOIN" logic interacts; how ACID assurances affect how data manipulation and mutation takes place.

And NoSQL and document stores are fine things to know as well. It's helpful to learn how OpenAPI and JSONSchemas work. These are all specific data structures and interfaces, more than specific programming languages. But regardless of whether you like to use PostreSQL or MySQL, you should learn SQL.

SQLite is a great place to start, by the way. Among other things, you can manipulate SQL directly within a memory store, or directly against a specific file, and it's API is built into common languages like Python. (This, by the way, is one of the ways you can tell how good a general-purpose language is--by what kind of tools it gives you "out of the box" to interact with common data and procedure interoperability requirements).

So. Choose any other language for any other category on this page. But learn SQL.

## Conclusion

Let's review. There are three "layers" of languages that you should learn at least one candidate for:

1. "Low-level languages" that are typically platform-specific, compiled, and "direct"--that is, free of garbage collection or other resource abstractions. (Sometimes you'll hear the term "systems programming languages" used here as well, by the way, though that is more specific.)

1. "General-purpose languages" that are quick and easy to use, typically interpreted in byte code, and come with a healthy package management ecosystem for reusable tools. (Your operating system will not be written in a GPL. But the main mechanics of your favorite game might be.)

1. "UI/scripting languages" that help easily bind high-level UI interactions and other events with basic behaviors and interactions that "glue" together other languages and resources.

By the way, there are specific ways for each of these layers to "interoperate" with one another, as well. Whether it's REST and WebSocket interactions between the top two layers, or C ABI and structure-sharing between the lower two layers, the "health" of your "stack" will likely depend on how well you can combine specific tools in each of these categories.

There are also three categories of languages beyond these "layers" that can be very helpful to consider.

1. Some form of scripting language for automating programs and other system interactions for your operating system

1. Some form of domain-specific language, or DSL, that is specific to your particular field or problem set

1. SQL, in order to learn how to "think" in data-oriented operations and structures.

![three and three](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/a1yc9b4i122cnsebahe9.png)

So that's about it. Learn them and love them! A good combination of these categories will take you all the way through your career. Unless you decide to dabble in the dark arts of functional programming, at least.
