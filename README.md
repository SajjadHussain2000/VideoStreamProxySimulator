# **VideoStreamProxySimulator**

A powerful and configurable proxy server designed to simulate streaming delays for testing video playback resilience. Supports HLS (HTTP Live Streaming) and DASH protocols, focusing on **debugging edge cases** such as timeout handling, buffering, and playback failures.

---

## **Features**
1. **Proxy Simulation**:
   - Acts as a middle layer between the video origin server and the player.
   - Monitors session starts, segment requests, and playlist interactions.

2. **Configurable Delays**:
   - Simulate delays for:
     - Playlist responses
     - Video/audio segment delivery
   - Test edge cases like **socket timeouts** and **stuck playlists**.

3. **Scripting Support**:
   - Scriptable delay conditions to customize testing scenarios (e.g., delaying audio segments).

4. **Protocol Support**:
   - Fully supports HLS.
   - Preliminary DASH support.

5. **Real-World Testing**:
   - Validate how streaming players handle network instability, ensuring **robustness** and **graceful failure recovery**.

---

## **Tech Stack**
- **Backend**: Python (Flask)
- **Proxy Logic**: Custom scripting for segment interception
- **Frontend**: HTML/CSS/JS (for visualizing or interacting with the proxy server)

---

## **Setup Instructions**

### **1. Clone the Repository**
```bash
git clone https://github.com/SajjadHussain2000/VideoStreamProxySimulator.git
cd VideoStreamProxySimulator
```

### **2. Install Dependencies**
Ensure Python (3.8+) is installed. Then run:
```bash
pip install -r requirements.txt
```

### **3. Start the Proxy Server**
```bash
python app.py
```
The server runs on `localhost:8080` by default.

---

## **How It Works**

### **Session Detection**:
- Detects when a video streaming session begins (e.g., HLS `m3u8` playlist request).

### **Delay Configuration**:
- Specify delays for:
  - **Playlist Fetching**: Simulate slow playlist delivery.
  - **Segment Fetching**: Introduce lag in video/audio chunks.
  
  Example usage:
  - Delay only audio segments to simulate **audio desync** or **buffer underruns**.

### **Testing Edge Cases**:
- **Timeout Simulation**: Verify how the player reacts to prolonged network responses.
- **Stuck Playlist**: Test if players correctly retry or handle interrupted responses.

---

## **Usage Examples**

1. **Testing Video Buffering**:
   - Delay video segments while serving playlists immediately.

2. **Timeout Handling**:
   - Introduce configurable delays to audio/video requests to test socket timeouts.

3. **Stuck Playback**:
   - Script scenarios where playlists or segments stop responding intermittently.

---

## **Future Improvements**
- Add full DASH protocol support.
- Include UI visualization for easier configuration.
- Enable detailed logging and analytics for video stream performance.

---

## **Contributing**
Contributions are welcome! Follow these steps:
1. Fork the repo.
2. Create a feature branch.
3. Submit a pull request.
