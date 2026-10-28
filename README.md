
# Phishing URL Awareness Checker

A beginner-friendly Python cybersecurity mini project that identifies common warning signs in URL text that may indicate a phishing attempt.

## Project Overview

Phishing attacks often use deceptive links to trick users into revealing sensitive information. This project checks URL text for selected warning signs and displays findings to help users review suspicious links carefully.

**Important:** This tool does not determine whether a URL is safe or malicious. It is an awareness tool only.

## Features

- Detects the `@` symbol in URL text.
- Flags URLs longer than 100 characters.
- Identifies IPv4 addresses used as hostnames.
- Flags hostnames containing five or more segments.
- Detects the `xn--` punycode marker.
- Flags URLs that use HTTP.
- Handles empty or malformed input.
- Supports repeated checks until the user chooses to quit.

## Technologies Used

- Python 3
- `re` — Python regular expressions
- `urllib.parse` — URL text parsing

No third-party Python packages are required.

## Project Structure

```text
phishing-url-awareness/
├── phishing_checker.py
├── README.md
├── requirements.txt
├── tests/
│   └── test_samples.md
└── screenshots/
    ├── sample_run.png
    └── test_results.png
```

## How to Run

1. Install Python 3.10 or later.
2. Open this project folder in VS Code.
3. Open the terminal.
4. Run:

```bash
python phishing_checker.py
```

5. Enter a sample URL when prompted.
6. Enter `q` to quit.

On Windows, if `python` does not work, try:

```bash
py phishing_checker.py
```

## Example

Input:

```text
http://192.0.2.10/account
```

Output:

```text
- Uses an IP address instead of a familiar domain.
- Uses HTTP. HTTPS alone does not prove trust.

REVIEW CAREFULLY: warning signs were found.
```

## Testing

Five sample test cases are documented in `tests/test_samples.md`:

1. Normal-looking HTTPS URL
2. IP address with HTTP
3. URL containing `@`
4. Hostname with many segments
5. Punycode-style hostname

See the `screenshots/` folder for program output and test-case evidence.

## Improvements

- Added a loop so users can check multiple URL strings in one run.
- Added a quit option to exit the program.
- Added input handling for empty or malformed URL text.
- Added a clear review message when warning signs are detected.

## Limitations

- Does not open or visit URLs.
- Does not perform live scanning or query external services.
- Uses simple warning-sign checks and may produce false positives or miss phishing URLs.
- Does not verify domain ownership, website reputation, certificates, or page content.
- HTTPS does not guarantee that a website is trustworthy.

## Ethical Use

Use this program for learning and defensive cybersecurity awareness. Test it with sample URL strings only. Never enter passwords or other sensitive information on suspicious websites.

## Author

Created as a Python cybersecurity mini project for phishing URL awareness.
