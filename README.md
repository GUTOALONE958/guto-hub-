se game.PlaceId == 2753915549 ou game.PlaceId == 4442272183 ou game.PlaceId == 7449423635 então
    game.StarterGui:SetCore("EnviarNotificação", {
      Ícone = "rbxassetid://9152775759";
          Título = "guto",
      Texto = "Bem-vindo, guto!"
  })
  
  esperar(1)
  
  game.StarterGui:SetCore("EnviarNotificação", {
      Ícone = "rbxassetid://9152775759";
      Título = "guto ",
      Texto = "Carregando Iu..."
  })
  
  esperar(10)
  
   
      jogo:GetService("Jogadores").LocalPlayer.Idled:connect(function()
          jogo:GetService("VirtualUser"):Button2Down(Vector2.new(0,0),workspace.CurrentCamera.CFrame)
          esperar(1)
          jogo:GetService("VirtualUser"):Button2Up(Vector2.new(0,0),workspace.CurrentCamera.CFrame)
      fim)
  
      _G.Color = Cor3.deRGB(255,0,0)
      se não for game:IsLoaded() então repita game.Loaded:Wait() até game:IsLoaded() terminar
      
      repita wait() até jogo:GetService("Jogadores")
      
      se não for jogo:GetService("Players").LocalPlayer.Character:FindFirstChild("HumanoidRootPart") então repita wait() até que jogo:GetService("Players").LocalPlayer.Character:FindFirstChild("HumanoidRootPart") termine
          
      esperar(1)
      
      fazer
          interface de usuário local = jogo.CoreGui:FindFirstChild("PROXOGUI")
          se ui então
              ui:Destruir()
          fim
      fim
      
      Serviço de Entrada de Usuário local = jogo:GetService("Serviço de Entrada de Usuário")
      TweenService local = jogo:GetService("TweenService")
      
      função local MakeDraggable(objetotopbar, objeto)
          Arrasto local = nulo
          DragInput local = nulo
          DragStart local = nulo
          PosiçãoInicial local = nulo
      
          função local Update(entrada)
              Delta local = entrada.Posição - DragStart
              posição local =
                  UDim2.novo(
                      PosiçãoInicial.X.Escala,
                      StartPosition.X.Offset + Delta.X,
                      PosiçãoInicial.EscalaY,
                      PosiçãoInicial.Y.Offset + Delta.Y
                  )
              Tween local = TweenService:Create(objeto, TweenInfo.new(0.2), {Posição = pos})
              Tween:Reproduzir()
          fim
      
          topbarobject.InputBegan:Conectar(
              função(entrada)
                  se input.UserInputType == Enum.UserInputType.MouseButton1 ou input.UserInputType == Enum.UserInputType.Touch então
                      Arrastando = verdadeiro
                      DragStart = entrada.Posição
                      PosiçãoInicial = objeto.Posição
      
                      entrada.Alterado:Conectar(
                          função()
                              se input.UserInputState == Enum.UserInputState.End então
                                  Arrastando = falso
                              fim
                          fim
                      )
                  fim
              fim
          )
      
          topbarobject.InputChanged:Conectar(
              função(entrada)
                  se
                      input.UserInputType == Enum.UserInputType.MouseMovement ou
                      entrada.UserInputType == Enum.UserInputType.Toque
                  então
                      DragInput = entrada
                  fim
              fim
          )
      
          UserInputService.InputChanged:Conectar(
              função(entrada)
                  se entrada == ArrastarEntrada e Arrastar então
                      Atualização(entrada)
                  fim
              fim
          )
      fim
      
      biblioteca local = {}
      
      biblioteca de funções:AddWindow(texto,keybind)
          vinculação local = keybind ou Enum.KeyCode.RightControl
          ff local = falso
          tabulação atual local = ""
      
          DoctorShiba local = Instância.new("ScreenGui")
          DoctorShiba.Name = "PROXOGUI"
          DoctorShiba.Parent = jogo.CoreGui
          DoctorShiba.ZIndexBehavior = Enum.ZIndexBehavior.Irmão
      
          local Principal = Instância.new("Quadro")
          Main.Name = "Principal"
          Principal.Parente = DoutorShiba
          Main.AnchorPoint = Vetor2.novo(0,5, 0,5)
          Main.BackgroundColor3 = Cor3.fromRGB(30, 28, 39)
          Main.BackgroundTransparency = 0,100
          Principal.BorderSizePixel = 0
          Main.ClipsDescendants = verdadeiro
          Posição principal = UDim2.novo(0,499526083, 0, 0,499241292, 0)
          Main.Size = UDim2.new(0, 600, 0, 350)
      
          local Topo = Instância.novo("Quadro")
          Top.Nome = "Topo"
          Top.Parent = Principal
          Topo.BackgroundColor3 = Cor3.fromRGB(255, 255, 255)
          Transparência de fundo superior = 1.000
          Topo.BorderSizePixel = 0
          Top.Size = UDim2.new(0, 600, 0, 20)
      
          Página local = Instance.new("Quadro")
          Page.Name = "Página"
          Page.Parent = Principal
          Page.BackgroundColor3 = Cor3.fromRGB(25, 23, 35)
          Page.BackgroundTransparency = 0,100
          Page.BorderSizePixel = 0
          Page.Size = UDim2.new(0, 125, 0, 350)
      
          NameHub local = Instância.new("TextLabel")
          NameHub.Nome = "NameHub"
          NameHub.Parent = Página
          NameHub.BackgroundColor3 = Cor3.fromRGB(255, 255, 255)
          NameHub.BackgroundTransparency = 1.000
          NameHub.Position = UDim2.new(0,113333493, 0, 0, 0)
          NameHub.Size = UDim2.new(0, 110, 0, 20)
          NameHub.Font = Enum.Font.GothamSemibold
          NameHub.Text = texto
          NameHub.TextColor3 = Color3.fromRGB(225, 0, 0)
          NameHub.TextSize = 11.000
          NameHub.TextXAligment = Enum.TextXAligment.Left
      
          Usuário local = Instance.new("Frame")
          User.Name = "Usuário"
          Usuário.Pai = Página
          Usuário.BackgroundColor3 = Cor3.fromRGB(255, 255, 255)
          User.BackgroundTransparency = 1.000
          Usuário.Posição = UDim2.new(0, 0, 0.8, 30)
          Usuário.Tamanho = UDim2.novo(0, 125, 0, 40)
      
          UserText local = Instância.new("TextLabel")
          UserText.Name = "TextoDoUsuário"
          UserText.Parent = Usuário
          UserText.BackgroundColor3 = Cor3.fromRGB(255, 255, 255)
          UserText.BackgroundTransparency = 1.000
          UserText.Position = UDim2.new(0,354999989, 0, 0, 11)
          UserText.Size = UDim2.new(0, 80, 0, 20)
          UserText.Font = Enum.Font.Gotham
          UserText.Text = tostring(jogo.Jogadores.JogadorLocal.Nome)
          spawn(função()
              enquanto espera() faz
                  pcall(função()
                      espere(0,1)
                      jogo:GetService('TweenService'):Criar(
                          Texto do Usuário,TweenInfo.new(1,Enum.EasingStyle.Linear,Enum.EasingDirection.InOut),
                          {TextColor3 = Color3.fromRGB(255, 0, 0)}
                      ):Jogar()
                      espere(.5)            
                      jogo:GetService('TweenService'):Criar(
                          Texto do Usuário,TweenInfo.new(1,Enum.EasingStyle.Linear,Enum.EasingDirection.InOut),
                          {TextColor3 = Color3.fromRGB(255, 155, 0)}
                      ):Jogar()
                      espere(.5)            
                      jogo:GetService('TweenService'):Criar(
                          Texto do Usuário,TweenInfo.new(1,Enum.EasingStyle.Linear,Enum.EasingDirection.InOut),
                          {TextColor3 = Color3.fromRGB(255, 255, 0)}
                      ):Jogar()
                      espere(.5)            
                      jogo:GetService('TweenService'):Criar(
                          Texto do Usuário,TweenInfo.new(1,Enum.EasingStyle.Linear,Enum.EasingDirection.InOut),
                          {TextColor3 = Color3.fromRGB(0, 255, 0)}
                      ):Jogar()
                      espere(.5)            
                      jogo:GetService('TweenService'):Criar(
                          Texto do Usuário,TweenInfo.new(1,Enum.EasingStyle.Linear,Enum.EasingDirection.InOut),
                          {TextColor3 = Color3.fromRGB(0, 255, 255)}
                      ):Jogar()
                      espere(.5)            
                      jogo:GetService('TweenService'):Criar(
                          Texto do Usuário,TweenInfo.new(1,Enum.EasingStyle.Linear,Enum.EasingDirection.InOut),
                          {TextColor3 = Color3.fromRGB(0, 155, 255)}
                      ):Jogar()
                      espere(.5)            
                      jogo:GetService('TweenService'):Criar(
                          Texto do Usuário,TweenInfo.new(1,Enum.EasingStyle.Linear,Enum.EasingDirection.InOut),
                          {TextColor3 = Color3.fromRGB(255, 0, 255)}
                      ):Jogar()
                      espere(.5)            
                      jogo:GetService('TweenService'):Criar(
                          Texto do Usuário,TweenInfo.new(1,Enum.EasingStyle.Linear,Enum.EasingDirection.InOut),
                          {TextColor3 = Color3.fromRGB(255, 0, 155)}
                      ):Jogar()
                      espere(.5)
                  fim)
              fim
          fim)
          UserText.TextScaled = verdadeiro
          UserText.TextSize = 11.000
          UserText.TextWrapped = verdadeiro
          UserText.TextXAligment = Enum.TextXAligment.Left
      
          UITextSizeConstraint local = Instance.new("UITextSizeConstraint")
          UITextSizeConstraint.Parent = TextoDoUsuário
          UITextSizeConstraint.MaxTextSize = 11
      
          Imagem de Usuário local = Instância.new("ImageLabel")
          UserImage.Name = "ImagemDoUsuário"
          UserImage.Parent = Usuário
          UserImage.BackgroundColor3 = Cor3.fromRGB(225, 225, 225)
          UserImage.Position = UDim2.new(0, 10, 0, 9)
          UserImage.Size = UDim2.new(0, 25, 0, 25)
          UserImage.Image = "https://www.roblox.com/headshot-thumbnail/image?userId="..game.Players.LocalPlayer.UserId.."&width=420&height=420&format=png"
      
          UserImageCorner local = Instance.new("UICorner")
          UserImageCorner.CornerRadius = UDim.new(0, 100)
          UserImageCorner.Name = "UserImageCorner"
          UserImageCorner.Parent = Imagem do Usuário
      
          Página de Rolagem local = Instância.new("Quadro de Rolagem")
          ScrollPage.Name = "Página de Rolagem"
          ScrollPage.Parent = Página
          ScrollPage.Active = verdadeiro
          ScrollPage.BackgroundColor3 = Cor3.fromRGB(255, 255, 255)
          ScrollPage.BackgroundTransparency = 1.000
          ScrollPage.BorderSizePixel = 0
          ScrollPage.Position = UDim2.new(0, 0, 0,086, 0)
          ScrollPage.Size = UDim2.new(0, 125, 0, 290)
          ScrollPage.CanvasSize = UDim2.new(0, 0, 0, 0)
          ScrollPage.ScrollBarThickness = 0
          Lista de Páginas local = Instância.new("UIListLayout")
          PageList.Name = "Lista de Páginas"
          PageList.Parent = Página de Rolagem
          PageList.SortOrder = Enum.SortOrder.LayoutOrder
          PageList.Padding = UDim.novo(0, 7)
      
          PagePadding local = Instância.new("UIPadding")
          PagePadding.Name = "Painel de Página"
          PagePadding.Parent = Página de Rolagem
          PagePadding.PaddingTop = UDim.novo(0, 5)
          PagePadding.PaddingLeft = UDim.novo(0, 28)
      
          TabFolder local = Instance.new("Pasta")
          TabFolder.Name = "PastaTab"
          TabFolder.Parent = Principal
      
          MakeDraggable(Topo,Principal)
      
          local uihide = falso
      
          UserInputService.InputBegan:Connect(função(entrada)
              se input.KeyCode == bind então
                  se uihide == falso então
                      uihide = verdadeiro
                      Principal:TweenSize(UDim2.new(0, 0, 0, 0),"In","Quad",0.2,true)
                  outro
                      uihide = falso
                      Principal:TweenSize(UDim2.new(0, 600, 0, 350),"Saída","Quad",0.2,true)
                  fim
              fim
          fim)
      
          uitab local = {}
      
          função uitab:AddTab(texto,imagem)
              Imagem local = imagem ou 6023426915
      
              Botão de página local = Instância.new("Botão de texto")
              PageButton.Name = "PáginaButton"
              PageButton.Parent = Página de Rolagem
              PageButton.BackgroundColor3 = Cor3.fromRGB(255, 255, 255)
              PageButton.BackgroundTransparency = 1.000
              PageButton.BorderSizePixel = 0
              PageButton.Position = UDim2.new(0,224000007, 0, 0,029787235, 0)
              PageButton.Size = UDim2.new(0, 97, 0, 20)
              PageButton.AutoButtonColor = falso
              PageButton.Font = Enum.Font.GothamSemibold
              PageButton.Text = texto
              PageButton.TextColor3 = Cor3.fromRGB(225, 225, 225)
              PageButton.TextSize = 11.000
              PageButton.TextXAlignment = Enum.TextXAlignment.Left
              
              PageImage local = Instance.new("ImageLabel")
              PageImage.Name = "ImagemPágina"
              PageImage.Parent = BotãoPágina
              PageImage.BackgroundColor3 = Cor3.fromRGB(255, 255, 255)
              PageImage.BackgroundTransparency = 1.000
              PageImage.Position = UDim2.new(0, -20, 0, 3)
              PageImage.Size = UDim2.new(0, 15, 0, 15)
              PageImage.Image = "rbxassetid://"..tostring(Imagem)
      
              Guia Principal local = Instância.new("Quadro")
              MainTab.Name = "Guia Principal"
              MainTab.Parent = PastaDeGuias
              MainTab.BackgroundColor3 = Cor3.fromRGB(30, 28, 39)
              MainTab.BorderSizePixel = 0
              MainTab.Position = UDim2.new(0,208333328, 0, 0, 0)
              MainTab.Size = UDim2.new(0, 475, 0, 350)
              MainTab.Visible = falso
      
              ScrollTab local = Instance.new("ScrollingFrame")
              ScrollTab.Name = "Guia de Rolagem"
              ScrollTab.Parent = Guia Principal
              ScrollTab.BackgroundColor3 = Cor3.fromRGB(255, 255, 255)
              ScrollTab.BackgroundTransparency = 1.000
              ScrollTab.BorderSizePixel = 0
              ScrollTab.Position = UDim2.new(0, 0, 0,057, 0)
              ScrollTab.Size = UDim2.new(0, 475, 0, 330)
              ScrollTab.CanvasSize = UDim2.new(0, 0, 0, 0)
              ScrollTab.ScrollBarThickness = 3
      
              TabList local = Instância.new("UIListLayout")
              TabList.Name = "TabList"
              TabList.Parent = Guia de Rolagem
              TabList.SortOrder = Enum.SortOrder.LayoutOrder
              TabList.Padding = UDim.novo(0, 5)
      
              TabPadding local = Instância.new("UIPadding")
              TabPadding.Name = "TabPadding"
              TabPadding.Parent = ScrollTab
              TabPadding.PaddingLeft = UDim.novo(0, 10)
              TabPadding.PaddingTop = UDim.novo(0, 10)
      
              PageButton.MouseButton1Click:Conectar(função()
                  currenttab = GuiaPrincipal.Nome
                  para i,v no próximo, TabFolder:GetChildren() faça
                      se v.Name == "MainTab" então
                          v.Visível = falso
                      fim
                  fim
                  MainTab.Visible = verdadeiro
      
                  para i,v no próximo, ScrollPage:GetChildren() faça
                      se v:IsA("TextButton") então
                          TweenService:Criar(
                              você,
                              TweenInfo.new(0.3,Enum.EasingStyle.Quad,Enum.EasingDirection.Out),
                              {TextColor3 = Color3.fromRGB(225, 225, 225)}
                          ):Jogar()
                      fim
                      TweenService:Criar(
                          Botão de página,
                          TweenInfo.new(0.3,Enum.EasingStyle.Quad,Enum.EasingDirection.Out),
                          {TextColor3 = Color3.fromRGB(255,0,0)}
                      ):Jogar()
                  fim
              fim)
      
              se ff == falso então
                  TweenService:Criar(
                      Botão de página,
                      TweenInfo.new(0.3,Enum.EasingStyle.Quad,Enum.EasingDirection.Out),
                      {TextColor3 = Color3.fromRGB(255,0,0)}
                  ):Jogar()
                  para i,v no próximo, TabFolder:GetChildren() faça
                      se v.Name == "MainTab" então
                          v.Visível = falso
                      fim
                      MainTab.Visible = verdadeiro
                  fim
                  ff = verdadeiro
              fim
      
              jogo:GetService("RunService").Etapa:Connect(função()
                  pcall(função()
                      ScrollPage.CanvasSize = UDim2.new(0,0,0,PageList.AbsoluteContentSize.Y + 10)
                      ScrollTab.CanvasSize = UDim2.new(0,0,0,TabList.AbsoluteContentSize.Y + 30)
                  fim)
              fim)
              
              principal local = {}
              
              função principal:AddButton(texto,retorno de chamada)
                  Botão local = Instance.new("TextButton")
      
                  Button.Name = "Botão"
                  Botão.Parent = ScrollTab
                  Botão.BackgroundColor3 = Cor3.fromRGB(15, 15, 15)
                  Botão.TransparênciaDeFundo = 0,1
                  Botão.BorderSizePixel = 0
                  Botão.Tamanho = UDim2.novo(0, 455, 0, 30)
                  Botão.AutoButtonColor = falso
                  Botão.Fonte = Enum.Fonte.Gotham
                  Botão.Texto = texto
                  Botão.TextColor3 = Cor3.fromRGB(225, 225, 225)
                  Botão.TamanhoDoTexto = 11.000
                  Button.TextWrapped = verdadeiro
                  
                  ButtonCorner local = Instance.new("UICorner")
                  ButtonCorner.Name = "CantoDoBotão"
                  ButtonCorner.CornerRadius = UDim.new(0, 5)
                  ButtonCorner.Parent = Botão
                  
                  Botão.MouseEnter:Conectar(função()
                      TweenService:Criar(
                          Botão,
                          TweenInfo.new(0.4,Enum.EasingStyle.Quad,Enum.EasingDirection.Out),
                          {TextColor3 = Color3.fromRGB(255,0,0)}
                      ):Jogar()
                  fim)
                  
                  Botão.MouseLeave:Conectar(função()
                      TweenService:Criar(
                          Botão,
                          TweenInfo.new(0.4,Enum.EasingStyle.Quad,Enum.EasingDirection.Out),
                          {TextColor3 = Color3.fromRGB(225, 225, 225)}
                      ):Jogar()
                  fim)
                  
                  Botão.BotãoDoMouse1Clique:Conectar(função()
                      ligar de volta()
                      Botão.TamanhoDoTexto = 0
                      TweenService:Criar(
                          Botão,
                          TweenInfo.new(0.4,Enum.EasingStyle.Back,Enum.EasingDirection.Out),
                          {Tamanho do texto = 11}
                      ):Jogar()
                  fim)
              fim
              
              função principal:AddToggle(texto,config,callback)
                  ToggleImage local = Instance.new("Quadro")
                  
                  Alternar local = Instance.new("TextButton")
                  Toggle.Name = "Alternar"
                  Alternar.Parente = Guia de Rolagem
                  Alternar.BackgroundColor3 = Cor3.fromRGB(15, 15, 15)
                  Alternar.TransparênciaDeFundo = 0,1
                  Alternar.BorderSizePixel = 0
                  Alternar.AutoButtonColor = falso
                  Alt
