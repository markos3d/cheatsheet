# CRON Cheatsheet

## Format
```
* * * * * command_to_be_executed
│ │ │ │ │
│ │ │ │ └─ Weekday (0=Sun .. 6=Sat)
│ │ │ └─── Month (1..12)
│ │ └───── Day (1..31)
│ └─────── Hour (0..23)
└───────── Minute (0..59)
```

## Common Time Specifications

| Pattern | Description |
|---------|-------------|
| `* * * * *` | Every minute |
| `*/15 * * * *` | Every 15 minutes |
| `0 */2 * * *` | Every 2 hours |
| `0 0 * * 0` | Every Sunday midnight |
| `@weekly` | Once a week |
| `@daily` | Every day |
| `@yearly` | Every year |
| `@monthly` | Every month |
| `@hourly` | Every hour |
| `@reboot` | At system startup |

## Value Ranges

- **Minutes**: 0-59
- **Hours**: 0-23
- **Days**: 1-31
- **Months**: 1-12
- **Weekdays**: 0-6 (Sunday to Saturday)

## Special Characters

- `*`: Any value
- `/`: Step values
- `-`: Range values
- `,`: List values

## Examples

```bash
# Run every minute
* * * * * command

# Run every 15 minutes
*/15 * * * * command

# Run at 2:30 AM daily
30 2 * * * command

# Run at midnight on Sundays
0 0 * * 0 command
```

## Notes

- Multiple values can be specified using commas: `1,15,30 * * * *`
- Ranges can be specified using hyphens: `0 2-4 * * *`
- Step values can be used with ranges: `*/10 * * * *`
- Use `@` shortcuts for common schedules: `@daily`, `@weekly`, etc.
