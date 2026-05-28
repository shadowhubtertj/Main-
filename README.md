-- ABA MAIN COMPLETA COM TODAS AS FUNÇÕES VISUAIS
local mc = tabContents["Main"]
local y = 5

-- ============ SEÇÃO SELECT ITEM ============
CreateLabel(mc, "🎯 SELECT ITEM", y); y = y + 24
CreateDivider(mc, y); y = y + 10

-- Botão para abrir seleção de item
local selectItemBtn = CreateButton(mc, "[ Selecione um Item ]", y, function()
    CriarMenuItem()
end)
y = y + 45

-- Label para mostrar item selecionado
local selectedItemLabel = Instance.new("TextLabel")
selectedItemLabel.Text = "Nenhum item selecionado"
selectedItemLabel.Size = UDim2.new(0, 200, 0, 20)
selectedItemLabel.Position = UDim2.new(0, 10, 0, y)
selectedItemLabel.BackgroundTransparency = 1
selectedItemLabel.TextColor3 = colors.textDim
selectedItemLabel.Font = Enum.Font.Gotham
selectedItemLabel.TextSize = 10
selectedItemLabel.TextXAlignment = Enum.TextXAlignment.Left
selectedItemLabel.Parent = mc
y = y + 25

-- ============ SEÇÃO SELECT BOSS ============
CreateLabel(mc, "👑 SELECT BOSS", y); y = y + 24
CreateDivider(mc, y); y = y + 10

-- Botão para abrir seleção de boss
local selectBossBtn = CreateButton(mc, "[ Selecione um Boss ]", y, function()
    CriarMenuBoss()
end)
y = y + 45

-- Label para mostrar boss selecionado
local selectedBossLabel = Instance.new("TextLabel")
selectedBossLabel.Text = "Nenhum boss selecionado"
selectedBossLabel.Size = UDim2.new(0, 200, 0, 20)
selectedBossLabel.Position = UDim2.new(0, 10, 0, y)
selectedBossLabel.BackgroundTransparency = 1
selectedBossLabel.TextColor3 = colors.textDim
selectedBossLabel.Font = Enum.Font.Gotham
selectedBossLabel.TextSize = 10
selectedBossLabel.TextXAlignment = Enum.TextXAlignment.Left
selectedBossLabel.Parent = mc
y = y + 25

-- ============ SEÇÃO BOSS ============
CreateLabel(mc, "⚔️ BOSS", y); y = y + 24
CreateDivider(mc, y); y = y + 10

CreateButton(mc, "🔥 Auto Kill Boss (Selecionado)", y, function()
    print("[Boss] Auto Kill no boss selecionado")
end)
y = y + 42

CreateButton(mc, "💀 Auto Kill All Boss (Spawnados)", y, function()
    print("[Boss] Auto Kill todos os bosses")
end)
y = y + 42

-- ============ SEÇÃO AUTO CHEST ============
CreateLabel(mc, "📦 AUTO CHEST", y); y = y + 24
CreateDivider(mc, y); y = y + 10

CreateToggle(mc, "Auto Chest (Normal)", y, function(s)
    print("[Chest] Auto Chest:", s)
end)
y = y + 42

CreateToggle(mc, "Auto Chest (Risk - TP Instantâneo)", y, function(s)
    print("[Chest] Auto Chest Risk:", s)
end)
y = y + 42

-- ============ SEÇÃO ITENS ESPECIAIS ============
CreateLabel(mc, "🏆 ITENS ESPECIAIS", y); y = y + 24
CreateDivider(mc, y); y = y + 10

CreateToggle(mc, "Ignorar Cálice de Deus (Rip Indra)", y, function(s)
    print("[Itens] Ignorar Cálice:", s)
end)
y = y + 42

CreateToggle(mc, "Ignorar Coração de Leviatã (Barba Negra)", y, function(s)
    print("[Itens] Ignorar Coração:", s)
end)
y = y + 42

-- ============ SEÇÃO SELECT ITEM MASTERY ============
CreateLabel(mc, "📈 SELECT ITEM MASTERY", y); y = y + 24
CreateDivider(mc, y); y = y + 10

