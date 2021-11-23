# versions-maven-plugin-practice

Having fun learning how to use the `versions-maven-plugin` - https://www.mojohaus.org/versions-maven-plugin/

## What I want to do

In a multi-module project where the child module versions vary independent of one another and the parent, I want to be
able to:

- Update the parent POM's version and have every child module's reference to the parent updated to that new version.
- Update a specific child module's version to a new SNAPSHOT version.

## Maven Goals

Increment the version of `child-module-a` and make it a `SNAPSHOT`

```shell
mvn versions:set -DnextSnapshot=true -DartifactId=child-moodule-a
```

So if `child-module-a` is currently `1.0`, running the command will update it to `1.1-SNAPSHOT`.

If you're happy with the changes, run `mvn versions:commit`, otherwise run `mvn versions:revert`.