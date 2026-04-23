---
hide:
  - navigation
---

# 1Panel Changelog

## Release Notes

### v2.1.10

2026‑04‑23

!!! note "Bug Fixes"

    - **Agents**: Fixed an issue where some model accounts in Hermes Agent were invalid

### v2.1.9

2026‑04‑23

!!! note "New Features"

    - **Agents**: Added Hermes Agent support
    - **Databases**: Added MongoDB management support
    - **File Browser**: Added file history management

!!! note "Improvements"

    - **App Store**: Optimized change detection logic for app Compose files
    - **Agents**: Added website unbinding support
    - **Agents**: Optimized the OpenClaw channel bot addition workflow
    - **Websites**: Optimized website name badge styles
    - **Containers**: Optimized container data handling and status synchronization logic
    - **File Browser**: Added support for stopping compression tasks and enhanced compression capabilities
    - **File Browser**: Added Dockerfile language support for file editing
    - **File Browser**: Added optional header configuration for file sharing to improve localization support
    - **File Browser**: Enhanced metadata validation capabilities for file and recycle bin services
    - **Panel Settings**: Improved AWS S3 object storage compatibility and connection stability
    - **System**: Optimized system table styles

!!! note "Bug Fixes"

    - **Runtime**: Fixed an issue where directories could still be modified while editing the runtime environment
    - **File Browser**: Fixed an issue where files shared via QR codes could not be downloaded
    - **Firewall**: Fixed an issue where firewall rule descriptions could not be modified
    - **Firewall**: Fixed abnormal listening status display on the firewall page
    - **Tamper**: Fixed translation errors in some languages

### v2.1.8

2026‑04‑10

!!! note "New Features"

    - **App Store**: Added a unified switch for external port access
    - **Agents**: Added role management support
    - **Agents**: Added support for multiple accounts per channel
    - **Agents**: Added website binding support
    - **Agents**: Added remark support
    - **Agents**: Added ClawHub China mirror support in the skill marketplace
    - **File Browser**: Added AI search support
    - **File Browser**: Added file link sharing support
    - **Panel Settings**: Added Bark alert channel support

!!! note "Improvements"

    - **Overview**: Optimized the app card layout
    - **Agents**: Added more channel configuration options
    - **Agents**: Switched QQ and Feishu channels to official plugins
    - **Agents**: Updated the default model configuration
    - **Agents**: Improved the model-related menu structure
    - **Agents**: Optimized OpenClaw plugin setup options
    - **Agents**: Added support for OpenClaw plugin uninstallation and upgrades
    - **Agents**: Added backup model configuration support for OpenClaw
    - **Agents**: Optimized OpenClaw DingTalk channel settings
    - **Agents**: Improved API call stability
    - **Models**: Improved model pull log display effects
    - **Models**: Added vLLM status sync logic
    - **Websites**: Optimized the layout of the OpenResty Other Settings page
    - **Websites**: Improved validation mechanisms when deleting OpenClaw websites
    - **Websites**: Simplified website binding options
    - **Runtime**: Improved script selection for the Node.js runtime
    - **File Browser**: Improved file operation stability
    - **SSH Management**: Improved the SSH config editing experience
    - **Terminal**: Improved the AI terminal update experience
    - **Panel Settings**: Added suspicious IP protection for two-factor authentication login
    - **System**: Optimized internationalized copy
    - **System**: Improved request handling and session management experience
    - **System**: Optimized auth lock handling and login feedback experience
    - **System**: Improved login security checks and entrance access experience
    - **System**: Improved code filtering mechanisms in development
    - **System**: Improved dialog display and interactions
    - **System**: Improved code editor loading speed

!!! note "Bug Fixes"

    - **Overview**: Fixed abnormal monitoring delta data display
    - **Agents**: Fixed incorrect OpenClaw Discord channel configuration
    - **Certificates**: Fixed abnormal certificate auto-renewal logic
    - **Panel Settings**: Fixed an issue where proxy checks were still performed after the proxy was disabled
    - **Panel Settings**: Fixed an issue where users could not return to the login page when two-factor authentication required a captcha

### v2.1.7

2026‑03‑26

!!! note "Bug Fixes"

    - **Agents**: Fixed search issues on the Installed Skills page
    - **System**: Fixed abnormal menu display in some languages

### v2.1.6

2026‑03‑26

!!! note "New Features"

    - **Agents**: Added skill management support
    - **Agents**: Added WeChat channel support
    - **Agents**: Added DingTalk channel support
    - **Agents**: Added Xiaomi support for model accounts
    - **Agents**: Added custom npm registry support
    - **Agents**: Added model pool configuration for model accounts
    - **Agents**: Added overview information support
    - **Agents**: Added main config file editing support
    - **Terminal**: Added AI terminal support

!!! note "Improvements"

    - **Agents**: Optimized plugin installation logic
    - **Agents**: Optimized the OpenClaw terminal page
    - **Agents**: Optimized validation logic for MiniMax model accounts
    - **Websites**: Added an option to skip SSL certificate verification in reverse proxy settings
    - **Containers**: Changed the default container directory entry path to the working directory
    - **Containers**: Added path bar navigation support in file management
    - **Containers**: Added a prompt when the Compose file is missing
    - **File Browser**: Optimized editor tab management and file handling logic
    - **File Browser**: Added validation and error messages for remote download URLs
    - **File Browser**: Added favorites to the file selection list page
    - **File Browser**: Added cancel support for remote downloads
    - **File Browser**: Moved tooltips to the left for better visibility
    - **File Browser**: Added total progress display for file uploads
    - **File Browser**: Preserved the original modification time after file extraction
    - **Terminal**: Optimized the quick command selection page style for the host terminal
    - **Multi-Node**: Optimized node dropdown page styles
    - **Multi-Node**: Added a multi-node overview entry on the node selection page
    - **System**: Unified sidebar menu item heights

