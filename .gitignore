local player = game.Players.LocalPlayer
local character = player.Character or player.CharacterAdded:Wait()
local hrp = character:WaitForChild("HumanoidRootPart")

local enabled = false
local funnyModel = nil

local function createFunnyPart()
    local model = Instance.new("Model")
    model.Name = "FunnyPart"
    model.Parent = character

    local leftBall = Instance.new("Part")
    leftBall.Shape = Enum.PartType.Ball
    leftBall.Size = Vector3.new(1.5, 1.5, 1.5)
    leftBall.CanCollide = false
    leftBall.Material = Enum.Material.SmoothPlastic
    leftBall.Parent = model

    local rightBall = leftBall:Clone()
    rightBall.Parent = model

    local stick = Instance.new("Part")
    stick.Size = Vector3.new(1.2, 3, 1.2)
    stick.CanCollide = false
    stick.Material = Enum.Material.SmoothPlastic
    stick.Parent = model

    local function weld(part, pos)
        part.CFrame = hrp.CFrame * pos
        local weld = Instance.new("WeldConstraint")
        weld.Part0 = hrp
        weld.Part1 = part
        weld.Parent = part
    end

    weld(leftBall, CFrame.new(-0.8, -2.7, 0))
    weld(rightBall, CFrame.new(0.8, -2.7, 0))
    weld(stick, CFrame.new(0, -1.5, 0))

    return model
end

-- toggle
enabled = not enabled

if enabled then
    funnyModel = createFunnyPart()
else
    if funnyModel then
        funnyModel:Destroy()
        funnyModel = nil
    end
end
