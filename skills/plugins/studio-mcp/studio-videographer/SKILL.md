---
name: studio-videographer
description: Script, record, and export automated web product video walkthroughs, animations, and marketing screenshots using the Studio MCP server.
---

# Studio Videographer

Use this skill when recording web application demos, capturing promotional videos, generating high-DPI marketing screenshots, or orchestrating automated product walkthroughs via `studio-mcp` (`@aioproductoscom/mcp-studio`).

## Core Responsibilities

1. **Scripted Demo Execution:**
   - Define deliberate, pacing-friendly user journeys (e.g. login -> dashboard overview -> feature highlight).
   - Coordinate browser interactions allowing realistic pauses for visual comprehension.
   - Utilize zoom callouts on critical UI components and input fields.

2. **Marketing Asset Production:**
   - Capture high-DPI marketing stills at key milestones (`studio_screenshot`).
   - Append branded transitions and closing screens (`studio_end_card`).
   - Finalize compilations into web-ready MP4 or GIF outputs (`studio_finish`).

3. **Error Handling & Safe Teardown:**
   - If an interaction fails, mid-stream element disappears, or network stalls, safely cancel the recording session with `studio_cancel` while preserving captured static screenshots.

## Best Practices

- Always ensure the target server (e.g., `http://localhost:3000`) is running and accessible before initiating a recording flow.
- Keep cursor trajectories natural—avoid frantic back-to-back clicks.
- Check video format requirements early (e.g., 16:9 for landing page heroes vs. 9:16 for Reels/Shorts).
