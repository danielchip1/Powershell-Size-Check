# Powershell-Size-Check
$dirsize=10
$dirfull="C:\Temp"

$out=(Get-ChildItem $dirfull | Measure-Object -Property Length -Sum).sum /1024 /1024 

if( [int]$out -lt $dirsize )
{
echo "the dir smaller than $dirsize"
exit 0
}
else
{
echo "the dir larger than $dirsize"
exit 2
}
