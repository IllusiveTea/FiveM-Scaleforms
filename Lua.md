# FiveM-Scaleforms
## Find some cool scaleforms? Contribute!


# Scaleform: mp_car_stats_01
![Scale](http://illusivetea.me/WhyIsThereSoManyFuckingRpServers/9929be833.png)
```
Citizen.CreateThread(function()
    function Initialize(scaleform)
        scaleform = RequestScaleformMovie(scaleform)
        while not HasScaleformMovieLoaded(scaleform) do
            Citizen.Wait(0)
        end
        PushScaleformMovieFunction(scaleform, "SET_VEHICLE_INFOR_AND_STATS")
        PushScaleformMovieFunctionParameterString("RE-7B")
        PushScaleformMovieFunctionParameterString("Tracked and Insured")
        PushScaleformMovieFunctionParameterString("MPCarHUD")
        PushScaleformMovieFunctionParameterString("Annis")
        PushScaleformMovieFunctionParameterString("Top Speed")
        PushScaleformMovieFunctionParameterString("Acceleration")
        PushScaleformMovieFunctionParameterString("Braking")
        PushScaleformMovieFunctionParameterString("Traction")
        PushScaleformMovieFunctionParameterInt(68)
        PushScaleformMovieFunctionParameterInt(60)
        PushScaleformMovieFunctionParameterInt(40)
        PushScaleformMovieFunctionParameterInt(70)
        PopScaleformMovieFunctionVoid()

        return scaleform
    end
    scaleform = Initialize("mp_car_stats_01")
    while true do
        Citizen.Wait(0)
        veh = GetVehiclePedIsUsing(PlayerPedId())
        veh2 = GetPlayersLastVehicle()
        ped = PlayerPedId()
        x,y,z = table.unpack(GetEntityCoords(veh2, true))
        xrot,yrot,zrot = table.unpack(GetEntityRotation(veh2, 1))
        DrawScaleformMovie_3d(scaleform, x,y,z+5.0, xrot, 180.0, zrot, 0.0, 1.0, 0.0, 5.0, 4.0, 5.0, 0)
    end
end)

```
# Scaleform: POPUP_WARNING
![Scale](http://illusivetea.me/WhyIsThereSoManyFuckingRpServers/8uf43G81x.png)
```
Citizen.CreateThread(function()
    function drawscaleform(scaleform)
        scaleform = RequestScaleformMovie(scaleform)
        while not HasScaleformMovieLoaded(scaleform) do
            Citizen.Wait(0)
        end
        PushScaleformMovieFunction(scaleform, "SHOW_POPUP_WARNING")
        PushScaleformMovieFunctionParameterFloat(500.0)
        PushScaleformMovieFunctionParameterString("ALERT")
        PushScaleformMovieFunctionParameterString("This is a pretty neat scaleform")
        PushScaleformMovieFunctionParameterString("~r~Colours work too!")
        PushScaleformMovieFunctionParameterBool(true)
        PushScaleformMovieFunctionParameterInt(0)
        PopScaleformMovieFunctionVoid()

        DrawScaleformMovieFullscreen(scaleform, 255, 255, 255, 255, 0)
    end
    while true do
        Citizen.Wait(0)
        drawscaleform("POPUP_WARNING")
    end
end)
```
# Hud rankup bar
![Scale](http://illusivetea.me/WhyIsThereSoManyFuckingRpServers/321Bf3A8E14W3wc5d0vc.png)
```
Citizen.CreateThread(function()
    function Initialize(currentRankLimit, nextRankLimit, playersPreviousXP, playersCurrentXP, rank)
        local scaleform = RequestHudScaleform(19)

        while not HasHudScaleformLoaded(scaleform) do
            Citizen.Wait(0)
        end

        PushScaleformMovieFunctionFromHudComponent(scaleform, "SET_RANK_SCORES")
        PushScaleformMovieFunctionParameterInt(currentRankLimit) -- currentRankLimit
        PushScaleformMovieFunctionParameterInt(nextRankLimit)-- nextRankLimit
        PushScaleformMovieFunctionParameterInt(playersPreviousXP) --  playersPreviousXP
        PushScaleformMovieFunctionParameterInt(playersCurrentXP) --  playersCurrentXP
        PushScaleformMovieFunctionParameterInt(rank) -- rank
        PopScaleformMovieFunctionVoid()

        PushScaleformMovieFunctionFromHudComponent(scaleform, "SET_COLOUR")
        PushScaleformMovieFunctionParameterInt(116)
        PopScaleformMovieFunctionVoid()


        return scaleform
    end
    while true do
        Citizen.Wait(0)
        if IsControlJustPressed(1, 47) then
            scaleform = Initialize(200, 2000, 200, 500, 2)
        end
    end
end)


```

# MULTIPLAYER_CHAT

```
Citizen.CreateThread(function()
    function Initialize(scaleform)
        local scaleform = RequestScaleformMovie(scaleform)
        while not HasScaleformMovieLoaded(scaleform) do
            Citizen.Wait(0)
        end

        PushScaleformMovieFunction(scaleform, "showInput")
        PushScaleformMovieFunctionParameterInt(2)
        PushScaleformMovieFunctionParameterInt(2)
        PopScaleformMovieFunctionVoid()

        PushScaleformMovieFunction(scaleform, "ADD_MESSAGE")
        PushScaleformMovieFunctionParameterString("Blü")
        PushScaleformMovieFunctionParameterString("Fuck David")
        PushScaleformMovieFunctionParameterString("Hate")
        PushScaleformMovieFunctionParameterBool(false)
        PushScaleformMovieFunctionParameterInt(9)
        PopScaleformMovieFunctionVoid()

        return scaleform
    end
    scaleform = Initialize("MULTIPLAYER_CHAT")
    while true do
        Citizen.Wait(0)
        DrawScaleformMovieFullscreen(scaleform, 255, 255, 255, 255, 0)
    end
end)
```

# TRAFFIC_CAM

```
Citizen.CreateThread(function()
    function Initialize(scaleform)
        local scaleform = RequestScaleformMovie(scaleform)
        while not HasScaleformMovieLoaded(scaleform) do
            Citizen.Wait(0)
        end

        PushScaleformMovieFunction(scaleform, "PLAY_CAM_MOVIE")
        PopScaleformMovieFunctionVoid()

        return scaleform
    end
    scaleform = Initialize("TRAFFIC_CAM")
    while true do
        Citizen.Wait(0)
        DrawScaleformMovieFullscreen(scaleform, 255, 255, 255, 255, 0)
    end
end)
```

```
Citizen.CreateThread(function()
    function Initialize(scaleform)
        local scaleform = RequestScaleformMovie(scaleform)
        while not HasScaleformMovieLoaded(scaleform) do
            Citizen.Wait(0)
        end

        PushScaleformMovieFunction(scaleform, "SHOW_HEALTH_ARMOUR")
        PushScaleformMovieFunctionParameterBool(true)
        PopScaleformMovieFunctionVoid()

        return scaleform
    end
    scaleform = Initialize("MINIMAP")
    function Initialize2(scaleform)
        local scaleform = RequestScaleformMovie(scaleform)
        while not HasScaleformMovieLoaded(scaleform) do
            Citizen.Wait(0)
        end

        PushScaleformMovieFunction(scaleform, "")
        PushScaleformMovieFunctionParameterInt(1)
        PopScaleformMovieFunctionVoid()

        return scaleform
    end
    scaleform2 = Initialize("MINIMAP_MAIN_MAP")
    while true do
        Citizen.Wait(0)
        --DrawScaleformMovieFullscreen(scaleform, 255, 255, 255, 255, 0)
        --DrawScaleformMovieFullscreen(scaleform2, 255, 255, 255, 255, 0)
        x,y,z = table.unpack(GetEntityCoords(PlayerPedId(),true))
        --DrawScaleformMovie_3dNonAdditive(scaleform, x+4.5,y+5.0,z-2.0, 0.0, 0.0, 0.0, 1.0, 1, 1, 10.0, 6.0, 6.0, 0)
        --DrawScaleformMovie_3dNonAdditive(scaleform2, x+4.5,y+5.0,z-2.0, 0.0, 0.0, 0.0, 1.0, 1, 1, 10.0, 6.0, 6.0, 0)
    end
end)

```

```
--[[
PushScaleformMovieFunctionParameterString()
PushScaleformMovieFunctionParameterInt()
PushScaleformMovieFunctionParameterFloat()
PushScaleformMovieFunctionParameterBool()
]]
-- SET_GRID_ITEM(i, sTitle, sTXD, sTXN, textureLoadType, verifiedType, eIcon, bCheck, rpMult, cashMult, bDisabled, iconCol)
Citizen.CreateThread(function()
    function Initialize(scaleform)
        local scaleform = RequestScaleformMovie(scaleform)
        while not HasScaleformMovieLoaded(scaleform) do
            Citizen.Wait(0)
        end

        PushScaleformMovieFunction(scaleform, "SET_TITLE")
        PushScaleformMovieFunctionParameterString("What Next?")
        PushScaleformMovieFunctionParameterString("Votes: ")
        PopScaleformMovieFunctionVoid()

        PushScaleformMovieFunction(scaleform, "SET_GRID_ITEM")
        PushScaleformMovieFunctionParameterInt(0)
        PushScaleformMovieFunctionParameterString("Some Cool Race")
        PushScaleformMovieFunctionParameterString("Votes: ")
        PushScaleformMovieFunctionParameterString("Votes: ")
        PushScaleformMovieFunctionParameterInt(1)
        PushScaleformMovieFunctionParameterString("No")
        PushScaleformMovieFunctionParameterInt(2)
        PushScaleformMovieFunctionParameterInt(2)
        PushScaleformMovieFunctionParameterInt(3)
        PushScaleformMovieFunctionParameterInt(1)
        PushScaleformMovieFunctionParameterInt(1)
        PopScaleformMovieFunctionVoid()

        PushScaleformMovieFunction(scaleform, "SET_GRID_ITEM")
        PushScaleformMovieFunctionParameterInt(0)
        PushScaleformMovieFunctionParameterString("Some Cool Race")
        PushScaleformMovieFunctionParameterString("Votes: ")
        PushScaleformMovieFunctionParameterString("Votes: ")
        PushScaleformMovieFunctionParameterInt(1)
        PushScaleformMovieFunctionParameterInt(1)
        PushScaleformMovieFunctionParameterInt(2)
        --PushScaleformMovieFunctionParameterInt(0)
        --PushScaleformMovieFunctionParameterInt(0)
        PushScaleformMovieFunctionParameterInt(1)
        PushScaleformMovieFunctionParameterInt(1)
        PopScaleformMovieFunctionVoid()

        return scaleform
    end
    scaleform = Initialize("mp_next_job_selection")
    while true do
        Citizen.Wait(0)
        DrawScaleformMovieFullscreen(scaleform, 255, 255, 255, 255, 0)
    end
end)
```

# Doomsday bunker screen
```
function CreateNamedRenderTargetForModel(name, model)
	local handle = 0
	
	if not IsNamedRendertargetRegistered(name) then
		RegisterNamedRendertarget(name, 0)
	end
	if not IsNamedRendertargetLinked(model) then
		LinkNamedRendertarget(model)
	end
	if IsNamedRendertargetRegistered(name) then
		handle = GetNamedRendertargetRenderId(name)
	end

	return handle
end

function Initialize(scaleform)
        local scaleform = RequestScaleformMovie(scaleform)

        while not HasScaleformMovieLoaded(scaleform) do
            Citizen.Wait(0)
        end
        PushScaleformMovieFunction(scaleform, "SHOW_LAUNCH")
		PushScaleformMovieFunctionParameterBool(false)
		PushScaleformMovieFunctionParameterString("This is a heist")
		PushScaleformMovieFunctionParameterString("IllusiveTea")
		PushScaleformMovieFunctionParameterString("A mission")
		PushScaleformMovieFunctionParameterString("Suck a huge cock")
		PushScaleformMovieFunctionParameterString("2,000,000")
		PushScaleformMovieFunctionParameterString("3_4_b_setup_03")
		PushScaleformMovieFunctionParameterString("prop_screen_nhp_base3")
		--SHOW_LAUNCH(skipLoader, title, gangName, missionName, description, cost, texture, txd)
        PopScaleformMovieFunctionVoid()
		
        return scaleform
    end

function LoadSprite(dict)
	if not HasStreamedTextureDictLoaded(dict) then
		RequestStreamedTextureDict(dict)
		while not HasStreamedTextureDictLoaded(dict) do
			Wait(0)
		end
	end
	return dict
end

Citizen.CreateThread(function ()
	--SetEntityCoords(PlayerPedId(), 483.2006225586, 4810.5405273438, -58.919288635254, 18.04705619812, 0, 0, 0, 0)
	local model = GetHashKey("xm_prop_x17dlc_monitor_wall_01a"); -- 2054093856
	local pos = { x = -810.59, y = 170.46, z = 77.25 };
	local entity = GetClosestObjectOfType(pos.x, pos.y, pos.z, 0.05, model, 0, 0, 0)
	local handle = CreateNamedRenderTargetForModel("Prop_x17DLC_Monitor_Wall_01a", model)
	LoadSprite("prop_screen_nhp_base3")
	scaleform = Initialize("iaa_heist_board")
	while true do
		--Set_2dLayer(4)
		SetScriptGfxDrawBehindPausemenu(true)
		N_0xe6a9f00d4240b519(scaleform, 1)
		SetTextRenderId(handle)
			--DrawRect(0.5, 0.5, 1.0, 1.0, 255, 0, 0, 255)
			DrawScaleformMovie(scaleform, 0.5, 0.501, 1.0, 1.0, 255, 255, 255, 255, 1)
			--DrawSprite(LoadSprite("prop_screen_nhp_base3"), "3_4_b_setup_03", 0.5, 0.5, 1.0, 1.0, 0.0, 255, 255, 255, 255)
		SetTextRenderId(GetDefaultScriptRendertargetRenderId()) -- reset
		SetScriptGfxDrawBehindPausemenu(false)
		Citizen.Wait(0)
	end
end)
```

