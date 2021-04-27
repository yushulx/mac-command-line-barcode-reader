# Command-line Barcode Reader for macOS
The sample is implemented using [Dynamsoft Barcode Reader SDK](https://www.dynamsoft.com/Products/Dynamic-Barcode-Reader.aspx).

## What You Should Know
- [![](https://img.shields.io/badge/Download-Offline%20SDK-orange)](https://www.dynamsoft.com/barcode-reader/downloads)
- [![](https://img.shields.io/badge/Get-30--day%20FREE%20Trial%20License-blue)](https://www.dynamsoft.com/customer/license/trialLicense/?product=dbr)

## Usage

Test image

![barcode image](test.jpg)

Build and run the app on `Intel-based Macbook Air`:

```
% sysctl -n machdep.cpu.brand_string
Intel(R) Core(TM) i7-5650U CPU @ 2.20GHz

% sw_vers
ProductName:    Mac OS X
ProductVersion: 10.15.6
BuildVersion:   19G73

% g++ -o barcodereader BarcodeReader.cpp -L./ -lDynamsoftBarcodeReader

% ./barcodereader test.jpg
CPU threads: 4

Thread count: 1. Total barcode(s) found: 49. Time cost: 426 ms

Thread count: 2. Total barcode(s) found: 49. Time cost: 505 ms

Thread count: 3. Total barcode(s) found: 49. Time cost: 483 ms

Thread count: 4. Total barcode(s) found: 49. Time cost: 479 ms

Multi-thread best performance: thread_count = 1, timecost = 426
```

Build and run the app on `Apple silicon–based Macbook Air`:

```
% sysctl -n machdep.cpu.brand_string
Apple processor

 % sw_vers
ProductName:    macOS
ProductVersion: 11.0
BuildVersion:   20A2411

% g++ -target x86_64-apple-macos10.9 -o barcodereader BarcodeReader.cpp -L./ -lDynamsoftBarcodeReader

% ./barcodereader test.jpg
CPU threads: 8

Thread count: 1. Total barcode(s) found: 49. Time cost: 291 ms

Thread count: 2. Total barcode(s) found: 49. Time cost: 302 ms

Thread count: 3. Total barcode(s) found: 49. Time cost: 300 ms

Thread count: 4. Total barcode(s) found: 49. Time cost: 298 ms

Thread count: 5. Total barcode(s) found: 49. Time cost: 301 ms

Thread count: 6. Total barcode(s) found: 49. Time cost: 297 ms

Thread count: 7. Total barcode(s) found: 49. Time cost: 298 ms

Thread count: 8. Total barcode(s) found: 49. Time cost: 298 ms

Multi-thread best performance: thread_count = 1, timecost = 291
```
