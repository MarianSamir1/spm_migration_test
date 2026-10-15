# Flutter SPM Reference

Flutter: 3.44.7
Dart: 3.12.2
iOS Minimum: 15.0

---

## Dart-only packages

| Package            | Version | Native Code | SPM |
|---|---|---|---|---|---|---|---|---|---|---|---|--|
| bloc               | 9.2.1   | No          | N/A |
| flutter_bloc.      | 9.1.1   | No          | N/A |
| flutter_screenutil | 5.9.3   | No          | N/A |
| http               | 1.6.0   | No          | N/A |
| flutter_svg        | 2.3.0   | No          | N/A |
| linear_progress_bar| 3.0.0   | No          | N/A |
| flutter_slidable   | 4.0.3   | No          | N/A |
| intl.              | 0.20.3  | No.         | N/A |
| encrypt            | 5.0.1   | No          | N/A |
| dio                | 5.11.1  | No          | N/A |
---

## Native packages - SPM Supported

| Package                       | Version | SPM |
|---|---|---|---|---|---|---|---|---|---|---|---|
| shared_preferences.           | 2.5.5   | YES |
| url_launcher.                 | 6.3.2.  | YES |
| fluttertoast                  | 10.0.0  | YES |
| firebase_core                 | 4.15.0  | YES |
| firebase_messaging            | 16.7.0  | YES |
| flutter_local_notifications   | 22.3.1  | YES |
| permission_handler            | 13.0.2  | YES |
| open_store:                   | 0.5.0   | YES |
| flutter_udid:                 | 4.1.6   | YES |
| package_info_plus             | 9.0.1   | YES |
| connectivity_plus             | 7.3.1   | YES |

---

## 3. Native Packages — SPM Blockers

### 3.1. `aad_oauth: 1.0.1`

**Dependency chain:**

```text
aad_oauth
└── flutter_secure_storage: 9.2.4
```

- **Issue:** `flutter_secure_storage 9.2.4` does not support SPM for iOS in the current project configuration.
- **Result:** CocoaPods fallback is required for this dependency.
- **Action:** Check newer versions of `aad_oauth` and `flutter_secure_storage` for SPM compatibility before upgrading.

### 3.2. `google_mlkit_entity_extraction: ^0.17.1`

- **Issue:** Does not support SPM for iOS in the current project configuration.
- **Related dependency:** `google_mlkit_commons`.
- **Result:** CocoaPods fallback is required for the related native dependencies.

### 3.3. `google_mlkit_text_recognition: ^0.17.1`

- **Issue:** Does not support SPM for iOS in the current project configuration.
- **Related dependency:** `google_mlkit_commons`.
- **Result:** CocoaPods fallback is required for the related native dependencies.

---

## 4. Important Notes

- A package without SPM support does not automatically prevent App Store submission.

- Flutter may use CocoaPods for plugins that do not support SPM, depending on the Flutter version and project configuration.

- Keep CocoaPods integration available while required plugins depend on it.
