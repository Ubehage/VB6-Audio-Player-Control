# VB6 Audio Player Control

A compact VB6 dll exposing a single AudioPlayer class for playing MP3 and WAV files.
(Other formats may be supported natively.)

---

## Key points / Philosophy

- Minimal, VB6-friendly class-object API.
- Plays audio directly without a window.
- Uses only native Windows audio support — no bundled codec or transcoding layers.

---

## Requirements

- Visual Basic 6.
- Windows with audio support.

---

## Interface
Class: **AudioPlayer**
- Properties
  - **FileName** (String): Path or URL to a supported audio file. Supported formats: MP3, WAV.
  - **Length** (Long, Read-only): Total length of the loaded audio file in seconds.
  - **Position** (Long): Current playback position in seconds. Can be read and set; setting seeks to the requested second (clamped to valid range).
  - **Command** (Multimedia_Command datatype): Controls playback. Valid commands: Open, Close, Play, Stop, Pause, Rewind.
- Behavior notes
  - After assigning FileName, caller must invoke Command = Open before playback or length/position queries are reliable.
  
Important behavior note: a file must be opened (Command = Open) before playback actions are valid.
Open will raise a runtime error if the FileName refers to an unsupported format.

---

## License

[MIT License](LICENSE)  
Copyright © Ubehage

---

## Credits

Created by Ubehage  
[GitHub Profile](https://github.com/Ubehage)