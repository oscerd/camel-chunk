# Chunk Component

# Introduction

This component use the Java Chunk library: http://www.x5software.com/chunk/examples/ChunkExample?loc=en_US

Chunk is a Template Engine for Java similar to Apache Velocity, Mustache Java and Freemarker

The **chunk:** component allows for processing a message using a Chunk template. This can be useful when using Templating to build responses for requests. 

Maven users will need to add the following dependency to their pom.xml for this component:

```xml

<dependency>
    <groupId>org.apache.camel</groupId>
    <artifactId>camel-chunk</artifactId>
    <version>x.x.x</version>
    <!-- use the same version as your Camel core version -->
</dependency>
```

# URI format

```

chunk:templateName[?options]

```

# Options

By default the chunk library will scan a default folder "themes" for a specific template, however is possible to define a differente folder to scan using the specific option.
Default extension of template file are .chtml and .cxml, however is possible to define different extension using the specific option.

| Option              | Default | Description                                                                                                            |
|---------------------|---------|------------------------------------------------------------------------------------------------------------------------|
| encoding            | null    | Character encoding of the resource content.                                                                            |
| themesFolder        | null    | Alternative folder to scan for a template name.                                                                        |
| themeSubfolder      | null    | Alternative subfolder to scan for a template name if themeFolder parameter is set.                                     |
| themeLayer          | null    | A specific layer of a template file to use as template.                                                                |
| extension           | null    | Alternative extension to scan for a template name if themeFolder and themeSubfolder are set                            |

#Examples

**Example 1**

```java
                from("direct:in")
                        .to("chunk://file")
                        .to("direct:out");
```

In this example the chunk component will look for file.chtml template in themes folder and it will use it as template.
