local StarterGui = game:GetService("StarterGui")

local function showMessage(text)
	StarterGui:SetCore("SendNotification", {
		Title = "Poder de Invisibilidad";
		Text = text;
		Duration = 2;
	})
end

UserInputService.InputBegan:Connect(function(input, gameProcessed)
	if gameProcessed then return end
	if input.KeyCode == Enum.KeyCode.V then
		invisible = not invisible
		ToggleEvent:FireServer(invisible)
		if invisible then
			showMessage("¡Invisibilidad ACTIVADA!")
		else
			showMessage("Invisibilidad DESACTIVADA")
		end
	end
end)