local selectMasteryBtn = CreateButton(mc, "[ Selecione para Farmar Maestria ]", y, function()
    CriarMenuMastery()
end)
y = y + 45

local selectedMasteryLabel = Instance.new("TextLabel")
selectedMasteryLabel.Text = "Nenhum item selecionado"
selectedMasteryLabel.Size = UDim2.new(0, 200, 0, 20)
selectedMasteryLabel.Position = UDim2.new(0, 10, 0, y)
selectedMasteryLabel.BackgroundTransparency = 1
selectedMasteryLabel.TextColor3 = colors.textDim
selectedMasteryLabel.Font = Enum.Font.Gotham
selectedMasteryLabel.TextSize = 10
selectedMasteryLabel.TextXAlignment = Enum.TextXAlignment.Left
selectedMasteryLabel.Parent = mc
y = y + 25

CreateToggle(mc, "Farm Mastery até 600", y, function(s)
    print("[Mastery] Farm até 600:", s)
end)
y = y + 42

-- ============ SEÇÃO SELECT SKILL ============
CreateLabel(mc, "⚡ SELECT SKILL (Mastery)", y); y = y + 24
CreateDivider(mc, y); y = y + 10

local selectSkillBtn = CreateButton(mc, "[ Selecione uma Skill ]", y, function()
    CriarMenuSkill()
end)
y = y + 45

local selectedSkillLabel = Instance.new("TextLabel")
selectedSkillLabel.Text = "Nenhuma skill selecionada"
selectedSkillLabel.Size = UDim2.new(0, 200, 0, 20)
selectedSkillLabel.Position = UDim2.new(0, 10, 0, y)
selectedSkillLabel.BackgroundTransparency = 1
selectedSkillLabel.TextColor3 = colors.textDim
selectedSkillLabel.Font = Enum.Font.Gotham
selectedSkillLabel.TextSize = 10
selectedSkillLabel.TextXAlignment = Enum.TextXAlignment.Left
selectedSkillLabel.Parent = mc

-- ============ FUNÇÕES DOS MENUS ============

-- Menu SELECT ITEM (Melee, Sword, Gun, Fruit)
function CriarMenuItem()
    local menu = Instance.new("Frame")
    menu.Size = UDim2.new(0, 250, 0, 200)
    menu.Position = UDim2.new(0.5, -125, 0.5, -100)
    menu.BackgroundColor3 = colors.bgSec
    menu.BorderSizePixel = 1
    menu.BorderColor3 = colors.accent
    menu.Parent = screenGui
    
    local menuCorner = Instance.new("UICorner")
    menuCorner.CornerRadius = UDim.new(0, 10)
    menuCorner.Parent = menu
    
    local title = Instance.new("TextLabel")
    title.Text = "Selecione o Item"
    title.Size = UDim2.new(1, 0, 0, 35)
    title.BackgroundColor3 = colors.accentDark
    title.TextColor3 = colors.text
    title.Font = Enum.Font.GothamBold
    title.TextSize = 14
    title.Parent = menu
    
    local titleCorner = Instance.new("UICorner")
    titleCorner.CornerRadius = UDim.new(0, 10)
    titleCorner.Parent = title
    
    local opcoes = {"Melee", "Sword", "Gun", "Fruit"}
    local yBtn = 45
    
    for _, op in ipairs(opcoes) do
        local btn = Instance.new("TextButton")
        btn.Text = op
        btn.Size = UDim2.new(0, 200, 0, 35)
        btn.Position = UDim2.new(0.5, -100, 0, yBtn)
        btn.BackgroundColor3 = colors.bg
        btn.TextColor3 = colors.text
        btn.Font = Enum.Font.GothamBold
        btn.TextSize = 12
        btn.BorderSizePixel = 1
        btn.BorderColor3 = colors.accent
        btn.Parent = menu
        
        local btnCorner = Instance.new("UICorner")
        btnCorner.CornerRadius = UDim.new(0, 6)
        btnCorner.Parent = btn
        
        btn.MouseButton1Click:Connect(function()
            selectedItemLabel.Text = "Item selecionado: " .. op
            menu:Destroy()
            print("[Item] Selecionado:", op)
        end)
        yBtn = yBtn + 45
    end
    
    local closeBtn = Instance.new("TextButton")
    closeBtn.Text = "X"
    closeBtn.Size = UDim2.new(0, 30, 0, 30)
    closeBtn.Position = UDim2.new(1, -35, 0, 5)
    closeBtn.BackgroundColor3 = colors.accentDark
    closeBtn.TextColor3 = colors.text
    closeBtn.Font = Enum.Font.GothamBold
    closeBtn.TextSize = 14
    closeBtn.BorderSizePixel = 0
    closeBtn.Parent = menu
    
    local closeCorner = Instance.new("UICorner")
    closeCorner.CornerRadius = UDim.new(0, 6)
    closeCorner.Parent = closeBtn
    
    closeBtn.MouseButton1Click:Connect(function()
        menu:Destroy()
    end)
