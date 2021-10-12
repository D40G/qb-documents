# qb-documents

qb-nuclear renamed, fixed and updated to qb-documents for QBCore by Manliketjb.

---

New!! - Changeable locations with in Config.lua

---

add to qb-core/shared.lua

```
["usb_device"]	= {["name"] = "usb_device", ["label"] = "Unknown USB", ["weight"] = 0,	["type"] = "item", ["image"] = "usb_device.png", ["unique"] = true, ["useable"] = true, ["shouldClose"] = false, ["combinable"] = nil, ["description"] = "What do you do?"},
["governfiles"] = {["name"] = "governfiles", ["label"] = "Gov Files", ["weight"] = 0, ["type"] = "item", ["image"] = "governfiles.png", ["unique"] = true, ["useable"] = false, 	["shouldClose"] = false, ["combinable"] = nil, ["description"] = "What is the worse that can happen?."},

```
---

add images to inventory/html/images (High chance the images are all ready in the qb/aj-inventory but are not used)

---
For the Old version of QBCore that uses GhmattiSQL the follow the instructions below

in the client.lua swap
```
QBCore = exports['qb-core']:GetCoreObject()
```
with
```
QBCore = nil

Citizen.CreateThread(function()
    while true do
        Citizen.Wait(10)
        if QBCore == nil then
            TriggerEvent('QBCore:GetObject', function(obj) QBCore = obj end)
            Citizen.Wait(200)
        end
    end
end)
```
and in server.lua change 
```
local QBCore = exports['qb-core']:GetCoreObject()
```
to 
```
QBCore = nil
TriggerEvent('QBCore:GetObject', function(obj) QBCore = obj end)
```
---

```
Credits to the original author for the script.

DO NOT SELL THIS SCRIPT, ITS FREE FOR QBCORE COMMUNITY 
```
