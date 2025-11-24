# 📝 Taskflow Logic CLI

A minimal, modular command-line to-do list application written in modern JavaScript (ES Modules). Features rich task management with due dates, status tracking, and overdue detection. Built to be easy to extend, easy to read, and lightning-fast for everyday task management directly from your terminal.

---

## ✨ Features

- 🎯 **Rich Task Management** — Create tasks with title, description, and due dates
- 📅 **Smart Date Handling** — Flexible date input formats (DD.MM.YYYY, DD/MM/YYYY, YYYY-MM-DD, DD-MM-YYYY)
- 🎨 **Visual Status Indicators** — Colorful emojis for task status and overdue warnings ⏰❗
- ⚠️ **Overdue Detection** — Automatic identification of past-due tasks
- 💾 **Persistent Storage** — Add / Remove / List tasks from a persistent JSON store
- 📋 **Task Details** — Each task includes title, body, creation date, due date, and completion status
- 🧹 **Clean Architecture** — Clean separation of concerns (Models, Game Logic, Data, Utilities)
- ⚡ **Modern JavaScript** — Written with async/await for readability—no callback spaghetti 🍝
- 🏗️ **Class-Based Models** — Modern class-based Task model with JSON serialization

---

## 🧩 Tech Stack

| Layer | Technology |
|-------|------------|
| Runtime | Node.js 18+ |
| Module System | ES Modules |
| CLI Interface | readline/promises (native) |
| Data Storage | JSON (tasks.json) |
| Date Handling | dayjs with customParseFormat |

---

## 📂 Project Structure

```
project-root/
│
├── 📁 src/
│   ├── models/           # Domain models (classes like Task)
│   │   └── Task.js
│   │
│   ├── game/             # Game logic
│   │   └── game.js
│   │
│   ├── data/             # Static and global data
│   │   ├── globalData.js
│   │   └── tasks.json
│   │
│   ├── utils/            # Utility functions
│   │   └── utils.js
│   │
│   └── main.js           # App entry point
│
├── package.json
└── README.md
```

Each file is self-contained. Replace or extend a module without touching the rest of the codebase.

---

## 🛠️ Getting Started

**Requirements**

- Node.js 18 or higher
- Git (to clone the repo)

**Installation**

```bash
# Clone the repository
git clone https://github.com/MrSSHH/taskflow-logic-cli.git
cd taskflow-logic-cli

# Install dependencies
npm install

# Start the application
node src/main.js
```

ℹ️ The first launch creates `src/data/tasks.json` automatically if it doesn't exist.

---

## 🎮 Usage

Below is a sample session (💬 user input in **bold**):

```
Welcome to the To-Do List app!

1 - ➕ Add a task
2 - 🗑️ Remove a task
3 - 📋 List tasks
4 - 🚪 Exit

> 1

Please enter the desired task:
Task title: Buy groceries
Task body: Get milk, bread, and eggs from the supermarket
Due date: 25.12.2024

✅ Task added successfully!

Would you like to add another task? [y/n]
> n

> 3

Current list of tasks:

1 - 📝 Title: Buy groceries | 📅 Due: 25.12.2024 🕒 | Status: ❌ Not Done
```

**Menu Options**

| Option | Description |
|--------|-------------|
| ➕ Add a task | Create a new task with title, description, and due date |
| 🗑️ Remove a task | Choose an existing task to delete |
| 📋 List tasks | Display all current tasks with detailed information |
| 🚪 Exit | Save & close the application |

---

## 📋 Task Model

Each task contains the following properties:

| Property | Type | Description |
|----------|------|-------------|
| taskTitle | String | Brief title of the task |
| taskBody | String | Detailed description |
| dueDate | Date | When the task should be completed |
| creationDate | Date | When the task was created |
| isDone | Boolean | Completion status |

**Supported Date Formats**

- DD.MM.YYYY (e.g., 25.12.2024)
- DD/MM/YYYY (e.g., 25/12/2024)
- YYYY-MM-DD (e.g., 2024-12-25)
- DD-MM-YYYY (e.g., 25-12-2024)

**Status Display**

- ✅ Done / ❌ Not Done — Visual completion status
- ⏰❗ — Overdue warning for past-due incomplete tasks
- Formatted Dates — Consistent DD.MM.YYYY display format
- Rich Information — Title, due date, and status at a glance

---

## ⚙️ Configuration

All config lives in `src/data/globalData.js`:

```javascript
export const strings = {
  tasksJsonPath: path.resolve('src/data/tasks.json'),
  promptScreensText: { /* UI copy */ },
  availableTasks: { /* Menu labels */ }
};
```

**Configuration Options**

- Change `tasksJsonPath` to relocate the task store
- Edit `promptScreensText` to localize or tweak UI wording

---

## 🗺️ Roadmap

- ✅ Rich task model with due dates
- ✅ Overdue task detection
- ✅ Visual status indicators
- 🔄 Task completion toggle functionality
- 🔄 Unit tests with Vitest / Jest
- 🔄 Import / export tasks to CSV
- 🔄 Tag-based filtering (e.g., work, personal)
- 🔄 Task priority levels
- 🔄 Search and filter tasks
- 🔄 Task editing capabilities

---

## 🤝 Contributing

Feel free to open issues or pull requests for new ideas! 🚀

- Fork the repository
- Create your feature branch: `git checkout -b feat/awesome-feature`
- Commit your changes: `git commit -m "Add awesome feature"`
- Push to the branch: `git push origin feat/awesome-feature`
- Open a Pull Request

Please follow the existing code style and include relevant unit tests when applicable.

---

## 📜 License

Distributed under the MIT License. See LICENSE for more information.