!!! note "Bug Fixes"

    - **App Store**: Fixed missing form fields when installing apps in some languages
    - **Agents**: Fixed an issue where the access address could not be set to a domain when creating OpenClaw agents
    - **Websites**: Fixed a failure when creating OpenClaw one-click deployment websites
    - **Websites**: Fixed extra whitespace in the default Composer command list
    - **Websites**: Fixed an issue where websites could not be started after being stopped
    - **Certificates**: Fixed missing options on the column selection page
    - **Containers**: Fixed abnormal Compose status display in some scenarios
    - **File Browser**: Fixed an issue where gz files could not be previewed after extraction
    - **Terminal**: Fixed an issue where the scroll speed setting did not take effect in the container terminal
    - **Toolbox**: Fixed an issue where unchecked items were still cleaned up during system upgrade backup cleanup
    - **Logs**: Fixed abnormal display for some operation logs
    - **Panel Settings**: Fixed an issue where entering an incorrect 2FA code redirected users to the login page
    - **Panel Settings**: Fixed an issue where file uploads failed for Qiniu backup accounts
    - **System**: Fixed abnormal overview status display when the panel theme followed system color mode changes
    - **System**: Fixed the abnormal display of the More button in table action columns on first entry

### v2.1.5

2026‑03‑17

!!! note "New Features"

    - **Agents**: Added WeCom Channel support
    - **Agents**: Added secure access address configuration
    - **Containers**: Added image update support
    - **Containers**: Added container file management
    - **Containers**: Added backup and restore for containers and Compose

!!! note "Improvements"

    - **Overview**: Added agents overview info with quick jump
    - **Agents**: OpenClaw now enables HTTPS access by default
    - **Agents**: Improved validation when adding Gemini model accounts
    - **Agents**: Added icons for agent types
    - **Panel Settings**: Improved Docker proxy setting prompt

!!! note "Bug Fixes"

    - **Local Models**: Fixed navigation failures when switching between some pages
    - **Containers**: Fixed image pull failures when creating Compose with private registries
    - **System**: Fixed failures when building from source

### v2.1.4

2026‑03‑11

!!! note "New Features"

    - **Agents**: Added QQ Channel support
    - **Agents**: Added OpenRouter model account support
    - **Local Models**: Added vLLM management support
    - **File Browser**: Added column show/hide support for the file list

!!! note "Improvements"

    - **Agents**: Optimized saving logic for custom model name configuration
    - **Databases**: Optimized PostgreSQL database deletion logic
    - **Containers**: Optimized Docker restart prompt message

!!! note "Bug Fixes"

    - **Containers**: Fixed an issue where the env file could be cleared when manually pasting the orchestration path
    - **Logs**: Fixed abnormal log display for some child nodes
    - **Panel Settings**: Fixed inability to receive emails when the sender name is Chinese
    - **System**: Fixed missing translations in some languages

### v2.1.3

2026‑03‑06

!!! note "Improvements"

    - **Agents**: Adapted to the latest OpenClaw configuration format
    - **Certificates**: Certificate selector now displays issuer and expiration time
    - **Panel Settings**: Optimized prompt information on the panel SSL page

!!! note "Bug Fixes"

    - **App Store**: Fixed abnormal sorting behavior for newly installed apps
    - **Websites**: Fixed errors when adding reverse proxy in some scenarios
    - **Containers**: Fixed container orchestration creation failures in some scenarios
    - **System**: Fixed several known issues in the international edition
    - **System**: Fixed menu flickering in some pages when switching language

### v2.1.2

2026‑03‑04

!!! note "New Features"

    -  **App Store**: Added installed app sorting support
    -  **Agents**: Added support for creating CoPaw agents
    -  **Agents**: Added Telegram channel support
    -  **Agents**: Added Discord channel support
    -  **Agents**: Added browser configuration support
    -  **Agents**: Added timezone configuration support
    -  **Agents**: Added API type selection for Ollama model accounts
    -  **Agents**: Added Z.ai model account support
    -  **Agents**: Added Ark Coding Plan model account support
    -  **Agents**: Added Alibaba Bailian Coding Plan model account support
    -  **Agents**: Added custom model account support for anthropic-messages API type
    -  **Certificates**: Added Technitium support for DNS accounts
    -  **Terminals**: Added custom font support
    -  **Terminals**: Added custom foreground and background color support
    -  **Settings**: Added panel runtime region switching support

!!! note "Improvements"

    -  **App Store**: Optimized remote app sync logic
    -  **App Store**: Optimized installed app card display style
    -  **Agents**: Added optional credential retention when creating model accounts
    -  **Agents**: Preserved Feishu account mapping during configuration updates
    -  **Agents**: Optimized Kimi Coding model account creation logic
    -  **WebSites**: Optimized website proxy API and log handling
    -  **WebSites**: Optimized domain handling logic during website creation
    -  **WebSites**: Added wildcard certificate issuance support for primary domains
    -  **GPU Monitoring**: Optimized selected-state style
    -  **Databases**: Added one-click full URL copy for database connection info
    -  **Containers**: Optimized container orchestration page layout
    -  **Containers**: Added `extra_hosts` support
    -  **Containers**: Optimized container log viewer and improved log download options
    -  **File Browser**: Optimized name column width
    -  **File Browser**: Added last-opened-file memory
    -  **File Browser**: Optimized file extraction workflow
    -  **Monitoring**: Optimized monitoring interval prompt text
    -  **Settings**: Optimized refresh-time prompt for two-factor verification
    -  **Settings**: Enhanced passkey login capability
    -  **System**: Made sort parameters optional for some APIs to support third-party systems
    -  **System**: Updated Prettier config to avoid unnecessary formatting
    -  **System**: Optimized i18n copywriting
    -  **System**: Completed partial system security updates
    -  **System**: Optimized SQLite connection configuration
    -  **System**: Optimized invocation patterns for some system commands
    -  **System**: Added cache mechanism to some system settings for better performance

