# Hsgudiehe    --atualizacao 
local Library = loadstring(game:HttpGet("https://raw.githubusercontent.com/xHeptc/Kavo-UI-Library/main/source.lua"))()

--windows
local Window = Library.CreateLib("em Atualizacao", "Sentinel")

--tabs
local Tab = Window:NewTab("em atualização")

Section:NewLabel("script")

--começo 

Section:NewButton("atualizaçao botao", "ButtonInfo", function()
    print("Clicked")
end)


--toggles usavel 
Section:NewToggle("velocidade", "ToggleInfo", function(state)
    if state then
        print("rapido on")
    else
        print("rapido Off")
    end
end)

Section:NewSlider("SliderText", "SliderInfo", 500, 0, function(s) -- 500 (MaxValue) | 0 (MinValue)
    game.Players.LocalPlayer.Character.Humanoid.WalkSpeed = s
end)
