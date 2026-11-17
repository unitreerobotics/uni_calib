# URDFs for Hand-eye Calibration

English | [中文](README_zh-CN.md)

For hand-eye calibration (live from robot), select the URDF of your robot on the page. This folder contains only the URDFs and the meshes they reference; they are not bundled in the AppImage.

| Folder | URDF | Robot | Notes |
|---|---|---|---|
| `g1_description/` | `g1_29dof_rev_1_0.urdf` | G1 (29 DoF) | Source in `SOURCE.txt` (unitree_ros), unmodified |
| `g1_d_description/` | `g1_d.urdf` | G1_D | Unmodified |
| `r1_d_description/` | `r1_d_with_dex1_1.urdf` | R1-A7-D (Dex1 gripper) | Includes wrist camera links (`*_dex1_camera_link`) for comparison with the calibration result |

* The robot model is recognized from the URDF's `<robot name>` (`g1_29dof*` → G1, `G1_D*` → G1_D, `R1_A7_D*` / `R1_D*` → R1-A7-D, case-insensitive), then each joint on the kinematic chain is checked; if the name is not recognized, matching is done by joints only.
* Forward kinematics uses only the URDF file itself; `meshes/` is used only by the result's "3D view".
* End effectors defined in the URDF are excluded from calibration and are not displayed in the 3D viewer.
* Meshes are looked up via the relative path `meshes/<file>` given in the URDF; when moving folders, keep the URDF and `meshes/` in the same relative position.