!!! note "Bug Fixes"

    -  **App Store**: Fixed app restore failures in some scenarios
    -  **App Store**: Fixed abnormal README loading for some apps
    -  **WebSites**: Fixed inability to restart sub-sites after stopping
    -  **WebSites**: Fixed inability to operate website reverse proxy under special configurations
    -  **WebSites**: Fixed errors when deleting some website types
    -  **Databases**: Fixed startup failures after app restore in some scenarios
    -  **Containers**: Fixed Compose creation failures in some scenarios
    -  **File Browser**: Fixed abnormal preview drawer opening when clicking compressed files
    -  **Terminals**: Fixed extra blank lines after modifying terminal settings
    -  **Website Monitoring**: Fixed date-based search failures in some scenarios
    -  **Logs**: Fixed abnormal login log recording in some scenarios

### v2.1.1

2026‑02‑25

!!! note "New Features"

    - **Agent**: Support custom model accounts
    - **Agent**: Adapt to latest OpenClaw version

### v2.1.0

2026‑02‑12

!!! note "New Features"

    - **Overview**: Notes module
    - **AI**: OpenClaw agent management
    - **SSL**: Custom ACME account validation
    - **Container**: Bulk import images
    - **File**: Notes support in File Manager
    - **WAF**: Export block records
    - **Settings**: WeCom, DingTalk, Feishu alerts
    - **System**: Key‑based login

!!! note "Improvements"

    - **Overview**: Optimize app icon loading
    - **App Store**: Optimize remote app update logic
    - **App Store**: Optimize icon caching
    - **App Store**: Improve installed app modal
    - **App Store**: Optimize OpenResty upgrade
    - **Website**: 3‑level directory support
    - **Website**: Optimize redirects for non‑443 ports
    - **Website**: Optimize browser cache for proxies
    - **Website**: Show parent website in list
    - **Website**: Disable redirects for stopped sites
    - **Website**: Validate name changes
    - **SSL**: Retry mechanism for certificate issuance
    - **Container**: Timestamps in logs
    - **Container**: Force pull option in Compose
    - **File**: Stream download to reduce memory
    - **Monitor**: Align dropdowns
    - **Firewall**: Show process using port
    - **Toolbox**: Optimize virus scan status
    - **Cluster**: Dark theme styling
    - **Cluster**: App upgrade on cluster overview
    - **Settings**: Optimize certificate reload in Mux mode
    - **System**: Validate API parameters

!!! note "Bug Fixes"

    - **Overview**: Hostname cache refresh
    - **App Store**: Hide password in plaintext
    - **Website**: Redirect rule display after disable
    - **Website**: Wrong HTTPS port for non‑443
    - **SSL**: IPv6 certificate issue
    - **Container**: Compose env load failure
    - **File**: Bulk chmod timeout
    - **Monitor**: Default NIC/disk not applied
    - **Terminal**: Leftover sshd processes
    - **Cron**: Task execution issues
    - **Toolbox**: Scan status display
    - **Cluster**: Node edit failure
    - **Monitor**: Wrong time display
    - **Monitor**: List page crash
    - **Logs**: Incorrect operation log after param change
    - **Settings**: OneDrive backup failure
    - **System**: OpenResty reinstall migration
    - **System**: System update failure

### v2.0.17

2026‑01‑16

!!! note "New Features"

    - **App Store**: Multi‑node deployment
    - **SSL**: Porkbun DNS support
    - **Database**: Custom backup params for MySQL
    - **Cluster**: Node overview
    - **Cluster**: Proxy for adding nodes
    - **Toolbox**: Clean unlinked backups
    - **Toolbox**: Clean website logs
    - **Toolbox**: Clean old app packages
    - **Settings**: Mux mode with SSL

!!! note "Improvements"

    - **Website**: UDP listen for TCP/UDP proxy
    - **SSL**: IP cert chain config
    - **Database**: Cache default connection
    - **Disk**: Continue boot on mount failure
    - **Toolbox**: Limit log lines
    - **Settings**: Revert AWS S3 SDK for compatibility
    - **Settings**: Add panel name/IP to email alerts
    - **System**: API timeout control
    - **System**: Stable Markdown editor
    - **System**: Log highlight regex
    - **System**: Security entrance validation

!!! note "Bug Fixes"

    - **App Store**: App icon display
    - **Website**: Duplicate HTTPS redirect
    - **Website**: 404 page sync
    - **Website**: PHP redirect loop
    - **Website**: HTTPS redirect URL error
    - **SSL**: Custom DNS not working
    - **SSL**: Wildcard validation failure
    - **GPU**: History refresh display
    - **Container**: Wrong image delete count
    - **Container**: Create Compose with empty list
    - **Container**: Reset edit on auto‑refresh
    - **File**: Terminal path with spaces
    - **Firewall**: iptables display
    - **Firewall**: ping rule persist
    - **Monitor**: Time filter inaccuracy
    - **Settings**: Too large snapshot restore
    - **Settings**: Email subject garbled
    - **Settings**: Snapshot failed with many images
    - **Settings**: Backup account endpoint echo
    - **Settings**: 444 not closing connection
    - **Settings**: SMS alert failure
    - **System**: Master view slave log error
    - **System**: Blank bottom on expand

### v2.0.16

2025‑12‑25

!!! note "New Features"

    - **Website**: TCP/UDP proxy
    - **Website**: Bulk SSL assignment
    - **SSL**: IP certificate support
    - **GPU**: Real‑time & history monitor
    - **Database**: Restore timeout
    - **Terminal**: Reset default login
    - **Firewall**: Port range forward
    - **Cluster**: Central app management
    - **System**: Switch node in Task Center

