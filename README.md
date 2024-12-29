# Expo Camera onBarCodeScanned Inconsistency

This repository demonstrates a bug in Expo's Camera API where the `onBarCodeScanned` callback function behaves inconsistently, particularly when scanning multiple barcodes in quick succession.  The issue is that not all scanned barcodes are reliably detected by the callback.

## Bug Description
The `onBarCodeScanned` function sometimes misses barcodes or only detects a fraction of them when scanning multiple barcodes rapidly.  This makes it unreliable for applications requiring accurate and consistent barcode scanning.

## Reproduction
Clone this repository and run the `bug.js` file.  Try scanning multiple barcodes quickly and observe that the console output doesn't always reflect all the scanned barcodes.

## Solution
The `bugSolution.js` file demonstrates a potential solution using debouncing to regulate barcode scan processing.  This approach mitigates the inconsistent behavior but may not be perfect in all scenarios.

## Further Investigation
The root cause may lie in the underlying barcode scanning library used by Expo Camera.  Further investigation into its limitations and potential performance bottlenecks might be necessary for a complete fix.