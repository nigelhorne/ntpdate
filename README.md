ntpdate
=======

# NTP Time Sync Script

![GitHub Workflow Status](https://img.shields.io/github/actions/workflow/status/nigelhorne/ntpdate/ntpdate.yml?branch=master)
![Perl Version](https://img.shields.io/badge/perl-5.34+-blue)

This Perl script synchronizes the system time with an NTP server and updates the system clock.
Please report any bugs or feature requests to the author.
This module is provided as-is without any warranty.

## Features
- Retrieves network time using an NTP server.
- Implements retry logic (up to 3 attempts) if time retrieval fails
- Converts and formats the time using `DateTime`.
- Supports configurable timezones via `config.cfg`.
- Logs events using `syslog`.
- Updates the system clock (requires sudo privileges).

## Requirements
- Perl
- Required Perl Modules:
  - L<Net::NTPTime>
  - L<DateTime>
  - L<Sys::Syslog>
  - L<Config::Simple>
- Linux-based system, or similar (for `date` command execution)

## Installation
### Clone the Repository
```sh
git clone https://github.com/nigelhorne/ntpdate.git
cd ntpdate
```

### Install Dependencies
```sh
cpanm Net::NTPTime DateTime Sys::Syslog Config::Simple
```

## Usage
Run the script with an NTP server:
```sh
perl ./ntpdate pool.ntp.org
```

## Configuration
To change the default timezone, create a `ntpdate.cfg` file:
```ini
timezone=America/New_York
```

## GitHub Actions
This project includes a GitHub Actions workflow to:
- Install dependencies
- Run the script with a test NTP server
- Lint the Perl script

## Logging and Error Handling
- If the script fails to retrieve the time, it will retry up to **3 times** before exiting with an error.
- Logs are recorded via C<syslog> for debugging and monitoring.

## License
This project is licensed under the GPL2 Licence.
