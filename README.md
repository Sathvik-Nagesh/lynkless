# 🌐 Lynkless - Real WebRTC File Sharing

**Local file sharing without servers or links - now with real WebRTC peer-to-peer connections!**

## ✨ Features

### 🚀 **Real WebRTC Implementation**
- **Peer-to-Peer Connections**: Direct device-to-device communication
- **NAT Traversal**: Uses STUN servers to connect through firewalls
- **Data Channels**: High-speed file transfer via WebRTC DataChannels
- **Chunked Transfer**: Large files sent in 64KB chunks for reliability

### 📡 **Network Discovery**
- **Radar System**: Scan for nearby peers on your local network
- **Manual Connection**: Connect using peer IDs
- **Connection Management**: Accept/deny incoming connection requests

### 📁 **File Management**
- **Drag & Drop**: Intuitive file upload interface
- **Multiple Files**: Upload and share multiple files at once
- **File Types**: Support for all file types (images, videos, documents, etc.)
- **Progress Tracking**: Real-time file transfer progress

## 🛠️ **How It Works**

### 1. **WebRTC Connection Setup**
```
User A (Initiator) → Creates Offer → User B (Receiver)
User B → Creates Answer → User A
ICE Candidates exchanged → Direct connection established
```

### 2. **File Transfer Process**
```
File Metadata → File Chunks (64KB) → File Assembly → Download
```

### 3. **Network Discovery**
- **Local Network**: Discovers peers on same WiFi/LAN
- **Manual Entry**: Enter peer IDs manually for connections
- **Connection Requests**: Accept/deny incoming requests

## 🚀 **Getting Started**

### **Prerequisites**
- Modern browser with WebRTC support (Chrome, Firefox, Safari, Edge)
- HTTPS connection (required for WebRTC in production)
- Local network access for peer discovery

### **Quick Start**
1. **Open** the app at https://sathvik-nagesh.github.io/lynkless/
2. **Click** "📡 Radar" tab
3. **Click** "🔍 Scan for Users" to discover peers
4. **Click** "Connect" on any discovered user
5. **Accept** connection requests in the "👥 Peers" tab
6. **Upload** files and share them with connected peers

## 🔧 **Technical Details**

### **WebRTC Configuration**
```javascript
const peerConnection = new RTCPeerConnection({
    iceServers: [
        { urls: 'stun:stun.l.google.com:19302' },
        { urls: 'stun:stun1.l.google.com:19302' }
    ]
});
```

### **File Transfer Protocol**
- **Chunk Size**: 64KB for optimal performance
- **Ordered Delivery**: Ensures file integrity
- **Progress Tracking**: Real-time transfer status
- **Error Handling**: Automatic retry and recovery

### **Security Features**
- **Peer Verification**: Manual connection approval required
- **Local Network**: Peers only visible on same network
- **No Server Storage**: Files never stored on external servers

## 🌍 **Deployment Options**

### **Local Development**
```bash
# Simple local server
python -m http.server 8000
# or
npx serve .
```

### **🚀 GitHub Pages (Live Now!)**
1. **Go to**: https://github.com/Sathvik-Nagesh/lynkless
2. **Settings** → **Pages** → **Deploy from branch** → **main** → **/ (root)**
3. **Access your live app**: https://sathvik-nagesh.github.io/lynkless/

### **Production Deployment**
- **HTTPS Required**: WebRTC requires secure connection
- **STUN Servers**: Configure custom STUN/TURN servers if needed
- **CDN**: Optional for faster loading

## 🔮 **Future Enhancements**

### **Planned Features**
- [ ] **Signaling Server**: Real-time peer discovery
- [ ] **File Encryption**: End-to-end encryption
- [ ] **Group Sharing**: Share with multiple peers simultaneously
- [ ] **Resume Transfer**: Resume interrupted file transfers
- [ ] **Mobile App**: Native mobile applications

### **Advanced WebRTC Features**
- [ ] **TURN Servers**: Fallback for complex network configurations
- [ ] **Multiple Data Channels**: Parallel file transfers
- [ ] **Bandwidth Management**: Adaptive chunk sizing
- [ ] **Connection Pooling**: Multiple peer connections

## 🐛 **Troubleshooting**

### **Common Issues**

#### **WebRTC Not Working**
- Ensure HTTPS connection (required for WebRTC)
- Check browser compatibility
- Verify STUN server accessibility

#### **Connection Failures**
- Check firewall settings
- Ensure both devices on same network
- Try different STUN servers

#### **File Transfer Issues**
- Check file size limits
- Verify peer connection status
- Monitor browser console for errors

### **Debug Mode**
Open browser console to see detailed WebRTC logs:
```javascript
// Enable WebRTC logging
localStorage.setItem('webrtc-debug', 'true');
```

## 📚 **API Reference**

### **Core Methods**
```javascript
// Initialize WebRTC
await lynklessApp.initializeWebRTC();

// Connect to peer
await lynklessApp.connectToPeerManually(peerId);

// Share files
await lynklessApp.shareFilesWithPeer(peerId);

// Send message
lynklessApp.sendToPeer('message-type', data);
```

### **Event Handlers**
```javascript
// Connection events
lynklessApp.peerConnection.onicecandidate
lynklessApp.peerConnection.ondatachannel

// Data channel events
lynklessApp.dataChannel.onopen
lynklessApp.dataChannel.onmessage
lynklessApp.dataChannel.onclose
```

## 🤝 **Contributing**

### **Development Setup**
1. Fork the repository
2. Create feature branch
3. Make changes
4. Test thoroughly
5. Submit pull request

### **Testing**
- Test on multiple browsers
- Verify file transfer reliability
- Check network compatibility
- Test with large files

## 📄 **License**

MIT License - see LICENSE file for details.

## 🙏 **Acknowledgments**

- **WebRTC**: Real-time communication technology
- **STUN Servers**: Google's free STUN service
- **Browser APIs**: File API, Drag & Drop, etc.

---

**Built with ❤️ for secure, local file sharing**

