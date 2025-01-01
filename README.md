java c
EEET 3050 -   Renewable   Energy   Systems
Practical 2 -   DFIG   Feeding   Power to a Grid through a Transformer   and   a   Line
Aim:                                                            The   aim   of   this   practical   is   to   evaluate   the   characteristics   of   a   DFIG   based   wind   power
plant connected to the grid through a transformer and a distribution line using   standard   MATLAB/SIMULINK   blocks given   in Simscape.
Objectives:                        Familiarise   with   modification/extension   of   MATLAB   Simulink   models
Develop the   model of a   realistic wind   power   plant feeding   power to   a   grid   Investigate the system   responses to change   in wind   speed
Background:                  Background   and theory   related to   this   practical   have   been   covered   in   Practical   -   1.   In
this   practical,you   will   be   modifying   the   Simulink   model   developed   in   Practical   -   1   to   represent a   more   realistic   model of a wind generating   system.
Description:Fig.1   illustrates   the   single   line   diagram   of   the   wind   power   plant   and   the   utility   grid   considered for this   practical.   Fig. 2 illustrates the corresponding Simulink   model   block   diagram. The   procedure for   developing the   block   diagram   (or   modifying the   diagram   of   practical   1)   is   given   in   the   following.

Instructions:
1.          Open   MATLAB   from   ‘Start’   menu.
2.          Select   ‘Open’   →      Open   the   Simulink   model   saved   from   Practical   01.
3.          Select   ‘File’   →   Save   as   →   Save   the   Simulink   file   with   a   different   name.
4.          Click   ‘Simulink   Library’   icon    in the toolbar to get the window   of the   Simulink   library.
5.          Search   for   the   following   blocks   and   drag      drop   them   into   your   Simulink   file.
•          Three-phase   PI   section   line,   Three-phase   transformer   (two   winding),   Three-phase   V-I   measurement, scope,   Abs, Step, Sum
6.          Delete   only   the      lines   connecting   the   ‘Three-Phase   Source’   and   the   ‘Three-Phase   Series   RLC load’   . Insert   the new elements   and   connect   all   as in Fig.2. Right click on   Three-phase   V-I   measurement   block and select   ‘flip’ to get   required configuration.
7.          Choose   the   solver:   Click   on   the   ‘Variable   step   auto’   (bottom   right   corner)    →   Settings   →   Solver   →   ode   45   (Dormand-Prince).
8.          Double click on the   ‘Three-phase   Source’   and   enter the   following   parameters:
•          Phase-to-phase   rms   voltage   -11   kV,   Frequency   -   60Hz,   Phase   angle   -   0,   3-phase   short circuit   level   -   100   MVA, X/R   ratio   – 7,   Base   voltage   –   11   kV.
9.          Double   click   on   the   ‘Three-phase   PI   section   line’   and   enter   the   following   parameters:
•            Line   length      -   10   km
   
Resistance( Ohm/km)
Inductance   (mH/km)
Capacitance   (nF/km)
Positive   seq.
0.01273
0.9337
12.74
Zero   seq.
0.3864
4.1264
7.751
10.    Double   click   on   the   ‘ Transformer’ and   enter   the   following   parameters:
•          In   the   ‘Configuration’ tab   →   winding   1   ‘Yg’   and   winding   2   ‘Delta   (D1)   ‘
•          In   the   ‘Parameters’   tab      →   Nominal      power   -   2.0   MVA,   frequency   -   60   Hz,   Winding   1   parameters      -         [11e3,      0.002,      0.08],      Winding      2      parameters      -         [575,      0.002,      0.08],   Magnetizing   resistance   -   500,   Magnetizing   inductance   - 500
11.    Double   click   on   the   ‘Three-phase   load’   block   and   enter   the   following   parameters   :
•          In   the   ‘Parameters’   tab   →   Nominal   phase-to-phase   voltage   -   575   V,   configuration   -   Y   (grounded),   frequency    -    60    Hz,    active      power      -          100    kW,    Inductive      and      capacitive reactive   power   -   0
•            In   the   ‘Load   flow’ tab   →   load   type   ‘Constant   Z’
12.    Double   click   on   the   ‘Wind   Turbine’   model   and   enter   the   following   parameters:
•          Select      the      ‘Generator’    option      →      Nominal      power,    line-to-line      voltage,    frequency      -   [1.5e6/0.9    575    60],   S代 写EEET 3050 - Renewable Energy Systems Practical 2 – DFIG Feeding Power to a Grid through a Transformer and a LineMatlab
代做程序编程语言tator    -    [    0.00706    0.171],    rotor      -    [    0.005    0.156],    Magnetizing inductance   -   2.9,   Inertia   constant,   friction   factor,   and   pairs   of   poles   -   [5.04   0.01   3],   Initial   conditions   -   [0.2 0   0   0   0   0]
•          Select   the   ‘Turbine’ option   →   Nominal   wind   turbine   mechanical   output   power   - 1.5e6,   Tracking   characteristic   speeds- [0.7 0.71 1.2 1.21],   Power   at   point   C   - 0.73,Wind   speed at   point   C   -   12,   Pitch   angle   controller   gain   - 500,   Maximum   pitch   angle   -   45,   Maximum rate   of   change   of   pitch   angle   -2
•          Click    on      the       ‘Display    wind      turbine      characteristics’      and      obtain      the      wind      turbine   characteristics.
•            Save the figure.
13.    Remove   the   ‘Step’   block   connected   to   the   ‘Wind’   input   of   the   DFIG   model.   Connect   the   ‘Sum’   block   and   other   ‘Step’   blocks   as   in   Fig.   2.
14.    Double   click   on   the   ‘Sum’   block   and   in   the   ‘   List   of   signs’   enter      |++++
15.    In   order   to   obtain   the   step   variation   of   wind   speed   connect four   different   step   blocks   to   the   summation   block as   illustrated   in   Fig.   2   and enter the following   parameters:
Block
Step time
Initial value
Final value
Step   1
100
8
10
Step   2
200
0
2
Step   3
300
0
2
Step   4
400
0
2
   
