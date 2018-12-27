# Powershell
$groups = Get-Content C:\Users\Administrator\Desktop\groups.csv  
            
foreach($Group in $Groups) {            
            
Get-ADGroupMember -Id $Group | select  @{Expression={$Group};Label="Group Name"},* | Export-CSV c:\temp\GroupsInfo.CSV -NoTypeInformation -append
            
}
