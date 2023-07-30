-- Configurações
local loadingTime = 5 -- Tempo de carregamento simulado em segundos
local backgroundColor = Color3.new(0, 0, 0) -- Cor de fundo preto

-- Função para criar a tela de carregamento
local function createLoadingScreen()
    local RLoading = Instance.new("ScreenGui")
    RLoading.Name = "RLoading"
    RLoading.Parent = game.CoreGui
    RLoading.ZIndexBehavior = Enum.ZIndexBehavior.Sibling

    local blackFrame = Instance.new("Frame")
    blackFrame.Name = "BlackFrame"
    blackFrame.Parent = RLoading
    blackFrame.BackgroundColor3 = backgroundColor
    blackFrame.BorderSizePixel = 0
    blackFrame.Position = UDim2.new(0, 0, 0, 0)
    blackFrame.Size = UDim2.new(1, 0, 1, 0)

    return RLoading
end

-- Função para remover a tela de carregamento
local function removeLoadingScreen(loadingGui)
    if loadingGui then
        loadingGui:Destroy()
    end
end

-- Cria a tela de carregamento
local loadingGui = createLoadingScreen()

-- Espera um tempo simulado e depois remove a tela de carregamento
wait(loadingTime)
removeLoadingScreen(loadingGui)
