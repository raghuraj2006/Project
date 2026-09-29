Vityarthi-Project

# Password Strength & Breach-Pattern Checker

This is a simple Python project I made for my CSE1021 course. It is a command line program that lets you set a password, checks if it follows some basic rules, and then tells you how strong it is (out of 10) with some tips to make it better.

## What it does

- Lets you set/change a password (it checks the password before accepting it)
- Checks the strength of your password and gives a score out of 10
- Tells you if you are using common weak patterns like "123", "password", "qwerty" etc.
- Also checks for repeated characters like "aaaa"
- Everything is done using plain Python, no external libraries or APIs used

## Requirements

- Python 3.10 or above (I used `match case` in the code which only works from Python 3.10 onwards)
- Nothing else needs to be installed, it only uses built-in Python stuff

## How to set it up

1. First make sure Python is installed on your system. You can check by running:
   ```bash
   python --version
   ```
   If it shows something below 3.10, you might need to update Python or use `python3` instead of `python`.

2. Download/clone this repository:
   ```bash
   git clone https://github.com/raghuraj2006/Project.git
   cd Project
   ```

3. That's it, no packages or setup needed since the whole thing is written in plain Python.

### Opening it in VS Code

If you have VS Code installed, you can open the cloned folder directly:
```bash
code Project
```

Or, if you don't want to clone it manually, open it straight from GitHub in your browser's VS Code editor:
https://github.dev/raghuraj2006/Project

## How to run it

Just run this command from the project folder:

```bash
python Password_Detector.py
```

(if that doesn't work try `python3 Password_Detector.py`)

After running it, you will see a menu like this:

```
===== Password Strength Checker =====
1. Set or replace password
2. Check password strength (out of 10)
3. Exit
Please choose an option (1-3):
```

- **Option 1**: type a new password. It has to be at least 10 characters, can't start with a number, and can't have these symbols: `^ * ( ) %`. If it's not valid it will ask you to try again.
- **Option 2**: shows the strength of the password you set, out of 10, along with tips on how to improve it. You have to set a password first using option 1, otherwise it will tell you no password is set.
- **Option 3**: closes the program.

## How the scoring works

The password starts with 0 points, and points are added like this:

- Length 14 or more characters → 2 points (10-13 characters only gives 1 point)
- Has a lowercase letter → 2 points
- Has an uppercase letter → 2 points
- Has a number → 2 points
- Has a special character → 2 points

Then points are taken away (2 points each) if:
- The password has a common weak word in it like "123", "password", "admin" etc.
- The same character is repeated 4 or more times in a row (like "aaaa")

Final score is kept between 0 and 10, and based on that it shows a label:

- 0-3 → Very Weak
- 4-5 → Weak
- 6-7 → Moderate
- 8-9 → Strong
- 10 → Very Strong

## Files in this repo

```
.
├── Password_Detector.py   -> main code file, everything is in here
└── README.md
```

## Note

This project doesn't actually check real passwords against real breach databases online (like haveibeenpwned), it just checks for common weak patterns manually in the code. Also nothing is saved anywhere, the password only stays in memory while the program is running and is gone once you close it.