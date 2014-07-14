##########################
### Creating/editing a cron job

# step1
crontab -e

# step2
# 1: Minutes (0-59)
# 2: Hours (0-23)
# 3: Day (0-31)
# 4: Month (0-12) // 12 == December
# 5: Day of the Week (0-7) // 0 or 7 == Sunday
1 2 3 4 5 /path/to/command arg1 arg2 argN

# The asterisk (*)
# This operator specifies all possible values for a field.
# For example, an asterisk in the hour time field would be equivalent
# to every hour or an asterisk in the month field would be equivalent to every month.

# The comma (,)
# This operator specifies a list of values,
# for example: "1,5,10,15,20, 25".

# The dash (-)
# This operator specifies a range of values,
# for example: "5-15" days , which is equivalent
# to typing "5,6,7,8,9,....,13,14,15" using the comma operator.

## Disable email output
1 2 3 4 5 /path/to/command >/dev/null 2>&1

## Set email address
MAILTO="sample@sample.com"
1 2 3 4 5 /path/to/command >/dev/null 2>&1

## Delete crontab jobs
crontab -r -u username

## Shortcuts
# @reboot	Run once, at startup.
# @yearly	Run once a year, "0 0 1 1 *".
# @annually     (same as @yearly)
# @monthly      Run once a month, "0 0 1 * *".
# @weekly	Run once a week, "0 0 * * 0".
# @daily	Run once a day, "0 0 * * *".
# @midnight     (same as @daily)
# @hourly	Run once an hour, "0 * * * *".
@hourly /path/to/command
@daily /path/to/command

##########################
### Editing other user's crontab

crontab -u [username] -e

##########################
### Viewing crontab entries

# View entries of current user
crontab -l

# View entries of a specific user
crontab -u [username] -l
