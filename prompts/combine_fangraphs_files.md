# Combine Fangraphs Files

## Sources

* fangraphs-the-board-ranks.csv
* fangraphs-the-board-scout.csv

## Goal

* Convert and reformat columns from both files into a single file

## Steps

From the fangraphs-the-board-ranks.csv file grab the Top 100, Name, Org, Pos, ETA, FV, Risk, Age (nearest tenth, round up), and Report columns

From the fangraphs-the-board-scout.csv file grab the Hit (second value), Bat Ctrl, Game Pwr (second value), and Spd columns (second value)

Combine these two data sets into a single file mapped to the players like this

Name => Name
Pos => Pos
Org => Org
ETA => ETA
Top 100 => Rank
FV => FV
Risk => Risk
Age => Age
Hit => HIT
Bat Ctrl => BAT
Game Pwr => PWR
Spd => SPD
Report => Report

## Output

* Render a downloadable csv file named fan_graphs_processed.csv with these headers:

  - Name,Pos,Org,ETA,Rank,FV,Risk,Age,HIT,BAT,PWR,SPD,Report

## Notes

* If a player has a record in one file and not the other, give them a unique record in the output file
* If a player lacks a value in either source file, leave it blank in the output file
