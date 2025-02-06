ntpdate
=======

# NTP Time Sync Script

![GitHub Workflow Status](https://img.shields.io/github/actions/workflow/status/nigelhorne/ntpdate/ci.yml?branch=main)
![License](https://img.shields.io/github//nigelhorne/ntpdate)
![Perl Version](https://img.shields.io/badge/perl-5.34+-blue)

This Perl script synchronizes the system time with an NTP server and updates the system clock.
Please report any bugs or feature requests to the author.
This module is provided as-is without any warranty.

## Features
- Retrieves network time using an NTP server.
- Converts and formats the time using `DateTime`.
- Supports configurable timezones via `config.cfg`.
- Logs events using `syslog`.
- Updates the system clock (requires sudo privileges).

## Requirements
- Perl
- Required Perl Modules:
  - `Net::NTPTime`
  - `DateTime`
  - `Sys::Syslog`
  - `Config::Simple`
- Linux-based system (for `date` command execution)

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

## License
This project is licensed under the GPL2 Licence.
