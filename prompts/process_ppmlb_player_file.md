# Process PPMLB Player File

## Sources

* ppmlb_fantasy_baseball_teams.csv
* ppmlb_fantasy_baseball_positions.csv
* ppmlb_players_2025_raw.csv

## Goal

* Convert and reformat columns in the file

## Steps

* Start with the ppmlb_players_2025_raw.csv file

## Process First Column - Roster

* Convert the PPMLB Fantasy Team names into acronyms in alignment with the ppmlb_fantasy_baseball_teams.csv file
* If the value is "FA", leave it alone

## Process Second Column - Player

* This column contains Player Name, Player Positions, and MLB Team Acronym
* We want to separate this column into First Name,Last Name,Pos,Team columns and leave the other columns as-is
* Identify the break between player name and positions using the ppmlb_fantasy_baseball_positions.csv reference file.
* Take the first name and separate using the space with middle, last, suffix, etc.
* Example: "Elly De La Cruz SS | CIN" will be Elly,De La Cruz,SS,CIN
* Example: "Victor Mesa Jr. CF | MIA" will be Victor,Mesa Jr.,CF,MIA
* Example: "Aaron Judge CF,DH,LF,RF | NYY" wil be Aaron,Judge,"CF,DH,LF,RF",NYY

## Output

* Render a downloadable csv file with these headers:

* Roster,First Name,Last Name,Pos,Team,AB,R,H,1B,2B,3B,HR,RBI,BB,K,SB,CS,AVG,OBP,SLG,Rank,
