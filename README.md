# hsr_ros2_ws

HSRのROS2パッケージをまとめたワークスペース  
underlayとして利用

## セットアップ

```bash
# サブモジュールを含めてクローン
git clone --recurse-submodules git@github.com:keisei4064/hsr_ros2_ws.git

# 実機用コードは無視
cd hsr_ros2_ws/
touch src/tmc_drivers/tmc_pgr_camera/COLCON_IGNORE
touch src/hsrb_launch/hsrb_robot_launch/COLCON_IGNORE

# 依存関係のインストール
cd ~/hsr_ros2_ws
rosdep update
rosdep install --from-paths . -y --ignore-src

# ビルド
colcon build --symlink-install
```

## 参考

> [hsr-project/hsr\_ros2\_doc](https://github.com/hsr-project/hsr_ros2_doc)
