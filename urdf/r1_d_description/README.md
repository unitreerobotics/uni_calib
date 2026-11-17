# R1D Description

`r1d.urdf` includes the Dex1 two-finger gripper adapted from
`g1_d_with_dex1_1.urdf`.

The gripper is mounted on each wrist through these chains:

- `left_wrist_yaw_link` -> `left_dex1_base_link`
- `right_wrist_yaw_link` -> `right_dex1_base_link`

Each side provides two prismatic finger joints with a `0` to `0.041 m`
travel range:

- `*_dex1_finger_joint_1`
- `*_dex1_finger_joint_2`

The gripper meshes are `Dex1_base_link.STL`, `Dex1_finger_link_1.STL`, and
`Dex1_finger_link_2.STL`; the optional wrist-mounted camera links are also
included in the URDF.
