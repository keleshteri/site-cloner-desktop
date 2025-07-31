# Site Cloner Desktop

A powerful desktop application designed to clone WordPress websites from SiteGround hosting to local development environments with automated setup and configuration.

## 🎯 Project Goals

This application is specifically designed to streamline the process of cloning WordPress websites hosted on **SiteGround** to local development environments, saving developers significant time and effort.

### Primary Objectives:

1. **SSH Connection to SiteGround**: Securely connect to SiteGround hosting via SSH
2. **Website Cloning**: Create complete backups of WordPress websites including files and databases
3. **Local Setup Automation**: Automatically configure cloned sites in local development environments
4. **Database Migration**: Handle database exports, imports, and URL replacements
5. **Time Saving**: Reduce manual setup time from hours to minutes

## 🚀 Key Features

### ✅ Currently Implemented:
- **SSH Connection Management**: Secure SSH connections with key-based authentication
- **Remote File Browser**: Navigate and explore remote server directories
- **Connection Testing**: Verify SSH credentials before establishing connections
- **Modern UI**: Clean, intuitive interface built with Vue.js and Electron

### 🔄 In Development:
- **Website File Archiving**: Create ZIP archives of WordPress installations
- **Database Backup**: Export MySQL databases from SiteGround
- **Local Environment Integration**: Integration with WP Local or similar tools
- **Automated Configuration**: Auto-configure WordPress settings for local development
- **URL Replacement**: Automatically update database URLs for local environment

### 🎯 Planned Features:
- **Batch Operations**: Clone multiple sites simultaneously
- **Scheduled Backups**: Automated periodic backups
- **Site Comparison**: Compare local and remote site differences
- **Plugin/Theme Management**: Selective cloning of plugins and themes
- **Environment Profiles**: Save and reuse connection profiles

## 🏗️ Architecture

### Technology Stack:
- **Frontend**: Vue.js 3 + TypeScript
- **Backend**: Electron (Node.js)
- **SSH Library**: ssh2 for secure connections
- **Build Tool**: Electron Vite
- **Styling**: CSS3 with modern design patterns

### Project Structure:
```
site-cloner-desktop/
├── src/
│   ├── main/                 # Electron main process
│   │   ├── services/         # Backend services
│   │   │   └── ssh-service.ts # SSH connection management
│   │   └── index.ts          # Main process entry
│   ├── preload/              # Preload scripts (IPC bridge)
│   └── renderer/             # Vue.js frontend
│       └── src/
│           ├── components/   # Vue components
│           └── assets/       # Static assets
├── docs/                     # Documentation
└── scripts/                  # Helper scripts
```

## 🎯 Target Workflow

### Typical Use Case:
1. **Connect**: Establish SSH connection to SiteGround server
2. **Browse**: Navigate to WordPress installation directory
3. **Select**: Choose website files and database to clone
4. **Archive**: Create ZIP backup of website files
5. **Export**: Generate database dump with proper formatting
6. **Download**: Transfer files and database to local machine
7. **Setup**: Automatically configure local WordPress environment
8. **Configure**: Update database URLs and paths for local development
9. **Launch**: Open cloned site in local development server

### Time Savings:
- **Manual Process**: 2-4 hours per site
- **With Site Cloner**: 10-15 minutes per site
- **Efficiency Gain**: 80-90% time reduction

## 🛠️ Installation & Setup

### Prerequisites:
- Node.js 18+
- npm or yarn
- SSH access to SiteGround hosting
- Local WordPress development environment (WP Local, XAMPP, etc.)

### Installation:
```bash
# Clone the repository
git clone https://github.com/keleshteri/site-cloner-desktop.git

# Navigate to project directory
cd site-cloner-desktop

# Install dependencies
npm install

# Start development server
npm run dev
```

## 🔧 Configuration

### SSH Setup:
1. **Generate SSH Key Pair** (if not already done):
   ```bash
   ssh-keygen -t ed25519 -C "your-email@example.com"
   ```

2. **Add Public Key to SiteGround**:
   - Copy your public key: `cat ~/.ssh/id_ed25519.pub`
   - Add to SiteGround SSH Keys in cPanel

3. **Test Connection**:
   ```bash
   ssh your-username@your-server.siteground.com -p 18765
   ```

### Application Configuration:
- **Host**: Your SiteGround server (e.g., `ssh.academy.psychscene.com`)
- **Port**: Usually `18765` for SiteGround
- **Username**: Your SiteGround SSH username
- **Authentication**: Private key (recommended) or password

## 📋 Usage Guide

### Basic Workflow:
1. **Launch Application**: Run `npm run dev`
2. **SSH Connection Tab**: Enter your SiteGround SSH details
3. **Test Connection**: Verify credentials work
4. **Connect**: Establish persistent connection
5. **Browse Files**: Navigate to your WordPress installation
6. **Clone Site**: Select and download website files and database

### SiteGround Specific Notes:
- WordPress installations typically located in `/public_html/`
- Database access through phpMyAdmin or SSH
- File permissions may need adjustment after cloning
- wp-config.php requires local database configuration

## 🔍 Troubleshooting

### Common Issues:
- **Connection Timeout**: Increase timeout, check firewall settings
- **Permission Denied**: Verify SSH key is added to SiteGround
- **File Access**: Ensure proper file permissions on server
- **Database Export**: Check MySQL access permissions

### Debug Mode:
- Open Developer Tools (F12) for detailed logging
- Check console for SSH connection debug messages
- Verify network connectivity to SiteGround servers

## 🤝 Contributing

We welcome contributions! Please see our contributing guidelines for:
- Code style and standards
- Pull request process
- Issue reporting
- Feature requests

## 📄 License

This project is licensed under the MIT License - see the LICENSE file for details.

## 🎯 Roadmap

### Phase 1 (Current): SSH Foundation ✅
- SSH connection management
- File browser interface
- Basic remote operations

### Phase 2: Website Cloning 🔄
- File archiving and compression
- Database export functionality
- Download management

### Phase 3: Local Integration 📋
- WP Local integration
- Automated local setup
- Database URL replacement

### Phase 4: Advanced Features 🚀
- Batch operations
- Scheduled backups
- Site synchronization

## 📞 Support

For support and questions:
- Create an issue on GitHub
- Check the documentation in `/docs`
- Review troubleshooting guide above

## Recommended IDE Setup

- [VSCode](https://code.visualstudio.com/) + [ESLint](https://marketplace.visualstudio.com/items?itemName=dbaeumer.vscode-eslint) + [Prettier](https://marketplace.visualstudio.com/items?itemName=esbenp.prettier-vscode) + [Volar](https://marketplace.visualstudio.com/items?itemName=Vue.volar)

## Development Commands

### Install
```bash
npm install
```

### Development
```bash
npm run dev
```

### Build
```bash
# For windows
npm run build:win

# For macOS
npm run build:mac

# For Linux
npm run build:linux
```

---

**Site Cloner Desktop** - Streamlining WordPress development workflows, one clone at a time! 🚀
