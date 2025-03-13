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

## Output

* Render a downloadable csv file named fsab_report_[YYYY-MM-DD-HH-MM-SS].csv with these sources and headers.

Across all files we want to merge players with the same names, position, and mlb team into the same row.

Some players may be on some source files, but not on others. All players need a record in the fsab_report

The structure below follows this pattern:

[File Ref].[column header] => [fsab header]

So PPDP.Roster is taking the value from ppmlb_player_data_processed.csv of "Roster" and copying to the fsab file

If a player does not have a corresponding value from FG, LAW, MCD, MLB, or BA files, just leave it blank
 
PPDP.Roster => Roster
First Name
Last Name
Pos
Team
LAW.Rank => LAW
MCD.Rank => MCD
BA.Rank => BA
MLB.Rank => MLB
FG.ETA => ETA
FG.Rank => FGR
FG.FV => FV
FG.Risk => Risk
FG.Age => Age
FG.HIT => HIT
FG.BAT => BAT
FG.PWR => PWR
FG.SPD => SPD