!!! note "Improvements"

    - **Website**: HTTP→HTTPS for non‑443
    - **Website**: UI/UX for creation
    - **Website**: Unicode IDN domains
    - **Website**: Left menu scroll
    - **Runtime**: PHP extension install tips
    - **Runtime**: PHP lz4 extension
    - **Container**: Delete confirm
    - **Container**: Compose .env support
    - **Container**: Compose creation
    - **Container**: Resource styling
    - **Container**: Image dependency message
    - **File**: View >10MB files
    - **File**: Upload button layout
    - **Firewall**: Allow UDP 443 (HTTP/3)
    - **Terminal**: Host select modal
    - **WAF**: IP group sync message
    - **Settings**: Preserve custom watermark
    - **System**: Toast position
    - **System**: 2FA input experience
    - **System**: 1pctl rollback message
    - **System**: SSH session logic
    - **System**: Clean temp update files
    - **System**: Swagger format
    - **System**: Simplify process data
    - **System**: Network & WebSocket performance
    - **System**: Process & connection page
    - **System**: Browser cache & i18n

!!! note "Bug Fixes"

    - **App Store**: MySQL charset selection
    - **App Store**: Local app major update config
    - **Website**: >100 redirects not shown
    - **Website**: One‑click deploy failure
    - **Website**: Settings timeout
    - **Database**: PostgreSQL backup failure
    - **Container**: Multi‑Compose YAML error
    - **Container**: Incomplete log on Compose fail
    - **Container**: Compose creation failure
    - **File**: Delete missing symlink error
    - **Firewall**: Forward init status
    - **Firewall**: UFW IPv6 error
    - **Cron**: Manual stop not working
    - **Cluster**: Heterogeneous slave update
    - **Monitor**: Spider count wrong
    - **Settings**: Snapshot local app backup
    - **Settings**: HTTP/HTTPS proxy container error
    - **System**: Monitor write block
    - **System**: Task name i18n
    - **System**: Task log garbage
    - **System**: File picker focus lost
    - **System**: Version update failure

### v2.0.15

2025‑12‑08

!!! note "Improvements"

    - **Container**: Compose UI styling
    - **Container**: Volume/device cleanup close
    - **System**: Remove invalid stat check

!!! note "Bug Fixes"

    - **App Store**: Update diff highlight
    - **App Store**: Remote MySQL root password
    - **Runtime**: Missing redirect after install
    - **Database**: PostgreSQL remote add failure
    - **Database**: PostgreSQL special char backup
    - **Container**: Compose directory redirect
    - **Container**: Compose log cleanup
    - **Container**: Compose/container status sync
    - **Process**: Empty search not refresh
    - **Cluster**: Slave upgrade failure
    - **System**: Captcha function

### v2.0.14

2025‑12‑04

!!! note "New Features"

    - **SSL**: AlibabaCloud ESA DNS
    - **SSL**: Amazon Route 53 DNS
    - **Database**: MySQL charsets & collation
    - **Database**: PostgreSQL 18 remote
    - **Container**: Multi‑network
    - **Container**: Favorite container/image
    - **Container**: Notes for containers
    - **GPU**: Metric reports
    - **Cron**: Multiple URLs for visit task

!!! note "Improvements"

    - **Overview**: CPU metrics detail
    - **Overview**: Distro info logic
    - **Overview**: Data cache
    - **App Store**: Home load performance
    - **App Store**: Local app RAM info
    - **App Store**: MySQL charset/collation
    - **Container**: Compose list UI
    - **Container**: Compose create log
    - **Container**: Network page style
    - **Container**: Async disk usage
    - **Container**: Copy raw config
    - **Container**: Auto‑refresh after reclaim
    - **File**: Path protection
    - **File**: Terminal quick command style
    - **Firewall**: Rule load performance
    - **Process**: Detail fields
    - **Disk**: Format flow
    - **System**: gzip for large response
    - **System**: File save error handling
    - **System**: HTTP status handling
    - **System**: AWS SDK v2
    - **System**: Log queue size
    - **System**: Language init
    - **System**: Immutable cache
    - **System**: Database config
    - **System**: Swagger lazy load
    - **System**: gzip for log API
    - **System**: Log read logic
    - **System**: System info logic
    - **System**: High‑usage process load
    - **System**: Terminal WebSocket buffer
    - **System**: App list memory

!!! note "Bug Fixes"

    - **Overview**: Uptime display on fast refresh
    - **App Store**: Compose change affect list
    - **App Store**: SQL Server version
    - **Runtime**: Edit port failure
    - **Runtime**: PHP extension uninstall
    - **Database**: PostgreSQL 18 settings page
    - **File**: Symlink creation
    - **Firewall**: iptables persist
    - **SSH**: Autostart status
    - **Toolbox**: Daemon page timeout
    - **Toolbox**: Scan status wrong
    - **Settings**: WebDAV init connect
    - **Settings**: Snapshot agent not restart
    - **Settings**: Snapshot get image error
    - **Settings**: Backup down log display
    - **System**: File open crash
    - **System**: X-Forwarded-For IP bypass
    - **System**: Login captcha bypass
    - **System**: Update service path

### v2.0.13

2025‑11‑20

!!! note "New Features"

    - **App Store**: App migrate node
    - **Website**: Bulk group
    - **Database**: Backup encryption
    - **Container**: Compose import/export
    - **Container**: Disk usage overview
    - **Container**: Build args
    - **File**: Editor new file/folder
    - **Monitor**: Process info
    - **Monitor**: Disk I/O select device
    - **Firewall**: iptables support
    - **Firewall**: Rule import/export
    - **Cron**: Clear all website logs
    - **Cron**: Sync WAF IP group
    - **Cluster**: Slave sync upgrade
    - **Cluster**: Import license on add
    - **Cluster**: Proxy for node request
    - **System**: OpenWRT/Alpine (no systemctl)

