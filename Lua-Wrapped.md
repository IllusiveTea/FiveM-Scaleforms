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

