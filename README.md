-- Este é um script básico em Lua para Roblox
-- Certifique-se de entender o que cada parte do código faz antes de usá-lo

-- Função para dar boas-vindas ao jogador
function welcomePlayer(player)
    print("Bem-vindo ao jogo, " .. player.Name .. "!")
end

-- Conectar a função ao evento de jogador adicionado
game.Players.PlayerAdded:Connect(welcomePlayer)

-- Função para dar uma espada ao jogador
function giveSword(player)
    local sword = Instance.new("Tool")
    sword.Name = "Espada"
    sword.Parent = player.Backpack
end

-- Conectar a função ao evento de jogador adicionado
game.Players.PlayerAdded:Connect(giveSword)

-- Função para criar uma habilidade especial de mira assistida
function createAimAssistSkill(player)
    local skill = Instance.new("Tool")
    skill.Name = "Mira Assistida"
    skill.Parent = player.Backpack

    -- Adicionar funcionalidade à habilidade
    skill.Activated:Connect(function()
        print(player.Name .. " usou a Mira Assistida!")
        -- Código para melhorar a precisão do jogador
        local character = player.Character
        if character then
            local humanoid = character:FindFirstChildOfClass("Humanoid")
            if humanoid then
                -- Aumentar a precisão temporariamente
                humanoid.WalkSpeed = humanoid.WalkSpeed * 1.5
                wait(5) -- Duração da habilidade
                humanoid.WalkSpeed = humanoid.WalkSpeed / 1.5
            end
        end
    end)
end

-- Conectar a função ao evento de jogador adicionado
game.Players.PlayerAdded:Connect(createAimAssistSkill)

