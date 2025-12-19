-- Delta Mobile Smooth (Blox Fruits)
-- For low-end phone

local Lighting = game:GetService("Lighting")

-- Force lowest graphics
settings().Rendering.QualityLevel = Enum.QualityLevel.Level01

-- Lighting optimize
Lighting.GlobalShadows = false
Lighting.FogEnd = 1e9
Lighting.Brightness = 1
Lighting.EnvironmentDiffuseScale = 0
Lighting.EnvironmentSpecularScale = 0

-- Disable post effects
for _,v in pairs(Lighting:GetChildren()) do
    if v:IsA("PostEffect") then
        v.Enabled = false
    end
end

-- Remove lag effects
for _,v in pairs(workspace:GetDescendants()) do
    if v:IsA("ParticleEmitter")
    or v:IsA("Trail")
    or v:IsA("Smoke")
    or v:IsA("Fire") then
        v.Enabled = false
    end
end

-- Simple materials
for _,v in pairs(workspace:GetDescendants()) do
    if v:IsA("BasePart") then
        v.Material = Enum.Material.Plastic
        v.Reflectance = 0
    end
end
