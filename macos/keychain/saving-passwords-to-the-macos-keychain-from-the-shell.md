# Saving Passwords to the macOS Keychain from the Shell

You can save a password to the macOS keychain from the shell using the native `security` command-line tool. In the terminal, run:

```
security add-generic-password -a "$USER" -s "MyService" -w "MyPassword"
```

A more secure way to do this is to omit the argument to the `-w` flag and let the terminal prompt you for your password. Passing `-w` with a plain-text password puts your secret into your shell history file.

```
security add-generic-password -a "$USER" -s "MyService" -w
```

The terminal will then prompt you for your password.

To read the password back, run:

```
security find-generic-password -a "$USER" -s "MyService" -w
```

Additionally, you can use that last command to load the password into a script variable using command substitution:

```
MY_PASSWORD=$(security find-generic-password -a "$USER" -s "MyService" -w)
```

---

[Using the OS X Keychain to store and retrieve passwords](https://www.netmeister.org/blog/keychain-passwords.html)
