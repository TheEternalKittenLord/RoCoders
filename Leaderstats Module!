local leaderstats = {}

local DataStore = game:GetService("DataStoreService"):GetDataStore("New")

function leaderstats.new(Player, DataTypes, Names, Values, Saves)
	if Saves == false then
		local leaderstats = Instance.new("Folder")
		leaderstats.Name = "leaderstats"
		leaderstats.Parent = Player
		
		for i,Type in pairs(DataTypes) do
			local Type = Instance.new(Type)
			Type.Name = Names[i]
			Type.Value = Values[i]
			Type.Parent = leaderstats
		end
	elseif Saves == true then
		local leaderstats = Instance.new("Folder")
		leaderstats.Name = "leaderstats"
		leaderstats.Parent = Player
		
		for i,Type in pairs(DataTypes) do
			local Type = Instance.new(Type)
			Type.Name = Names[i]
			Type.Value = Values[i]
			Type.Parent = leaderstats
			local Data
			local epic, e = pcall(function()
				Data = DataStore:GetAsync("Id-" .. Player.UserId)
			end)
			if Data then
				Type.Value = Data[i]
			else
				print("Oki Boomer")
			end	
		end
	end
end

	
function leaderstats:SetData(Player, Names)
	local data = {}
	for i,v in pairs(Names) do
		table.insert(data, #data, Player.leaderstats[v].Value)
	end	
	pcall(function()
		DataStore:SetAsync("id-" .. Player.UserId, data)
	end)	
end

function leaderstats.ChangeValue(Player, ValueName, ChangeAmount)
	Player.leaderstats[ValueName].Value += ChangeAmount
end

return leaderstats
