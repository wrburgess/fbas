# Aggregate Date

## Sources (and reference names)

* ppmlb_player_data_processed.csv (PPDP)
* mlb_prospect_rankings.csv (MLB)
* kiley_mcdaniel_prospect_rankings.csv (MCD)
* keith_law_baseball_prospects_rankings.csv (LAW)
* baseball_america_prospect_rankings.csv (BA)
* fan_graphs_processed.csv (FG)

## Goal

* Combine data across the sources files into a new single file

## Steps

* copy baseball_america_prospect_rankings.csv rankings to column BA
* copy mlb_prospect_rankings.csv rankings to column MLB
* copy kiley_mcdaniel_prospect_rankings.csv rankings to column MCD
* copy keith_law_baseball_prospects_rankings.csv rankings to column LAW

## Notes

* The MLB teams may be referred to various names across files that are mapped in the context file mlb_teams.csv
* Players may have their names in separate columns of first_name, last_name, etc but may have full name combined
* Player positions may be described differently across files with those mappings in the context file ppmlb_fantasy_baseball_positions.csv
* Trying to match players explicitly by exact matches of name, position (pos), and team may be problematic. You'll need to allow for variation across the files for slight differences.

## Output

* Render a downloadable csv file named fsab_report_[YYYY-MM-DD-HH-MM-SS].csv with these sources and headers.

Across all files we want to merge players with the same names, position, and mlb team into the same row.

Some players may be on some source files, but not on others. All players need a record in the fsab_report

The structure below follows this pattern:

[File Ref].[column header] => [fsab header]

So PPDP.Roster is taking the value from ppmlb_player_data_processed.csv of "Roster" and copying to the fsab file

If a player does not have a corresponding value from FG, LAW, MCD, MLB, or BA files, just leave it blank

For the Roster value, convert the full name to the abbreviated name in the ppmlb_fantasy_baseball_teams.csv context file. For example, Wrigleyville Fielders will be WRI instead.
 
* PPDP.Roster => Roster
* First Name
* Last Name
* Pos
* Team
* LAW.Rank => "LAW Rank"
* MCD.Rank => "MCD Rank"
* BA.Rank => "BA Rank"
* MLB.Rank => "MLB Rank"
* FG.ETA => ETA
* FG.Rank => "FG Rank"
* FG.FV => FV
* FG.Risk => Risk
* FG.Age => Age
* FG.HIT => HIT
* FG.BAT => BAT
* FG.PWR => PWR
* FG.SPD => SPD
