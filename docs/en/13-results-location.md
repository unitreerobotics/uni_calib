[← Back to README](../../README.md)

## 13、 📁 Where Results Are Saved

```
<save folder>/
├─ <robot ID>/                         one folder per robot (live capture)
│  ├─ device.json                      robot information
│  ├─ images/<camera>/<time>/          captured images
│  ├─ intrinsic/<camera>/<time>/calib.json, quality.json
│  ├─ extrinsic/head_stereo/…
│  ├─ handeye/<left_arm|right_arm>/…
│  └─ uniclib_calibration.json         merged file last copied to the robot
├─ intrinsic/custom/                   custom-data intrinsics
├─ extrinsic/custom/                   custom-data extrinsics
└─ handeye/custom/<time>/handeye.json  custom-data hand-eye
```

The robot ID has the form `<Jetson module serial>_<eth0 MAC>` and is read automatically when connecting.

Main fields of `calib.json`: `camera_model` (`Pinhole` / `Fisheye`, where Fisheye is Kannala-Brandt KB4), `image_size` ([height, width]), `intrinsic` (fx, fy, cx, cy + distortion coefficients), `rms_reproj_err_px`.

The `handeye` section of the merged `uniclib_calibration.json` holds `T_wrist_cam` (reference link `<left|right>_wrist_yaw_link`) and the joint offsets.

### Settings and logs

| Item | Location |
|---|---|
| Page settings | `~/.config/uniclib/` (override with the `UNICLIB_CONFIG_DIR` environment variable) |
| Log | `~/.config/uniclib/logs/uniclib.log` |

Error messages on the page carry an error code; please include the code and the log file when reporting a problem.
