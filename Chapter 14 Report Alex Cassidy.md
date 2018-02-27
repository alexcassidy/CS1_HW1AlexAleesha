# Chapter 14 Report-Alex Cassidy
## 14.11 
### Description: 
(Paint a smiley face) Write a program that paints a smiley face
### Code:
``` Java
/*
 * To change this license header, choose License Headers in Project Properties.
 * To change this template file, choose Tools | Templates
 * and open the template in the editor.
 */
package programmingexercise14.pkg11.alexcassidy;

import javafx.application.Application;
import javafx.event.ActionEvent;
import javafx.event.EventHandler;
import javafx.scene.Scene;
import javafx.scene.control.Button;
import javafx.scene.layout.StackPane;
import javafx.scene.paint.Color;
import javafx.scene.shape.Arc;
import javafx.scene.shape.ArcType;
import javafx.scene.shape.Circle;
import javafx.scene.shape.Ellipse;
import javafx.scene.shape.Line;
import javafx.scene.shape.Polyline;
import javafx.stage.Stage;

/**
 *
 * @author alexc
 */
public class ProgrammingExercise1411AlexCassidy extends Application {
    
    @Override
    public void start(Stage primaryStage) {
        
        Circle head = new Circle();
        head.setRadius(120);
        head.setFill(Color.WHITE);
        head.setStroke(Color.BLACK);
        
        Ellipse eyeball = new Ellipse(); 
        eyeball.setRadiusX(30);
        eyeball.setRadiusY(20);
        eyeball.setTranslateX(-50);
        eyeball.setTranslateY(-30);
        eyeball.setFill(Color.WHITE);
        eyeball.setStroke(Color.BLACK);
        
        Ellipse eyeball2 = new Ellipse();
        eyeball2.setRadiusX(30);
        eyeball2.setRadiusY(20);
        eyeball2.setTranslateX(50);
        eyeball2.setTranslateY(-30);
        eyeball2.setFill(Color.WHITE);
        eyeball2.setStroke(Color.BLACK);
        
        Circle insideeye = new Circle();
        insideeye.setRadius(14);
        insideeye.setTranslateX(-50);
        insideeye.setTranslateY(-30);
        insideeye.setFill(Color.BLUEVIOLET);
        insideeye.setStroke(Color.TURQUOISE);
        
        Circle insideeye2 = new Circle();
        insideeye2.setRadius(14);
        insideeye2.setTranslateX(50);
        insideeye2.setTranslateY(-30);
        insideeye2.setFill(Color.BLUEVIOLET);
        insideeye2.setStroke(Color.TURQUOISE);
        
        
        Polyline nose = new Polyline();
        nose.getPoints().addAll(new Double[]{
        0.0, 0.0,
        20.0, 10.0,
        10.0, 20.0 });
        
        Arc mouth = new Arc(
                head.getCenterX(), // center x
                head.getCenterY() + (head.getRadius() / 3), // center y
                head.getRadius() / 2, // x radius
                head.getRadius() / 2 / 2, // y radius
                180, 180); // start point and length
         mouth.setTranslateY(30);
         mouth.setFill(Color.TRANSPARENT);
        mouth.setStroke(Color.BLACK);
        
        
        StackPane root = new StackPane();
        root.getChildren().addAll(head, eyeball, eyeball2, insideeye, insideeye2, nose, mouth);
        
        Scene scene = new Scene(root, 500, 500);
        
        primaryStage.setTitle("Hello World!");
        primaryStage.setScene(scene);
        primaryStage.show();
    }
    
    public static void main(String[] args) {
        launch(args);
    }
    
}

```
### Comments:
 I enjoyed messing with this program. It was cool to experiment with the different facial features.
