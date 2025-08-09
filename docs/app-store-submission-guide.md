# App Store Submission Guide for MinuteRepeater

## Encryption Declaration

When submitting your MinuteRepeater app to App Store Connect, you need to declare whether your app uses encryption.

### Step 1: Add to Info.plist

In your Xcode project, add the following key to your `Info.plist` file:

```xml
<key>ITSAppUsesNonExemptEncryption</key>
<false/>
```

### Step 2: Understanding the Value

**Set to `false` if your app:**
- Only uses standard iOS encryption (HTTPS, keychain, etc.)
- Does not implement custom encryption algorithms
- Only uses Apple's built-in encryption APIs

**Set to `true` if your app:**
- Implements custom encryption algorithms
- Uses third-party encryption libraries
- Has proprietary encryption methods

### For MinuteRepeater App

Since MinuteRepeater is a virtual minute repeater app that likely only uses:
- Standard HTTPS for network requests
- Standard iOS keychain for storing preferences
- Standard iOS audio APIs
- Standard Apple Watch connectivity

You should set this to `false`:

```xml
<key>ITSAppUsesNonExemptEncryption</key>
<false/>
```

### Alternative: Xcode Project Settings

You can also set this in Xcode:

1. Select your project in the navigator
2. Select your app target
3. Go to the "Info" tab
4. Add a new row with key: `App Uses Non-Exempt Encryption`
5. Set the type to `Boolean`
6. Set the value to `NO`

### What This Prevents

Adding this key prevents the encryption export compliance dialog from appearing during App Store Connect submission, streamlining the submission process.

## Additional App Store Requirements

### App Privacy

Make sure to configure your app's privacy settings in App Store Connect:
- Data collection practices
- Data usage policies
- Third-party SDK data collection

### App Review Information

Provide clear information about:
- How the minute repeater functionality works
- Any audio permissions required
- Apple Watch integration features

### Testing Notes

Include testing instructions for reviewers:
- How to activate the minute repeater chimes
- Apple Watch pairing requirements
- Any specific testing scenarios

## Contact

For technical questions about the app submission: 18600064502@163.com