# amateur.radio

Collecting things that I have found useful in my amateur radio beginnings

# US Band Plan

https://www.arrl.org/files/file/Regulatory/Band%20Chart/Band%20Chart%20-%2011X17%20Color.pdf

# WSPR

WSPR reception setup using RTL-SDR dongle V3 https://docs.google.com/document/d/10_xEGW_tdC7LhA-5_UE7ZmgMfPv4ySvz6DQrv02X4ek/edit?usp=sharing

https://www.vk6ysf.com/wspr_frequ.htm

Generally
* use USB 
* use 2500 bandwidth
* turn down the gain until wsjt-x is green
* RTLSDR/Airspy
* Sample Rate 1.024
* Sample Mode Direct Sampling (Q branch)
* Correct IQ


# Windows Time Sync Frequency 

Set to every 6 hrs

C:\Windows\system32>reg query HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\W32Time\TimeProviders\NtpClient /v SpecialPollInterval

HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\W32Time\TimeProviders\NtpClient
    SpecialPollInterval    REG_DWORD    0x5460

Or use NetTime and set a faster frequency.  Some recommend 15 min.  Ive had fine experience with 75 min.
