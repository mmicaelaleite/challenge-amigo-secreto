// Array de amigos
let amigos = [];

// Boas-vindas
alert("Bem-vindo ao site Amigo Secreto!");
alert("Adicione todos os nomes que deseja sortear e depois clique em 'Sortear Amigo'.");

// Função para adicionar amigo
function adicionarAmigo() {
    const adiNome = document.getElementById("amigo");
    const nome = adiNome.value.trim();

    // Verifica se o nome é válido
    if (!nome) {
        alert("Por favor, insira um nome válido!");
        return;
    }

    // Insere novo nome no array e atualiza a lista
    amigos.push(nome);
    console.log(`Lista: ${amigos}`);
    atualizarLista();
    adiNome.value = ""; // Limpa campo
}

// Função para atualizar a lista na tela
function atualizarLista() {
    const lista = document.getElementById("listaAmigos");
    lista.innerHTML = ""; // Limpa a lista antes de recriar

    amigos.forEach(amigo => {
        const novoAmigo = document.createElement("li");
        novoAmigo.textContent = amigo;
        lista.appendChild(novoAmigo);
    });
}

// Função para sortear um amigo
function sortearAmigo() {
    if (amigos.length === 0) {
        alert("Adicione pelo menos um amigo antes de sortear!");
        return;
    }

    const indice = Math.floor(Math.random() * amigos.length);
    const sorteado = amigos[indice];
    const resultado = document.getElementById("resultado");
    resultado.textContent = `😁 O amigo secreto sorteado foi: ${sorteado}`;
}
