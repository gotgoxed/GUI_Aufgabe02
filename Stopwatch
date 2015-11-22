	import javafx.event.ActionEvent;
	import javafx.event.Event;
	import javafx.event.EventHandler;
	import javafx.geometry.Pos;
	import javafx.scene.control.Button;
	import javafx.scene.control.Label;
	import javafx.scene.layout.BorderPane;
	import javafx.scene.layout.HBox;
	import javafx.scene.layout.VBox;
	
public class Stopwatch extends BorderPane implements EventHandler<ActionEvent>{
 
		final static int interval = 100;
		private static Timer timer = new Timer(interval);
		private static Label counterLabel = new Label("Sekunden: " + timer.getTimeString());		  
	
//CONSTRUCTOR		
	public Stopwatch(){
				
				timer.attach(this);
	
				final Button start = new Button("Start");
				final Button stop = new Button("Stop");
				final Button reset = new Button("Reset");
				final HBox startStopReset = new HBox (10);
				startStopReset.getChildren().addAll (start, stop, reset);
				startStopReset.setAlignment(Pos.CENTER);
				
				final HBox bottom = new HBox ();
				final Label bottomLabel = new Label("Stopped");
				bottom.getChildren().addAll(bottomLabel);
				
				final VBox vBoxBottom = new VBox (5);
				vBoxBottom.getChildren().addAll(startStopReset, bottom);
				
				//EVENTHANDLER 
				start.addEventHandler(ActionEvent.ACTION, new EventHandler<Event>() {

					@Override
					public void handle(Event event) {
						// TODO Auto-generated method stub
						start.setDisable(true);
						stop.setDisable(false);
						bottomLabel.setText("Running");
						timer.start();
					}
				});
				
				stop.addEventHandler(ActionEvent.ACTION, new EventHandler<Event>(){
					
					@Override
					public void handle(Event event) {
						// TODO Auto-generated method stub
						start.setDisable(false);
						stop.setDisable(true);
						bottomLabel.setText("Stopped");
						timer.stop();
					}
				});
											
				reset.addEventHandler(ActionEvent.ACTION, new EventHandler<Event>(){
					
					@Override
					public void handle(Event event) {
						// TODO Auto-generated method stub
						timer.stop();
						timer.reset();
						bottomLabel.setText("Stopped");
					}
				});
    
			this.setPrefHeight(300);
			this.setPrefWidth(300);		
			this. setCenter (counterLabel);
			this. setBottom (vBoxBottom);		
			}
	
/**
 * Update Method
 */
	public void update() {
		// TODO Auto-generated method stub
		counterLabel.setText("Sekunden: " + timer.getTimeString());
	}
	
@Override
	public void handle(ActionEvent event) {
	// TODO Auto-generated method stub
	}
}