!!! note "Improvements"

    - **Overview**: Hide sensitive info
    - **Overview**: Real‑time process
    - **App Store**: Local app arch
    - **App Store**: Installed app name
    - **App Store**: Delete app DB detect
    - **App Store**: Install UI
    - **App Store**: Compose diff
    - **App Store**: Upgrade Compose check
    - **Website**: Proxy cache display
    - **Website**: Site code length
    - **Website**: PHP config logic
    - **Website**: Certificate security
    - **Website**: Auto SSL on HTTPS
    - **Website**: LB fail_timeout
    - **Website**: Bulk delete
    - **Runtime**: extra_hosts
    - **Runtime**: Port mapping
    - **Container**: Command input
    - **Container**: Detail tab view
    - **Container**: Env hint
    - **Container**: Background task
    - **Container**: Network tab view
    - **Container**: Copy image name
    - **Container**: Disable IP on invalid net
    - **Container**: Terminal resize
    - **Container**: Cleanup log
    - **File**: Right drawer for more actions
    - **File**: Multi‑tab start path
    - **Monitor**: Shorter interval
    - **Disk**: Detection logic
    - **Disk**: LVM detect
    - **Terminal**: New connect modal
    - **Terminal**: Quick command select
    - **Cron**: Not run status
    - **WAF**: Map load
    - **WAF**: Block HTTP detail
    - **Settings**: License master name
    - **Settings**: S3 region select
    - **System**: Dynamic i18n
    - **System**: Typo fixes
    - **System**: Cron name validate
    - **System**: Upgrade/rollback logic
    - **System**: Regex refactor
    - **System**: Docker check before restart

!!! note "Bug Fixes"

    - **Overview**: Space path display
    - **App Store**: Upgrade notice
    - **App Store**: Container search filter
    - **Website**: Cert note lose domain
    - **Website**: Log UA display
    - **Website**: OperateProxy clean misuse
    - **Website**: One‑click deploy load
    - **SSL**: Push lose domain
    - **Runtime**: PHP extension install
    - **Database**: postgres sync
    - **Container**: Dark theme edit page
    - **Monitor**: Settings title
    - **Process**: Network count
    - **SSH**: Config highlight
    - **Cron**: Special char name fail
    - **Monitor**: First read
    - **Settings**: Tab switch
    - **Settings**: Tab delete redirect
    - **Settings**: Email user send fail
    - **Settings**: Menu drag
    - **Settings**: HTTP/HTTPS proxy error
    - **Offline**: Offline update lose version
    - **System**: Enter submit desc

### v2.0.12

2025‑10‑22

!!! note "New Features"

    - **Website**: Bulk actions
    - **SSL**: OVH DNS
    - **SSL**: ACME-DNS
    - **SSL**: Upload local cert
    - **Runtime**: PHP slow log
    - **Runtime**: PHP daemon env
    - **Runtime**: Node.js pm2
    - **Runtime**: PHP extension source
    - **AI**: TensorRT LLM
    - **Database**: DB terminal
    - **Terminal**: Quick command import/export
    - **File**: Image/video convert
    - **SSH**: Authorized keys
    - **Cluster**: External panel
    - **Cluster**: Custom master name
    - **Settings**: Spanish
    - **Settings**: Watermark
    - **Settings**: Menu drag sort
    - **Settings**: Email SMTP user

!!! note "Improvements"

    - **Overview**: Quick setting tooltip
    - **Overview**: Resource status style
    - **Overview**: Path alias
    - **App Store**: Pull logic
    - **App Store**: Edit button style
    - **App Store**: Local app no local prefix
    - **App Store**: URL validate
    - **Website**: CORS
    - **Website**: OpenResty conf
    - **Website**: Delete DB on site delete
    - **Website**: Quick rename
    - **Website**: Nginx quick comment
    - **Website**: Remember last type
    - **Website**: Speed limit tooltip
    - **SSL**: List ID
    - **SSL**: Manual renew local
    - **Runtime**: PHP extension flow
    - **Runtime**: PHP default conf
    - **Runtime**: PHP timeout
    - **Runtime**: PHP daemon log
    - **Database**: Sync password mask
    - **Container**: Bulk pull
    - **Container**: Image tag bulk
    - **Container**: macvlan parent NIC
    - **Container**: Volume shared
    - **File**: Favorite jump
    - **File**: Terminal quick command
    - **Firewall**: Forward inbound if
    - **SSH**: Key edit
    - **Process**: Performance
    - **Process**: Network performance
    - **Process**: Style
    - **Cron**: Border
    - **Cron**: Python2/3
    - **Cron**: Script auto sync
    - **Cron**: Manual stop Shell
    - **Toolbox**: Scan timeout
    - **Toolbox**: Swap background task
    - **Cluster**: IPv6 node
    - **Tamper**: Background task
    - **Tamper**: Input tooltip
    - **Tamper**: Message
    - **Tamper**: Force off
    - **Tamper**: Status
    - **Tamper**: File list
    - **Settings**: Proxy check
    - **System**: Backup status
    - **System**: zh‑TW
    - **System**: Log IPv6
    - **System**: 1pctl app commands
    - **System**: Extract password error
    - **System**: Static traverse
    - **System**: Exclude style
    - **System**: Custom backup count

!!! note "Bug Fixes"

    - **Overview**: Network monitor layout
    - **App Store**: Post‑install param
    - **App Store**: Edit resource missing
    - **App Store**: Upgrade log order
    - **App Store**: Edit var required
    - **App Store**: OpenResty relative path
    - **App Store**: Low RAM OpenResty
    - **Website**: LB backup error
    - **Website**: HTTPS WordPress style
    - **Website**: HSTS off default site
    - **Website**: Restore log
    - **SSL**: Slave sync fail
    - **Container**: Bulk restart timeout
    - **Container**: Push log format
    - **Container**: Network IP range
    - **SSH**: Port sync
    - **SSH**: Port not apply
    - **Cron**: Report delete
    - **Cron**: View log crash
    - **Cron**: Expression comma
    - **Cron**: Shell quote error
    - **Toolbox**: Clean exclude current
    - **Cluster**: Community node name
    - **Cluster**: NIC after switch
    - **Cluster**: Overview refresh
    - **HA**: MySQL backup fail
    - **System**: aarch64 app filter
    - **System**: 1pctl language

