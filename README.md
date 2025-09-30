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

```json
"sessionip":"167.235.0.254"
```
This one's obvious, it's the current server's IP Address.


```json
"match_type":"Echo_Combat_Private"
```
The Match Type. Indicates things such as, Are we in a social lobby? Are we in a private/tournament match? Are we in arena? Are we in combat?


```json
"map_name":"mpl_combat_dyson"
```
The name of the map we are currently playing on.


```json
"tournament_match":false
```
Are we currently playing on a match with tournament mode enabled?


```json
"private_match":true
```
Is the current match private or public?


```json
"blue_round_score":0 / "orange_round_score":0
```
Used to track Round Victories. Echo Combat works on a best of 3 system, so first team to 2 score, usually wins.


```json
"total_round_count":0
```
Total amount of rounds this match has endured. Usually does not go above 3.


```json
"contested":false
```
Is the Capture Point / Payload Currently contested?


```json
"orange_points":0.0 / "blue_points":0.0
```
This value tracks Capture Point progress (0% - 100%). It also is not present in Payload Matches.


```json
"right_shoulder_pressed":0.0 / "right_shoulder_pressed2":0.0
```
Honestly no clue why trigger input vars are in here.


```json
"left_shoulder_pressed":0.0 / "left_shoulder_pressed2":0.0
```
Same as above :P


```json
"client_name":"Furo"
```
The Display Name of the Local Client. This will be whatever your local username is.


```json
"err_code":0
```
This error code is not-zero when an error occurs. The most common error is -6 (You are in the lobby, and the lobby does not serve session data).


```json
"teams": []
```
This array stores the teams (3), which are "BLUE TEAM", "ORANGE TEAM" and "SPECTATORS"


```json
"team":"BLUE TEAM",
```
Indicates this array entry's team's name.


```json
"players": []
```
An array containing player data, which lives inside each Team Object.


```json
"name":"Furo"
```
This player's Display Name.


```json
"playerid":0
```
This player's player ID. A player ID is a number that is server-specific. Usually the first player that joins, is player 0, the second is player 1, and so on. 
This is seperate from team affiliation.



```json
"userid":14712
```
Your Account User ID. This can be used to track you accross matches, even after Display-Name change.


```json
"is_emote_playing":false
```
Is this player currently using his emotes?


```json
"number":0
```
Customizeable User-Number.
Usually changeable via Spark, or the Number Emblem.


```json
"level":1
```
Your Combat Level.


```json
"ping":40
```
The time it takes in milliseconds for a packet to be sent from your computer to the server.


```json
"packetlossratio":0.0
```
Idk



```json
"Weapon":"assault"
```
What pistol is this player using? 
I don't know the internal names for the 4 new weapons yet. I'll add them when i can find the time.


```json
"TacMod":"heal"
```
What tac-mod is this player using?


```json
"Ordnance":"det"
```
What ordnance is this player using?


```json
"Arm":"Right"
```
Which arm is the weapon on for this player?


```json
"velocity":[0.0,0.0,0.0]
```
The player's current velocity as a vector. (X, Y, Z)


```json
"head": [] / "body": [] / "rhand": [] / "lhand": [] 
```
Each of these arrays tracks position, and rotation as a vector.
Position is a simple X Y Z position, and rotation is stored by defining the Euler Angles.



```json
"player": []
```
This array stores Local XR Tracking Data.


```json
"vr_position": [] / "vr_left": [] / "vr_forward": [] / "vr_up": []
```
These arrays store the exact values for the players Playspace Position and rotation in euler angles.


```json
"last_throw": []
```
I don't know honestly... i can't decide between "data about the last object you've thrown" or "data about the last time you pushed yourself off of an object".


```json
"pause": []
```
This array stores data about Team Pauses. When in a private match, any team can call in a "huddle", pausing the game.
