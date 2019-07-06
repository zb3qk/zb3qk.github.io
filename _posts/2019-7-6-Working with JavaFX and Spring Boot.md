---
layout: post
topics: ['GUI']
tags: ['JavaFX', 'Spring Boot']
---
# A quick overview

JavaFX is a graphic library baked directly into Java 8, but since Java 9 it has been removed from Java. To date, the easiest way to 
make JavaFX applications has been to develop with JDK 8. 

How does it work? Here is an example.
```Java
@SpringBootApplication
public class MyApp extends Application {
    private ConfigurableApplicationContext springContext;
    private Parent rootNode;
    private FXMLLoader fxmlLoader;
    static Stage stg;

    public static void main(String[] args) {
        launch(args);
    }

    @Override
    public void init() throws Exception {
        springContext = SpringApplication.run(MyApp.class);
        fxmlLoader = new FXMLLoader();
        fxmlLoader.setControllerFactory(springContext::getBean);
    }

    @Override
    public void start(Stage primaryStage) throws Exception {
        fxmlLoader.setLocation(getClass().getResource("/fxml/sample.fxml"));
        rootNode = fxmlLoader.load();
        this.stg = primaryStage;
        primaryStage.setTitle("Hello World");
        Scene scene = new Scene(rootNode, 800, 600);
        primaryStage.setScene(scene);
        primaryStage.show();
    }

    @Override
    public void stop() {
        springContext.stop();
    }

}
```

Using Spring Boot, the production pipeline is greatly simplified so as to start the GUI application on runtime.

Akin to Web Design, an easy way to design JavaFX Scenes is via <i>.fxml</i> files. FXML is an extension of XML (in the same way of HTML)
and takes advantage of its nested structure to organize GUI elements.

```xml
<?import javafx.scene.control.Button?>
<?import javafx.scene.control.Label?>
<?import javafx.scene.layout.GridPane?>
<?import javafx.scene.control.TableView?>
<GridPane fx:controller="ReportApplication.SampleController" xmlns:fx="http://javafx.com/fxml" alignment="CENTER" hgap="10" vgap="10">
            <Button text="Hallo" onAction="#sayHelloWorld"/>
            <Label GridPane.rowIndex="1" fx:id="helloWorld"/>
            <TableView fx:id="tableView" GridPane.columnIndex="0"
                       GridPane.rowIndex="1"/>
            <Button fx:id="button1" text="Click me!" onAction="#pressButton"/>
</GridPane>

```