### v2.0.11

2025‑09‑15

!!! note "New Features"

    - **Overview**: Quick directory
    - **MCP**: uvx MCP Server
    - **Disk**: Disk management

!!! note "Improvements"

    - **Website**: OpenResty build timeout
    - **SSL**: Sort by expire
    - **Runtime**: Log & terminal style
    - **Database**: ZIP backup upload
    - **Container**: Volume list info
    - **Container**: Fullscreen Compose
    - **Firewall**: Restart Docker option
    - **Process**: Performance
    - **Terminal**: Default connect
    - **Cron**: Backup all with empty
    - **Cron**: Execution mechanism
    - **Toolbox**: Daemon PID detail
    - **Transfer**: rsync check
    - **Tamper**: Delete message
    - **Settings**: 189 mail
    - **System**: Backup server select
    - **System**: Copy version
    - **System**: Log read
    - **System**: Esc/click close log
    - **System**: Default list size 20
    - **System**: HTML log

!!! note "Bug Fixes"

    - **App Store**: Ignore update still show
    - **Website**: Browser cache wrong
    - **Website**: Hotlink duplicate domain
    - **Website**: Hotlink disable cache
    - **SSL**: Push node not work
    - **MCP**: streamablehttp config
    - **Container**: Upgrade lose command
    - **Container**: WSL2 Docker status
    - **Container**: Delete system network
    - **File**: Extract gz fail
    - **Toolbox**: Clear scan record error
    - **Toolbox**: fail2ban IP save fail
    - **Monitor**: Large data error
    - **HA**: Slave install fail
    - **Logs**: Operation log i18n
    - **Settings**: Alert delete not stop
    - **Settings**: Snapshot timeout
    - **Settings**: Offline alert
    - **System**: API doc

### v2.0.10

2025‑09‑02

!!! note "New Features"

    - **Overview**: Copy system info
    - **App Store**: Copy password
    - **SSL**: Push cert to node
    - **File**: Right‑click menu
    - **File**: Multi‑tab
    - **File**: Drag upload
    - **WAF**: IP group import/export
    - **WAF**: URL/UA list import/export
    - **Logs**: Export SSH login
    - **Settings**: Login, SSH, license, node alert
    - **System**: Historical changelog

!!! note "Improvements"

    - **Overview**: Recommend logic
    - **App Store**: Upgrade diff
    - **App Store**: Restart policy
    - **App Store**: Container nav
    - **App Store**: Empty state
    - **App Store**: Tag select
    - **App Store**: Search description
    - **App Store**: Upgrade timeout
    - **App Store**: Tag style
    - **Website**: Reverse proxy root
    - **Website**: Reverse proxy custom conf
    - **Website**: Reverse proxy cache
    - **Website**: Alias special char
    - **Website**: Alias regex
    - **Website**: OpenResty default
    - **Website**: HSTS subdomain
    - **Website**: Quick jump directory
    - **Website**: Sort
    - **Website**: Reverse proxy UI
    - **Website**: Reverse proxy rule
    - **Website**: Hotlink options
    - **Runtime**: Restart PHP
    - **Runtime**: PHP concurrent
    - **Runtime**: PHP fpm status
    - **Runtime**: PHP Composer
    - **Runtime**: PHP daemon bulk restart
    - **GPU**: More versions
    - **Database**: Delete website hint
    - **Database**: Delete message
    - **Container**: Port check
    - **Container**: Bulk image upgrade
    - **Container**: Terminal ctrl+c
    - **Container**: Compose nav
    - **Container**: Push logic
    - **Container**: Push log
    - **Container**: Image sort
    - **Container**: Compose restart
    - **File**: Upload exit confirm
    - **File**: Download dark mode
    - **File**: File picker
    - **File**: Row select
    - **File**: Rename logic
    - **Cron**: Backup logic
    - **Cron**: Backup filename
    - **Cron**: Custom schedule hint
    - **Toolbox**: Cache cleanup
    - **Node**: Rename & group
    - **Node**: Sync logic
    - **Node**: Install hash check
    - **Node**: Edit health check
    - **Settings**: Snapshot exclude IP
    - **Settings**: License error
    - **Settings**: Google Drive logic
    - **System**: Auto focus login
    - **System**: Log highlight
    - **System**: riscv64
    - **System**: No log tip
    - **System**: Log read

!!! note "Bug Fixes"

    - **App Store**: Node.js shown not installed
    - **App Store**: Pagination not cache
    - **Website**: OpenResty module upgrade crash
    - **Website**: Slave HSTS
    - **Website**: proxy_ssl_name wrong
    - **Website**: Hotlink static 404
    - **Website**: OpenResty reinstall directory
    - **SSL**: Slave renew fail
    - **Runtime**: Create port missing
    - **Database**: MySQL slow log switch
    - **Container**: Delete Compose still show
    - **Container**: Image delete warning
    - **SSH**: Session infinite load
    - **Cron**: Report display
    - **Toolbox**: Scan timeout
    - **WAF**: URL allow with param
    - **WAF**: Pagination not cache
    - **Node**: List refresh not cache
    - **Monitor**: Status 0 normal
    - **Monitor**: Clear log not sync
    - **Settings**: Snapshot temp file
    - **Settings**: WebDAV upload fail
    - **Settings**: Allowed IPv6
    - **System**: Mobile task bar
    - **System**: Async log
    - **System**: Command user info
    - **System**: Log missing
    - **System**: Backup load timeout
    - **System**: Multi‑update description
    - **System**: Page flash

### v2.0.9

2025‑08‑14

