- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - 
To install SWNGMACH, make a directory on root called
SWNGMACH.  Unzip attached file into that directory
and READ ALL  .txt  information.

There is a file called BobH2Fil.txt that is the source
for the BobH2Fil.ela -- this will transcribe data from
TS or SCrealtime to a format that SwingMachine can use.

**********************************************************

All material in this and associated files are
copyrighted and cannot be reproduced without permission.

Clyde Lee   Chairman/CEO        email:   <clydelee@hic.net>
SYTECH Corporation              Work:    (713) 783-9540
7910 Westglen, Suite 105        Fax:     (713) 783-1092
Houston,  TX  77063           
- - - - - - - - - - - - - - - - - - - - - - - - - - - - - -

The SwingMachine program should be installed in a directory
titled   SWNGMACH  .  If not you may have some problems !

Unzip the SWNGMACH.ZIP file into this directory and you will
find the following:

    README.TXT   -- full length of this file

    SWNGMAIN.EXE -- the DOS execution module.
    SWNGSETU.DAT -- information necessary to make the program
                    function.  As detailed below you should
                    setup the disk and directories which
                    contain data.
    SWNGVARS.DAT -- user variables required by program.  The
                    default values can be changed but must be
                    done with extreme care.
    SWNGHELP.DAT -- contains (not necessarily current) HELP
                    information about various program user
                    variables.
                    
    PATTERNS.TXT -- an explanation of the concepts involved in
                    the program.
                    
                    

The following entries in the  SWNGSETU.DAT  file should be updated
to fit your system.

Remember, this system can only read  ASC(II), CSI, COMPUTRAC, and
TC2000 files.

ASCII DATA CAN BE COMMA OR BLANK OR TAB SEPERATED FIELDS
DATE FORMAT CAN BE   YYMMDD   OR    MM/DD/YY   EITHER WAY.

If ASCII data contains TIME in the second field then the
FIRST LINE IN FILE MUST CONTAIN THE WORD  TIME  SOMEWHERE
ON THAT FIRST LINE.

Acceptable ASCII formats:

1.      date,time,open,high,low,close,vol,oi
        date  time  open  high  low  close  vol  oi

for the above format do not forget the first line in
the file should contain the word  time   somewhere in
that line.


2.      date,open,high,low,close,vol,oi
        date  open  high  low  close  vol  oi



To make it easy to find your data you should update the path for
each of the types of data which you will read.

Always include the drive in a fashion similar to the following.

Set DATATYPE to the type of data you wish to have as the 'default'
data type.  The program will allow you to change as required.



DATATYPE = COM 

ASC = C:\SYTECH\GET 
CSI = C:\CSI\DATA\FUTURES 
COM = C:\MS\DATA\CLCDATA 
COT = C:\MS\DATA\CLCDATA 
TC2 = C:\TC2000

        Note:   For  TC2  data the drive and directory specified
                in the  SWNGSETU.DAT  file must point to the
                TC2000 ***PROGRAM*** DIRECTORY (not the data
                directory as is the other cases).  The program
                expects to read the location of your tc2000 data
                file from a file that is stored with the program.
                AGAIN -- POINT TO THE TC2000 PROGRAM FILE DIRECTORY.
  

Once you have updated the setup file -- don't mess with any other
items in the file ! ! ! -- start the program by entering DOS and
changing to the SWNGMACH directory and typing  SWNGMAIN.  

(I'm sure you will want to make a "shortcut" to do this for you
from the desktop.  There is a file titled  SWNG  in the .zip which
is a properly setup shortcut which you can copy to your desktop).

Once the program is started you can generally just press the <enter>
key and the program will do what you want or follow the instructions
on the screen.

Once you have a data set loaded there are a number of keys that can
be pressed to achieve various taskds:

Key     Function

A       Allows you to set number of bars to use in evaluating each
        turning point (1,2,3,5,7,9).  You can actually squeeze the
        data into 2 bar, 3 bar, ..... data set if you desire.  After
        pressing   A   , instead of entering a single digit decimal
        number you may enter a minus (-) sign and system will ask
        for number of bars to use which may be any number desired.

F       Go to Fourier menue and do it's thing.

Q       Quit program

R       Read new data file.

S       Save data on swings in file.

****************************************************************

+/=     Adds an UP bar at end of data displayed.  (Model turn)

-       Adds a DOWN bar at end of data displayed. (Model turn)

X       Removes the last bar on the chart.

****************************************************************

F1      Brings up a menu of user variable parameters.  Generally
        you will not want to change these but don't be scared to
        try since the next time you start program the original
        parameters are restored.

F2      Reset beginning and ending days to chart.

F5      Replot data without clearing screen.

F6      Clear screen & replot data.

<-      Left Arrow -- move cursor (^) left on chart.
->      Right Arrow - move cursor (^) right on chart.

F7      Set beginning date for F2 at date pointed to by cursor.

