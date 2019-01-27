# MP_MISSION_NAME_FREEMODE
https://images.illusivetea.me/2X36N2.png

```lua
local s

local x, y, z = table.unpack(GetEntityCoords(PlayerPedId()))

Citizen.CreateThread(function()
    s = Scaleform.Request("MP_MISSION_NAME_FREEMODE")
    while true do
        Citizen.Wait(0)
        --s:Draw2D()
        local CamRot = GetGameplayCamRot()
        s:Render3D(x, y, z+1, 0.0, 0.0, -CamRot.z, 3.5, 3.0, 1.0)
    end
end)

Citizen.CreateThread(function()
    while not s do Citizen.Wait(0) end
    s:CallFunction("SET_MISSION_INFO", "Test", "<FONT COLOR=\'#8466E2\'><FONT FACE='$Font2' SIZE='100'>Glonch Series", "Testing", "69%", "debug?", true, "64", 2500, 500, "\n   15:33:10")
end)
```

# RACE_POSITION

https://images.illusivetea.me/2685H9.jpg

```lua
local s

Citizen.CreateThread(function()
    s = Scaleform.Request("race_position")
    while true do
        Citizen.Wait(0)
        s:Draw2D()
    end
end)

Citizen.CreateThread(function()
    while not s do Citizen.Wait(0) end
    --s:CallFunction("debug")
    s:CallFunction("SET_RACE_LABELS", "POSITION","TIME","BEST TIME"," GATES","RACE RESULTS") -- SET_RACE_LABELS(racePosLabel, raceTimeLabel, bestTimeLabel, gateCounterLabel, raceResultsLabel)
    s:CallFunction("SET_RACE_POSITION", 2, 10) -- SET_RACE_POSITION(_position, _racers)
    s:CallFunction("SET_GATES_POSITION", 3, 20) -- SET_GATES_POSITION(_gateposition, _gates)
    s:CallFunction("SET_RACE_TIME", "1'34\"567") -- SET_RACE_TIME(_time)
    s:CallFunction("SET_BEST_TIME", "1'10\"567") -- SET_BEST_TIME(_time)
    s:CallFunction("SET_RACE_RESULTS", "0", "1", "glitchdetector", "0.01.118") -- SET_RACE_RESULTS(_index, _position, _racer, _time)
    s:CallFunction("SET_RACE_RESULTS", "1", "2", "IllusiveTea", "0.02.118")
    s:CallFunction("SET_RACE_RESULTS", "2", "3", "Ghostly Snailium", "0.03.118")
    s:CallFunction("SET_RACE_RESULTS", "3", "4", "Era", "0.04.118")
    s:CallFunction("SET_RACE_RESULTS", "4", "5", "Indra", "0.05.118")
    s:CallFunction("SET_RACE_RESULTS", "5", "6", "iridium", "0.06.118")
    s:CallFunction("SET_RACE_RESULTS", "6", "7", "IceHax", "0.07.118")
    s:CallFunction("SET_RACE_RESULTS", "7", "8", "Jack", "0.08.118")
    s:CallFunction("SET_RACE_RESULTS", "8", "9", "Snaily", "0.09.118")
    s:CallFunction("SET_RACE_RESULTS", "9", "10", "God", "0.10.118")
    s:CallFunction("SHOW_RACE_RESULTS", true) -- SHOW_RACE_RESULTS(vis)
    --SHOW_RACE_MODULE(enum, show) dunno
end)
```

# SOCIAL_CLUB_TV

https://images.illusivetea.me/4Q08a7.jpg
```lua
local s

Citizen.CreateThread(function()
    s = Scaleform.Request("social_club_tv")
    while true do
        Citizen.Wait(0)
        s:Draw2D()
    end
end)

Citizen.CreateThread(function()
    while not s do Citizen.Wait(0) end
    s:CallFunction("SET_LIVE_PANEL", "LIVE", "Here is a user", "BOB", "___HEYO", "", "") -- SET_LIVE_PANEL(title, description, player, crewTag, txd, txn)
    s:CallFunction("SHOW_LIVE_PANEL", true) -- SHOW_LIVE_PANEL(value)
    s:CallFunction("SET_TICKER_TITLE", "Ghostly Snailium discovers new doggo breed") -- SET_TICKER_TITLE(title)
    s:CallFunction("ADD_TICKER_TEXT", "what does this do?", "yo", "hey", "IllusiveTea is cool") -- ADD_TICKER_TEXT()
    s:CallFunction("SHOW_TICKER", true) -- SHOW_TICKER(value)
end)
```