!!! note "Bug Fixes"

    - **App Store**: Missing app tags
    - **Website**: IPv6 unstar
    - **Runtime**: PHP Supervisor error
    - **File**: Extract tgz
    - **File**: Hidden file state
    - **Terminal**: Connect init fail
    - **Settings**: SSL not update system cert
    - **Settings**: Domain bind IP access
    - **Settings**: Alert config missing

### v2.0.8

2025‑08‑07

!!! note "Bug Fixes"

    - **App Store**: Sync lock

### v2.0.7

2025‑08‑07

!!! note "New Features"

    - **Website**: HTTPS domain lock
    - **MCP**: Streamable HTTP MCP Server
    - **SSH**: Key management
    - **Cron**: Task grouping

!!! note "Improvements"

    - **App Store**: Enter confirm delete
    - **App Store**: Pull timeout message
    - **App Store**: Skip upgrading on uninstall
    - **Website**: Log load
    - **SSL**: Prevent deleting pending cert
    - **Runtime**: PHP list style
    - **Database**: Remote connect timeout
    - **Container**: Clean in Task Center
    - **File**: Dark mode editor
    - **WAF**: Block crawler
    - **HA**: Master IP check
    - **Monitor**: Log usage
    - **Monitor**: List load speed
    - **Monitor**: HOST field
    - **Monitor**: OpenResty version tip
    - **System**: Node switch refresh
    - **System**: Login autocomplete

!!! note "Bug Fixes"

    - **App Store**: Ignore update not work
    - **App Store**: Upgrade pull old image
    - **App Store**: Sync lose local tag
    - **Website**: Reverse proxy config list error
    - **SSL**: Delete fail
    - **SSL**: Apply log display
    - **Runtime**: Site stop not start
    - **Database**: Redis cluster error
    - **Database**: PostgreSQL restore
    - **Database**: Redis cluster display
    - **File**: Overwrite not update
    - **Firewall**: Route fail
    - **Toolbox**: Daemon autostart off
    - **Node**: Slave view master backup
    - **Logs**: SSH fail log
    - **Settings**: Menu tab name
    - **Settings**: Docker proxy no auth
    - **System**: Forward error
    - **System**: EditorConfig warning
    - **System**: tar.gz extract
    - **System**: SSH SDK timeout hang

### v2.0.6

2025‑07‑30

!!! note "New Features"

    - **Cron**: Import/export
    - **Cron**: Report log trace & download
    - **Settings**: Tencent COS Lite
    - **System**: Login button color

!!! note "Improvements"

    - **Backup**: Optimize filename
    - **Settings**: API whitelist tooltip
    - **System**: Dark mode sidebar

!!! note "Bug Fixes"

    - **App Store**: Edit unexposed app bind 127.0.0.1
    - **Website**: Custom domain 443 error
    - **Website**: OpenResty non‑80/443 domain port
    - **Runtime**: Rename PHP fail
    - **Runtime**: Podman PHP site
    - **Database**: MySQL cluster import
    - **Database**: PostgreSQL cluster restore
    - **Cron**: Switch to custom schedule
    - **Node**: Style after switch
    - **Node**: Normal marked deleted
    - **Node**: Slave cert verify
    - **Node**: Init data
    - **UI**: Custom Logo
    - **Settings**: Email alert fail
    - **Settings**: Offline alert

### v2.0.5

2025‑07‑24

!!! note "New Features"

    - **Node**: Master/slave switch
    - **HA**: MySQL, PostgreSQL, Redis cluster
    - **Settings**: Email alert
    - **Settings**: Turkish

!!! note "Improvements"

    - **App Store**: Use existing remote DB
    - **Website**: HSTS optional
    - **Website**: LB tooltip
    - **Runtime**: Docker not install tip
    - **Runtime**: Terminal user
    - **Runtime**: sodium extension
    - **Container**: Async build
    - **Container**: Continue edit or back
    - **Container**: Async create
    - **Cron**: Container status
    - **Node**: Deleted status
    - **Node**: Sync display
    - **Node**: Starting status
    - **Settings**: Backup account type
    - **Settings**: Snapshot timeout
    - **System**: Backup temp dir
    - **System**: Prevent drawer close
    - **System**: Node switch animation

!!! note "Bug Fixes"

    - **Overview**: RAM exclude shared
    - **App Store**: App tag wrong language
    - **App Store**: Log title
    - **App Store**: Script fail
    - **App Store**: No port jump button
    - **App Store**: Mailserver install
    - **App Store**: Encrypted backup restore
    - **Website**: LB display
    - **Website**: Delete HTTPS repo Docker restart
    - **SSL**: Edit IPv6 self‑sign fail
    - **Container**: Log color
    - **Container**: Multi log tail error
    - **Container**: Log download fail
    - **Container**: Log filter off
    - **Container**: Edit DNS
    - **Container**: Edit name get fail
    - **File**: UTF-8 garbage
    - **File**: Sort size wrong
    - **Firewall**: Forward fail
    - **Node**: Add directory not exist
    - **Monitor**: Trend error
    - **System**: Demo terminal

### v2.0.4

2025‑07‑07

!!! note "Improvements"

    - **Toolbox**: FTP root check

!!! note "Bug Fixes"

    - **Overview**: Monitor not auto refresh
    - **App Store**: Stop timeout uninstall
    - **AI**: OpenResty non‑80/443 MCP
    - **Toolbox**: Slave timezone logout
    - **WAF**: Block log detail
    - **Monitor**: Independent IP
    - **System**: License verify

### v2.0.3

2025‑07‑04

