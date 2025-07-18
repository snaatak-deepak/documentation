# Cron Job Management Standard Operating Procedure (SOP)

| Author      | Created on  | Version    | Last updated by | Last edited on |
|-------------|-------------|------------|-----------------|----------------|
| Deepak Kushwaha    | 16-07-25    | version 1  | 17-07-2025        | 17-07-25       |


## Table of Contents
- [Introduction](#introduction)
- [Creating Cron Job](#creating-cron-job)
- [Editing Cron Job](#editing-cron-job)
- [Listing Cron Jobs](#listing-cron-jobs)
- [Deleting Cron Jobs](#deleting-cron-jobs)
- [Checking Cron Job Logs](#checking-cron-job-logs)
- [Cron Syntax Guide](#cron-syntax-guide)
- [Special Strings](#Special-Strings)
- [Output Redirection](#output-redirection)
- [Best Practices](#best-practices)
- [Contact Information](#contact-information)
- [References](#references)
- [Author](#author)

---
## Introduction
Cron is a time-based job scheduler in Unix-like operating systems that allows users to schedule tasks to run automatically at specified intervals. This document provides a comprehensive Standard Operating Procedure (SOP) for managing Cron jobs.

## Creating Cron Job
```bash
crontab -e

* * * * * /path/to/your/script.sh
```

## Editing Cron Job
```bash
crontab -e
```

## Listing Cron Jobs
```bash
crontab -l
```

## Deleting Cron Jobs
```bash
crontab -r
crontab -i  #For interactive removal
```

## Checking Cron Job Logs
### System logs location varies by distribution:
```bash
grep CRON /var/log/syslog  #grep CRON /var/log/syslog
/var/log/cron  #For dedicated cron log
```

## Cron Syntax Guide
### The cron syntax consists of five time fields followed by the command:
## Cron Timing Format

A cron expression consists of 5 fields separated by spaces. Each field represents a time unit for scheduling:

| **Field**       | **Values**          | **Description**                      |
|------------------|---------------------|--------------------------------------|
| Minute           | 0–59                | Minute when the command runs         |
| Hour             | 0–23                | Hour when the command runs           |
| Day of Month     | 1–31                | Day of the month                     |
| Month            | 1–12                | Month of the year                    |
| Day of Week      | 0–7 (0 = Sunday)    | Day of the week                      |

>  Example: `30 14 * * 1` runs the job every Monday at 2:30 PM.

```bash
* * * * * command_to_execute
```


## Special Strings

Cron also provides special strings as shortcuts for common schedules:

| **String**   | **Description**         | **Equivalent To**     |
|--------------|--------------------------|------------------------|
| `@reboot`    | Run once at startup      | *(no exact time)*     |
| `@yearly`    | Run once a year          | `0 0 1 1 *`            |
| `@monthly`   | Run once a month         | `0 0 1 * *`            |
| `@weekly`    | Run once a week          | `0 0 * * 0`            |
| `@daily`     | Run once a day           | `0 0 * * *`            |
| `@hourly`    | Run once an hour         | `0 * * * *`            |

> These shortcuts improve readability and simplify common cron schedules.

## Output Redirection
- To suppress email output:
```bash
* * * * * /path/to/script.sh >/dev/null 2>&1
```
- To log output to a file:
```bash
* * * * * /path/to/script.sh >> /var/log/cron.log 2>&1
```

## Best Practices

1. Always test scripts before adding them to cron  
2. Use absolute paths in cron jobs  
3. Redirect output appropriately  
4. Document your cron jobs  
5. Consider using lock files for long-running jobs  
6. For complex scheduling, consider using [`anacron`](https://man7.org/linux/man-pages/man8/anacron.8.html)

---


## Contact Information

| **Name**           | **Email address**                         |
|--------------------|--------------------------------------------|
| Deepak Kushwaha    | [deepak.kushwaha.snaatak@mygurukulam.co](mailto:deepak.kushwaha.snaatak@mygurukulam.co) |

---

## References

| **Link**                                                                 | **Description**                                   |
|--------------------------------------------------------------------------|---------------------------------------------------|
| [Cron Documentation ](https://cronitor.io/guides/cron-jobs/) | Document format followed from this link.          |




## Author

- [Deepak Kushwaha](#)

