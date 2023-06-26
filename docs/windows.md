# Windows
## Registry Edits
### Enable/disable Bing search on Start Menu

=== "Disable"

    ```registry
    Windows Registry Editor Version 5.00

    [HKEY_CURRENT_USER\Software\Policies\Microsoft\Windows\Explorer]
    "DisableSearchBoxSuggestions"=dword:00000000
    ```

=== "Enable"

    ```registry
    Windows Registry Editor Version 5.00

    [HKEY_CURRENT_USER\Software\Policies\Microsoft\Windows\Explorer]
    "DisableSearchBoxSuggestions"=dword:00000001
    ```

## Powershell shortcut to activate venv (Python)

Create an alias called `activenv` that runs the activate script relative to the current location:

```powershell
New-Alias -Name activenv -Value venv/scripts/activate.ps1
```

Export the alias to a script.

```powershell
Export-Alias -Name activenv -Path "activenv.ps1" -As Script
```

Add script to startup:

```powershell
Add-Content -Path $Profile -Value (Get-Content activenv.ps1)
```