# DDoS Tool - ItzPopelka

A simple Python-based multithreaded tool for stress-testing web servers by sending continuous HTTP GET requests.

## Features

* **Multithreading:** Supports custom thread counts to simulate high traffic.
* **Input Validation:** Basic checks for URL formatting and thread integers.
* **Visual Interface:** Includes an ASCII art header and real-time request tracking.

## Prerequisites

Before running the script, ensure you have Python installed and the following libraries:

```bash
pip install requests colorama

```

## Usage

1. **Clone or download** the script to your local machine.
2. **Open your terminal** in the script's directory.
3. **Run the script**:
```bash
python main.py

```


4. **Follow the prompts**:
* Enter the target URL (must include `http://` or `https://`).
* Enter the number of threads you wish to spawn.



## Technical Details

The script uses the `threading` module to execute the `dos` function concurrently. Each thread runs an infinite loop that performs a `requests.get()` call to the target URL.

```python
def dos(target):
    while True:
        try:
            res = requests.get(target)
            print("Request sent!")
        except requests.exceptions.ConnectionError:
            print("[!!!] Connection error!")

```

## Disclaimer

**Warning:** This tool is intended for educational purposes and authorized penetration testing only. Using this script against targets without explicit permission is illegal and unethical. The developer (ItzPopelka) assumes no liability for misuse or damage caused by this program.
