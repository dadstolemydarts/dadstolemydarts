    getgenv().AutoAscending = true;

    task.spawn(function()
        while getgenv().AutoAscending == true do
            pcall(function()
                if game:GetService("Players").LocalPlayer:WaitForChild("Data"):WaitForChild("Ability"):GetAttribute("AbilityLevel") == 200 then
                    local args = {[1] = game:GetService("Players").LocalPlayer:WaitForChild("Data"):WaitForChild("Ability").Value};
                    game:GetService("ReplicatedStorage"):WaitForChild("ReplicatedModules"):WaitForChild("KnitPackage"):WaitForChild("Knit"):WaitForChild("Services"):WaitForChild("LevelService"):WaitForChild("RF"):WaitForChild("AscendAbility"):InvokeServer(unpack(args));
                end
            end)
            task.wait(0.35);
        end
    end)