end

-- Menu SELECT BOSS (detecta quais estão spawnados)
function CriarMenuBoss()
    local menu = Instance.new("Frame")
    menu.Size = UDim2.new(0, 280, 0, 350)
    menu.Position = UDim2.new(0.5, -140, 0.5, -175)
    menu.BackgroundColor3 = colors.bgSec
    menu.BorderSizePixel = 1
    menu.BorderColor3 = colors.accent
    menu.Parent = screenGui
    
    local menuCorner = Instance.new("UICorner")
    menuCorner.CornerRadius = UDim.new(0, 10)
    menuCorner.Parent = menu
    
    local title = Instance.new("TextLabel")
    title.Text = "Selecione o Boss (Spawnados)"
    title.Size = UDim2.new(1, 0, 0, 35)
    title.BackgroundColor3 = colors.accentDark
    title.TextColor3 = colors.text
    title.Font = Enum.Font.GothamBold
    title.TextSize = 13
    title.Parent = menu
    
    local titleCorner = Instance.new("UICorner")
    titleCorner.CornerRadius = UDim.new(0, 10)
    titleCorner.Parent = title
    
    -- Scroll para os bosses
    local scroll = Instance.new("ScrollingFrame")
    scroll.Size = UDim2.new(1, -10, 1, -45)
    scroll.Position = UDim2.new(0, 5, 0, 40)
    scroll.BackgroundTransparency = 1
    scroll.CanvasSize = UDim2.new(0, 0, 0, 400)
    scroll.ScrollBarThickness = 4
    scroll.ScrollBarImageColor3 = colors.accent
    scroll.Parent = menu
    
    -- Lista de possíveis bosses
    local allBosses = {"Dough King", "Rip Indra", "Barba Negra", "Leviathan", "Cake Queen", "Darkbeard", "Greybeard", "Thunder God"}
    local yBtn = 5
    
    for _, boss in ipairs(allBosses) do
        local btn = Instance.new("TextButton")
        btn.Text = "🔍 " .. boss .. " (Verificando...)"
        btn.Size = UDim2.new(0, 250, 0, 35)
        btn.Position = UDim2.new(0, 10, 0, yBtn)
        btn.BackgroundColor3 = colors.bg
        btn.TextColor3 = colors.textDim
        btn.Font = Enum.Font.GothamBold
        btn.TextSize = 11
        btn.BorderSizePixel = 1
        btn.BorderColor3 = colors.accentDark
        btn.Parent = scroll
        
        local btnCorner = Instance.new("UICorner")
        btnCorner.CornerRadius = UDim.new(0, 6)
        btnCorner.Parent = btn
        
        -- Verificar se o boss está spawnado
        pcall(function()
            local encontrado = false
            for _, obj in pairs(Workspace:GetDescendants()) do
                if obj.Name and obj.Name:lower():find(boss:lower()) then
                    encontrado = true
                    break
                end
            end
            if encontrado then
                btn.Text = "✅ " .. boss .. " (Spawnado!)"
                btn.TextColor3 = colors.text
                btn.BorderColor3 = colors.accent
                btn.BackgroundColor3 = colors.accentDark
            else
                btn.Text = "❌ " .. boss .. " (Não spawnado)"
            end
        end)
        
        btn.MouseButton1Click:Connect(function()
            selectedBossLabel.Text = "Boss selecionado: " .. boss
            menu:Destroy()
            print("[Boss] Selecionado:", boss)
        end)
        yBtn = yBtn + 42
    end
    
    scroll.CanvasSize = UDim2.new(0, 0, 0, yBtn + 10)
    
    local closeBtn = Instance.new("TextButton")
    closeBtn.Text = "X"
    closeBtn.Size = UDim2.new(0, 30, 0, 30)
    closeBtn.Position = UDim2.new(1, -35, 0, 5)
    closeBtn.BackgroundColor3 = colors.accentDark
    closeBtn.TextColor3 = colors.text
    closeBtn.Font = Enum.Font.GothamBold
    closeBtn.TextSize = 14
    closeBtn.BorderSizePixel = 0
    closeBtn.Parent = menu
    
    local closeCorner = Instance.new("UICorner")
    closeCorner.CornerRadius = UDim.new(0, 6)
    closeCorner.Parent = closeBtn
    
    closeBtn.MouseButton1Click:Connect(function()
        menu:Destroy()
    end)
