# README

## Examples
Look at the "Fantasy1" or "Klingon" files for some examples

## Requirements
An up-to-date LaTeX distribution.

## Quick Start
The codes are "based" (aka. copied) on tikz' calendar library and
its pgf counterpart. As such, many options available to tikz' \calendar should
be available *via* \PrintFantasycalendarBase (the equivalent to \calendar). 
For an easy "print the whole year" you may use `\PrintFantasyCalendarYear`.

## Commands
To load the code just include `\input{fantasycalender.code}` in your preamble.

Dates are given in ISO Format: year-month-day.

To add months and specify the number of days in each month
use `\FantasyCalendarAddMonths{offset}{month-key-val-list}`.
`offset` defines the starting day in the year 0.

To add days use `\FantasyCalendarAddDays{list of week names}`.  

Calendars can be either printed by \PrintFantasycalendarBase or
using the more advanced command `\PrintFantasyCalendarYear{year}{if
statements}`, where
`year` is simply the number of the year (I think negative numbers are 
not yet allowed). `if statements` are equaivalent to the ones in tikz´ 
calendar library (see the `tikz` documentation)


### Moons
Each fantasy world needs moons. More moons=more mystery=more fantasy=more
pretended deepness. Moons are defined using `\NewFantasyMoon \MoonName
{lunar-cycle} {offset}`. `lunar-cycle` and `offset` should be integers. Those
moons
are automatically added to `\PrintFantasyCalendarYear`, but they also define
the command `\MoonName {moon-phase}`where `moon-phase` is an integer. 

To add moons to normal calendars set the tikz' option `add moons` to `true`.

### Notes
Adding notes is essential for any calendar. Either yearly events or party
specific one-time happenings, both can be added to the calendar using either
`\FantasyCalendarDateEntry` or `\FantasyCalendarOneTimeEntry`. 

To print the notes in the calendar use tikz option `add day notes` 
(by optional argument or `\tikz{add day notes=true}`). 
This option is set to `true` in `\PrintFantasyCalendarYear` by default. 

`\FantasyCalendarDateEntry{month-day}{text}`. Adds a regular event to the
calendar which happens every year in the month `month` on day `day` (see
`Fantasy1`).

`\FantasyCalendarOneTimeEntry{iso-date}{text}`. Adds a one-time event or note
to the date given by `iso-date` (aka. year-month-date). 


## Calendar size
One can set the width and height of each box with the options `box width`, `box
height` or `box size` (if you want to set both at once). They accept dimensions
(`2cm`, `3in`, etc.), but they  also accept the value `fit` which tries to fit
the width or height to the available `\textwidth`/`\textheight`. `box size`
also  accepts the key `fit-square` which makes sure the boxes are squares
(width=height).

You may set them in the optional arguments of `\PrintFantasycalendarBase`,
`PrintFantasyCalendarYear` or using `\tikzset`. (See "Fantasy2")

Drawing a frame around each box is easy using `box draw=black` (instead
of black you may use any colour available).

Alignment of the box content can be changed using `box ragged =
left/center/right` or `box vertical=top/center/bottom`. 

The last two options only have an effect if a box size was defined using `box
width/height/size`.


### Custozmizing Stuff

#### Printing Dates and Text


`add year to month=left/right` adds the current year to the left or right of 
the month (if printed)

`add moons` adds the moons defined by `\NewFantasyMoon` to each calendar entry.
(chaning box sized may be advisable)

`add day notes` adds notes to each entry (changing the box size may also be advisable).
 

More general changes are also possible by using the following options:

```
\tikzset{day text=
  {\%d-\,\FantasycalendarPrintMoons\\ \FantasycalendarPrinDayNotes}
}
```

```
\tikzset{month text=
  {\bfseries\%mt [\%m0]}
}
```

```
\tikzset{weekday text=
  {weekday text={\%wt}}
}
```


## ToDo
Write a better ReadMe. Add some optional arguments for customization.

Allow iso the names of months/days?
Add option to add notes.


## Not Implemented
Leap years. They make me unhappy.
