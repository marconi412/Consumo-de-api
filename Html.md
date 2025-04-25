<!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="UTF-8">
  <title>Lista de Usuários</title>
</head>
<body>
  <h1>Usuários</h1>
  <ul id="lista-usuarios"></ul>

  <script>
    async function carregarUsuarios() {
      try {
        const resposta = await fetch('http://localhost:3000/api/usuarios');
        const usuarios = await resposta.json();

        const lista = document.getElementById('lista-usuarios');
        usuarios.forEach(usuario => {
          const item = document.createElement('li');
          item.textContent = `${usuario.nome} - ${usuario.idade} anos`;
          lista.appendChild(item);
        });
      } catch (erro) {
        console.error('Erro ao carregar usuários:', erro);
      }
    }

    carregarUsuarios();
  </script>
</body>
</html>
