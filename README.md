# Expo Linking.openURL Silent Failure

This repository demonstrates a silent failure in Expo's `Linking.openURL` when attempting to open a URL with a custom scheme that doesn't have a corresponding app installed. The issue is the lack of any error feedback, making debugging challenging.

## Bug Description

The `Linking.openURL` method in Expo, when used with a custom URL scheme, does not provide any indication of failure if the app responsible for handling that scheme is not present on the device.  This silent failure makes it hard to identify and handle such situations gracefully.

## Reproduction

1. Clone the repository.
2. Run the app (using `expo start`).
3. Attempt to open the custom URL scheme. Observe that no error is reported, even if the intended app isn't installed.

## Solution

The solution involves using `Linking.canOpenURL` before attempting to open the URL. This allows for checking the availability of a handler for the specified URL scheme.  This provides a way to handle the absence of the handling app gracefully.  This updated code provides a more robust and user-friendly experience.