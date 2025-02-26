# Source Directory

Make sure that your source code is in the `src` directory.
The script below  extracts log entries for a specified date from a log file and saves them in an output folder, handling errors and supporting command-line usage.

import os
import sys

def get_logs(log_file, date, size=1024 * 1024):
    output_folder = "output"
    os.makedirs(output_folder, exist_ok=True)
    output_path = os.path.join(output_folder, f"logs_{date}.txt")

    try:
        with open(log_file, "r", buffering=size) as file, open(output_path, "w") as output:
            for line in file:
                if line.startswith(date):
                    output.write(line)

        print(f"Logs saved in: {output_path}")

    except FileNotFoundError:
        print("Log file not found.")
    except Exception as e:
        print(f"Error: {e}")

if __name__ == "__main__":
    if len(sys.argv) != 2:
        print("Usage: python extract_logs.py YYYY-MM-DD")
        sys.exit(1)

    date = sys.argv[1]
    log_file = "test_logs.log"
    
    get_logs(log_file, date)

The script below generates a log file with 10,000 randomly timestamped log entries, each containing a log level and a message, for testing or development purposes.
import random
import datetime

# Define log levels and sample messages
log_levels = ["INFO", "ERROR", "WARN", "DEBUG"]
messages = [
    "User logged in",
    "Failed to connect to the database",
    "Disk space running low",
    "User logged out",
    "File not found",
    "Connection timeout",
    "Unauthorized access attempt",
    "Server restarted successfully",
    "Database query executed",
    "Memory usage high"
]

def generate_logs(file_name, num_lines=10000):
    start_date = datetime.datetime(2024, 1, 1, 0, 0, 0)
    
    with open(file_name, "w") as f:
        for _ in range(num_lines):
            # Generate a random date and time within a given range
            random_days = random.randint(0, 364)  # 1 year range
            random_seconds = random.randint(0, 86399)  # Seconds in a day
            timestamp = start_date + datetime.timedelta(days=random_days, seconds=random_seconds)
            
            log_level = random.choice(log_levels)
            message = random.choice(messages)
            
            log_entry = f"{timestamp.strftime('%Y-%m-%d %H:%M:%S')} {log_level} {message}\n"
            f.write(log_entry)

    print(f"Generated {num_lines} log entries in {file_name}")

# Generate a log file with 10,000 lines
generate_logs("test_logs.log", 10000)

