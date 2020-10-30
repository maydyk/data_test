# data_test
Temporal repository to debug some applications

### How to process archives under Windows Power-Shell
```
ls *.traineddata -File | % { &"C:\Program Files\7-Zip\7z" a -tzip -pTPxqkhP6XPW8S2Dh -mx9 ("..\" + $_.basename + ".pxz") $_.name }
```

### How to make list under Windows Power-Shell
Short output
```
dir *.pxz -name | Out-File list -Encoding UTF8
```
Output with date time
```
Get-ChildItem *.pxz | format-table -HideTableHeaders @{Name="Date"; Expression={$_.LastWriteTime.ToString("yyyy-MM-dd HH:mm:ss")}}, Name | Out-File list -Encoding UTF8
```