F8      Set ending date for F2 at date pointed to by cursor.

AltF8   Set price scale limits.

F9      Move data displayed to an earlier period of time.  The
        amount of movement is about 1/3 of that on the screen
        at the time F9 is pressed.   Alt F9  will cause data to
        move in the opposite direction.
        
F10     Move data displayed to an earlier period of time.  The
        amount of movement is a FULL screen.  Alt F10 move in the
        other direction.
        
F11     Move data displayed to the next bar (or some number of
        bars that you have setup by first pressing  A  and then
        S  and then entering the number of bars you want F11 to
        step).  To use you must first do AltF9  or  AltF10  one
        or more times to "backup" time to some point to begin.

F1 MENU - - - - - - - - - - - - - - - - - - - - - - - - - -


The following is taken from the SWNGVARS.DAT file.

DISPSCL: DISPLAY PRICE SCALE DEFINED BY USER (N=auto scale)
DISPPTN: DISPLAY Patterns    N=No H=hi/lo T=true B=Both hlt
DISPDIV: DISPLAY N-1,2,.. PROJECTION SUMS .x =mode 1,2..,8 
DISPONL: DISPLAY C=CANDLE  B=BAR  L=LINE @ CLOSE  O=OPN/CLO
DISPOSC: DISPLAY +=OSC/BBW -=HHLL/ANDR+ XXX.YYY (X=CH Y=OS)
DISPMAX: +/-XX.YYY XX=BARS TO DISPLAY   YYY*10,000=MAX LOAD
EXTENDA: #BARS TO EXTEND ZONE AFTER LAST BAR (-=NO FIB LIN)
ASCIEXT: EXTENSION TO USE WITH ASCII FILES Csv/Prn/Txt/Asc 



There is a "help" file that will appear if you highlight one 
of these variables and again press F1.


I strongly urge you to use the AltF9 key to step back in time
and see through your data and observe how the projections of
the program have worked in the past.

If you step back with AltF9 and then use F11 to step forward
bar by bar you will educate yourself to realtime operation.

In the near past you will typically find that the lower, middle,
or upper 1/3 of patterns tend to fit best and this will last
over a considerable period of time.  But, when things change
they generally REALLY change.

One of the primary uses of the Fourier capability is to 
establish the primary cyclic elements of a data set if one
exists.  To do this be select to print out the data to
the screen or to a file when asked for your choice.

Generally you can hit the <esc>  (escape) key at any time
and stop any goings on that the program is into.  Sometimes
I start to plot the whole file and suddenly decide that I
don't want to do that -- <esc> and it quits.  Try it you
will like it.



When a display of a file is on the screen you can press the 
F1 key to access a series of variables which effect the
display/operation of the system.  If you mode the cursor to
highlight one of these varaiables and press F1 then the
selection from the following HELP file will appear.




DISPSCL: DISPLAY PRICE SCALE DEFINED BY USER   (N=auto scale)

You may request system to allow user to set the high and low prices
for the top and bottom of each bar chart generated.
If the  DISPSCL  variable is set to Y, then when a chart is about
to be generated the system will inform you of the current values
and request that you use the ones specified or enter new values.

The following messages/inquiries are used:

   NEW    HIGH/LOW  VALUES ARE:  xxxxx / yyyyy
   OLD    HIGH/LOW  VALUES ARE:  aaaaa / bbbbb

   ENTER:  99999 to Use  -OLD-  HIGH/LOW  Values

           TOPVAL: VALUE TO USE FOR TOP    OF BAR GRAPH

           BOTVAL: VALUE TO USE FOR BOTTOM OF BAR GRAPH
ENDDEF
DISPPTN: DISPLAY Ptrn|His N/H/T/B=No/Hi-Lo/True/Both|N/S/P/B

The system automatically determines inflection (swing) points,
defines pattern numbers based on the current and prior three
inflection point price levels, posts these pattern numbers on
the chart, and draws straight lines between determined in-
flection points.
  N=No Display of Patterns      H=Display P# at High/Low
  B=Display P# at H/L & True    T=Display P# at True BAR

Pattern numbers can be posted at the High(low) point of the
swing, the True point of determination of an inflection, or
at both the High & True points, or no pattern numbers or lines
will be placed on chart.
ENDDEF
DISPDIV: DISPLAY N-1,2,.. PROJECTION SUMS .x =mode 0,1,2,3

The number of projections to display can vary from 1 to n,
where n is the total number of swings that were found.
This value is displayed on the screen as  SW=x/YY where
YY is the total number of swings.  If this value is set
to 1 then only one projection is displayed and it is the
sum of all observed projections.  A value of 2 will display
a total of 2 projections . . . . .

The decimal portion of this value (1 to 7) established
the manner in which data is organized before any summing/
averaging takes place.  A value of  0 = order by number
of days in first leg.  1 = order by slope of first leg.
2 = order by number of days in first + second leg.
3 = order by value of projection at end of 3rd leg.
Using the above values ONLY data with swings ending
on current or future bars is displayed.

