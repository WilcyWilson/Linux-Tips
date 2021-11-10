## What is timedatectl?

- The timedatectl command allows you to query and change the configuration of the system clock and its settings, you can use this command to set or change the current date, time, and timezone or enable automatic system clock synchronization with a remote NTP server.

## Make Linux Use Local Time

- You can use timedatectl command in most of the linux distro to make this change.

- Just open the terminal and type in  the following command

```
[wilson@wilson-pc ~]$ timedatectl set-local-rtc 1 --adjust-system-clock

[wilson@wilson-pc ~]$ timedatectl
               Local time: Wed 2021-11-10 08:21:59 +0545
           Universal time: Wed 2021-11-10 02:36:59 UTC
                 RTC time: Wed 2021-11-10 08:21:59
                Time zone: Asia/Kathmandu (+0545, +0545)
System clock synchronized: no
              NTP service: inactive
          RTC in local TZ: yes

Warning: The system is configured to read the RTC time in the local time zone.
         This mode cannot be fully supported. It will create various problems
         with time zone changes and daylight saving time adjustments. The RTC
         time is never updated, it relies on external facilities to maintain it.
         If at all possible, use RTC in UTC by calling
         'timedatectl set-local-rtc 0'.
```

- If you see “RTC in local TZ: yes”, Linux is set to use the local time zone instead of UTC.

- If you ever want to undo the change we did above we can use the following command.

```
[wilson@wilson-pc ~]$ timedatectl set-local-rtc 0 --adjust-system-clock
```

### Note: You may want to adjust your bios clock if the system time doesn't match with real time after you restart your PC.