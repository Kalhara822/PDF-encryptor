# PDF Locker

A single-file tool that adds or removes a password on PDF files.
It runs entirely in your web browser, works offline, and installs nothing.

## Quick start

1. Double-click PDF-Locker.html (opens in Edge, Chrome or Firefox).
2. Encrypt tab: click or drag in your PDF (Import PDF).
3. Type a password, then type it again in "Confirm password".
4. Click "Encrypt & Export".
5. The new file downloads as <name>_encrypted.pdf (usually in Downloads).

To open the encrypted PDF, double-click it in any PDF viewer and enter
the password when asked.

## Unlock tab

Use this to save a copy of an encrypted PDF with the password removed.
1. Open the Unlock tab and import the encrypted PDF.
2. Enter its password.
3. Click "Unlock & Export". It downloads as <name>_unlocked.pdf.

## Privacy and safety

- Everything happens on your computer. The page has no server and is
  blocked from making network requests, so your PDF and password are
  never uploaded.
- No .exe, .bat or installer is needed, so Windows Smart App Control
  has nothing to block.
- Your original PDF is not changed and stays unprotected. Delete it
  (and empty the Recycle Bin) if it must not stay readable.
- If you forget the password, the file cannot be recovered. There is
  no reset and no backdoor. Store the password in a password manager.

## Password tips

- The tool requires at least 4 characters. Use 12 or more in practice.
- A passphrase of 4 or more random words is strong and easy to remember.
- Passwords are case-sensitive and may contain spaces and symbols.
- Don't send the password in the same message as the file.

## Technical details

- Encryption: AES-256 (PDF 2.0 / Revision 6) using qpdf compiled to
  WebAssembly. The engine is bundled inside the HTML file (~1.7 MB).
- The same password is set as both the "open" (user) and "owner"
  password. No printing/copying restrictions are applied.
- Page content, images and text are preserved. Only the file is
  encrypted.
- What is NOT hidden: the file name, file size and the fact that the
  file is a PDF.
- Compatibility: Adobe Acrobat/Reader, Chrome, Edge, Firefox and
  macOS Preview open AES-256 PDFs. Very old PDF readers (before about
  2008) may not.
- Detection of "already protected" PDFs is a quick scan of the file,
  so an unusual file may occasionally need a retry.

## Troubleshooting

- Nothing downloads: allow downloads for this page in the browser
  and check the browser's Downloads list (Ctrl+J).
- "Wrong password": check Caps Lock and spelling. Tick "Show
  password" to see what you typed.
- "Already password protected": use the Unlock tab first if you want
  to change the password.
- "Could not read this PDF": the file may be damaged, or may not be
  a real PDF. Try opening it in a PDF viewer first.
- Page is blank or buttons do nothing: use an up-to-date desktop
  browser and open the file directly, not from inside an email or
  chat preview.
- Very large PDFs (hundreds of MB) may be slow or run out of
  memory, because processing happens in the browser.

## Credits and license

- PDF engine: qpdf (Apache License 2.0), via @jspawn/qpdf-wasm.
- You can copy this file to other computers. Keep it as one file.
