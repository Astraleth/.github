# Hello there 👋

Welcome to our GitHub organization.
Here you can find a lot of different tools and projects
written for the [Astraleth Minecraft Server](https://astraleth.net).

For questions or support, please head over to our [Discord](https://dc.astraleth.net)!

## Table of Contents

- 💻 [Our technology](#-our-technology)
- 🦅 [Branching strategy](#-branching-strategy)
- 📖 [Style guide](#-style-guide)
- 💼 [Hiring](#-hiring)

## 💻 Our technology

Our core server software is built using [Minestom](https://minestom.net/).
For our database, we use a combination of PostgreSQL for structured and MongoDB for unstructured data.
Each game server runs independently of each other and is built to be redeployed at any point,
meaning all player data is stored in the database.
Our core system is organized by using a [module system](https://git.astraleth.net/astramod).
For deployment,
we use Docker with a custom cloud system that allows a deployment of Docker containers depending on the player count.

## 🦅 Branching strategy

At Astraleth, we follow the `stable <- dev` strategy. In practice, that means that the `stable` branch should be
deployable at any given time. All code is first pushed into the `dev` or a `feature/<feature>` branch, the latter being
then pushed into the `dev` branch. When the code inside the `dev` branch is ready for a new release, the `dev` branch is
merged into the `stable` branch by using a pull request. This secures stability and provides a better overview of
changes.

When committing, a commit should always have a good commit description. Ideally, a message is written in a way that
allows someone to add `When applied this commit will ` in front of it. This allows a consistent commit history. An
example of a bad commit is:

```
+ DatabaseModule 
```

A better version would be:

```
Add the DatabaseModule
```

## 📖 Style guide

We value readability and consistency at Astraleth. For that reason, we declared a few things that are mandatory for all
commits to the codebase:

- All packages should follow the format `net.astraleth.<project>.<package>`, for
  example `net.astraleth.astramod.annotations`.
- The main class of each project should be named in a way that resembles the project name and be placed in the root
  package. For example, a project named AstraCloud would have its main class named `AstraCloud` and placed in the
  package `net.astraleth.astracloud.AstraCloud`. Classes that have a `public static void` method should be
  called `Launcher` and only initialize the main class.
- Static abuse is strictly forbidden; dependency injection should be used in every possible scenario.
- Variables should have a clear and understandable name, nothing like `int i; float f;` etc.

## 💼 Hiring

Since we are a group of MMO enthusiasts that don't really plan on making any money with the server, all positions inside
Astraleth are voluntary positions.
Because of obvious reasons, we require each new member of the team to sign an NDA and
a copyright assignment.
Because of that, we are only hiring above the age of 18.
If you want to join our team and are
willing to sign the documents required, you can reach out to us using different ways:

- By using our [website](https://www.astraleth.net) (currently down)
- By writing an email to apply@astraleth.net
- Or by joining our [Discord server](https://dc.astraleth.net)