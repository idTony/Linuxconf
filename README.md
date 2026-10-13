
# Linux Configuration Practice

Linux 系統管理與網路組態練習專案，記錄 Linux 基礎操作、系統設定、網路服務部署及故障排除過程。

## 📌 專案目標

- 熟悉 Linux 基本操作與常用指令
- 學習使用者、群組及檔案權限管理
- 練習網路組態與防火牆設定
- 建立並測試 Linux 網路服務
- 記錄問題與故障排除方法

## 🖥️ 練習環境

| 項目 | 環境 |
|------|------|
| 虛擬化平台 | VMware Workstation |
| 作業系統 | Ubuntu、Debian、Rocky Linux、SUSE |
| 網路環境 | VMware VMnet |
| 操作方式 | CLI、SSH |

## 📂 專案結構

```text
linuxconf/
├── README.md
├── basic-commands/
│   └── commands.md
├── user-management/
│   └── users.md
├── network/
│   └── network-config.md
├── firewall/
│   └── firewall.md
└── services/
    ├── ssh.md
    └── dhcp.md
```

## 📚 練習內容

### 1. Linux 基礎指令

練習目錄切換、檔案管理與系統資訊查詢。

```bash
pwd             # 顯示目前工作目錄
ls -la          # 列出所有檔案及詳細資訊
cd /etc         # 切換目錄
mkdir test      # 建立目錄
cp file1 file2  # 複製檔案
```

### 2. 使用者與權限管理

```bash
sudo useradd -m leon
sudo passwd leon
id leon
chmod 755 script.sh
```

### 3. 網路組態

使用 Linux 指令檢查 IP、路由及網路連線。

```bash
ip addr
ip route
ping 8.8.8.8
ss -tuln
```

### 4. 防火牆設定

以 Ubuntu UFW 為例：

```bash
sudo ufw enable
sudo ufw allow ssh
sudo ufw status verbose
```

### 5. 網路服務部署

練習項目：

- SSH Server 安裝及遠端登入
- DHCP Server IP 位址分配
- DHCP Relay 跨網段轉送
- Linux IP Forwarding 路由功能

## 📝 練習紀錄

| 日期 | 練習主題 | 狀態 |
|------|----------|------|
| YYYY-MM-DD | Linux 基本指令 | ✅ 完成 |
| YYYY-MM-DD | 靜態 IP 設定 | ✅ 完成 |
| YYYY-MM-DD | SSH 遠端連線 | 🔄 進行中 |
| YYYY-MM-DD | DHCP Server | ⬜ 未開始 |

## 🔧 故障排除紀錄

### 問題：無法透過 SSH 連線

**可能原因：**
1. SSH Server 尚未啟動
2. 防火牆未開放 TCP 22
3. 虛擬機器網路設定錯誤

**檢查指令：**

```bash
sudo systemctl status ssh
sudo ufw status
ip addr
```
