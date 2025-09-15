# 🚀 Lynkless Deployment Guide

## GitHub Pages Deployment

### Quick Setup
1. Go to your repository: https://github.com/Sathvik-Nagesh/lynkless
2. Click on **Settings** tab
3. Scroll down to **Pages** section in the left sidebar
4. Under **Source**, select **Deploy from a branch**
5. Choose **main** branch and **/ (root)** folder
6. Click **Save**

### Access Your Deployed App
Once deployed, your app will be available at:
**https://sathvik-nagesh.github.io/lynkless/**

## Alternative Deployment Options

### Netlify (Recommended for WebRTC)
1. Go to [netlify.com](https://netlify.com)
2. Connect your GitHub account
3. Select the `lynkless` repository
4. Deploy settings:
   - Build command: (leave empty)
   - Publish directory: `/` (root)
5. Click **Deploy site**

### Vercel
1. Go to [vercel.com](https://vercel.com)
2. Import your GitHub repository
3. Deploy with default settings

## Testing the Deployment

### Local Testing
```bash
# Start local server
python -m http.server 8000

# Open in browser
http://localhost:8000
```

### Production Testing
1. Open the deployed URL in multiple browser tabs
2. Copy Peer ID from one tab
3. Enter it in another tab's connection field
4. Upload files and test sharing
5. Try the chat functionality

## Features Working in Production

✅ **WebRTC Peer-to-Peer Connections**
✅ **Real-time File Sharing** (16KB chunks)
✅ **Chat Functionality**
✅ **Network Discovery**
✅ **Cross-device Sharing** (via URLs)
✅ **Progress Tracking**
✅ **Error Handling**

## Troubleshooting

### WebRTC Issues
- Ensure you're using HTTPS in production
- Check browser console for WebRTC errors
- Try different STUN servers if needed

### File Sharing Issues
- Large files are chunked automatically
- Check network connectivity
- Verify peer connections are established

### Connection Issues
- Make sure both devices are on the same network
- Check firewall settings
- Try refreshing the page

## Browser Support

- ✅ Chrome (recommended)
- ✅ Firefox
- ✅ Safari
- ✅ Edge
- ❌ Internet Explorer (not supported)

## Security Notes

- All connections are peer-to-peer (no server storage)
- Files are transferred directly between devices
- No data is stored on external servers
- WebRTC requires HTTPS in production
