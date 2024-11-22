# How to remove timestamp on screenshots in MacOS

When you take screenshots on MacOS they are saved with a rather long name, like `Screenshot 2023-10-18 at 4.13.56 PM`

To remove the timestamp making the names shorter just enter this in your terminal:

```bash
defaults write com.apple.screencapture "include-date" 0
```

After doing that go ahead and run this:

```bash
killall SystemUIServer
```

Now your screenshots will just be saved as `Screenshot` and successive screenshots in the same directory will have a number appended to them. (i.e `Screenshot 1`, `Screenshot 2`, etc.)
