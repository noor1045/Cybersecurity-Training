# HASHCAT

Hashcat is a powerful password recovery and hash-cracking tool used in penetration testing, digital forensics, and security assessments.

It supports CPU and GPU acceleration, multiple hash algorithms, and different cracking techniques such as:

* Dictionary attacks
* Brute-force attacks
* Rule-based attacks
* Hybrid attacks

In Kali Linux, Hashcat is generally available by default, but it can also be installed or updated manually.

> **Disclaimer:** Hashcat should only be used for authorized security testing, password recovery, educational labs, and systems you own or have permission to test.

##  Update System and Check Hashcat Version

Update the package list:

```bash
sudo apt update
```

Check the installed Hashcat version:

```bash
hashcat --version
```

##  Run Hashcat Help

To display Hashcat help and available options:

```bash
hashcat -h
```

This displays the available commands, attack modes, hash modes, and other options.

##  Check Supported Modes

To search the help output for supported modes:

```bash
hashcat --help | grep -i "mode"
```

Hashcat supports many different hash types and attack modes.

##  Generate a Test Hash

For this practical, a hash was generated from the test string:

```text
CUST
```

The generated hash was then used as the target hash for the Hashcat practical.

##  Create Hash File

Create a new file named:

```text
hash.txt
```

Paste the generated hash inside this file and save it.

The file will be used as the target input for Hashcat.

##  Dictionary Attack

A dictionary attack was first performed using the `rockyou.txt` wordlist.

```bash
hashcat -m 0 -a 0 hash.txt /usr/share/wordlists/rockyou.txt
```

### Command Explanation

* `-m 0` — MD5 hash type
* `-a 0` — Dictionary attack
* `hash.txt` — File containing the target hash
* `/usr/share/wordlists/rockyou.txt` — Wordlist used for testing

##  Dictionary Attack Result

After running the dictionary attack, Hashcat displayed:

```text
Recovered: 0/1
```

This means the password was not found inside the selected dictionary.

Therefore, another attack method was required.

##  Lowercase Brute-Force Attack

Next, a brute-force attack was performed using four lowercase letters:

```bash
hashcat -m 0 -a 3 hash.txt ?l?l?l?l
```

### Mask Explanation

```text
?l = lowercase letter
```

The mask:

```text
?l?l?l?l
```

tests combinations containing four lowercase characters.

Total possible combinations:

```text
26⁴ = 456,976
```

### Result

In this practical, the target password was successfully cracked using the lowercase `?l?l?l?l` brute-force mas

Therefore, the lowercase brute-force attack successfully recovered the password.


## Uppercase Brute-Force Example

Another possible brute-force mask is:

```bash
hashcat -m 0 -a 3 hash.txt ?u?u?u?u
```

### Mask Explanation

```text
?u = uppercase letter
```

The mask:

```text
?u?u?u?u
```

tests four uppercase letters.

Possible combinations:

```text
26⁴ = 456,976
```

However, because the password had already been cracked using the lowercase mask, the successful result for this practical came from:

```text
?l?l?l?l
```

## Cracked Password Result

The successful recovered password was:

```text
cust
```

Attack used:

```text
Brute-force
```

Mask used:

```text
?l?l?l?l
```

Hash type:

```text
MD5
```

Result:

```text
Password Successfully Cracked
```


## Task 13 — Common Brute-Force Masks

| Mask       | Description                             | Example Candidates     |
| ---------- | --------------------------------------- | ---------------------- |
| `?l?l?l?l` | 4 lowercase letters                     | `abcd`, `test`, `zyxw` |
| `?u?u?u?u` | 4 uppercase letters                     | `TEST`, `ABCD`, `WXYZ` |
| `?d?d?d?d` | 4 digits                                | `1234`, `9876`, `2025` |
| `?s?s?s?s` | 4 special characters                    | `!@#$`, `^&*?`         |
| `?a?a?a?a` | All character types                     | `Ab1!`, `z9#Q`         |
| `?l?l?d?d` | 2 lowercase + 2 digits                  | `ab12`, `xy34`         |
| `?u?u?d?d` | 2 uppercase + 2 digits                  | `AB12`, `XY34`         |
| `?l?u?d?s` | Lowercase + uppercase + digit + special | `aB1!`, `xZ9#`         |
| `?u?l?l?d` | Uppercase + 2 lowercase + digit         | `Abc1`, `Xyz9`         |

## Hashcat Mask Characters

| Mask | Character Type                |
| ---- | ----------------------------- |
| `?l` | Lowercase letters             |
| `?u` | Uppercase letters             |
| `?d` | Digits                        |
| `?s` | Special characters            |
| `?a` | All supported character types |

## Conclusion

Hashcat was successfully tested using both dictionary and brute-force techniques.

The dictionary attack using `rockyou.txt` did not recover the target password. A four-character lowercase brute-force attack was then performed using:

```text
?l?l?l?l
```

This attack successfully recovered the original test password:

```text
cust
```

This practical demonstrated how different Hashcat attack modes and masks can be used in an authorized password-recovery lab.

## Disclaimer

This practical was performed for educational and authorized security testing purposes. Hashcat should never be used to recover or crack passwords belonging to systems or users without explicit authorization.

