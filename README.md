package.json
{
  "name": "fin-lean-mvp2",
  "version": "1.0.0",
  "scripts": {
    "dev": "next dev",
    "build": "next build",
    "start": "next start"
  },
  "dependencies": {
    "next": "14.2.5",
    "react": "18.2.0",
    "react-dom": "18.2.0"
  }
}
vercel.json
{
  "version": 2,
  "builds": [
    { "src": "package.json", "use": "@vercel/next" }
  ]
}
pages/index.js
import { useState } from "react";

export default function Home() {
  const [messages, setMessages] = useState([]);
  const [input, setInput] = useState("");

  const handleSend = () => {
    if (!input) return;
    const userMessage = { role: "user", content: input };
    setMessages([...messages, userMessage]);
    setInput("");

    const aiReply = { role: "assistant", content: "💸 AI Dominatrix: Thank you for your tribute." };
    setMessages((prev) => [...prev, aiReply]);
  };

  return (
    <div style={{ maxWidth: 600, margin: "50px auto", fontFamily: "sans-serif" }}>
      <h1 style={{ textAlign: "center" }}>💸 Findom Lean MVP</h1>
      <div style={{ border: "1px solid #ccc", padding: 10, minHeight: 300 }}>
        {messages.map((msg, i) => (
          <div key={i} style={{ margin: "10px 0" }}>
            <strong>{msg.role === "user" ? "You" : "AI"}:</strong> {msg.content}
          </div>
        ))}
      </div>
      <div style={{ display: "flex", marginTop: 10 }}>
        <input
          type="text"
          value={input}
          onChange={(e) => setInput(e.target.value)}
          style={{ flex: 1, padding: 10 }}
          placeholder="Send a tribute message..."
        />
        <button onClick={handleSend} style={{ padding: "10px 20px" }}>Send</button>
      </div>
    </div>
  );
}
