![[Pasted image 20231118103248.png]]
- Apparently thinking in the Von Neumann Architecture causes a greater cognitive load than is usual for our brain. Is that possibly because our brain itself is not built like the Von Neumann Architecture?

# A Case:
Using the imperative style, we can copy the code of the old program and add an `if` statement.

```java
int sum = 0; i = 0;
while (i <= n) {
	i = i + 1;   
	 if (isPrime(i)) {
	       sum = sum + i * i;   
	  }
}
```

Here, we assume `isPrime` is a method that returns `true` if the argument is a prime and returns `false` otherwise.

However, in the functional programming paradigm, the solution is much more elegant.

```haskell
(fold (+) 0 . map square . filter isPrime) [1..n];;
```

# The Declarative Paradigm
The declarative programming paradigm is a style of programming where you focus on describing "what" you want to achieve, rather than specifying "how" to achieve it. In declarative programming, you declare the desired outcome, and the programming language or system figures out the steps and details of execution. This is in contrast to imperative programming, where you explicitly specify the sequence of steps and actions to achieve a goal.

Key characteristics of the declarative paradigm include:

1. **Abstraction:** Declarative languages and frameworks often provide higher-level abstractions that allow you to express complex operations or transformations concisely. This makes code more expressive and easier to read.

2. **No Side Effects:** Declarative code aims to minimize or eliminate side effects, which means that a function or expression doesn't modify any state outside of its scope. This makes it easier to reason about the behavior of code and can lead to fewer bugs.

3. **Emphasis on Expressions:** Declarative programming often revolves around expressions and functional constructs. You define relationships and transformations between data using expressions and functions rather than explicit statements.

4. **Data-Driven:** In declarative programming, data often drives the logic. You specify the desired outcome based on the input data, and the system or programming language takes care of processing that data to produce the desired result.

5. **Concurrency and Parallelism:** Declarative languages and systems are often well-suited for managing concurrency and parallelism since they focus on expressing relationships between data and tasks rather than explicit control flow.

Examples of declarative programming paradigms and languages include:

- **Functional Programming:** Functional programming languages like Haskell, Lisp, and languages that support functional programming features (e.g., JavaScript and Python) encourage a declarative style by emphasizing pure functions and immutability.

- **SQL (Structured Query Language):** SQL is a declarative language used for database querying. You specify the data you want to retrieve or manipulate, and the database engine handles the query optimization and execution details.

- **HTML and CSS:** In web development, HTML is declarative for structuring content, and CSS is declarative for specifying the styling and layout of web pages.

- **Regular Expressions:** Regular expressions are a declarative way to define patterns for text searching and manipulation.

Declarative programming can lead to code that is more concise, easier to understand, and less error-prone, particularly for complex operations or tasks that involve data transformation and manipulation. It also lends itself well to parallelism and can be a natural fit for certain problem domains, such as data processing and querying.

# Declarative Build Systems

**Imperative vs. Declarative in Build Systems:**

1. **Imperative Approach:** Imagine you're building a Lego structure by giving step-by-step instructions, like "Put the blue block on the red block, then add the yellow block on top." You're explicitly telling each action.

2. **Declarative Approach:** Now, imagine you have a picture of the desired Lego structure, and you tell someone, "I want it to look like this picture." You're declaring what you want, not how to do it.

**Advantages of Declarative Build Systems:**

- **Easier Planning:** With declarative build systems like Maven and Gradle, you describe what you want to build, like "I need a web app," and the system figures out how to build it. You don't need to worry about the nitty-gritty details.

- **Modular Building:** Declarative systems let you create complex builds by combining smaller building blocks. It's like assembling Lego pieces to make bigger structures, making it easier to manage large projects.

**Functional Programming and Declarative Thinking:**

- **Functional programming** is a style of programming that aligns well with declarative thinking. It encourages writing code that focuses on what you want to achieve, not how to do it. It helps you see through different programming languages, frameworks, and tools used in the software industry because you approach problems in a clear and abstract way.

In a nutshell, declarative programming is like giving a goal or a picture of what you want, while imperative programming is like giving detailed step-by-step instructions. Declarative build systems make it easier to manage complex projects, and learning functional programming can help you think in a more abstract and goal-oriented way, which is useful in various aspects of software development.

# Basics of Build Systems 
A build system is a software tool or framework used in software development to automate the process of compiling, assembling, and organizing source code and resources into executable or deployable artifacts. It plays a crucial role in the software development lifecycle, simplifying and streamlining the process of turning source code into a runnable or deployable application. Here are some key aspects of build systems:

1. **Compilation:** Build systems often handle the compilation of source code written in programming languages like C, C++, Java, or others. They ensure that source code is transformed into machine code or bytecode that can be executed by a computer.

2. **Dependency Management:** Build systems manage dependencies, which are external libraries or modules required by a project. They automatically download, install, and link these dependencies, ensuring that the software can run correctly.

3. **Build Process Automation:** Build systems automate the build process, eliminating the need for manual compilation and resource management. Developers can trigger builds with a single command or integrate them into development pipelines.

4. **Resource Management:** They manage resources such as configuration files, images, and templates, ensuring that these assets are properly included in the final application or package.

5. **Testing:** Many build systems incorporate testing frameworks to run unit tests, integration tests, or other types of tests as part of the build process, helping ensure the quality and reliability of the software.

6. **Packaging and Deployment:** Build systems often package the built artifacts into distributable formats, such as executable files, JAR files, or installable packages, making it easier to deploy the software on various platforms.

7. **Optimization:** They can perform code optimization, minification, or other transformations to improve the efficiency and performance of the final application.

8. **Parallelization:** Some build systems can perform tasks in parallel to take advantage of multi-core processors, speeding up the build process for large projects.

Popular build systems include:

- **Maven:** Used primarily for Java projects, Maven uses XML configuration files to manage dependencies and define build lifecycles.

- **Gradle:** Another popular choice for Java projects, Gradle uses a domain-specific language (DSL) based on Groovy or Kotlin for build configuration.

- **Make:** A general-purpose build tool that uses makefiles to describe dependencies and build rules.

- **CMake:** Used for C and C++ projects, CMake generates platform-specific build scripts or project files for various development environments.

- **Ant:** An older build tool primarily used for Java projects, using XML build scripts.

- **Webpack:** Commonly used in modern web development, Webpack bundles and manages JavaScript and other web assets.

- **MSBuild:** Microsoft's build system used for .NET applications.

Build systems are an integral part of the software development process, ensuring that code is built consistently and efficiently, and that dependencies are managed correctly, ultimately contributing to the reliability and maintainability of software projects.





