# README

## Examples
Look at the "Fantasy" or "Klingon" files for some examples

## Requirements
An up-to-date LaTeX distribution.

## Quick Start
The codes are based (aka. copied) on tikz' calendar library and
its pgf counterpart. As such, many options available to tikz' \calendar should be available *via* \PrintFantasycalendarBase (the equivalent to \calendar). 

## Commands
To load the code just include `\input{fantasycalender.code}`.

Dates are given in ISO Format: year-month-day.

To add months and specify the number of days in each month
use `\FantasyCalendarAddMonths{offset}{month-key-val-list}`.
`offset` defines the starting day in the year 0.

To add days use `\FantasyCalendarAddDays{list of week names}`.  

Calendars can be either printed by \PrintFantasycalendarBase or
using the more advanced command `\PrintFantasyCalendar{year}`, where
`year` is simply the number of the year (I think negative numbers are 
not yet allowed).

### Moons
Each fantasy world needs moons. More moons=more mystery=more fantasy=more pretended deepness. Moons are defined using `\NewFantasyMoon \MoonName {lunar-cycle} {offset}`. `lunar-cycle` and `offset` should be integers. Those moons
are automatically added to `\PrintFantasyCalendar`, but they also define the command `\MoonName {moon-phase}`where `moon-phase` is an integer. 


## ToDo
Write a better ReadMe. Add some optional arguments for customization.

## Not Implemented
Leap years. They make me unhappy.
