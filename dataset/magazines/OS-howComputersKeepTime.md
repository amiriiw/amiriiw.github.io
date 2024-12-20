<h2 align="center">HOW COMPUTERS KEEP TIME</h2>
<p align="center">learning URLs:<a href="https://youtu.be/1quyXzn6TyQ?si=H-_cD7SANGNFfKKi">jadi</a></p>

---

# How Computers Keep Time

Computers keep track of time through a combination of hardware and software mechanisms. Here’s a detailed explanation of how they maintain and update the time:

## 1. Real-Time Clock (RTC)

Most computers have a **Real-Time Clock (RTC)**, a hardware component that keeps track of the current time, even when the computer is powered off.

- The RTC is powered by a small **CMOS battery** that provides energy to the clock, allowing it to run continuously.
- The RTC is part of the motherboard and works like a simple digital watch. It counts time based on oscillations of a quartz crystal (32.768 kHz).
- The RTC keeps track of the date and time and provides this information when the computer starts up.

## 2. System Time (Software Level)

When the computer is turned on, it reads the time from the RTC and loads it into the operating system’s memory as **system time**.

- The operating system maintains a **software clock** that updates based on system interrupts or ticks.
- The **tick count** or **clock tick** is generated by hardware interrupts (e.g., Programmable Interval Timer or High Precision Event Timer), usually at 1000 times per second.
- Each interrupt updates the software clock by a small increment, usually a millisecond.

## 3. Network Time Protocol (NTP) Synchronization

Computers often synchronize their clocks with external **time servers** using **Network Time Protocol (NTP)**.

- NTP is a protocol that synchronizes computers with **accurate time sources**, such as atomic clocks or GPS.
- Periodically, the system connects to NTP servers over the internet to correct any drift or inaccuracy.
- Time drift occurs due to imperfections in hardware clocks, causing the system time to gradually become inaccurate.

## 4. Time in Operating Systems

Each operating system (Windows, Linux, macOS) manages time similarly:

- At boot, the system initializes its software clock from the hardware RTC.
- The OS synchronizes the system time with time servers via NTP to keep it accurate.
- The system time is essential for tasks like event logging, scheduling, and file timestamps.

## 5. UTC vs Local Time

Operating systems store time in **Coordinated Universal Time (UTC)** and apply time zone offsets for local time:

- UTC is a universal time standard that doesn’t change with time zones or daylight saving time.
- The OS converts UTC to local time using the system’s configured time zone, including daylight saving adjustments.

## 6. Handling Power Loss

If the computer is powered off or the CMOS battery dies:

- The RTC may reset or stop functioning.
- If the RTC is working, the OS reads the RTC and sets the system time.
- If the RTC resets, the system may default to a specific time (e.g., January 1, 1970) until it syncs with an NTP server.
- Modern systems alert users if the time is incorrect, prompting manual correction or NTP synchronization.

## 7. High-Resolution Clocks

For applications needing precise time tracking, high-resolution timers are used:

- **High-Resolution Timers** like the **TSC (Time Stamp Counter)** in modern CPUs track time with great precision (nanoseconds or microseconds).
- The TSC counts CPU cycles since the last reset, allowing for very accurate time measurement.
- These clocks are critical for performance tuning and real-time applications.

## Summary:

- **Real-Time Clock (RTC)**: Keeps time while the system is off, powered by a battery.
- **System Clock**: Managed by the operating system, updates using system interrupts.
- **NTP Synchronization**: Periodically syncs system time with external time servers.
- **UTC vs Local Time**: System stores time in UTC, converting it to local time based on the time zone.
- **Handling Drift**: Imperfections in hardware clocks cause drift, corrected by NTP.
- **High-Resolution Clocks**: Used for precise time measurements in specific applications.

---
