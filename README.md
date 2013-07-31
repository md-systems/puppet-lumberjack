# puppet-lumberjack2

A puppet module for managing and configuring lumberjack2

https://github.com/jordansissel/lumberjack/tree/lumberjack2-hack

This module is based upon https://github.com/electrical/puppet-lumberjack 
This update has not been puppet 3 tested.

## Usage

Installation, make sure service is running and will be started at boot time:

     class { 'lumberjack2': 
       config           => '/path/to/config/file',
       cpuprofile       => '/path/to/write/cpu/profile/to/file',
       idle_flush_time  => '5',
       log_to_syslog    => false,
       spool_size       => '1024',
     }

Removal/decommissioning:

     class { 'lumberjack2':
       ensure => 'absent',
     }

Install everything but disable service(s) afterwards:

     class { 'lumberjack2':
       status => 'disabled',
     }
