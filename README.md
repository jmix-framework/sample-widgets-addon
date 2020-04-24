# sample-widgets-addon

An example of a widgets add-on that can be added to a Jmix project as a dependency.

## Widgets Add-on

Theme add-ons may provide SCSS files for a theme compilation. They must comply with the following requirements:

* The `*.gwt.xml` file must be created in a JAR-file
* The JAR-file must contain the `Vaadin-Widgetsets` key in the Manifest with the path to the `*.gwt.xml` file:

```
jar {
    // pack client Java sources
    with copySpec {
        from sourceSets.main.allJava
        include "com/example/widgetsaddon/client/**"
    }
    // register exported widgetset
    manifest {
        attributes(['Vaadin-Widgetsets': 'com.example.widgetsaddon.WidgetsAddon'])
    }
}
```

## Adding an add-on to a project

* Build and install add-on to a maven local:

```
./gradlew clean assemble install
```

* Include add-on dependency to a project:

```
implementation 'com.example:sample-widgets-addon:1.0-SNAPSHOT'
widgets 'com.example:sample-widgets-addon:1.0-SNAPSHOT'
```
