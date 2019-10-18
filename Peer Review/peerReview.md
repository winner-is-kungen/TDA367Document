# Code Review

## Do the design and implementation follow design principles?

Yes, to some extent.

### Does the project use a consistent coding style?

Very consistent. All field and variable names are in camelCase, and all class/interface/enum names are in PascalCase. All classes follow the pattern of `static fields`, `instance fields`, `constructor`, `static methods`, and `instance methods`.

### Is the code reusable?

A lot of the model is `protected`, `package-private` or `private`, preventing others from extending the model in other projects. Meaning no reusability of the model from the outside.

However, inside the model there is a great deal of possible (and realized) reusability, with many interfaces and abstract classes.

### Is it easy to maintain?

Yes. With most files being around or under 150 lines, somewhat documented in code, and few unexpected dependencies the model looks to be relatively easy to maintain.

### Can we easily add/remove functionality?

For the most part, yes.

One suggestion: Use maps instead place of `switch`-statements. Less boilerplate when adding/removing options. Some could map to values and some could map to lambda functions.

### Are design patterns used?

Nice method chaining with the Vector class.

Yes, some.

## Is the code documented?

Somewhat. Many methods lack comments completely, and some only have comments for specific lines. And other are complete with nice JDoc comments.

## Are proper names used?

All names consistently use camelCase, which is nice. The content of names is also consistent, and almost all are relevant and understandable.

## Is the design modular? Are there any unnecessary dependencies?

Very modular design 👍

One thing that can be improved is the models dependency on the different classes in the `services` package. Some classes, such as the `collisions` package, could probably be moved into the model. And some, such as the `LevelLoader`, could probably benefit from being a interface in the model and then having the implementation be injected into the model. That would allow for different implementations of file format for levels.  
The result of all of this would be a completely separated model that could be dropped into other projects.

## Does the code use proper abstractions?

Yes. Good use of interfaces and abstract classes to be able to re-use code.

## Is the code well tested?

About 50 % of the code base is run tests. Although, many tests tets the implementation of methods, not there result/effect.

## Are there any security problems, are there any performance issues?

Didn't find any. Also didn't look.

## Is the code easy to understand? Does it have an MVC structure, and is the model isolated from the other parts?

The code is as easily understood as can be. It's a lot of code, but not to difficult to wrap your mind around.

It do have an MVC structure that fits nicely with the used framework.

The model is not completely separated form the rest, but it is separated from the other parts of the MVC structure.

## Can the design or code be improved? Are there better solutions?

Everything can always be improved. Especially a work in progress.

# Document Review

In your system architecture uml, you have included dependencies the packages have with themselves. This removes focus from whats important in the graph, the relationships between the packages.

Include your user stories in the RAD document, not just a link to where to find them. If you feel that the user stories take up too much space you can some, or event most, in the appendix.

All sections should contain text, some of yours only contain subsections and some are empty.

Some spelling and grammatical mistakes, for example: some "it's" where it should have been "its".