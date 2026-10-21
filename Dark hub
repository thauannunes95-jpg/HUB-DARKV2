-- DARK HUB | ANIMAL SIMULATOR V2

local Players = game:GetService("Players")
local TweenService = game:GetService("TweenService")

local player = Players.LocalPlayer
local playerGui = player:WaitForChild("PlayerGui")

local gui = Instance.new("ScreenGui")
gui.Name = "DarkHubIntro"
gui.IgnoreGuiInset = true
gui.DisplayOrder = 999999
gui.ResetOnSpawn = false
gui.Parent = playerGui

local fundo = Instance.new("Frame")
fundo.Size = UDim2.fromScale(1, 1)
fundo.BackgroundColor3 = Color3.fromRGB(0, 0, 0)
fundo.BorderSizePixel = 0
fundo.Parent = gui

local titulo = Instance.new("TextLabel")
titulo.Size = UDim2.fromScale(1, 1)
titulo.BackgroundTransparency = 1
titulo.Text = "DARK HUB"
titulo.TextColor3 = Color3.fromRGB(140, 0, 255)
titulo.TextScaled = true
titulo.Font = Enum.Font.GothamBlack
titulo.Parent = fundo

-- Carrega o script original em paralelo
task.spawn(function()
    local ok, err = pcall(function()
        loadstring(game:HttpGet(
            "https://animal-simulator-server.vercel.app/lua/mod_animal_simulator_v2.lua"
        ))()
    end)

    if not ok then
        warn("DARK HUB: " .. tostring(err))
    end
end)

-- Fica visível por 10 segundos
task.wait(10)

-- Desaparece suavemente
local info = TweenInfo.new(1)

TweenService:Create(fundo, info, {
    BackgroundTransparency = 1
}):Play()

TweenService:Create(titulo, info, {
    TextTransparency = 1
}):Play()

task.wait(1)
gui:Destroy()
