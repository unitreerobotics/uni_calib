[← Back to README](../../README.md)

## 14、 ❓ FAQ

| Symptom | What to do |
|---|---|
| The AppImage does nothing | Run it from a terminal to see the output; if FUSE is missing, add `--appimage-extract-and-run` |
| Port already in use | The next free port is used automatically; trust the address printed in the terminal |
| Cannot connect to the image service | Make sure TeleImager is running on the robot; check host / port on the left, or click "Detect robot & cameras" |
| A camera is not detected | Check the camera configuration of TeleImager on the robot (see the TeleImager documentation) |
| "The robot runs TeleImager v2.1.0 or later … not supported yet", or no cameras detected at all | The robot is running TeleImager v2.1.0 or later (not supported yet). Switch to commit `940fd69` as described in 3.1 and use a config file in that version's format |
| Hand-eye says the URDF "matches no supported robot model" or "the joint check failed" | The robot model is not supported (or the wrong URDF was chosen), see 9.5 |
| "Robot ID not read yet" | Check that you can SSH into the robot, or click "Detect robot & cameras" |
| Extrinsics say inner corners must be non-square | Use a board with different horizontal / vertical square counts (e.g. 9×12), or switch to a ChArUco board |
| ChArUco board not detected / too few corners | Check that ArUco dictionary, marker ratio and square counts match the printed board (print the PDF from "Download board"); bring the board closer or use larger squares (about 35 px per square or more) |
| Head stereo says no usable intrinsics | Calibrate the head left and right intrinsics first (error passed, camera model matching the current setting) |
| Hand-eye says no wrist intrinsics | Calibrate the wrist intrinsics and copy them to the robot first |
| Hand-eye gets no joint data / hold keeps releasing | Make sure the PC is on the robot's subnet over a wired connection; if needed, enter the PC's interface towards the robot in "DDS interface" |
| R1-A7-D does not resume normal motion after calibration | Calibration switched it into debug mode, which is not undone automatically; reboot the robot |
| R1-A7-D says the lift is not homed | Home the lift first, then start hand-eye calibration |
| Capture never finishes by itself | Fill in the missing regions or poses as prompted, or click "Finish & calibrate" |
| Robot ID mismatch when copying | You are connected to a different robot than the results belong to; check the address and read the ID again |
| Result "Not usable" or large error | Check against Section 4: corners / edges covered, both left/right and up/down tilt present, board flat without glare, square size accurate; capture more and recalibrate |
| Calibration fails with an error code | Check the board settings and camera model, add images at more positions / angles / distances and retry |
