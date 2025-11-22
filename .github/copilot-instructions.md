Visual Studio Code terminal is set to use `aiterm` which automatically wraps commands in `aicmd`. Just use regular terminal commands - `aiterm` handles the wrapping. After each command you must read both `output_file` and `log_file` files to get results and exit code. Do not use `cat`, nor `tail`, not `head`, nor any other terminal command to read these files. Run  `aiterm_set_next_aicmd_timeout 5m` as separate command to increase timeout for next command if needed. Default timeout is 5 seconds. Use `cd to-my/dir && my-command` to run your command in the expected directory.

If any command returns no output (`output_file` is empty) then AI must check also `log_file` file for errors, warnings and exit code. Checking `log_file` is good practice for any doubtful cases.

Do not use `npm run watch`. Set `aiterm_set_next_aicmd_timeout 5m`, run build and check output and log files produced.
