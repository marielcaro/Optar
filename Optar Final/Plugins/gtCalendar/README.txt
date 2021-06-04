=====
ABOUT
=====
gtCalendar is a custom canvas based calendar control for the Xojo (previously REALbasic) language. It works on 
all platforms  (Windows, Linux and Mac) and can be easily localized to any language.

The project website can be found here:

     http://www.miscjunk.org/mj/pg_rbcal.html

David Gadberry (info@miscjunk.org)


=====
USAGE
=====
To use the calendar control simply drag the gtCalendar control object and supporting images directory
into  your project.  In the window editor drag the gtCalendar control onto your window.  The control was
designed at a size of 224 (width) and 180 (height).  It will scale to fit any canvas size although the
font size will not adjust - about 80% (180 x 144) is the smallest practical size.

The arrows at the left and right top corners of the calendar, when clicked on with the mouse, moves to the 
previous and next months.  Holding the SHIFT key while clicking on the arrows moves to the previous and next
year while the month remains constant.

The following event and methods are available:

Event -
   DateSelected(d as Date) - Fired when a date has been selected.

Methods - 
   SelectToday() - Selects and displays the current date.

   SelectDate(d as Date) - Selects and displays the date passed to the method.

   ShowToday() - Displays the current date without changing the selected date.

   ShowDate(d as Date) - Displays the date passed to the method without changing the selected date.

   ShowSelected() - Displays the selected date.

Flags -
   gHighlightToday:  default TRUE - specifies whether the current day is highlighted in the calendar


============
LOCALIZATION
============
The language used by the control defaults to English but can be changed to other languages by assigning
values to the global arrays gaMonthNames and gaDayNamesAbr (in the control's Open event) as shown in 
the following examples:

'French
me.gaMonthNames = Array("", "janvier", "février", "mars", "avril", "mai", "juin", "juillet", "août", "septembre", "octobre", "novembre", "décembre")
me.gaDayNamesAbr = Array("", "dim", "lun", "mar", "mer", "jeu", "ven", "sam")

'German
me.gaMonthNames = Array("", "Januar", "Februar", "März", "April", "Mai", "Juni", "Juli", "August", "September", "Oktober", "November", "Dezember")
me.gaDayNamesAbr = Array("", "Son", "Mon", "Die", "Mit", "Don", "Fre", "Sam")

'Spanish
me.gaMonthNames = Array("", "enero", "febrero", "marzo", "abril", "mayo", "junio", "julio", "agosto", "septiembre", "octubre", "noviembre", "diciembre")
me.gaDayNamesAbr = Array("", "dom", "lun", "mar", "mié", "jue", "vie", "sáb")


RealBasic's dynamic string constants can also be used.  First, define a dynamic string constant and for each language
enter the strings as shown below:

'English
,January,February,March,April,May,June,July,August,September,October,November,December
,Sun,Mon,Tue,Wed,Thu,Fri,Sat

'French
,janvier,février,mars,avril,mai,juin,juillet,août,septembre,octobre,novembre,décembre
,dim,lun,mar,mer,jeu,ven,sam

'German
,Januar,Februar,März,April,Mai,Juni,Juli,August,September,Oktober,November,Dezember
,Son,Mon,Die,Mit,Don,Fre,Sam

'Spanish
,enero,febrero,marzo,abril,mayo,junio,julio,agosto,septiembre,octubre,noviembre,diciembre
,dom,lun,mar,mié,jue,vie,sáb

Then in the control's Open event populate the global arrays (discussed above) with the following code:

me.gaMonthNames = split(kMonthNames, ",") 'kMonthNames is the dynamic string constant
me.gaDayNamesAbr = split(kDayNamesAbr, ",") ' kDayNameAbr is the dynamic string contant

Note:

If utilizing alternate month or day names or setting the HighlightToday flag to false the calendar must be
refreshed in it's Open event by calling the follwing method:

me.ShowToday()


=======
LICENSE
=======
This code is licensed under the Creative Commons Attribution-ShareAlike 4.0 International License. 

A summary of the license can be found here:

     https://creativecommons.org/licenses/by-sa/4.0/

A complete copy of the license can be found here:

     https://creativecommons.org/licenses/by-sa/4.0/legalcode


