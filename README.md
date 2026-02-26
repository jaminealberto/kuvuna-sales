<!DOCTYPE html>
<html lang="pt">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>KUVUNA - Protótipo Plataforma</title>
<style>
    body { font-family: Arial, sans-serif; margin:0; background:#f5f5f5; }
    header { background:#0E7C4F; color:#fff; padding:1rem; display:flex; justify-content:space-between; align-items:center; }
    header h1 { margin:0; }
    nav { background:#111; width:200px; min-height:100vh; color:#fff; position:fixed; top:0; left:0; padding-top:3rem; }
    nav a { display:block; color:#fff; padding:1rem; text-decoration:none; }
    nav a:hover { background:#0E7C4F; }
    main { margin-left:200px; padding:2rem; }
    .card { background:#fff; padding:1rem; margin-bottom:1rem; border-radius:8px; box-shadow:0 2px 5px rgba(0,0,0,0.1); }
    canvas { max-width:100%; }
    .green { color:#0E7C4F; }
    .gold { color:#D4A017; }
    .btn { padding:0.5rem 1rem; background:#0E7C4F; color:#fff; border:none; border-radius:5px; cursor:pointer; }
    .btn:hover { background:#0b5c38; }
</style>
</head>
<body>
<header>
    <h1>KUVUNA</h1>
    <div>Bem-vindo, Usuário</div>
</header>
<nav>
    <a href="#dashboard">Dashboard</a>
    <a href="#produtos">Meus Produtos</a>
    <a href="#afiliados">Afiliados</a>
    <a href="#relatorios">Relatórios</a>
    <a href="#configuracoes">Configurações</a>
</nav>
<main>
<section id="dashboard">
    <h2>Dashboard</h2>
    <div class="card">
        <h3>Vendas Mensais: <span class="gold">1.000.000 MZN</span></h3>
        <h3>Produtores Ativos: <span class="green">100</span></h3>
        <h3>Afiliados Ativos: <span class="green">500</span></h3>
        <h3>Ticket Médio: <span class="gold">500 MZN</span></h3>
        <canvas id="graficoVendas"></canvas>
    </div>
</section>
<section id="produtos">
    <h2>Meus Produtos</h2>
    <div class="card">
        <button class="btn">Adicionar Produto</button>
        <ul>
            <li>Curso de Marketing Digital - 500 MZN</li>
            <li>Ebook Empreendedorismo - 350 MZN</li>
        </ul>
    </div>
</section>
<section id="afiliados">
    <h2>Afiliados</h2>
    <div class="card">
        <ul>
            <li>João Silva - 50 vendas</li>
            <li>Maria Santos - 40 vendas</li>
        </ul>
    </div>
</section>
<section id="relatorios">
    <h2>Relatórios</h2>
    <div class="card">
        <canvas id="graficoRelatorio"></canvas>
    </div>
</section>
<section id="configuracoes">
    <h2>Configurações</h2>
    <div class="card">
        <p>Métodos de pagamento: M-Pesa, e-Mola, Mkesh, PayPal, Cartão</p>
        <p>Moeda selecionada: MZN</p>
        <p>Comissão de Afiliados: 40-60%</p>
    </div>
</section>
<script src="https://cdn.jsdelivr.net/npm/chart.js"></script>
<script>
    const ctx = document.getElementById('graficoVendas').getContext('2d');
    const graficoVendas = new Chart(ctx, {
        type: 'line',
        data: {
            labels: ['Jan','Fev','Mar','Abr','Mai','Jun'],
            datasets: [{
                label: 'Vendas MZN',
                data: [200000, 300000, 400000, 500000, 600000, 1000000],
                borderColor: '#D4A017',
                backgroundColor: 'rgba(212,160,23,0.2)',
                tension:0.3
            }]
        }
    });

    const ctx2 = document.getElementById('graficoRelatorio').getContext('2d');
    const graficoRelatorio = new Chart(ctx2, {
        type: 'bar',
        data: {
            labels: ['Produtor A','Produtor B','Produtor C'],
            datasets: [{
                label: 'Vendas',
                data: [50, 30, 20],
                backgroundColor: ['#0E7C4F','#D4A017','#0E7C4F']
            }]
        }
    });
</script>
</body>
</html>
