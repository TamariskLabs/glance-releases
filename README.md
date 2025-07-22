# Glance LED Firmware Release
Firmware Releases for Glance LED OTA Updates

## Repo File Structure
### Project_Type : 
  - Each root folder represents a different project or product
  - Inside of each Project_Type folder should be a collection of folders that represent each Major Release.
  - Inside of each Project_Type folder should be a single json file ```release-info.json``` that contains the metadata of the latest firmware release

### Latest Firmware Meta Data File: ```release-info.json```
Example File

```
{
  "C5": {
    "version": "3.0.2",
    "url_to_firmware_binary": "https://raw.githubusercontent.com/TamariskLabs/glance-releases/main/glance-v3/v3.0/glance-c5_v3.0.2.bin",
    "build_date_utc": "2025-05-25",
    "build_time_utc": "15:31:22",
    "build_hash": "0x9c7e4b2d8f1a6e9c4f7b8d2e3a9f6c1b4d7e8f2a6c9b3f8d4e7a1c6b9f2",
    "git_commit_hash": "0xe3b0c44298fc1c149afbf4c8996fb92427ae41e4",
    "is_development_version": true
  },
  "S3": {
    "version": "3.0.3",
    "url_to_firmware_binary": "https://raw.githubusercontent.com/TamariskLabs/glance-releases/main/glance-v3/v3.0/glance-s3_v3.0.3.bin",
    "build_date_utc": "2025-05-25",
    "build_time_utc": "15:30:25",
    "build_hash": "0x9c7e4b2d8f1a6e9c4f7b8d2e3a9f6c1b4d7e8f2a6c9b3f8d4e7a1c6b9f1",
    "git_commit_hash": "0xe3b0c44298fc1c149afbf4c8996fb92427ae41e3",
    "is_development_version": true
  }
}
```

JSON Key Descriptions:
  - version: A string that holds the major, minor, patch version of the software.
  - url_to_firmware_binary: Download link to the firmware binary file.
  - build_data_utc: The date which the firmware was built. Format is "yyyy-mm-dd". (Produced by the build system).
  - build_time_utc: The time which the firmware was built.  Format is "24hr:mm:ss" (Produced by the build system).
  - build_hash: This is the md5 checksum of the firmware.  This is a uint8_t [32] element value.
  - git_commit_hash: A string value holding the git commit produced while deploying this firmware release.
  - is_development_version: If this is set to true, only units that are flashed with a setting of "is_development_firmware" equal to true will download this firmware.  (is_development_firmware parameter is located in the /spiffs/fusion_fw_manager.config file)
