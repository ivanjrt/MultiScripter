# MultiScripter
This will run variouos scripts in Sync Mode

```` Ruby
$scriptsLocation = 'c:\Temp'

Workflow Invoke-PilotMultiScripts{
    $ScriptFiles = Get-ChildItem $scriptsLocation -Filter '*.ps1'
    ForEach -Parallel ($ScriptFile in $ScriptFiles){
      Start-Transcript -Path $scriptsLocation 
      Start-Process Powershell.exe -Argumentlist "-File $($ScriptFile.Fullname)"
    }   stop-transcript
}
Invoke-PilotMultiScripts
```` 

#the Start-Transcript is just there to give an idea of how long all this scripts deployment will take
