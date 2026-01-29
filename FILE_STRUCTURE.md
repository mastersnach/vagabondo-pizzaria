absolute-ide/
├── 📁 .github/                          # GitHub Configuration & Automation
│   ├── 📁 workflows/                     # CI/CD pipeline definitions
│   │   ├── ci.yml                       # Continuous Integration workflow
│   │   ├── release.yml                  # Release automation workflow
│   │   └── test.yml                     # Test automation workflow
│   └── 📁 ISSUE_TEMPLATE/               # GitHub issue templates
│       ├── bug-report.md                # Template for bug reports
│       ├── feature-request.md           # Template for feature requests
│       └── config.yml                   # Issue template configuration
│
├── 📁 .vscode/                          # Visual Studio Code Workspace Settings
│   ├── settings.json                    # VSCode workspace-specific settings
│   ├── extensions.json                  # Recommended VSCode extensions
│   └── launch.json                      # Debug configurations for VSCode
│
├── 📁 .etherius/                        # Absolute IDE Internal Configuration
│   └── 📁 rules/                        # Development rules and guidelines
│       ├── architecture.md              # Architecture design principles
│       └── coding-guidelines.md         # Code style and best practices
│
├── 📁 apps/                             # Application Packages (Monorepo Applications)
│   └── 📁 desktop/                      # Electron Desktop Application
│       ├── 📁 src/                      # Desktop App Source Code
│       │   ├── 📁 main/                 # Main Process (Node.js Environment)
│       │   │   ├── 📁 ipc/              # Inter-Process Communication Handlers
│       │   │   │   ├── fs-handler.ts    # File system operations IPC handler
│       │   │   │   ├── terminal-handler.ts # Terminal operations IPC handler
│       │   │   │   ├── git-handler.ts   # Git operations IPC handler
│       │   │   │   ├── lsp-handler.ts   # Language Server Protocol IPC handler
│       │   │   │   ├── extension-handler.ts # Extension system IPC handler
│       │   │   │   ├── ai-handler.ts    # AI features IPC handler
│       │   │   │   ├── workspace-handler.ts # Workspace management IPC handler
│       │   │   │   └── dialog-handler.ts # Native dialog IPC handler
│       │   │   ├── 📁 services/         # Main Process Services
│       │   │   │   ├── window-manager.ts # Electron window management
│       │   │   │   ├── menu-manager.ts  # Application menu management
│       │   │   │   ├── dialog-service.ts # Native dialog services
│       │   │   │   ├── permission-manager.ts # Security permission management
│       │   │   │   ├── file-watcher.ts  # File system change monitoring
│       │   │   │   ├── process-manager.ts # Child process management
│       │   │   │   └── protocol-manager.ts # Custom protocol handlers
│       │   │   ├── 📁 types/            # TypeScript Type Definitions
│       │   │   │   └── ipc-types.ts     # IPC channel type definitions
│       │   │   ├── main.ts              # Electron main process entry point
│       │   │   └── preload.ts           # Preload script for security bridge
│       │   │
│       │   └── 📁 preload/              # Preload Scripts (Bridge between Main and Renderer)
│       │       ├── index.ts             # Preload script entry point
│       │       ├── ipc-expose.ts        # Exposes safe IPC methods to renderer
│       │       ├── api.ts               # Typed API surface for renderer
│       │       └── 📁 contexts/         # Context isolation utilities
│       │           ├── renderer-context.ts # Renderer process context
│       │           └── extension-context.ts # Extension host context
│       │
│       ├── 📁 resources/                # Application Resources
│       │   ├── icons/                   # Application icons for all platforms
│       │   │   ├── icon.icns            # macOS icon
│       │   │   ├── icon.ico             # Windows icon
│       │   │   └── icon.png             # Linux/PNG icon
│       │   ├── images/                  # Application images and assets
│       │   │   ├── splash-screen.png    # Splash screen image
│       │   │   ├── logo.svg             # Application logo
│       │   │   └── screenshots/         # Screenshots for documentation
│       │   └── locales/                 # Internationalization files
│       │       ├── en.json              # English translations
│       │       ├── sv.json              # Swedish translations
│       │       └── ja.json              # Japanese translations
│       │
│       ├── package.json                 # Desktop app package configuration
│       ├── vite.config.ts               # Vite build configuration for desktop
│       └── tsconfig.json               # TypeScript configuration for desktop
│
├── 📁 packages/                         # Shared Packages (Monorepo Packages)
│   ├── 📁 core/                         # Core Utilities Library
│   │   ├── src/                         # Core package source code
│   │   │   ├── 📁 events/               # Event system
│   │   │   │   ├── EventEmitter.ts      # Typed event emitter implementation
│   │   │   │   └── Disposable.ts        # Disposable pattern implementation
│   │   │   ├── 📁 uri/                  # URI handling utilities
│   │   │   │   └── URI.ts               # Uniform Resource Identifier implementation
│   │   │   ├── 📁 logging/              # Logging system
│   │   │   │   ├── Logger.ts            # Configurable logger with levels
│   │   │   │   └── LogLevel.ts          # Log level enumeration
│   │   │   ├── 📁 storage/              # Storage abstractions
│   │   │   │   ├── Storage.ts           # Abstract storage interface
│   │   │   │   └── KeyValueStorage.ts   # Key-value storage implementation
│   │   │   ├── 📁 config/               # Configuration management
│   │   │   │   └── Config.ts            # Hierarchical configuration system
│   │   │   ├── 📁 utils/                # Utility functions
│   │   │   │   ├── assert.ts            # Type assertion utilities
│   │   │   │   ├── collections.ts       # Collection utilities (Map, Set, Array)
│   │   │   │   └── platform.ts          # Platform detection utilities
│   │   │   └── index.ts                 # Core package public API
│   │   └── package.json                 # Core package configuration
│   │
│   ├── 📁 protocol/                     # Typed Message Contracts
│   │   ├── src/                         # Protocol package source code
│   │   │   ├── 📁 ipc/                  # IPC protocol definitions
│   │   │   │   ├── fs-protocol.ts       # File system IPC message contracts
│   │   │   │   ├── terminal-protocol.ts # Terminal IPC message contracts
│   │   │   │   ├── git-protocol.ts      # Git IPC message contracts
│   │   │   │   ├── lsp-protocol.ts      # LSP IPC message contracts
│   │   │   │   ├── extension-protocol.ts # Extension IPC message contracts
│   │   │   │   └── ai-protocol.ts       # AI features IPC message contracts
│   │   │   ├── 📁 rpc/                  # RPC protocol definitions
│   │   │   │   ├── extension-rpc.ts     # Extension host RPC contracts
│   │   │   │   └── ai-rpc.ts            # AI worker RPC contracts
│   │   │   ├── 📁 types/                # Protocol type definitions
│   │   │   │   ├── lsp-types.ts         # Language Server Protocol types
│   │   │   │   └── dap-types.ts         # Debug Adapter Protocol types
│   │   │   └── index.ts                 # Protocol package public API
│   │   └── package.json                 # Protocol package configuration
│   │
│   ├── 📁 workspace/                    # Workspace Model & Management
│   │   ├── src/                         # Workspace package source code
│   │   │   ├── 📁 model/                # Workspace data models
│   │   │   │   ├── Workspace.ts         # Workspace abstraction and management
│   │   │   │   ├── Folder.ts            # Folder/directory representation
│   │   │   │   └── Buffer.ts            # File buffer representation
│   │   │   ├── 📁 watch/                # File watching
│   │   │   │   └── FileWatcher.ts       # Cross-platform file system watcher
│   │   │   ├── 📁 search/               # Search functionality
│   │   │   │   ├── SearchEngine.ts      # File content search engine
│   │   │   │   └── SearchIndex.ts       # Search index for fast lookups
│   │   │   ├── 📁 history/              # History and undo/redo
│   │   │   │   └── HistoryService.ts    # Document history service
│   │   │   ├── 📁 vfs/                  # Virtual File System
│   │   │   │   ├── VFS.ts               # Virtual file system interface
│   │   │   │   ├── RealFileSystem.ts    # Real file system implementation
│   │   │   │   └── MemoryFileSystem.ts  # In-memory file system implementation
│   │   │   └── index.ts                 # Workspace package public API
│   │   └── package.json                 # Workspace package configuration
│   │
│   ├── 📁 editor/                       # Editor Subsystem
│   │   ├── src/                         # Editor package source code
│   │   │   ├── editor-core.ts           # Editor abstraction layer
│   │   │   ├── monaco-adapter.ts        # Monaco Editor integration adapter
│   │   │   ├── language-registry.ts     # Language definitions and registration
│   │   │   ├── theme-manager.ts         # Theme management and syntax highlighting
│   │   │   ├── keybinding-registry.ts   # Keybinding system and conflict resolution
│   │   │   └── snippet-manager.ts       # Code snippet management
│   │   └── package.json                 # Editor package configuration
│   │
│   ├── 📁 terminal/                     # Terminal Package
│   │   ├── src/                         # Terminal package source code
│   │   │   ├── 📁 contract/             # Terminal contracts and interfaces
│   │   │   │   └── Terminal.ts          # Terminal abstraction interface
│   │   │   ├── 📁 renderer/             # Terminal UI rendering
│   │   │   │   └── TerminalUI.tsx       # React terminal UI component
│   │   │   ├── 📁 backend/              # Terminal backend
│   │   │   │   └── PTYProtocol.ts       # Pseudo-terminal protocol implementation
│   │   │   ├── terminal-manager.ts      # Terminal session management
│   │   │   └── index.ts                 # Terminal package public API
│   │   └── package.json                 # Terminal package configuration
│   │
│   ├── 📁 lsp/                          # Language Server Protocol Client
│   │   ├── src/                         # LSP package source code
│   │   │   ├── 📁 client/               # LSP client implementation
│   │   │   │   ├── LSPClient.ts         # LSP client core
│   │   │   │   └── LSPSession.ts        # Individual LSP session management
│   │   │   ├── 📁 monaco/               # Monaco editor integration
│   │   │   │   ├── MonacoAdapter.ts     # Monaco to LSP protocol adapter
│   │   │   │   └── CompletionProvider.ts # LSP-based completion provider
│   │   │   ├── 📁 server/               # Language server management
│   │   │   │   └── ServerManager.ts     # Language server lifecycle management
│   │   │   ├── language-manager.ts      # Language detection and configuration
│   │   │   └── diagnostics-manager.ts   # Diagnostic message management
│   │   └── package.json                 # LSP package configuration
│   │
│   ├── 📁 dap/                          # Debug Adapter Protocol Client
│   │   ├── src/                         # DAP package source code
│   │   │   ├── 📁 client/               # DAP client implementation
│   │   │   │   ├── DAPClient.ts         # DAP client core
│   │   │   │   └── DAPSession.ts        # Individual debug session management
│   │   │   ├── 📁 ui/                   # Debugger UI components
│   │   │   │   └── DebuggerUI.tsx       # React debugger UI component
│   │   │   ├── debug-manager.ts         # Debug session management
│   │   │   └── breakpoint-manager.ts    # Breakpoint management
│   │   └── package.json                 # DAP package configuration
│   │
│   ├── 📁 extensions/                   # Extension Runtime System
│   │   ├── src/                         # Extensions package source code
│   │   │   ├── 📁 host/                 # Extension host
│   │   │   │   ├── ExtensionHost.ts     # Extension host process manager
│   │   │   │   └── ProcessManager.ts    # Extension process lifecycle management
│   │   │   ├── 📁 api/                  # Extension API surface
│   │   │   │   ├── ExtensionAPI.ts      # VS Code-compatible extension API
│   │   │   │   ├── AbsoluteAPI.ts       # Absolute-specific extension API
│   │   │   │   ├── ContributionPoints.ts # Extension contribution points
│   │   │   │   └── types.ts             # Extension API type definitions
│   │   │   ├── 📁 registry/             # Extension registry
│   │   │   │   └── ExtensionRegistry.ts # Extension discovery and registration
│   │   │   ├── 📁 isolation/            # Extension isolation
│   │   │   │   └── sandbox-manager.ts   # Extension sandboxing and security
│   │   │   └── extension-manager.ts     # Extension lifecycle management
│   │   └── package.json                 # Extensions package configuration
│   │
│   ├── 📁 ai/                           # AI System Core
│   │   ├── src/                         # AI package source code
│   │   │   ├── 📁 chat/                 # Chat System
│   │   │   │   ├── 📁 core/             # Chat core components
│   │   │   │   │   ├── ChatSession.ts   # Individual chat session management
│   │   │   │   │   ├── ChatMessage.ts   # Chat message data structure
│   │   │   │   │   ├── ChatThread.ts    # Chat thread/conversation management
│   │   │   │   │   └── ChatManager.ts   # Chat system orchestration
│   │   │   │   ├── 📁 context/          # Context Engine
│   │   │   │   │   ├── ContextBuilder.ts # Context aggregation and building
│   │   │   │   │   ├── ContextWindow.ts  # Context window/token management
│   │   │   │   │   └── 📁 providers/    # Context providers
│   │   │   │   │       ├── EditorContext.ts # Editor state context provider
│   │   │   │   │       ├── FileContext.ts   # File system context provider
│   │   │   │   │       ├── TerminalContext.ts # Terminal context provider
│   │   │   │   │       └── GitContext.ts    # Git repository context provider
│   │   │   │   ├── 📁 tools/            # AI Tools System
│   │   │   │   │   ├── ToolRegistry.ts  # Tool registration and discovery
│   │   │   │   │   ├── 📁 fs-tools/     # File system tools
│   │   │   │   │   │   ├── EditFileTool.ts  # File editing tool
│   │   │   │   │   │   ├── CreateFileTool.ts # File creation tool
│   │   │   │   │   │   ├── DeleteFileTool.ts # File deletion tool
│   │   │   │   │   │   └── ReadFileTool.ts  # File reading tool
│   │   │   │   │   ├── 📁 shell-tools/  # Shell/terminal tools
│   │   │   │   │   │   ├── ExecuteCommandTool.ts # Command execution tool
│   │   │   │   │   │   └── RunScriptTool.ts   # Script execution tool
│   │   │   │   │   ├── 📁 lsp-tools/    # LSP integration tools
│   │   │   │   │   │   ├── FindReferencesTool.ts # Find references tool
│   │   │   │   │   │   ├── GetSymbolsTool.ts   # Get symbols tool
│   │   │   │   │   │   └── GetDiagnosticsTool.ts # Get diagnostics tool
│   │   │   │   │   ├── 📁 git-tools/    # Git integration tools
│   │   │   │   │   │   ├── GitStatusTool.ts    # Git status tool
│   │   │   │   │   │   └── GitDiffTool.ts      # Git diff tool
│   │   │   │   │   └── 📁 editor-tools/ # Editor integration tools
│   │   │   │   │       ├── ApplyEditTool.ts    # Apply text edits tool
│   │   │   │   │       └── FormatCodeTool.ts   # Code formatting tool
│   │   │   │   └── 📁 streaming/        # Streaming communication
│   │   │   │       ├── WebSocketManager.ts     # WebSocket connection management
│   │   │   │       └── WebSocketStream.ts      # WebSocket streaming adapter
│   │   │   │
│   │   │   ├── 📁 autocomplete/         # Inline Autocomplete System
│   │   │   │   ├── InlineCompletion.ts  # Inline completion provider
│   │   │   │   ├── SuggestionRanker.ts  # Suggestion ranking algorithm
│   │   │   │   └── CompletionProvider.ts # AI-powered completion provider
│   │   │   │
│   │   │   ├── 📁 inline-chat/          # Inline Chat UI Components
│   │   │   │   ├── InlineChatWidget.tsx # Inline chat React component
│   │   │   │   ├── DiffPreview.tsx      # Diff preview React component
│   │   │   │   └── MessageBubble.tsx    # Chat message bubble component
│   │   │   │
│   │   │   ├── 📁 code-actions/         # AI Code Actions
│   │   │   │   ├── ErrorFixer.ts        # Error fixing suggestions
│   │   │   │   ├── DocGenerator.ts      # Documentation generation
│   │   │   │   └── RefactorSuggestions.ts # Code refactoring suggestions
│   │   │   │
│   │   │   ├── 📁 pair-programming/     # Pair Programming Features
│   │   │   │   ├── LiveReview.ts        # Live code review
│   │   │   │   └── StyleLearner.ts      # Coding style learning
│   │   │   │
│   │   │   ├── 📁 indexing/             # Code Indexing System
│   │   │   │   ├── Indexer.ts           # Code indexing engine
│   │   │   │   ├── EmbeddingService.ts  # Text embedding service
│   │   │   │   └── vector-store.ts      # Vector storage implementation
│   │   │   │
│   │   │   ├── 📁 retrieval/            # Retrieval-Augmented Generation (RAG)
│   │   │   │   ├── semantic-search.ts   # Semantic search implementation
│   │   │   │   └── context-retriever.ts # Context retrieval engine
│   │   │   │
│   │   │   ├── 📁 providers/            # AI Provider Abstraction
│   │   │   │   ├── ProviderInterface.ts # AI provider interface
│   │   │   │   ├── OpenAIProvider.ts    # OpenAI API provider
│   │   │   │   ├── AnthropicProvider.ts # Anthropic Claude API provider
│   │   │   │   ├── OllamaProvider.ts    # Ollama local provider
│   │   │   │   └── LocalProvider.ts     # Local model provider
│   │   │   │
│   │   │   ├── 📁 policy/               # AI Policy and Security
│   │   │   │   ├── RedactionService.ts  # Sensitive data redaction
│   │   │   │   └── AllowlistManager.ts  # Operation allowlisting
│   │   │   │
│   │   │   ├── 📁 agents/               # AI Agents
│   │   │   │   ├── agent-manager.ts     # Agent lifecycle management
│   │   │   │   ├── coding-agent.ts      # Coding assistance agent
│   │   │   │   └── review-agent.ts      # Code review agent
│   │   │   │
│   │   │   ├── ChatEngine.ts            # Main chat engine orchestration
│   │   │   ├── RetrievalEngine.ts       # Retrieval engine orchestration
│   │   │   └── ai-worker.ts             # AI worker process implementation
│   │   └── package.json                 # AI package configuration
│   │
│   ├── 📁 ui/                           # Shared UI Components
│   │   ├── src/                         # UI package source code
│   │   │   ├── 📁 components/           # React Components
│   │   │   │   ├── 📁 base/             # Base UI components
│   │   │   │   │   ├── Button.tsx       # Button component
│   │   │   │   │   ├── Input.tsx        # Input component
│   │   │   │   │   ├── Select.tsx       # Select/dropdown component
│   │   │   │   │   └── Modal.tsx        # Modal dialog component
│   │   │   │   ├── 📁 layout/           # Layout components
│   │   │   │   │   ├── Panel.tsx        # Panel component
│   │   │   │   │   ├── SplitPane.tsx    # Split pane component
│   │   │   │   │   └── Resizable.tsx    # Resizable component
│   │   │   │   ├── 📁 editor/           # Editor-related components
│   │   │   │   │   ├── CodeBlock.tsx    # Code block display component
│   │   │   │   │   ├── CodeDiffView.tsx # Code diff view component
│   │   │   │   │   └── MarkdownRenderer.tsx # Markdown renderer component
│   │   │   │   └── 📁 ai/               # AI-specific components
│   │   │   │       ├── ChatBubble.tsx   # Chat message bubble
│   │   │   │       ├── ThinkingIndicator.tsx # AI thinking indicator
│   │   │   │       └── ContextSelector.tsx # Context selection component
│   │   │   ├── 📁 hooks/                # Custom React Hooks
│   │   │   │   ├── useMonaco.ts         # Monaco editor hook
│   │   │   │   ├── useFileSystem.ts     # File system operations hook
│   │   │   │   ├── useAI.ts             # AI features hook
│   │   │   │   └── useWorkspace.ts      # Workspace operations hook
│   │   │   ├── 📁 stores/               # State Management (Zustand)
│   │   │   │   ├── createStore.ts       # Store factory function
│   │   │   │   ├── editor-store.ts      # Editor state store
│   │   │   │   ├── workspace-store.ts   # Workspace state store
│   │   │   │   └── ai-store.ts          # AI state store
│   │   │   └── index.ts                 # UI package public API
│   │   └── package.json                 # UI package configuration
│   │
│   └── 📁 renderer/                     # Renderer Application (React)
│       ├── src/                         # Renderer source code
│       │   ├── main.tsx                 # React application entry point
│       │   ├── App.tsx                  # Root React component
│       │   ├── 📁 app/                  # Application shell
│       │   │   ├── AppShell.tsx         # Application shell component
│       │   │   └── routes.tsx           # Application routing configuration
│       │   │
│       │   ├── 📁 editor/               # Editor Integration
│       │   │   ├── Editor.tsx           # Monaco editor React wrapper
│       │   │   ├── EditorProvider.tsx   # Editor context provider
│       │   │   ├── EditorCommands.ts    # Editor command definitions
│       │   │   └── editor-config.ts     # Editor configuration
│       │   │
│       │   ├── 📁 features/             # Feature Modules (Organized by domain)
│       │   │   ├── 📁 explorer/         # File Explorer Feature
│       │   │   │   ├── FileTree.tsx     # File tree component
│       │   │   │   ├── FileTreeItem.tsx # File tree item component
│       │   │   │   ├── FileTreeContext.tsx # File tree context
│       │   │   │   └── Breadcrumb.tsx   # Breadcrumb navigation
│       │   │   ├── 📁 search/           # Global Search Feature
│       │   │   │   ├── SearchView.tsx   # Search interface component
│       │   │   │   └── SearchResults.tsx # Search results component
│       │   │   ├── 📁 terminal/         # Terminal Feature
│       │   │   │   ├── TerminalPanel.tsx # Terminal panel component
│       │   │   │   └── TerminalTab.tsx  # Terminal tab component
│       │   │   ├── 📁 debugger/         # Debugger Feature
│       │   │   │   ├── DebugView.tsx    # Debugger interface component
│       │   │   │   ├── BreakpointPanel.tsx # Breakpoint panel
│       │   │   │   └── VariablesPanel.tsx # Variables inspection panel
│       │   │   └── 📁 git/              # Git Integration Feature
│       │   │       ├── GitPanel.tsx     # Git panel component
│       │   │       └── DiffView.tsx     # Diff view component
│       │   │
│       │   ├── 📁 ui/                   # UI Components (Renderer-specific)
│       │   │   ├── 📁 chat-panel/       # Chat Panel Components
│       │   │   │   ├── ChatPanel.tsx    # Main chat panel component
│       │   │   │   ├── MessageList.tsx  # Message list component
│       │   │   │   ├── ChatInput.tsx    # Chat input component
│       │   │   │   ├── ThinkingProcess.tsx # AI thinking process display
│       │   │   │   ├── MessageBubble.tsx # Chat message bubble
│       │   │   │   ├── CodeBlock.tsx    # Code block in chat
│       │   │   │   ├── ChatHistory.tsx  # Chat history component
│       │   │   │   ├── QuickActions.tsx # Quick action buttons
│       │   │   │   └── MarkdownRenderer.tsx # Markdown renderer for chat
│       │   │   ├── 📁 shared/           # Shared UI Components
│       │   │   │   ├── CodeDiffView.tsx # Code diff viewer
│       │   │   │   ├── ContextPill.tsx  # Context indicator pill
│       │   │   │   ├── BackendStatus.tsx # Backend status indicator
│       │   │   │   ├── ContextSelector.tsx # Context selector component
│       │   │   │   └── FileTreeContext.tsx # File tree context menu
│       │   │   ├── 📁 commands/         # Command System Components
│       │   │   │   ├── SlashCommands.tsx # Slash command interface
│       │   │   │   └── CommandPalette.tsx # Command palette component
│       │   │   ├── 📁 workbench/        # Workbench Layout Components
│       │   │   │   ├── Workbench.tsx    # Main workbench layout
│       │   │   │   ├── Sidebar.tsx      # Sidebar component
│       │   │   │   ├── ActivityBar.tsx  # Activity bar component
│       │   │   │   ├── EditorPane.tsx   # Editor pane component
│       │   │   │   ├── Panel.tsx        # Bottom panel component
│       │   │   │   └── StatusBar.tsx    # Status bar component
│       │   │   │
│       │   │
│       │   ├── 📁 providers/            # Context Providers
│       │   │   ├── ThemeProvider.tsx    # Theme context provider
│       │   │   ├── WorkspaceProvider.tsx # Workspace context provider
│       │   │   ├── EditorProvider.tsx   # Editor context provider
│       │   │   └── AIProvider.tsx       # AI context provider
│       │   │
│       │   ├── 📁 services/             # Backend Services (Renderer-side)
│       │   │   ├── AIService.ts         # AI service client
│       │   │   ├── WebSocketService.ts  # WebSocket service
│       │   │   ├── FileSystemService.ts # File system service client
│       │   │   └── TerminalService.ts   # Terminal service client
│       │   │
│       │   ├── 📁 config/               # Configuration
│       │   │   └── backend-config.json  # Backend service configuration
│       │   │
│       │   └── 📁 styles/               # Styling
│       │       ├── 📁 themes/           # Theme definitions
│       │       │   ├── dark.ts          # Dark theme configuration
│       │       │   ├── light.ts         # Light theme configuration
│       │       │   └── high-contrast.ts # High contrast theme
│       │       └── globals.css          # Global CSS styles
│       │
│       ├── index.html                   # HTML entry point
│       ├── vite.config.ts               # Vite configuration for renderer
│       └── package.json                 # Renderer package configuration
│
├── 📁 extensions-builtin/               # Built-in Extensions
│   ├── 📁 typescript/                   # TypeScript Language Support
│   │   ├── package.json                 # TypeScript extension manifest
│   │   └── src/                         # TypeScript extension source
│   │       ├── extension.ts             # TypeScript extension entry point
│   │       └── language-server.ts       # TypeScript language server integration
│   ├── 📁 python/                       # Python Language Support
│   │   ├── package.json                 # Python extension manifest
│   │   └── src/                         # Python extension source
│   │       ├── extension.ts             # Python extension entry point
│   │       └── language-server.ts       # Python language server integration
│   ├── 📁 rust/                         # Rust Language Support
│   │   ├── package.json                 # Rust extension manifest
│   │   └── src/                         # Rust extension source
│   │       ├── extension.ts             # Rust extension entry point
│   │       └── language-server.ts       # Rust language server integration
│   ├── 📁 markdown/                     # Markdown Support
│   │   ├── package.json                 # Markdown extension manifest
│   │   └── src/                         # Markdown extension source
│   │       ├── extension.ts             # Markdown extension entry point
│   │       └── preview.tsx              # Markdown preview component
│   └── 📁 absolute-ai/                  # Built-in AI Features Extension
│       ├── package.json                 # AI extension manifest
│       └── src/                         # AI extension source
│           ├── extension.ts             # AI extension entry point
│           └── ai-commands.ts           # AI command definitions
│
├── 📁 scripts/                          # Build and Development Scripts
│   ├── 📁 electron/                     # Electron-specific scripts
│   │   ├── notarize.js                  # macOS app notarization script
│   │   └── sign.js                      # Code signing script
│   ├── build.ts                         # Main build script
│   ├── package.ts                       # Package preparation script
│   ├── release.ts                       # Release automation script
│   ├── setup.sh                         # Development environment setup
│   ├── clean.sh                         # Clean build artifacts
│   └── dev.sh                           # Development server script
│
├── 📁 docs/                             # Documentation
│   ├── 📁 architecture/                 # Architecture Documentation
│   │   ├── ARCHITECTURE_MAP.md         # High-level architecture overview
│   │   ├── FILE_STRUCTURE.md           # Detailed file structure (this document)
│   │   └── PROCESS_FLOW.md             # Process and data flow diagrams
│   ├── 📁 decisions/                    # Architecture Decision Records (ADR)
│   │   ├── ADR-001-monorepo-structure.md # Monorepo structure decision
│   │   ├── ADR-002-process-isolation.md # Process isolation decision
│   │   ├── ADR-003-ipc-design.md       # IPC design decision
│   │   └── ADR-004-ai-integration.md   # AI integration decision
│   ├── 📁 api/                          # API Documentation
│   │   ├── API_REFERENCE.md            # Complete API reference
│   │   └── EXTENSION_API.md            # Extension API documentation
│   └── 📁 guides/                       # Guides and Tutorials
│       ├── CONTRIBUTING.md             # Contribution guidelines
│       └── EXTENSION_DEVELOPMENT.md    # Extension development guide
│
├── 📁 tests/                            # Test Suite
│   ├── 📁 unit/                         # Unit Tests
│   │   ├── core/                       # Core utilities unit tests
│   │   │   ├── EventEmitter.test.ts
│   │   │   ├── Logger.test.ts
│   │   │   └── URI.test.ts
│   │   ├── editor/                     # Editor unit tests
│   │   │   ├── editor-core.test.ts
│   │   │   └── language-registry.test.ts
│   │   └── ai/                         # AI unit tests
│   │       ├── ChatSession.test.ts
│   │       ├── ToolRegistry.test.ts
│   │       └── ProviderInterface.test.ts
│   ├── 📁 integration/                  # Integration Tests
│   │   ├── lsp/                        # LSP integration tests
│   │   │   ├── LSPClient.test.ts
│   │   │   └── language-manager.test.ts
│   │   ├── extensions/                 # Extensions integration tests
│   │   │   ├── ExtensionHost.test.ts
│   │   │   └── extension-manager.test.ts
│   │   └── ai/                         # AI integration tests
│   │       ├── ChatEngine.test.ts
│   │       └── RetrievalEngine.test.ts
│   └── 📁 e2e/                         # End-to-End Tests
│       ├── playwright.config.ts         # Playwright configuration
│       ├── 📁 tests/                    # E2E test files
│       │   ├── app.spec.ts             # Application lifecycle tests
│       │   ├── editor.spec.ts          # Editor functionality tests
│       │   └── ai-chat.spec.ts         # AI chat functionality tests
│       └── 📁 fixtures/                 # Test fixtures
│           ├── test-workspace/          # Test workspace structure
│           ├── test-file.ts             # Test file content
│           └── test-config.json         # Test configuration
│
├── 📁 configs/                          # Shared Configuration Files
│   ├── tsconfig.base.json              # Base TypeScript configuration
│   ├── tsconfig.node.json              # Node.js TypeScript configuration
│   ├── tsconfig.web.json               # Web TypeScript configuration
│   ├── vite.config.base.ts             # Base Vite configuration
│   └── eslint.config.js                # ESLint configuration
│
├── .editorconfig                       # Editor configuration for consistent coding styles
├── .gitignore                          # Git ignore file
├── .prettierrc                         # Prettier code formatter configuration
├── LICENSE                             # Project license (MIT or other)
├── README.md                           # Project README with overview and setup
├── package.json                        # Root package.json (monorepo manager)
├── pnpm-workspace.yaml                 # pnpm workspace configuration
├── turbo.json                          # Turborepo build system configuration
├── tsconfig.json                       # Root TypeScript configuration
├── vite.config.ts                      # Root Vite configuration
└── electron-builder.json               # Electron builder configuration