end

-- Menu SELECT ITEM MASTERY (Gun, Fruit)
function CriarMenuMastery()
    local menu = Instance.new("Frame")
    menu.Size = UDim2.new(0, 250, 0, 200)
    menu.Position = UDim2.new(0.5, -125, 0.5, -100)
    menu.BackgroundColor3 = colors.bgSec
    menu.BorderSizePixel = 1
    menu.BorderColor3 = colors.accent
    menu.Parent = screenGui
    
    local menuCorner = Instance.new("UICorner")
    menuCorner.CornerRadius = UDim.new(0, 10)
    menuCorner.Parent = menu
    
    local title = Instance.new("TextLabel")
    title.Text = "Selecione para Farmar Maestria"
    title.Size = UDim2.new(1, 0, 0, 35)
    title.BackgroundColor3 = colors.accentDark
    title.TextColor3 = colors.text
    title.Font = Enum.Font.GothamBold
    title.TextSize = 13
    title.Parent = menu
    
    local titleCorner = Instance.new("UICorner")
    titleCorner.CornerRadius = UDim.new(0, 10)
    titleCorner.Parent = title
    
    local opcoes = {"Gun", "Fruit"}
    local yBtn = 45
    
    for _, op in ipairs(opcoes) do
        local btn = Instance.new("TextButton")
        btn.Text = op
        btn.Size = UDim2.new(0, 200, 0, 35)
        btn.Position = UDim2.new(0.5, -100, 0, yBtn)
        btn.BackgroundColor3 = colors.bg
        btn.TextColor3 = colors.text
        btn.Font = Enum.Font.GothamBold
        btn.TextSize = 12
        btn.BorderSizePixel = 1
        btn.BorderColor3 = colors.accent
        btn.Parent = menu
        
        local btnCorner = Instance.new("UICorner")
        btnCorner.CornerRadius = UDim.new(0, 6)
        btnCorner.Parent = btn
        
        btn.MouseButton1Click:Connect(function()
            selectedMasteryLabel.Text = "Maestria: " .. op
            menu:Destroy()
            print("[Mastery] Item selecionado:", op)
        end)
        yBtn = yBtn + 45
    end
    
    local closeBtn = Instance.new("TextButton")
    closeBtn.Text = "X"
    closeBtn.Size = UDim2.new(0, 30, 0, 30)
    closeBtn.Position = UDim2.new(1, -35, 0, 5)
    closeBtn.BackgroundColor3 = colors.accentDark
    closeBtn.TextColor3 = colors.text
    closeBtn.Font = Enum.Font.GothamBold
    closeBtn.TextSize = 14
    closeBtn.BorderSizePixel = 0
    closeBtn.Parent = menu
    
    local closeCorner = Instance.new("UICorner")
    closeCorner.CornerRadius = UDim.new(0, 6)
    closeCorner.Parent = closeBtn
    
    closeBtn.MouseButton1Click:Connect(function()
        menu:Destroy()
    end)
