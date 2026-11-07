
<!DOCTYPE html>
<html lang="pt-BR">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>EBC - Exército Brasileiro de Combate</title>
<style>
*{box-sizing:border-box}
body{margin:0;font-family:Arial,sans-serif;background:#050b18;color:white}
button{cursor:pointer;border:0;border-radius:8px;padding:14px 22px;font-weight:bold}
.screen{min-height:100vh;display:flex;align-items:center;justify-content:center;background:radial-gradient(circle,#102d58,#030711 70%);padding:20px}
.panel{width:100%;max-width:430px;text-align:center;background:#09172b;border:1px solid #17477c;padding:35px 25px;border-radius:16px;box-shadow:0 0 35px #087bff33}
.logo{font-size:35px;font-weight:900;color:#58aaff;letter-spacing:3px}
.sub{color:#9eb8d8;margin:12px 0 28px}
.primary{background:#087cff;color:white;width:100%;margin-top:12px}
.secondary{background:#142c49;color:white;width:100%;margin-top:12px}
.hidden{display:none!important}
#site{min-height:100vh}
header{background:#08172b;border-bottom:1px solid #174477;padding:18px 22px;display:flex;justify-content:space-between;align-items:center;gap:12px}
header strong{color:#58aaff;font-size:22px}
header span{color:#9bb9dc;font-size:12px}
.layout{display:flex;min-height:calc(100vh - 65px)}
nav{width:220px;background:#071326;padding:20px 12px;border-right:1px solid #15375d}
nav button{display:block;width:100%;text-align:left;background:transparent;color:#b8cbe2;margin:4px 0}
nav button:hover{background:#102b4d;color:white}
main{padding:28px;width:100%;max-width:1100px;margin:auto}
h1{color:#65b2ff}
h2{color:#65b2ff}
.card{background:#0b1b31;border:1px solid #183d67;padding:20px;border-radius:12px;margin:14px 0}
.grid{display:grid;grid-template-columns:repeat(auto-fit,minmax(190px,1fr));gap:12px}
.rank{background:#102846;padding:13px;border-radius:8px;border-left:3px solid #1685ff}
.small{color:#9db5d1;font-size:13px}
@media(max-width:650px){
.layout{display:block}
nav{width:100%;display:grid;grid-template-columns:repeat(2,1fr);border-right:0;border-bottom:1px solid #15375d}
main{padding:18px}
}
</style>
</head>
<body>

<!-- TELA INICIAL -->
<section id="startScreen" class="screen">
  <div class="panel">
    <div class="logo">EBC</div>
    <h1>VERIFIQUE-SE</h1>
    <p class="sub">Exército Brasileiro de Combate</p>
    <button class="primary" onclick="showVerify()">VERIFICAR</button>
  </div>
</section>

<!-- ESCOLHA DA VERIFICAÇÃO -->
<section id="verifyScreen" class="screen hidden">
  <div class="panel">
    <div class="logo">EBC</div>
    <h2>Você está se verificando.</h2>
    <p class="sub">Não saia desta página. Depois de voltar, confirme sua verificação.</p>
    <button class="primary" onclick="openRoblox()">VERIFICAR PELA ROBLOX</button>
    <button class="secondary" onclick="backStart()">VOLTAR</button>
    <p class="small">O Roblox será aberto em outra aba. Não informe sua senha neste site.</p>
  </div>
</section>

<!-- TELA DE RETORNO -->
<section id="returnScreen" class="screen hidden">
  <div class="panel">
    <div class="logo">EBC</div>
    <h2>Você voltou!</h2>
    <p class="sub">Se você já realizou sua verificação, confirme abaixo.</p>
    <button class="primary" onclick="enterSite()">JÁ ME VERIFIQUEI</button>
  </div>
</section>

<!-- SITE PRINCIPAL -->
<div id="site" class="hidden">
<header>
  <strong>EBC | EXÉRCITO BRASILEIRO DE COMBATE</strong>
  <span>PORTAL OFICIAL DO GRUPO</span>
</header>

<div class="layout">
<nav>
  <button onclick="openPage('inicio')">⌂ Início</button>
  <button onclick="openPage('hierarquia')">♜ Hierarquia</button>
  <button onclick="openPage('divisoes')">▣ Divisões</button>
  <button onclick="openPage('especiais')">★ Membros especiais</button>
  <button onclick="openPage('regras')">☰ Regras</button>
  <button onclick="openPage('perfil')">♙ Perfil</button>
</nav>

<main>
  <section id="inicio" class="page">
    <h1>QUARTEL-GENERAL DO EBC</h1>
    <div class="card">
      <h2>Bem-vindo ao Exército Brasileiro de Combate!</h2>
      <p>Este é o portal do EBC. Aqui você encontra informações sobre a hierarquia, divisões, regras e organização do nosso grupo.</p>
    </div>
    <div class="grid">
      <div class="card"><h2>HIERARQUIA</h2><p>Consulte todos os postos e graduações.</p><button class="primary" onclick="openPage('hierarquia')">ACESSAR</button></div>
      <div class="card"><h2>DIVISÕES</h2><p>Conheça as unidades do EBC.</p><button class="primary" onclick="openPage('divisoes')">ACESSAR</button></div>
      <div class="card"><h2>REGRAS</h2><p>Consulte as regras do grupo.</p><button class="primary" onclick="openPage('regras')">ACESSAR</button></div>
    </div>
  </section>

  <section id="hierarquia" class="page hidden">
    <h1>HIERARQUIA DO EBC</h1>
    <p class="small">Ordem oficial dos cargos do grupo.</p>
    <div id="rankList" class="grid"></div>
  </section>

  <section id="divisoes" class="page hidden">
    <h1>DIVISÕES DO EXÉRCITO</h1>
    <div class="grid">
      <div class="card"><h2>CIE</h2><p>Centro de Inteligência do Exército</p></div>
      <div class="card"><h2>CIGS</h2><p>Centro de Instrução de Guerra na Selva</p></div>
      <div class="card"><h2>BAC</h2><p>Batalhões de Ações de Comando</p></div>
      <div class="card"><h2>FE</h2><p>Forças Especiais do Exército</p></div>
      <div class="card"><h2>PE</h2><p>Polícia do Exército</p></div>
    </div>
  </section>

  <section id="especiais" class="page hidden">
    <h1>MEMBROS ESPECIAIS</h1>
    <div class="card">
      <h2>Comunicado</h2>
      <p>Boa tarde, membros especiais! Boa tarde aos integrantes do TSE, SGEC e CDE. Sejam todos muito bem-vindos ao Quartel-General do EBC!</p>
    </div>
  </section>

  <section id="regras" class="page hidden">
    <h1>REGRAS DO EBC</h1>
    <div class="card">
      <p>1. Respeitar todos os membros.</p>
      <p>2. Respeitar a hierarquia do grupo.</p>
      <p>3. Não utilizar linguagem ofensiva.</p>
      <p>4. Não abusar de permissões ou cargos.</p>
      <p>5. Seguir as orientações da administração.</p>
      <p>6. Manter a organização durante as atividades.</p>
    </div>
  </section>

  <section id="perfil" class="page hidden">
    <h1>PERFIL</h1>
    <div class="card">
      <h2>Membro do EBC</h2>
      <p>Bem-vindo ao portal do grupo.</p>
      <p class="small">A vinculação real de uma conta Roblox precisa de integração segura com o Roblox.</p>
    </div>
  </section>
</main>
</div>
</div>

<script>
const screens = ["startScreen","verifyScreen","returnScreen"];
let aguardandoRetorno = false;

function showScreen(id){
  screens.forEach(s => document.getElementById(s).classList.add("hidden"));
  document.getElementById("site").classList.add("hidden");
  document.getElementById(id).classList.remove("hidden");
}

function showVerify(){
  showScreen("verifyScreen");
}

function backStart(){
  showScreen("startScreen");
}

function openRoblox(){
  aguardandoRetorno = true;
  sessionStorage.setItem("ebcAguardandoRetorno","sim");
  window.open("https://www.roblox.com/login","_blank");
}

function mostrarBotaoRetorno(){
  if(aguardandoRetorno && !document.hidden){
    showScreen("returnScreen");
  }
}

window.addEventListener("focus", mostrarBotaoRetorno);
document.addEventListener("visibilitychange", mostrarBotaoRetorno);

function enterSite(){
  aguardandoRetorno = false;
  sessionStorage.removeItem("ebcAguardandoRetorno");
  screens.forEach(s => document.getElementById(s).classList.add("hidden"));
  document.getElementById("site").classList.remove("hidden");
  openPage("inicio");
}

function openPage(page){
  document.querySelectorAll(".page").forEach(p => p.classList.add("hidden"));
  document.getElementById(page).classList.remove("hidden");
}

const ranks = [
"Recruta","Soldado","Cabo","Terceiro Combatente",
"Segundo Combatente","Primeiro Combatente","Cadete",
"Aspirante a Oficial","Segundo Tenente","Primeiro Tenente",
"Capitão","Major","Coronel","General de Brigada",
"General de Divisão","General de Exército","Elite Militar",
"Elite Secreta","Elite Real","Vice-Presidente","Marechal",
"Subcomandante","Comandante","Presidente"
];

document.getElementById("rankList").innerHTML =
ranks.map((r,i)=>`<div class="rank"><strong>${i+1}º — ${r}</strong></div>`).join("");

if(sessionStorage.getItem("ebcAguardandoRetorno")==="sim"){
  aguardandoRetorno = true;
}
</script>
</body>
</html>
