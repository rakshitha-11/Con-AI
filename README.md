## 🧩 Session Management Module – Create Session User

This module is responsible for initializing a new user session each time a user starts interacting with the chatbot. It assigns a unique session ID and prepares the context for storing conversation history, enabling a more personalized and continuous experience.

### 🔧 Features:
- Generates a unique `session_id` using UUID.
- Records the session creation time.
- Initializes an empty context for chat history.
- Enables tracking for multi-turn conversations.

### 🧪 Sample Code:
```python
from uuid import uuid4
from datetime import datetime

def create_session():
    session_id = str(uuid4())
    session_data = {
        "session_id": session_id,
        "created_at": datetime.now(),
        "context": [],
    }
    # save_session(session_data) → this would store in DB
    return {"session_id": session_id, "message": "Session created successfully"}
