--

local CorrectKey = "SNA" -- Change this to your desired key
local AdLink = "Coming" -- Replace with your Reshort link

-- UI for key input
local ScreenGui = Instance.new("ScreenGui")
ScreenGui.Parent = game.Players.LocalPlayer:WaitForChild("PlayerGui")

local TextBox = Instance.new("TextBox")
TextBox.Size = UDim2.new(0, 200, 0, 50)
TextBox.Position = UDim2.new(0.5, -100, 0.3, 0)
TextBox.PlaceholderText = "Enter Key"
TextBox.Parent = ScreenGui

local VerifyButton = Instance.new("TextButton")
VerifyButton.Size = UDim2.new(0, 200, 0, 50)
VerifyButton.Position = UDim2.new(0.5, -100, 0.4, 0)
VerifyButton.Text = "Verify Key"
VerifyButton.Parent = ScreenGui

local CopyButton = Instance.new("TextButton")
CopyButton.Size = UDim2.new(0, 200, 0, 50)
CopyButton.Position = UDim2.new(0.5, -100, 0.5, 0)
CopyButton.Text = "Get Key (Copy Link)"
CopyButton.Parent = ScreenGui

-- Function to check key
VerifyButton.MouseButton1Click:Connect(function()
    local userKey = TextBox.Text
    if userKey == CorrectKey then
        ScreenGui:Destroy()
        print("Access Granted!") 
        
        
        loadstring(game:HttpGet("https://raw.githubusercontent.com/SNAFUL/SNAFUL/refs/heads/main/MAIN"))() 

    else
        TextBox.Text = "Invalid Key"
    end
end)


CopyButton.MouseButton1Click:Connect(function()
    setclipboard(AdLink) -- Copies the link to the user's clipboard
    CopyButton.Text = "Link Copied!"
    task.wait(1.5)
    CopyButton.Text = "Get Key"
end)
