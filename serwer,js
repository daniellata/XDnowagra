const express = require('express');
const path = require('path');
const cors = require('cors');
const app = express();
app.use(express.json()); // do obsługi JSON payloadów
app.use(cors()); // umożliwiający CORS

let highScore = { score: 0, time: Date.now() };

app.get('/highscore', (req, res) => {
    res.json(highScore);
});

app.post('/highscore', (req, res) => {
    const score = req.body.score;
    const time = Date.now();

    if (score > highScore.score) {
        highScore = { score, time };
    }

    res.json(highScore);
});

// Obsługa statycznych plików
app.use(express.static(path.join(__dirname, 'public'))); // Załóżmy, że plik HTML jest w katalogu 'public'

app.listen(3000, () => {
    console.log('Server is listening on port 3000');
});
