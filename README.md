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
  "version": "3.0.2",
  "url_to_firmware_binary": "https://raw.githubusercontent.com/TamariskLabs/glance-releases/main/glance-v2/v3.0/glance-v2_v3.0.1.bin",
  "build_date_utc": "2025-05-25",
  "build_time_utc": "15:31:22"
  "build_hash": 9123417129549,
  "git_commit_hash": "0xA0D109",
  "is_development_version": false
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
