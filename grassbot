#!/bin/bash

# 更新包列表并安装 Python3 和 pip
echo "Updating package list and installing Python3 and pip..."
sudo apt update && sudo apt install -y python3 python3-pip screen

# 克隆仓库并进入项目目录
echo "Cloning the grassbot repository..."
git clone https://github.com/Semutireng22/grassbot.git
cd grassbot || { echo "Failed to enter grassbot directory"; exit 1; }

# 安装 Python 依赖项
echo "Installing required Python packages..."
pip3 install websockets_proxy loguru aiohttp aiohttp_socks

# 创建默认的配置文件（main.py）
echo "Configuring main.py for user input..."
cat <<EOL > main.py
# Grassbot configuration file

# Replace '_user_id' with your user ID and 'socks5_proxy_list' with your proxy if necessary
_user_id = 'your_user_id_here'
socks5_proxy_list = []
# Other configurations as needed

# Main code would follow...
EOL

# 提示用户编辑 main.py 文件
echo "Opening main.py for configuration. Please replace 'your_user_id_here' with your actual user ID."
sleep 1
nano main.py

# 启动 screen 会话并运行程序
echo "Starting the grassbot in a screen session..."
screen -dmS grassbot_session bash -c "python3 main.py"

# 显示完成信息
echo "Grassbot setup is complete! The program is running in a screen session named 'grassbot_session'."
echo "Use 'screen -r grassbot_session' to reattach to the session."