### 14.15
### Description:
(Display a STOP sign) Write a program that displays a STOP sign
### Code:
``` Java
/*
 * To change this license header, choose License Headers in Project Properties.
 * To change this template file, choose Tools | Templates
 * and open the template in the editor.
 */
package javafxapplication2;


import javafx.application.Application;
import javafx.event.ActionEvent;
import javafx.event.EventHandler;
import javafx.scene.Scene;
import javafx.scene.control.Label;
import javafx.scene.layout.Pane;
import javafx.scene.layout.StackPane;
import javafx.scene.paint.Color;
import javafx.scene.shape.Polygon;
import javafx.stage.Stage;
import javafx.scene.text.Font;
import static javafx.scene.text.Font.font;
import javafx.scene.text.FontWeight;

/**
 *
 * @author alexc
 */
public class ProgrammingExercise1415AlexCassidy extends Application {
    
    @Override
    public void start(Stage primaryStage) {
        Pane pane = new Pane();
        
        Polygon octagon = new Polygon();
        octagon.getPoints().addAll(new Double[]{
        100.0, 400.0,
        200.0, 400.0,
        300.0, 300.0, 
        300.0, 200.0,
        200.0, 100.0,
        100.0, 100.0,
        0.0, 200.0,
        0.0, 300.0,
        });
        octagon.setTranslateX(-5);
        octagon.setTranslateY(-20);
        octagon.setFill(Color.RED);
        octagon.setStroke(Color.WHITE);
        octagon.setStrokeWidth(7);
        octagon.setRotate(45.0);
        
        Font test = new Font("Arial", 12);
        Label stop = new Label("STOP");
        stop.setScaleX(7);
        stop.setScaleY(13);
        stop.setTextFill(Color.WHITE);
     
       pane.getChildren().addAll(octagon); 
       stop.setFont(test.font("Arial", FontWeight.BOLD, 12));
       stop.setTranslateX(0);
       stop.setTranslateY(-25);
       
       
        
        
        StackPane root = new StackPane();
        root.getChildren().addAll(octagon, stop);
        
        Scene scene = new Scene(root, 500, 500);
        
        primaryStage.setTitle("PolygonOctagon");
        primaryStage.setScene(scene);
        primaryStage.show();
    }

    /**
     * @param args the command line arguments
     */
    public static void main(String[] args) {
        launch(args);
    }
    
}
```
### Comments:
This one was irritating to deal with, but I finally got it right. 
### 14.6
### Description:
(Game: display a checkerboard) Write a program that displays a checkerboard in which each white and black cell is a Rectangle with a fill color black or white
### Code:
``` Java
package programmingexercise14.pkg6alexcassidy.java;

import javafx.application.Application;
import javafx.scene.Scene;
import javafx.scene.layout.StackPane;
import javafx.scene.paint.Color;
import javafx.scene.shape.Rectangle;
import javafx.stage.Stage;

public class ProgrammingExercise146AlexCassidyJava extends Application {
    
    @Override
    public void start(Stage primaryStage) {
        StackPane root = new StackPane();
        
        int y = -175;
        for(int i = 0; i < 8; i++){
            int x = -175;
            for(int k = 0; k < 8; k++){
                Rectangle piece = new Rectangle(50, 50);
                
                if(i % 2 == 0 || i == 0){
                    if(k % 2 == 0 || k == 0)
                        piece.setFill(Color.WHITE);
                    else
                        piece.setFill(Color.BLACK);
                }
                else{
                    if(k % 2 == 0 || k == 0)
                        piece.setFill(Color.BLACK);
                    else
                        piece.setFill(Color.WHITE); 
                }
                
                piece.setTranslateX(x);
                piece.setTranslateY(y);
                root.getChildren().add(piece);
                x+=50;
            }
            y+=50;
        }
                
        Scene scene = new Scene(root, 400, 400);
        
        primaryStage.setTitle("Programming Exercise 14.6 - Alex Cassidy");
        primaryStage.setScene(scene);
        primaryStage.show();
    }
    public static void main(String[] args) {
        launch(args);
    }
}

```
### Comments: 
This one was interesting to make. The array worked well for the checkerboard.