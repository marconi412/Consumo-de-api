const express = require('express');
const cors = require('cors');
const app = express();
const PORT = 3000;

app.use(cors());

const usuarios = [
  { id: 1, nome: 'João Silva', idade: 30 },
  { id: 2, nome: 'Maria Oliveira', idade: 25 },
  { id: 3, nome: 'Carlos Souza', idade: 35 },
];

app.get('/api/usuarios', (req, res) => {
  res.json(usuarios);
});

app.listen(PORT, () => {
  console.log(`Servidor rodando em http://localhost:${PORT}`);
});