end

-- Menu SELECT SKILL
function CriarMenuSkill()
    local menu = Instance.new("Frame")
    menu.Size = UDim2.new(0, 260, 0, 300)
    menu.Position = UDim2.new(0.5, -130, 0.5, -150)
    menu.BackgroundColor3 = colors.bgSec
    menu.BorderSizePixel = 1
    menu.BorderColor3 = colors.accent
    menu.Parent = screenGui
    
    local menuCorner = Instance.new("UICorner")
    menuCorner.CornerRadius = UDim.new(0, 10)
    menuCorner.Parent = menu
    
    local title = Instance.new("TextLabel")
    title.Text = "Selecione a Skill (Farm Mastery)"
    title.Size = UDim2.new(1, 0, 0, 35)
    title.BackgroundColor3 = colors.accentDark
    title.TextColor3 = colors.text
    title.Font = Enum.Font.GothamBold
    title.TextSize = 13
    title.Parent = menu
    
    local titleCorner = Instance.new("UICorner")
    titleCorner.CornerRadius = UDim.new(0, 10)
    titleCorner.Parent = title
    
    local scroll = Instance.new("ScrollingFrame")
    scroll.Size = UDim2.new(1, -10, 1, -45)
    scroll.Position = UDim2.new(0, 5, 0, 40)
    scroll.BackgroundTransparency = 1
    scroll.CanvasSize = UDim2.new(0, 0, 0, 400)
    scroll.ScrollBarThickness = 4
    scroll.ScrollBarImageColor3 = colors.accent
    scroll.Parent = menu
    
    local skills = {"Z (Primeira Skill)", "X (Segunda Skill)", "C (Terceira Skill)", "V (Quarta Skill)", "F (Quinta Skill)"}
    local yBtn = 5
    
    for _, skill in ipairs(skills) do
        local btn = Instance.new("TextButton")
        btn.Text = skill
        btn.Size = UDim2.new(0, 230, 0, 35)
        btn.Position = UDim2.new(0, 10, 0, yBtn)
        btn.BackgroundColor3 = colors.bg
        btn.TextColor3 = colors.text
        btn.Font = Enum.Font.GothamBold
        btn.TextSize = 11
        btn.BorderSizePixel = 1
        btn.BorderColor3 = colors.accent
        btn.Parent = scroll
        
        local btnCorner = Instance.new("UICorner")
        btnCorner.CornerRadius = UDim.new(0, 6)
        btnCorner.Parent = btn
        
        btn.MouseButton1Click:Connect(function()
            selectedSkillLabel.Text = "Skill: " .. skill
            menu:Destroy()
            print("[Skill] Selecionada:", skill)
        end)
        yBtn = yBtn + 42
    end
    
    scroll.CanvasSize = UDim2.new(0, 0, 0, yBtn + 10)
    
    local closeBtn = Instance.new("TextButton")
    closeBtn.Text = "X"
    closeBtn.Size = UDim2.new(0, 30, 0, 30)
    closeBtn.Position = UDim2.new(1, -35, 0, 5)
    closeBtn.BackgroundColor3 = colors.accentDark
    closeBtn.TextColor3 = colors.text
    closeBtn.Font = Enum.Font.GothamBold
    closeBtn.TextSize = 14
    closeBtn.BorderSizePixel = 0
    closeBtn.Parent = menu
    
    local closeCorner = Instance.new("UICorner")
    closeCorner.CornerRadius = UDim.new(0, 6)
    closeCorner.Parent = closeBtn
    
    closeBtn.MouseButton1Click:Connect(function()
        menu:Destroy()
    end)
end

-- Atualizar CanvasSize
mc.CanvasSize = UDim2.new(0, 0, 0, y + 80)
