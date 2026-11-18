[← Back to README](../../README.md)

## 12、 📤 Copy Results to the Robot

First click "Detect robot & cameras" on the left to read the robot ID, then click **Copy calibration to robot** above the task list on the right:

1. The program reads the existing `/home/unitree/calib/uniclib_calibration.json` on the robot
2. It compares RMS and P95 item by item with the latest local results; if the robot's result is clearly better it is highlighted in red and kept by default
3. For each item choose "Use new local" or "Keep robot's"
4. Click **Merge & copy selection**: everything is merged into one file and written to the robot; the old file is backed up as `uniclib_calibration.<time>.json`

* The robot ID is checked again before writing; on mismatch the copy is cancelled
* If the intrinsics used by the head stereo extrinsics differ from the left/right intrinsics about to be written (e.g. extrinsics used local intrinsics but you chose to keep the robot's old intrinsics), the dialog warns you and asks again before copying
