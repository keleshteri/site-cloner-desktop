# Site Cloner Desktop - Development Roadmap

## 🎯 Project Vision

Create a comprehensive desktop application that automates the entire process of cloning WordPress websites from SiteGround hosting to local development environments, reducing setup time from hours to minutes.

## 📋 Development Phases

### Phase 1: SSH Foundation ✅ COMPLETED
**Goal**: Establish secure SSH connectivity and basic remote file operations

#### Completed Features:
- [] SSH connection management with ssh2 library
- [] Support for password and private key authentication
- [] Connection testing and validation
- [] Remote file browser with navigation
- [] File listing with permissions and metadata
- [] Command execution on remote server
- [] Modern Vue.js + TypeScript UI
- [] Electron application framework
- [] IPC communication between main and renderer processes

#### Technical Implementation:
- SSH service backend (`src/main/services/ssh-service.ts`)
- Vue.js connection form component
- Secure IPC communication layer
- Type-safe API definitions
- Error handling and user feedback

---

### Phase 2: Website Cloning 🔄 IN PROGRESS
**Goal**: Implement core website cloning functionality

#### Planned Features:
- [ ] **File Archive Creation**
  - Create ZIP archives of WordPress installations
  - Selective file inclusion/exclusion
  - Progress tracking for large archives
  - Compression options and settings

- [ ] **Database Export**
  - MySQL database dump generation
  - wp-config.php parsing for database credentials
  - SQL export with proper formatting
  - Large database handling with streaming

- [ ] **Download Management**
  - File transfer progress tracking
  - Resume interrupted downloads
  - Bandwidth throttling options
  - Local storage management

- [ ] **WordPress Detection**
  - Automatic WordPress installation detection
  - wp-config.php analysis
  - Plugin and theme inventory
  - Database table identification

#### Technical Requirements:
- Archive creation service (tar/zip)
- MySQL dump functionality
- File transfer with progress tracking
- WordPress-specific file parsing
- Storage management utilities

---

### Phase 3: Local Integration 📋 PLANNED
**Goal**: Automate local WordPress environment setup

#### Planned Features:
- [ ] **WP Local Integration**
  - Automatic site creation in WP Local
  - Environment configuration
  - Local server startup
  - SSL certificate handling

- [ ] **Database Migration**
  - Local MySQL database creation
  - SQL import with error handling
  - URL replacement (remote → local)
  - Search and replace functionality

- [ ] **Configuration Management**
  - wp-config.php modification for local environment
  - Database connection updates
  - Debug settings configuration
  - Local path adjustments

- [ ] **Environment Setup**
  - PHP version compatibility checking
  - Required extension verification
  - File permission adjustments
  - Local domain configuration

#### Technical Requirements:
- WP Local API integration
- Database manipulation utilities
- File system operations
- Configuration file parsing and modification
- Local server management

---

### Phase 4: Advanced Features 🚀 FUTURE
**Goal**: Enhanced functionality for power users

#### Planned Features:
- [ ] **Batch Operations**
  - Multiple site cloning simultaneously
  - Queue management
  - Resource allocation
  - Progress monitoring

- [ ] **Scheduled Backups**
  - Automated periodic cloning
  - Backup scheduling interface
  - Retention policies
  - Notification system

- [ ] **Site Synchronization**
  - Compare local vs remote changes
  - Selective sync options
  - Conflict resolution
  - Change tracking

- [ ] **Advanced Configuration**
  - Custom clone profiles
  - Environment templates
  - Plugin/theme filtering
  - Performance optimization

#### Technical Requirements:
- Job queue system
- Scheduling engine
- File comparison algorithms
- Template management system
- Performance monitoring

---

## 🛠️ Technical Architecture Evolution

### Current Architecture (Phase 1):
```
┌─────────────────┐    ┌──────────────────┐    ┌─────────────────┐
│   Vue.js UI     │◄──►│  Electron Main   │◄──►│  SSH Service    │
│   (Renderer)    │    │   (IPC Bridge)   │    │   (Backend)     │
└─────────────────┘    └──────────────────┘    └─────────────────┘
```

### Target Architecture (Phase 4):
```
┌─────────────────┐    ┌──────────────────┐    ┌─────────────────┐
│   Vue.js UI     │◄──►│  Electron Main   │◄──►│  SSH Service    │
│   (Renderer)    │    │   (IPC Bridge)   │    │   (Backend)     │
└─────────────────┘    └──────────────────┘    └─────────────────┘
                                │
                                ▼
                       ┌──────────────────┐
                       │  Service Layer   │
                       ├──────────────────┤
                       │ • Archive Service│
                       │ • Database Svc   │
                       │ • Download Mgr   │
                       │ • WP Local API   │
                       │ • Config Manager │
                       │ • Job Queue      │
                       └──────────────────┘
```

## 📊 Success Metrics

### Performance Targets:
- **Connection Time**: < 10 seconds to SiteGround
- **File Browsing**: < 2 seconds to load directory
- **Archive Creation**: 1GB site in < 5 minutes
- **Database Export**: 100MB database in < 2 minutes
- **Local Setup**: Complete clone in < 15 minutes

### User Experience Goals:
- **Ease of Use**: One-click cloning process
- **Reliability**: 99% success rate for standard WordPress sites
- **Feedback**: Real-time progress for all operations
- **Error Handling**: Clear, actionable error messages

## 🔄 Development Workflow

### Current Sprint (Phase 2.1): File Operations
1. **Archive Service Implementation**
   - Design archive creation API
   - Implement ZIP compression
   - Add progress tracking
   - Test with various file sizes

2. **WordPress Detection**
   - Create WordPress site scanner
   - Parse wp-config.php files
   - Identify standard WordPress structure
   - Handle custom installations

### Next Sprint (Phase 2.2): Database Operations
1. **Database Export Service**
   - MySQL connection handling
   - SQL dump generation
   - Large database streaming
   - Error recovery mechanisms

2. **Download Management**
   - File transfer implementation
   - Progress tracking UI
   - Resume functionality
   - Storage optimization

## 🎯 Immediate Next Steps

### High Priority:
1. **Fix SSH Connection Issues**
   - Debug SiteGround connection problems
   - Improve error handling and user feedback
   - Add connection retry mechanisms

2. **Implement File Archive Creation**
   - Create ZIP archive service
   - Add file selection interface
   - Implement progress tracking

3. **WordPress Site Detection**
   - Scan for WordPress installations
   - Parse configuration files
   - Display site information

### Medium Priority:
1. **Database Export Functionality**
2. **Download Progress Interface**
3. **Local Storage Management**

### Low Priority:
1. **Advanced Configuration Options**
2. **Batch Operation Support**
3. **Scheduled Backup Features**

## 📝 Notes

### SiteGround Specific Considerations:
- SSH port typically 18765
- WordPress sites usually in `/public_html/`
- Database access via phpMyAdmin or SSH
- File permission considerations
- Shared hosting limitations

### WordPress Compatibility:
- Support for WordPress 5.0+
- Handle custom directory structures
- Multisite installation support
- Plugin/theme compatibility checking
- Database prefix variations

### Local Environment Integration:
- WP Local (primary target)
- XAMPP/WAMP compatibility
- Docker environment support
- Custom local server setups

---

This roadmap will be updated as development progresses and new requirements are identified.
