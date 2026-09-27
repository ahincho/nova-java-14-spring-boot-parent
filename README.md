# Nova Spring Boot Parent

The Maven parent POM for services built on the Nova Platform. Inheriting
from it fixes the Java version, imports the Nova BOM and the platform
starter, and pins the compiler, test and packaging plugins — so a service
POM declares what it *is*, not how it builds.

## What it sets

| | |
|---|---|
| Java | 25, source and target |
| Encoding | UTF-8 |
| Nova BOM | `nova-bom` 1.0.0 |
| Nova starter | `nova-spring-boot-starter` 1.0.1 |
| Test | `spring-boot-starter-test` |
| Plugins | `maven-compiler-plugin` 3.14.0, `maven-surefire-plugin` 3.5.3, `spring-boot-maven-plugin` 4.0.5 |

## Use

```xml
<parent>
    <groupId>pe.edu.nova.java</groupId>
    <artifactId>nova-spring-boot-parent</artifactId>
    <version>1.0.0</version>
</parent>
```

Published to GitHub Packages, so add the repository and authenticate with
a token that has `read:packages`:

```xml
<repositories>
    <repository>
        <id>github</id>
        <url>https://maven.pkg.github.com/ahincho/nova-java-14-spring-boot-parent</url>
    </repository>
</repositories>
```

## Starting from scratch

Do not hand-write the POM — generate the project:
[nova-java-spring-boot-archetype](https://github.com/ahincho/nova-java-17-spring-boot-archetype).

## The Gradle equivalent

[nova-java-spring-boot-gradle-plugin](https://github.com/ahincho/nova-java-16-spring-boot-gradle-plugin)
carries the same conventions as a convention plugin.

## License

Eclipse Public License 2.0 — see [LICENSE](LICENSE).

Copyright © 2026 Angel Hincho.