16.    Right   click   the   ‘Bus   creator’   →   Block   parameter   →   Set   no. of   inputs   to   ‘7’   .
17.    Right   click   on   the   ‘Bus   selector’   →   Block   parameter   →   Select   P   (pu),   Q   (pu),   pitch   angle, Tm,   wr→   Click   ‘OK’   . Connect the signals from the ‘   Bus selector’   to   the   ‘Bus   creator’
18.    Double   click   on the scope   and   click the   ‘Parameter’   icon      on the   toolbar   of the   scope   →   Select   the   ‘Logging’   tab   →   untick   the   box   for   ‘Limit   data   points   to   last’   →Click   ‘OK’   .   Do   this   change on   all the   scopes.
19.   Set   the   ‘Simulation   Stop   Time’   in   the   tool   bar   to   ‘500‘ as   follows:
                                                                 
20.    Run   the   simulation   by   clicking   on   the   ‘Run’   icon   in   the   tool   bar.
21.    Double   click   on   all   the   scopes   and   observe   the   parameter   variations. Click   the   ‘Auto   scale’ icon    on the scope toolbar to view the full   simulation.
22.   To open the Workspace   browser   if it   is   not currently   visible,   do   either   of   the   following:
•          Type   workspace at the   Command   Window   prompt.
•          The   variables   you   selected   from   the   DFIG   in   the   previous   section   (P   (pu),   Q (pu),   pitch angle, Tm, wr) are   saved   in   the   ‘simout’   matrix.
23.   Type      the   following   command   in   the   command   window   and   press   ‘Enter’:
•          plot(out.simout(   :,1),out.simout(:,   2))
The   x-axis   of   the   graph   denotes   the   time   variable   while   they-axis   represents   the   second   output   coming from the wind generator   model.In order to add   labels to the x-axis andy-axis   and   a title,   select   ‘Insert’   in   the   graph   and   select   the appropriate   labels and title. Then type the   label   names and the title. Alternatively, double   click   on   ‘arrow’   of figure toolbar   and   edit the   axis   by   double   clicking   on   any   of the   axis.   Save   the    plot    or    use      ‘Copy      Figure’      option      from      Edit      menu      and      paste    the      figure      in      the      word   document.
24.   Similarly,   plot the following   outputs from the wind   generator   in   separate   figures   and   save   all   the figure files. Submit the graphs   in   a   report.
•          Time   vs   Active    power,   Time   vs   Reactive   power,   Time   vs   Wind   speed,   Time   vs   Pitch   angle, Time vs   Rotor speed, Time vs   Mechanical Torque
Report:The   report should include a   brief introduction, all   plots   of   step   24   with   critical   analysis   and   discussion,   and   a   conclusion.   The   report   should   be   approximately   600   words   long,   excluding   figures,   diagrams,   and tables.
   
   



         
加QQ：99515681  WX：codinghelp  Email: 99515681@qq.com
