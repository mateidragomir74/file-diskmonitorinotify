📁 File & Disk Monitor with inotify
A real-time file system monitoring tool built with Bash and inotify-tools. It watches a target directory for any changes and logs all events along with available disk space.
What it does

Detects when files or folders are created, deleted, or modified in real time
Logs every event with a timestamp and the current free disk space
Saves all activity to a report file (modificari.txt) for later review
Runs continuously until manually stopped

How to run
Prerequisites
Make sure inotify-tools is installed:
bashsudo apt-get install inotify-tools
Run the monitor
bashchmod +x monitor.sh
./monitor.sh
The script will start watching the test/ directory and output events to both the terminal and modificari.txt.
Press Ctrl+C to stop monitoring.
Example output

START MONITORIZARE: Wed Apr 29 12:00:00 2026

12:00:05 | [+] A APARUT un fisier/folder nou: test/document.txt | Spatiu Liber: 45G

12:00:12 | [*] S-a MODIFICAT continutul: test/document.txt | Spatiu Liber: 45G

12:00:20 | [-] A DISPARUT (sters): test/document.txt | Spatiu Liber: 45G


Tech used

Bash
inotifywait (from inotify-tools) — Linux kernel-level file system event monitoring
df — disk space reporting

Project structure

├── monitor.sh        # Main monitoring script

├── modificari.txt    # Auto-generated event log

└── documentatie.docx # Project documentation

*Project made for the Instructiuni si Tehnici de Baza in Informatica course 
