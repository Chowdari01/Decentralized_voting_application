# Decentralized Voting Application

A blockchain-based voting system with facial recognition for voter verification.

## Features

- 🔐 **Facial Recognition**: Uses DeepFace for voter identity verification
- 🗳️ **Blockchain Integration**: Smart contracts for secure voting
- 📱 **Web Interface**: Modern, responsive web application
- 👥 **Admin Dashboard**: Manage candidates and monitor voting
- 🔍 **Voter Verification**: Real-time voter status checking

## Quick Start

### Local Development

1. **Clone the repository**:
   ```bash
   git clone <your-repo-url>
   cd Decentralized_voting_application
   ```

2. **Install dependencies**:
   ```bash
   pip install -r requirements.txt
   ```

3. **Run the application**:
   ```bash
   python app.py
   ```

4. **Open your browser**:
   Navigate to `http://localhost:5000`

## Deployment

### Deploy to Vercel

This application is configured for deployment on Vercel. See [DEPLOYMENT.md](./DEPLOYMENT.md) for detailed instructions.

**Quick deployment**:
```bash
# Using the deployment script
./deploy.sh  # Linux/Mac
deploy.bat   # Windows

# Or manually
vercel --prod
```

### Alternative Platforms

For production use, consider:
- **Railway**: Full Flask support with persistent storage
- **Heroku**: Traditional Flask deployment
- **DigitalOcean**: VPS with full control

## Project Structure

```
Decentralized_voting_application/
├── app.py              # Main Flask application
├── contracts/          # Smart contract files
├── static/            # CSS, JS, and static assets
├── templates/         # HTML templates
├── uploads/           # Temporary file storage
├── requirements.txt   # Python dependencies
├── vercel.json       # Vercel configuration
└── DEPLOYMENT.md     # Deployment guide
```

## Technologies Used

- **Backend**: Flask (Python)
- **Frontend**: HTML, CSS, JavaScript
- **Blockchain**: Solidity smart contracts
- **AI**: DeepFace for facial recognition
- **Deployment**: Vercel (serverless)

## Contributing

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Submit a pull request

## License

This project is licensed under the MIT License.