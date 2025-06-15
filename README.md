# handy
handy stuff

to sort folder by size in windows

```cmd
cmd /v /c "set zeropad=000,000,000,000,000,&for /f "delims=" %a in ('dir /ad /b') do @set bytes=!zeropad!000&(for /f "tokens=3" %b in ('dir /s "%a" 2^>NUL ^| find "File(s)"') do @set bytes=%b)& @for /f "tokens=1* delims=," %c in ('echo !bytes!') do @(set bytes=%c&@set bytes=000!bytes!&@set bytes=!bytes:~-3!& @set bytes=!zeropad!!bytes!&if "%d" NEQ "" set bytes=!bytes!,%d) & @echo !bytes:~-23! %a" | sort /R
```