To display ALL patterns for the selected number of
patterns to display, the decimal portion of this parameter
should be set to 4 through 7  (corresponding to 0 thru 3).
ENDDEF
DISPONL: DISPLAY C=CANDLE  B=BAR  L=LINE @ CLOSE  O=OPN/CLO

The user can choose to display price data in one of several
generally known display types:

If Set To:         Display Type
    C              Candlestick
    B              Open,High,Low,Close Bar
    L              Line from Close to Close
    O              Line from Open to Close to Open . . 

ENDDEF
DISPOSC: DISPLAY OSCILLATOR/CHAN WIDTH  XXX.YYY (X=CH Y=OS)

Two oscillators exist which may be displayed as desired
this is done so by assigning some value such as   15.035
to this variable (or the negative of this value).

The decimal value multiplied by 1000 is the numbers in the
length for the oscillator function (equivalent to Bill
Williams "Awful Oscillator".

The Value before the decimal is the length "channel 
width" function (width of Bollinger Band Channel).

ENDDEF
DISPMAX: +/-XX.YYY XX=BARS TO DISPLAY   YYY*10,000=MAX LOAD

The max bars to load (.yyy * 10,000 is really only applicable
to Computrac and Sytech type files and simply limits the     
number of bars that will be loaded from a file.  Generally
not used.

The XX portion defining the number of bars to currently
displayed should be set to your choice for your analysis. 
This is the value at the time you read a file and may be
changed later simply by defining new beginning and ending
dates to display using the  F2  key operation.

ENDDEF
EXTENDA: #BARS TO EXTEND ZONE AFTER LAST BAR (-=NO FIB LIN)

Blank space on the screen AFTER the last data point can be
established by setting this variable to whatever value is
desired.  Typically a value of 30 provides sufficient 
area for projections.

The system generates a histogram of the first two legs
of all swings that were found.  You may inhibit the display
of this histogram by making the value of this variable
negative.

ENDDEF
ASCIEXT: EXTENSION TO USE WITH ASCII FILES Csv/Prn/Txt/Asc 

This is provided for later use.  Set it to whatever is 
your most used extension for ASCII files.
ENDDEF


Some information on using Fourier:



If you want to do a Fourier analysis and then do an edited
projection removing some components or simply make a 
projection based on some cyclic values.  Read on!!!



There are two methods:

Method 1 -- make a file:

Press  F   for Fourier
press  C   for type of analysis
press  F   to output to a file

           Follow instructions and specify an output file.

Enter  1000  (on whatever length data you want to analyze)

That created the file.  When you were assigning the file
I hope you made a note of file name and location 'cause you
will need to access the file to edit the spectral components.

You may remove ANY line which shows period/ampl/phase....
for a component and later when you input the file those
will not appear.

After editing your file again:

Press  F   for Fourier
press  1   to show you are now modeling
press  F   to indicate system should read file.

           Follow instructions and specify an input file.

System will read file of spectral components and create a
prediction/filtered curve based on your selections!!!!!


Method 2 -- interatively model and set components to ZERO:

Press  F   for Fourier
press  C   for type of analysis
press  <enter> to accept default (no) output or
       S   if you want to see output and make notes.

Enter  1000  (on whatever length data you want to analyze)

At this point I normally press  F5  or   F6   to clear the
screen.

Now:

Press  F   for Fourier
press  1   for modeling
press  <enter>  to accept default


Now, on the last line of the screen will appear something 
similar to the following:


WAVE # x OF yy  ENTER: Q,0,<RET>, PP/DD.DD/AAAA  pp/dd.d/aaa

where:  x  = number of current wave data being displayed
       yy  = total number of wave data sets recorded

       pp  = period of current wave
    dd.dd  = delay (phase) in bars to first maxima for this
             wave
      aaa  = amplitude of this wave

and you should simply press  <enter> / <return>  if you want
to keep that wave in the simulation/model.  If you don't 
want to use a particular wave then enter  0  (zero) and
press return and that wave is gone,gone!!

If you reach a point where you don't want to include any of
the shorter length waves then just enter   Q   (for quit)
and the simulation will run an show you the resulting curve.

In case you have not figured it out already, you can use
this feature and enter something like:

   200/100.0/300

instead of accepting the first value and then enter  Q
the next step and suddenly you have a 200 period sine
(or actually cosine) wave with a peak at the 100th bar
in your data set -- or at least that is how it is supposed
to work.





-- 
- - - - - - - - - - - - - - - - - - - - - - - - - - - - - -
Clyde Lee   Chairman/CEO       (Home of SwingMachine)
SYTECH Corporation             email:   <clydelee@hic.net> 
7910 Westglen, Suite 105       Work:    (713) 783-9540
Houston,  TX  77063            Fax:     (713) 783-1092    
- - - - - - - - - - - - - - - - - - - - - - - - - - - - - -
