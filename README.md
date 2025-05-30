-- Script para adicionar uma semente específica ao inventário

local Players = game:GetService("Players")
local ReplicatedStorage = game:GetService("ReplicatedStorage")

-- Função para adicionar a semente
local function adicionarSemente(nomeSemente)
    local jogador = Players.LocalPlayer
    local mochila = jogador:WaitForChild("Backpack")
    
    -- Verifica se a semente já existe na mochila
    for _, item in ipairs(mochila:GetChildren()) do
        if item:IsA("Tool") and item.Name == nomeSemente .. " Seed" then
            print("Semente já está no inventário.")
            return
        end
    end

    -- Cria a semente e adiciona à mochila
    local novaSemente = Instance.new("Tool")
    novaSemente.Name = nomeSemente .. " Seed"
    novaSemente.Parent = mochila
    print("Semente adicionada: " .. novaSemente.Name)
end

-- Exemplo de uso
adicionarSemente("Dragon Fruit")
