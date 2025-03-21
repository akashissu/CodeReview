# Code Review Using Google Gemini API

## Project Description
This project leverages **Google Gemini API** to automate and enhance the code review process. It provides AI-powered insights, suggestions, and improvements for better code quality, efficiency, and maintainability. The frontend is built using **React**, while the backend is powered by **Express.js and Node.js**.

## Features
- AI-driven code analysis and review
- Suggestions for optimizing performance, readability, and security
- Supports multiple programming languages
- Integration with Git repositories
- Automated feedback with detailed explanations

## Technologies Used
- **Google Gemini API** for AI-driven code analysis
- **React** for the frontend
- **Express.js & Node.js** for the backend
- **MongoDB/PostgreSQL (Optional)** for database storage
- **Git & GitHub** for version control

## Installation & Setup
### Prerequisites:
- Node.js (>=14.0)
- Google Gemini API access
- Git installed on your system
- MongoDB/PostgreSQL (if using a database)

### Steps:
1. Clone the repository:
   ```sh
   git clone https://github.com/your-username/code-review-gemini.git
   cd code-review-gemini
   ```
2. Set up the backend:
   ```sh
   cd backend
   npm install
   ```
3. Set up environment variables in `.env` file:
   ```sh
   GEMINI_API_KEY=your_api_key_here
   PORT=5000
   ```
4. Start the backend server:
   ```sh
   npm start
   ```
5. Set up the frontend:
   ```sh
   cd ../frontend
   npm install
   ```
6. Start the frontend server:
   ```sh
   npm start
   ```

## Usage
- Submit your code for review via the web interface.
- The AI will analyze the code and provide suggestions for improvements.
- View detailed feedback and make necessary changes.

## Example API Call (Backend)
```javascript
const express = require('express');
const axios = require('axios');
require('dotenv').config();

const app = express();
app.use(express.json());

app.post('/review', async (req, res) => {
    const { code } = req.body;
    try {
        const response = await axios.post('https://gemini-api.example.com/review', 
            { code },
            { headers: { "Authorization": `Bearer ${process.env.GEMINI_API_KEY}` } }
        );
        res.json(response.data);
    } catch (error) {
        res.status(500).json({ error: 'Error processing request' });
    }
});

app.listen(5000, () => console.log('Server running on port 5000'));
```

## Future Enhancements
- Integration with GitHub Actions for automated PR reviews
- Support for more languages and frameworks
- Customizable review rules and configurations

## Contributing
Contributions are welcome! Please follow these steps:
1. Fork the repository.
2. Create a new branch (`feature-xyz`).
3. Commit your changes.
4. Push the branch and create a Pull Request.


