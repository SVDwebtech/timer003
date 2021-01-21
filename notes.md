# Notes

## master branch 

## developApp branch
    * 2021/01/21 4:48pm
        - created boilerplate for index.html
        - created notes.md file for general notes and planning
        - wrote up architecture of app
        - updated README.md file with what app does
    

##   THINGS OUR PROGRAM DOES
    *   Displays a timer --- (T)
    *   Shows an animated border around the timer --- (B)


##   POSSIBLE IMPLEMENTATION ---- EVENTED STYLE APPROACH

    *   Event listener to watch for a click on "start" button --------------- (T)

        **  Emit an event stating that the timer has started ---------------- (B)  Watch for this event.  When it occurs, draw a full border around the timer.

        **  Start counting down the timer ----------------------------------- (T)

        **  Emit an event that the timer has 'ticked' ----------------------- (B)  Watch for this event.  Each time the timer counts down, update the border.

        **  Each time the timer counts down, update the text ---------------- (T)

        **  If we counted down and timer reaches 0 -------------------------- (T)

            *** Emit an event that the timer is done ------------------------ (B)  Watch for this event.  When it occurs, reset the border.

            *** Reset internal timer to get ready for another run ----------- (T)

##   class Timer 
    *   constructor(durationInput, startButton, pauseButton)
    *   start() ----------------------  click start btn
    *   pause() ----------------------  click pause btn
    *   onDurationChange() -----------  change number display
    *   tick() -----------------------  every single second run code to update number display 

    **  class Timer
        *** Knows only about the start btn, pause btn and number display.
        *** Knows nothing about the border display
    
    ** Timer class will listen for a durationInput, click of startButton or click of pauseButton
    ** When an event happens our Timer class will run the relevant method defined inside of it  