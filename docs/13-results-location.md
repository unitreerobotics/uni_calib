[← 返回 README](../README_zh-CN.md)

## 13、 📁 结果保存在哪里

```
<保存目录>/
├─ <机器人编号>/                       每台机器人一个目录（实时采集）
│  ├─ device.json                      机器人信息
│  ├─ images/<相机>/<时间>/            采集的图像
│  ├─ intrinsic/<相机>/<时间>/calib.json, quality.json
│  ├─ extrinsic/head_stereo/…
│  ├─ handeye/<left_arm|right_arm>/…
│  └─ uniclib_calibration.json         最近一次拷贝到机器人的合并文件
├─ intrinsic/custom/                   自定义数据内参
├─ extrinsic/custom/                   自定义数据外参
└─ handeye/custom/<时间>/handeye.json  自定义数据手眼
```

机器人编号格式为 `Jetson模组序列号_eth0 MAC`，连接机器人时自动读取。

`calib.json` 主要字段：`camera_model`（`Pinhole` / `Fisheye`，Fisheye 即 Kannala-Brandt KB4）、`image_size`（[高, 宽]）、`intrinsic`（fx, fy, cx, cy + 畸变系数）、`rms_reproj_err_px`。

合并文件 `uniclib_calibration.json` 中的 `handeye` 段包含 `T_wrist_cam`（参考 link 为 `<left|right>_wrist_yaw_link`）和关节零位。

### 设置与日志

| 内容 | 位置 |
|---|---|
| 网页设置 | `~/.config/uniclib/`（可用环境变量 `UNICLIB_CONFIG_DIR` 修改） |
| 日志 | `~/.config/uniclib/logs/uniclib.log` |

页面上的错误提示带有错误编号，反馈问题时请附上该编号和日志文件。
