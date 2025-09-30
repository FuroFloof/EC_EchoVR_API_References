# Echo VR API References

In this repository i archive Echo VR Match API Sessions.
These session "snapshots" have been cleaned up and re-ordered by me, by hand, to make them more readable, and digestable.

So far added:

  - Combat - Dyson (Capture Point)
  - Combat - Combustion (Capture Point)
  - Combat - Fission (Payload)
  - Combat - Surge (Payload)

In each session i simply started a new private match alone, 
loaded in, took a snapshot, and left. 

There were no other players present, and i always occupy team blue.

## What do these values mean?
Now i'm not someone who would ever go into the game, and document when every single variable changes why,
but i can make educated guesses, and please correct me if i'm wrong with anything here:

<br><br><br>

```json
"sessionid":"D8A4CC1D-C086-49DF-9C51-12E831B88A38"
```
The Session ID is a unique Match-ID that is probably used for internal serverside shenanigans, things like stats, and so on.
<br><br><br>
```json
"sessionip":"167.235.0.254"
```
This one's obvious, it's the current server's IP Address.
<br><br><br>

```json
"match_type":"Echo_Combat_Private"
```
The Match Type. Indicates things such as, Are we in a social lobby? Are we in a private/tournament match? Are we in arena? Are we in combat?
<br><br><br>

```json
"map_name":"mpl_combat_dyson"
```
The name of the map we are currently playing on.
<br><br><br>

```json
"tournament_match":false
```
Are we currently playing on a match with tournament mode enabled?
<br><br><br>

```json
"private_match":true
```
Is the current match private or public?
<br><br><br>

```json
"blue_round_score":0  "orange_round_score":0
```
Used to track Round Victories. Echo Combat works on a best of 3 system, so first team to 2 score, usually wins.
<br><br><br>

```json
"total_round_count":0
```
Total amount of rounds this match has endured. Usually does not go above 3.
<br><br><br>

```json
"contested":false
```
Is the Capture Point / Payload Currently contested?
<br><br><br>

```json
"orange_points":0.0  "blue_points":0.0
```
This value tracks Capture Point progress (0% - 100%). It also is not present in Payload Matches.
<br><br><br>

```json
"right_shoulder_pressed":0.0  "right_shoulder_pressed2":0.0
```
Honestly no clue why trigger input vars are in here.
<br><br><br>

```json
"left_shoulder_pressed":0.0  "left_shoulder_pressed2":0.0
```
Same as above :P
<br><br><br>

```json
"client_name":"Furo"
```
The Display Name of the Local Client. This will be whatever your local username is.
<br><br><br>

```json
"err_code":0
```
This error code is not-zero when an error occurs. The most common error is -6 (You are in the lobby, and the lobby does not serve session data).
<br><br><br>

```json
"teams": []
```
This array stores the teams (3), which are "BLUE TEAM", "ORANGE TEAM" and "SPECTATORS"
<br><br><br>

```json
"team":"BLUE TEAM",
```
Indicates this array entry's team's name.
<br><br><br>

```json
"players": []
```
An array containing player data, which lives inside each Team Object.
<br><br><br>

```json
"name":"Furo"
```
This player's Display Name.
<br><br><br>

```json
"playerid":0
```
This player's player ID. A player ID is a number that is server-specific. Usually the first player that joins, is player 0, the second is player 1, and so on. 
This is seperate from team affiliation.
<br><br><br>


```json
"userid":14712
```
Your Account User ID. This can be used to track you accross matches, even after Display-Name change.
<br><br><br>

```json
"is_emote_playing":false
```
Is this player currently using his emotes?
<br><br><br>

```json
"number":0
```
Customizeable User-Number.
Usually changeable via Spark, or the Number Emblem.
<br><br><br>

```json
"level":1
```
Your Combat Level.
<br><br><br>

```json
"ping":40
```
The time it takes in milliseconds for a packet to be sent from your computer to the server.
<br><br><br>

```json
"packetlossratio":0.0
```
Idk
<br><br><br>


```json
"Weapon":"assault"
```
What pistol is this player using? 
I don't know the internal names for the 4 new weapons yet. I'll add them when i can find the time.
<br><br><br>

```json
"TacMod":"heal"
```
What tac-mod is this player using?
<br><br><br>

```json
"Ordnance":"det"
```
What ordnance is this player using?
<br><br><br>

```json
"Arm":"Right"
```
Which arm is the weapon on for this player?
<br><br><br>

```json
"velocity":[0.0,0.0,0.0]
```
The player's current velocity as a vector. (X, Y, Z)
<br><br><br>

```json
"head": []  "body": []  "rhand": []  "lhand": [] 
```
Each of these arrays tracks position, and rotation as a vector.
Position is a simple X Y Z position, and rotation is stored by defining the Euler Angles.
<br><br><br>


```json
"player": []
```
This array stores Local XR Tracking Data.
<br><br><br>

```json
"vr_position": []  "vr_left": []  "vr_forward": []  "vr_up": []
```
These arrays store the exact values for the players Playspace Position and rotation in euler angles.
<br><br><br>

```json
"last_throw": []
```
I don't know honestly... i can't decide between "data about the last object you've thrown" or "data about the last time you pushed yourself off of an object".


```json
"pause": []
```
This array stores data about Team Pauses. When in a private match, any team can call in a "huddle", pausing the game.
