# README

## Examples
Look at the "Fantasy1" or "Klingon" files for some examples

## Requirements
An up-to-date LaTeX distribution.

## Quick Start
The codes are "based" (aka. copied) on tikz' calendar library and
its pgf counterpart. As such, many options available to tikz' \calendar should be available *via* \PrintFantasycalendarBase (the equivalent to \calendar). 

## Commands
To load the code just include `\input{fantasycalender.code}` in your preamble.

Dates are given in ISO Format: year-month-day.

To add months and specify the number of days in each month
use `\FantasyCalendarAddMonths{offset}{month-key-val-list}`.
`offset` defines the starting day in the year 0.

To add days use `\FantasyCalendarAddDays{list of week names}`.  

Calendars can be either printed by \PrintFantasycalendarBase or
using the more advanced command `\PrintFantasyCalendarYear{year}`, where
`year` is simply the number of the year (I think negative numbers are 
not yet allowed).

### Moons
Each fantasy world needs moons. More moons=more mystery=more fantasy=more pretended deepness. Moons are defined using `\NewFantasyMoon \MoonName {lunar-cycle} {offset}`. `lunar-cycle` and `offset` should be integers. Those moons
are automatically added to `\PrintFantasyCalendarYear`, but they also define the command `\MoonName {moon-phase}`where `moon-phase` is an integer. 

### Notes
Adding notes is essential for any calendar. Either yearly events or party specific one-time happenings, both can be added to the calendar using either
`\FantasyCalendarDateEntry` or `\FantasyCalendarOneTimeEntry`.

`\FantasyCalendarDateEntry{month-day}{text}`. Adds a regular event to the calendar which happens every year in the month `month` on day `day` (see `Fantasy1`).

`\FantasyCalendarOneTimeEntry{iso-date}{text}`. Adds a one-time event or note to the date given by `iso-date` (aka. year-month-date). 

### Custozmizing Stuff

#### Printing Dates and Text


\tikzset{day text=
  {\%d-\,\FantasycalendarPrintMoons\\ \FantasycalendarPrinDayNotes}
}

\tikzset{month text=
  {\bfseries\%mt [\%m0]}
}

\tikzset{weekday text=
  {weekday text={\%wt}}
}



\FantasycalendarTextDay
\FantasycalendarPrintMoons
\FantasycalendarPrinDayNotes

## ToDo
Write a better ReadMe. Add some optional arguments for customization.

## Not Implemented
Leap years. They make me unhappy.
