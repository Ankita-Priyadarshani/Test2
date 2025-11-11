# Test2
# Meeting Minutes 📝

[![Version](https://img.shields.io/badge/version-0.0.1-blue.svg)](https://github.com/yourusername/meeting-minutes)
[![License](https://img.shields.io/badge/license-Proprietary-red.svg)](#license)
[![Built with](https://img.shields.io/badge/built%20with-React%20%7C%20TypeScript-61DAFB.svg)](https://reactjs.org/)
[![AI Powered](https://img.shields.io/badge/AI-SEMOSS-blueviolet.svg)](https://semoss.org/)

> Automate meeting minutes generation with AI-powered transcript analysis

Meeting Minutes is an intelligent application that transforms meeting transcripts into structured, professional meeting minutes with automatically extracted action items. Built for the Defense Health Agency (DHA), it streamlines meeting documentation, team collaboration, and action item tracking.

---

## ✨ Features

### 🤖 AI-Powered Generation
- Automatically generate meeting minutes from transcript uploads
- Extract meeting title, purpose, and key decisions
- Generate attendee tables and executive summaries
- Identify and structure action items with assignees and deadlines

### 📄 Document Processing
- Support for multiple formats: **PDF**, **DOCX**, **TXT**
- Drag-and-drop file upload interface
- Automatic text extraction and processing
- Export to professional Word documents

### 👥 Team Collaboration
- Team and topic management with granular access control
- Role-based permissions and user management
- Collaborative meeting creation and editing
- Subscribe to relevant topics within teams

### 🗂️ Smart Storage & Search
- **PostgreSQL** database for meeting metadata and action items
- **FAISS** vector database for semantic transcript search
- Historical meeting archive with powerful search
- Search by team, topic, date, or keywords

### ✅ Action Item Tracking
- Automatically extract action items from transcripts
- Assign tasks to team members with due dates
- Priority levels: Low, Medium, High
- Persistent tracking in database

### 📊 Professional Output
- Real-time markdown preview
- Structured meeting minute templates
- Export to Word with professional formatting
- Archive access for past meetings

---

## 📦 Installation

### Prerequisites

| Requirement | Version | Purpose |
|-------------|---------|---------|
| **Node.js** | v16+ | Frontend runtime |
| **pnpm** | v10.11.1+ | Package manager |
| **Java JDK** | 1.8+ | Backend services |
| **Maven** | 3.6+ | Build automation |
| **PostgreSQL** | v12+ | Database storage |
| **SEMOSS** | Latest | AI platform |

### Quick Start

```bash
# Clone the repository
git clone https://github.com/yourusername/meeting-minutes.git
cd meeting-minutes

# Install frontend dependencies
cd assets/client
pnpm install

# Install backend dependencies
cd ../meeting-minutes-be
mvn clean install
```

### Database Setup

```bash
# Create database
createdb pmo_meeting_minutes

# Initialize schema
psql -U your_username -d pmo_meeting_minutes -c "CREATE SCHEMA pmomm;"
```

> **Note:** The database stores teams, topics, meetings, action items, and user information.

---

## ⚙️ Configuration

Create `.env` file in `assets/client/`:

```bash
# SEMOSS Platform
MODULE="/Monolith"
ENDPOINT="https://your-govconnect-instance.ai"
APP="your-meeting-minutes-app-id"

# AI Models
MODEL="your-llm-model-id"
EMBEDDER_ENGINE="your-embedder-engine-id"

# Development
NODE_ENV=development
PORT=3001
```

Edit `assets/meeting-minutes-be/project.properties`:

```properties
client=Meeting_Minutes
projectId=your-app-id-here
SemossProjectPath=/path/to/semoss/project

# Database
DB_HOST=localhost
DB_NAME=pmo_meeting_minutes
DB_USER=your_username
DB_PASSWORD=your_password
DB_SCHEMA=pmomm
```

---

## 🚀 Usage

### Development

```bash
cd assets/client
pnpm run dev
```

Open [http://localhost:3001](http://localhost:3001) in your browser.

### Basic Workflow

1. **Setup Team & Topics**
   - Create or join teams
   - Subscribe to relevant topics

2. **Upload Transcript**
   ```
   Drag & drop or click to upload
   Supported: PDF, DOCX, TXT
   ```

3. **Generate Minutes**
   - AI processes transcript
   - Creates structured minutes
   - Extracts action items automatically

4. **Review & Edit**
   - Live markdown preview
   - Edit as needed
   - Assign action items to team members

5. **Save & Export**
   - Save to database
   - Export to Word document
   - Archive for future reference

### Production Build

```bash
# Frontend
cd assets/client
pnpm build

# Backend
cd assets/meeting-minutes-be
mvn clean package
```

**Output:**
- Frontend: `portals/` directory
- Backend: `target/meetingminutes-0.0.1.jar`

---

## 🚢 Deployment

Deploy to **Govconnect.ai** (SEMOSS Platform):

1. Build application (frontend + backend)
2. Initialize PostgreSQL database with schema
3. Create deployment package (portals, assets, metadata)
4. Upload to Govconnect.ai and configure environment
5. Compile reactors and publish

See [_PMO_Documentation.pptx](./assets/_PMO_Documentation.pptx) for detailed deployment guide.

---

## 🛠️ Tech Stack

| Category | Technologies |
|----------|-------------|
| **Frontend** | React 18.3, TypeScript, Material UI v5 |
| **State** | MobX 6, React Hook Form v7 |
| **Backend** | Java 8, Maven, SEMOSS Reactors |
| **Database** | PostgreSQL 12+, FAISS Vector DB |
| **AI/ML** | SEMOSS LLM (Guanaco), Embedder Engine |
| **Processing** | Mammoth.js, Marked v5, React-MDE v11 |
| **Build** | pnpm 10.11.1+, Webpack 5 |

---

## 📚 Documentation

- **[User Guide](_PMO_Documentation.pptx)** - Complete application documentation
- **[Code Style](assets/client/CodeStyle.md)** - Development standards
- **[API Docs](https://semoss.org/docs)** - SEMOSS SDK reference
- **[Component Docs](assets/client/src/components/README.md)** - UI architecture

---

## 🤝 Contributing

Contributions are welcome! Please read our contributing guidelines before submitting PRs.

**Development Workflow:**

```bash
# Fork and clone the repo
git clone https://github.com/yourusername/meeting-minutes.git

# Create feature branch
git checkout -b feature/amazing-feature

# Make your changes
pnpm run dev

# Run quality checks
pnpm lint && pnpm type-check

# Commit with semantic messages
git commit -m "feat: add amazing feature"

# Push and create PR
git push origin feature/amazing-feature
```

**Code Quality Requirements:**
- ✅ All ESLint checks must pass
- ✅ TypeScript types properly defined
- ✅ Components < 750 lines
- ✅ Use `styled` components (no inline styles)
- ✅ Include error handling

---

## 📄 License

**Proprietary Software** - Defense Health Agency (DHA)

This software is licensed exclusively for use by:
- Defense Health Agency personnel
- Authorized government contractors
- Approved government entities

**Restrictions:** No redistribution, modification, or public use without authorization.

**Third-Party:** Open-source components (React, Material UI, MobX) retain their original licenses.

---

## 💬 Support

### Get Help

| Channel | Response Time |
|---------|---------------|
| 🔴 **Critical Issues** | IT Service Desk (Priority 1) - 1 hour |
| 🟡 **Bugs** | IT Service Desk (Priority 2-3) - 1-2 days |
| 💡 **Features** | Product Owner - Next sprint |
| 💬 **Questions** | Team Channel - Same day |

### Contact

- **Team:** DHA PMO Development Team
- **Email:** dha-pmo-support@example.mil
- **Platform:** [SEMOSS Support](https://semoss.org/docs)

**Bug Reports:** Include environment, steps to reproduce, screenshots, and browser version.

---

## 🙏 Acknowledgments

Built with ❤️ for the **Defense Health Agency**

**Powered by:**
- [SEMOSS AI Platform](https://semoss.org) - AI & Analytics
- [React](https://react.dev) + [TypeScript](https://www.typescriptlang.org) - Frontend
- [PostgreSQL](https://www.postgresql.org) + [FAISS](https://github.com/facebookresearch/faiss) - Data Storage
- [Material UI](https://mui.com) - UI Components

**Special Thanks:**
- DHA PMO Team
- Deloitte SEMOSS Team
- Open Source Community

---

## 🗺️ Roadmap

**v0.1.0** (Current)
- ✅ AI-powered minute generation
- ✅ Team & topic management
- ✅ Action item tracking
- ✅ Vector database search

**v0.2.0** (Planned)
- 🔄 Real-time collaboration
- 📊 Analytics dashboard
- 📱 Mobile responsive design
- 📧 Email notifications

**v0.3.0** (Future)
- 🔗 Microsoft Teams integration
- 🔍 Natural language search
- 📈 Advanced analytics
- 🔐 Audit logging

---

<div align="center">

**[⬆ Back to Top](#meeting-minutes-)**

Made with 💙 by DHA PMO | Version 0.0.1 | Last Updated: November 2025

</div>
