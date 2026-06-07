local alvo = workspace:FindFirstChild("NomeDoInimigo")

if alvo and alvo:FindFirstChild("HumanoidRootPart") then
	local bolha = Instance.new("Part")
	bolha.Shape = Enum.PartType.Ball
	bolha.Material = Enum.Material.ForceField
	bolha.Color = Color3.fromRGB(170, 0, 255)
	bolha.Size = Vector3.new(8, 8, 8)
	bolha.Transparency = 0.3
	bolha.CanCollide = false
	bolha.Anchored = false
	bolha.Parent = workspace

	local weld = Instance.new("WeldConstraint")
	weld.Part0 = bolha
	weld.Part1 = alvo.HumanoidRootPart
	weld.Parent = bolha

	bolha.Position = alvo.HumanoidRootPart.Position

	game:GetService("Debris"):AddItem(bolha, 5) -- some após 5 segundos
end
