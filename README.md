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
| Nova BOM | `nova-spring-boot-bom` 2.0.3 |
| Nova starter | `nova-spring-boot-starter` 1.0.4 |
| Test | `spring-boot-starter-test` |
| Plugins | `maven-compiler-plugin` 3.14.0, `maven-surefire-plugin` 3.5.3, `spring-boot-maven-plugin` 4.0.8 |

2.0.0 inherits the BOM family with the
[ADR-039](https://github.com/ahincho/nova-shared-01-docs/blob/main/adrs/shared/ADR-039-nombres-de-artefacto-derivados-del-repositorio.md)
names: the starters are `nova-*-spring-boot-starter`, and the 1.0.x names
(`nova-api-standard-starter`, `nova-mask-starter`, `nova-observability-starter`)
are no longer managed. A child that declares one of them has to move to the new name.

## Use

```xml
<parent>
    <groupId>pe.edu.nova.java</groupId>
    <artifactId>nova-spring-boot-parent</artifactId>
    <version>2.0.2</version>
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
[nova-java-17-spring-boot-archetype](https://github.com/ahincho/nova-java-17-spring-boot-archetype).

## The Gradle equivalent

[nova-java-16-spring-boot-gradle-plugin](https://github.com/ahincho/nova-java-16-spring-boot-gradle-plugin)
carries the same conventions as a convention plugin.

## License

Eclipse Public License 2.0 — see [LICENSE](LICENSE).

Copyright © 2026 Angel Hincho.