!!! note "Improvements"

    - **Overview**: Show installed apps
    - **App Store**: One‑click container terminal
    - **App Store**: Upgrade diff button
    - **Website**: OpenResty public access limit
    - **SSL**: Small screen DNS select
    - **Runtime**: Note
    - **Runtime**: PHP version switch
    - **Runtime**: PHP config
    - **Container**: Docker restart after registry
    - **File**: Show hidden by default
    - **File**: Interpreter by content
    - **Cron**: Backup ignore error
    - **Cron**: Snapshot partial customize
    - **Cron**: Shell output
    - **Cron**: Report style
    - **Toolbox**: Disable clean 0B
    - **WAF**: Apply to all
    - **Node**: Non‑root user
    - **Node**: Long name display
    - **Task**: Highlight IPv6
    - **Settings**: Snapshot app backup
    - **Settings**: Snapshot name
    - **Settings**: Snapshot mechanism
    - **Settings**: Google Drive chunk
    - **Settings**: Backup switch
    - **Settings**: Snapshot docker conf
    - **System**: Node select popup
    - **System**: Compress exclude
    - **System**: More page sizes
    - **System**: 1pctl output
    - **System**: Custom install
    - **System**: Uninstall data choice

!!! note "Bug Fixes"

    - **Overview**: Wrong distro
    - **Overview**: Console error
    - **Overview**: Mount fail load
    - **App Store**: GPU missing
    - **App Store**: Uninstall DB app fail
    - **App Store**: Console error
    - **Website**: Directory wrong
    - **Website**: SSL IPv6
    - **Runtime**: PHP command fail
    - **Runtime**: Java install
    - **Runtime**: Java mount display
    - **Container**: Log error
    - **Container**: Snap Docker mirror
    - **File**: Upload log path
    - **File**: Slave preview
    - **File**: Multi move same name
    - **Toolbox**: Daemon stop loading
    - **WAF**: Chart theme
    - **WAF**: Log clear
    - **Node**: Edit verify
    - **Monitor**: Trend error
    - **Settings**: Snapshot no website check
    - **Settings**: Google Drive token
    - **Settings**: Snapshot create
    - **System**: Empty flash
    - **System**: English error CN
    - **System**: Log copy newline
    - **System**: Slave site icon
    - **System**: Dropdown overflow

### v2.0.2

2025‑06‑20

!!! note "New Features"

    - **SSL**: Rynu DNS
    - **SSL**: Baidu Cloud DNS

!!! note "Improvements"

    - **App Store**: docker‑compose compat
    - **App Store**: Docker not install tip
    - **Runtime**: PHP pcntl extension
    - **Database**: Remove Redis password strength
    - **File**: GBK encode
    - **File**: Edit size limit
    - **Cron**: Container Shell user
    - **Cron**: Status button
    - **Script**: Sync log
    - **Toolbox**: Swap timeout
    - **WAF**: Deploy rule to sites
    - **Node**: Filter
    - **Node**: Pro delete
    - **Node**: Availability check
    - **Node**: Add check
    - **SMS**: Cache record
    - **Settings**: License node filter
    - **Settings**: License retry
    - **System**: Button style
    - **System**: Snap Docker compat
    - **System**: Drawer close

!!! note "Bug Fixes"

    - **App Store**: Init container status
    - **App Store**: Local app port
    - **App Store**: Edit field validate
    - **Website**: HTTP/3
    - **Runtime**: Edit .NET env missing
    - **Runtime**: PHP 7.2 Swoole
    - **Database**: PostgreSQL remote no same name
    - **File**: Hidden file page
    - **Cron**: Log incomplete
    - **Toolbox**: Swap enable fail
    - **Toolbox**: Cache auto check
    - **WAF**: Site rule apply
    - **Tamper**: Exclude file delete
    - **UI**: Clear cache image
    - **Logs**: Login log
    - **Settings**: Menu show & sort
    - **Settings**: Google Drive backup
    - **Settings**: Hide AI website
    - **Settings**: Alipan bind sync
    - **System**: Script no output
    - **System**: Container log open
    - **System**: Docker log not terminate
    - **System**: 1pctl update port

### v2.0.1

2025‑06‑13

!!! note "New Features"

    - AI Website Builder
    - reg.ru DNS

!!! note "Improvements"

    - PHP runtime jump to Files
    - Command container create
    - Toolbox doc link
    - System messages
    - EN & zh‑TW translation

!!! note "Bug Fixes"

    - Overview align
    - Overview status bar
    - HTTPS SSL protocol
    - Daemon log clear fail
    - HTTPS unsafe TLS
    - Cron backup all DB
    - Cron retention not work
    - Theme after restart
    - Google Drive proxy leftover
    - Snapshot create
    - Doc link
    - Version info
    - Multi‑arch slave
    - Slave non‑default port transfer

### v2.0.0

2025‑06‑10

!!! note "Highlights"

    - **Multi‑Server Management**
    
      One master manages multiple slaves, cross‑server resource scheduling.

    - **Custom Repo & Offline Install**
    
      Custom app/image repos for offline environments.

    - **Server File Transfer**
    
      High‑speed rsync over SSH.

    - **Website Management Redesigned**
    
      - Subwebsites
      - One‑click HTTPS & DB
      - Real IP, type switch, DB switch

    - **Website Load Balancer**
    
      Visual config for high availability.

    - **Script Library**
    
      Manage install scripts, upload custom, use in Cron.

    - **Container Page Redesigned**
    
      - Overview page
      - More create params
      - Command‑line create

    - **Snapshot Redesigned**
    
      Flexible policies.

!!! Abstract "Full List"

    - **Task Center** for app/website tasks
    - **WAF** performance
    - Runtime: custom port, env, volume
    - **OpenResty** HTTP/3
    - OpenResty custom directory
    - Multi‑site PHP sharing
    - PHP **Supervisor**
    - PHP extension management
    - **Backup Accounts** upgraded
    - Support Google Drive, Alipan, UPYUN
    - Multiple accounts same type
    - Overview custom app cards
    - Hide sidebar
    - **Terminal Redesigned**
    - Default SSH key login
    - Font, cursor, scroll settings
    - Custom login page
    - Many UX improvements
    - **Fixed known issues**
