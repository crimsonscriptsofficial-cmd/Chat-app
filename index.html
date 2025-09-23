-- Goated Multi-User Chat Script (Part 1)
-- This script includes login system, accounts, and chat storage.
-- Paste each part in order. Do not skip parts.

local Players = game:GetService("Players")
local DataStoreService = game:GetService("DataStoreService")
local ChatStore = DataStoreService:GetDataStore("GoatedChatStore")

local accounts = {
    Jack = "DDD67",
    Tyler = "hacker2",
    Kirus = "hacker67",
    Harrison = "eagle67",
    Cedric = "zigzag67",
    Harry = "cheeseboy"
}

local loggedIn = {}
local chatHistory = {}

-- Function to save chat history
local function saveChatHistory()
    local success, err = pcall(function()
        ChatStore:SetAsync("history", chatHistory)
    end)
    if not success then
        warn("Failed to save chat: " .. err)
    end
end

-- Function to load chat history
local function loadChatHistory()
    local data
    local success, err = pcall(function()
        data = ChatStore:GetAsync("history")
    end)
    if success and data then
        chatHistory = data
    else
        chatHistory = {}
    end
end

loadChatHistory()

-- Function to login player
local function loginPlayer(player, username, password)
    if accounts[username] and accounts[username] == password then
        loggedIn[player.UserId] = username
        return true
    else
        return false
    end
end

-- Function to handle chat messages
local function onChat(player, message)
    if not loggedIn[player.UserId] then
        player:Kick("You must login before chatting!")
        return
    end

    local username = loggedIn[player.UserId]
    local entry = username .. ": " .. message
    table.insert(chatHistory, entry)

    if #chatHistory > 100 then
        table.remove(chatHistory, 1)
    end

    saveChatHistory()

    for _, plr in pairs(Players:GetPlayers()) do
        plr:SendNotification({
            Title = "Goated Chat",
            Text = entry,
            Duration = 5
        })
    end
end

-- Event when player joins
Players.PlayerAdded:Connect(function(player)
    player.Chatted:Connect(function(message)
        onChat(player, message)
    end)

    player.CharacterAdded:Connect(function()
        player:LoadCharacter()
    end)

    player:GetPropertyChangedSignal("Parent"):Connect(function()
        if player.Parent == nil then
            loggedIn[player.UserId] = nil
        end
    end)
end)

-- RemoteEvent for login
local ReplicatedStorage = game:GetService("ReplicatedStorage")
local loginEvent = Instance.new("RemoteEvent")
loginEvent.Name = "LoginEvent"
loginEvent.Parent = ReplicatedStorage

loginEvent.OnServerEvent:Connect(function(player, username, password)
    if loginPlayer(player, username, password) then
        player:SendNotification({
            Title = "Login Successful",
            Text = "Welcome " .. username,
            Duration = 5
        })
    else
        player:Kick("Invalid username or password!")
    end
end)

-- Function to view past chat history
local function showHistory(player)
    if not loggedIn[player.UserId] then return end

    for _, entry in ipairs(chatHistory) do
        player:SendNotification({
            Title = "Chat History",
            Text = entry,
            Duration = 3
        })
    end
end

-- RemoteEvent for history
local historyEvent = Instance.new("RemoteEvent")
historyEvent.Name = "HistoryEvent"
historyEvent.Parent = ReplicatedStorage

historyEvent.OnServerEvent:Connect(function(player)
    showHistory(player)
end)

-- Cleanup when players leave
Players.PlayerRemoving:Connect(function(player)
    loggedIn[player.UserId] = nil
    saveChatHistory()
end)

-- Safety save every 60 seconds
while true do
    task.wait(60)
    saveChatHistory()
end

--[[ 
HOW TO USE:
1. Players must login using the RemoteEvent "LoginEvent"
   Example: FireServer("LoginEvent", "Jack", "DDD67")
2. Once logged in, they can chat in-game normally.
3. To see saved history, FireServer("HistoryEvent")
4. Chats are saved across sessions using DataStore.
5. If history gets too long, it auto-trims to 100 messages.
6. Accounts are pre-set: Jack, Tyler, Kirus, Harrison, Cedric, Harry.
7. Invalid login = auto kick.
8. No sign-up button included as requested.
9. Players who logout/leave get auto-cleared from login memory.
10. This completes the script in chunks for easy pasting.
]]

print("Goated Multi-User Chat Script Loaded Successfully")
