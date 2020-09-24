# bottlenose-lab-teams
Bottlenose script to create staff/team lab pairings (used in Microsoft Teams).

Creates a `students.csv` and `staff.csv` with the student:staff and staff:team pairings.

## Example
`python3 bottlenose_teams.py 111 12676 Nick Daniel Jake Ben --latest`

**students.csv:**
|Group  |Team  |Staff|Member 1   |Member 2       |Member 3     |Teams Channel Name                                     |
|-------|------|-----|-----------|---------------|-------------|-------------------------------------------------------|
|0      |43423 |Nick |\<redacted>|\<redacted>    |\<redacted>  |Team 43423 - \<redacted>, \<redacted>, and \<redacted> |
|0      |43512 |Nick |\<redacted>|\<redacted>    |             |Team 43512 - \<redacted> and \<redacted>               |
|0      |43513 |Nick |\<redacted>|\<redacted>    |             |Team 43513 - \<redacted> and \<redacted>               |
|...    |...   |...  |...        |...            |...          |...                                                    |

**staff.csv:**
|Group|Start|End  |Staff |Teams Channel Name           |Count|
|-----|-----|-----|------|-----------------------------|-----|
|0    |43423|43525|Nick  |Groups (43423-43525) - Nick  |15   |
|1    |43526|43540|Daniel|Groups (43526-43540) - Daniel|15   |
|2    |43541|43555|Jake  |Groups (43541-43555) - Jake  |14   |
|3    |43556|43796|Ben   |Groups (43556-43796) - Ben   |14   |

## Setup
1. `python3 -m venv env`
1. `source env/bin/activate`
1. `pip3 install -r requirements.txt`

## Usage

`bottlenose_teams.py [-h] [-o OFFSET] [-s SHEET] [--latest] course lab staff [staff ...]`

positional arguments:
```
  course                        ID of the course
  lab                           CRN of lab section
  staff                         Names of staff members
```

optional arguments:
```
  -h, --help                    show this help message and exit
  -o OFFSET, --offset OFFSET    Used to rotate staff members
  -s SHEET, --sheet SHEET       Name of sheet to read team data
  --latest                      Uses the latest teamsets
```

The `KHOURY_USERNAME` and `KHOURY_PASSWORD` environment variables can be set to fully automate this script.
