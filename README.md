
<!DOCTYPE html>
<html lang="pt-BR">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1">
<title>EBC | Exército Brasileiro de Combate</title>

<style>
*{box-sizing:border-box;margin:0;padding:0;font-family:Arial,sans-serif}
body{background:#070d18;color:white}
button{cursor:pointer;border:1px solid #1764a0;background:#087de0;color:white;padding:13px 18px;border-radius:7px;font-weight:bold}
button:hover{background:#159aff}
.hidden{display:none!important}

/* VERIFICAÇÃO */
.screen{
position:fixed;inset:0;background:#020409;z-index:1000;
display:flex;align-items:center;justify-content:center;padding:20px
}
.verify-card{
width:100%;max-width:430px;text-align:center;padding:38px 25px;
background:#080f1c;border:1px solid #087de0;border-radius:14px;
box-shadow:0 0 35px #0066bb44
}
.logo{font-size:43px;font-weight:900;color:#168fff;letter-spacing:7px;margin-bottom:20px}
.verify-card h1{font-size:25px;margin-bottom:15px}
.verify-card p{color:#b5c7db;line-height:1.6;margin:15px 0}
.verify-card button{display:block;width:100%;margin-top:12px}
.secondary{background:#14263c}

/* SITE */
#site{display:none;min-height:100vh}
header{
background:#0b1728;padding:18px 22px;border-bottom:1px solid #17375b;
display:flex;justify-content:space-between;align-items:center;gap:10px
}
header strong{color:#42aaff;font-size:18px}
.layout{display:flex;min-height:calc(100vh - 60px)}
aside{
width:230px;background:#091321;padding:18px 12px;
border-right:1px solid #17375b;flex-shrink:0
}
aside h4{font-size:11px;color:#6685a8;margin:18px 10px}
.menu{
display:block;width:100%;text-align:left;background:transparent;
color:#c6d5e5;font-weight:normal;margin:4px 0;border:0
}
.menu.active,.menu:hover{background:#102c49;color:#42aaff}
main{padding:28px;flex:1;min-width:0}
.page{display:none}
.page.active{display:block}
.hero{
padding:32px;background:linear-gradient(120deg,#102c49,#091321);
border:1px solid #174c7b;border-radius:12px;margin-bottom:20px
}
.hero h1{margin-bottom:12px}
.hero p{color:#b8c9dc;line-height:1.7}
h2{color:#45aaff;margin:10px 0 20px}
.grid{display:grid;grid-template-columns:repeat(auto-fit,minmax(190px,1fr));gap:14px}
.card{background:#0d1a2b;border:1px solid #1a3859;padding:20px;border-radius:10px}
.card h3{color:#48aaff;margin-bottom:10px}
.card p{color:#bdcada;line-height:1.6}
.rank{background:#0d1a2b;border:1px solid #1a3859;border-radius:8px;padding:13px;margin:7px 0}
.special{border-color:#b18b35;background:#211d12}
.special h3{color:#f2c75c}
footer{text-align:center;color:#61758b;font-size:12px;padding:25px}

@media(max-width:700px){
.layout{display:block}
aside{width:100%;display:flex;overflow-x:auto;padding:9px}
aside h4{display:none}
.menu{width:auto;white-space:nowrap}
main{padding:17px}
.hero{padding:23px}
}
</style>
</head>

<body>

<!-- PRIMEIRA TELA -->
<div class="screen" id="startScreen">
 <div class="verify-card">
  <div class="logo">EBC</div>
  <h1>VERIFIQUE-SE</h1>
  <p>Bem-vindo ao portal do Exército Brasileiro de Combate.</p>
  <button onclick="showVerify()">VERIFICAR</button>
 </div>
</div>

<!-- SEGUNDA TELA -->
<div class="screen hidden" id="verifyScreen">
 <div class="verify-card">
  <div class="logo">EBC</div>
  <h1>VERIFICAÇÃO</h1>
  <p>Você está se verificando. Não saia desta página.</p>
  <button onclick="showBio()">VERIFICAR PELA BIO</button>
  <button class="secondary" onclick="showRoblox()">VERIFICAR PELA ROBLOX</button>
  <button class="secondary" onclick="backStart()">VOLTAR</button>
 </div>
</div>

<!-- TELA BIO -->
<div class="screen hidden" id="bioScreen">
 <div class="verify-card">
  <div class="logo">EBC</div>
  <h1>VERIFICAR PELA BIO</h1>
  <p>Use este código temporário na sua descrição pública do Roblox:</p>
  <div class="code" id="bioCode">EBC-48291</div>
  <button onclick="copyCode()">COPIAR CÓDIGO</button>
  <p id="bioMessage">A confirmação automática precisa de um servidor conectado ao Roblox.</p>
  <button class="secondary" onclick="backVerify()">VOLTAR</button>
 </div>
</div>

<!-- TELA ROBLOX -->
<div class="screen hidden" id="robloxScreen">
 <div class="verify-card">
  <div class="logo">EBC</div>
  <h1>VERIFICAR PELA ROBLOX</h1>
  <p>Entre na página oficial do Roblox para acessar sua conta. Nunca informe sua senha neste site.</p>
  <button onclick="window.open('https://www.roblox.com/login','_blank')">ABRIR ROBLOX OFICIAL</button>
  <p>O login oficial não confirma automaticamente sua identidade no EBC.</p>
  <button class="secondary" onclick="backVerify()">VOLTAR</button>
 </div>
</div>

<!-- PORTAL PRINCIPAL -->
<div id="site">
<header>
 <strong>⚔ EBC | EXÉRCITO BRASILEIRO DE COMBATE</strong>
 <span>PORTAL OFICIAL</span>
</header>

<div class="layout">
<aside>
 <h4>MENU PRINCIPAL</h4>
 <button class="menu active" onclick="openPage('inicio',this)">⌂ Início</button>
 <button class="menu" onclick="openPage('hierarquia',this)">♜ Hierarquia</button>
 <button class="menu" onclick="openPage('divisoes',this)">⚔ Divisões</button>
 <button class="menu" onclick="openPage('especiais',this)">★ Pessoas especiais</button>
 <button class="menu" onclick="openPage('regras',this)">☷ Regulamento</button>
 <button class="menu" onclick="openPage('perfil',this)">♙ Meu perfil</button>
 <h4>INFORMAÇÕES</h4>
 <button class="menu" onclick="openPage('discord',this)">◉ Discord</button>
</aside>

<main>

<section class="page active" id="inicio">
 <div class="hero">
  <h1>QUARTEL-GENERAL DO EBC</h1>
  <p>Seja bem-vindo ao portal oficial do Exército Brasileiro de Combate. Aqui você encontra informações sobre a organização, cargos, divisões e atividades.</p>
 </div>
 <div class="card special">
  <h3>★ MENSAGEM AOS MEMBROS ESPECIAIS</h3>
  <p>Boa tarde, membros especiais! Boa tarde aos integrantes do TSE, SGEC e CDE. Sejam todos muito bem-vindos ao Quartel-General do EBC!</p>
 </div>
 <div class="grid">
  <div class="card"><h3>Hierarquia</h3><p>Consulte todos os cargos do Exército.</p></div>
  <div class="card"><h3>Divisões</h3><p>Conheça as unidades do EBC.</p></div>
  <div class="card"><h3>Portal</h3><p>Central de informações dos membros.</p></div>
 </div>
</section>

<section class="page" id="hierarquia">
 <h2>HIERARQUIA MILITAR</h2>
 <div id="rankList"></div>
</section>

<section class="page" id="divisoes">
 <h2>DIVISÕES DO EBC</h2>
 <div class="grid">
  <div class="card"><h3>CIE</h3><p>Centro de Inteligência do Exército.</p></div>
  <div class="card"><h3>CIGS</h3><p>Centro de Instrução de Guerra na Selva.</p></div>
  <div class="card"><h3>BAC</h3><p>Batalhões de Ações de Comando.</p></div>
  <div class="card"><h3>FE</h3><p>Forças Especiais do Exército.</p></div>
  <div class="card"><h3>PE</h3><p>Polícia do Exército.</p></div>
 </div>
</section>

<section class="page" id="especiais">
 <h2>PESSOAS ESPECIAIS</h2>
 <div class="grid">
  <div class="card special"><h3>TSE</h3><p>Integrantes especiais do EBC.</p></div>
  <div class="card special"><h3>SGEC</h3><p>Integrantes especiais do EBC.</p></div>
  <div class="card special"><h3>CDE</h3><p>Integrantes especiais do EBC.</p></div>
 </div>
</section>

<section class="page" id="regras">
 <h2>REGULAMENTO</h2>
 <div class="card">
  <h3>Regras gerais</h3>
  <p>Respeitar todos os membros.</p>
  <p>Respeitar a hierarquia da organização.</p>
  <p>Manter comportamento adequado.</p>
  <p>Seguir as orientações da liderança.</p>
 </div>
</section>

<section class="page" id="perfil">
 <h2>MEU PERFIL</h2>
 <div class="card">
  <h3>Área do membro</h3>
  <p>Seu perfil Roblox e sua patente poderão aparecer aqui após a integração oficial de verificação.</p>
 </div>
</section>

<section class="page" id="discord">
 <h2>DISCORD OFICIAL</h2>
 <div class="card">
  <h3>Comunidade EBC</h3>
  <p>Adicione o link oficial do Discord nesta área.</p>
 </div>
</section>

<footer> EBC — EXÉRCITO BRASILEIRO DE COMBATE </footer>
</main>
</div>
</div>

<script>
const screens=["startScreen","verifyScreen","bioScreen","robloxScreen"];

function showOnly(id){
 screens.forEach(screen=>{
  document.getElementById(screen).classList.toggle("hidden",screen!==id);
 });
}

function showVerify(){showOnly("verifyScreen")}
function showBio(){showOnly("bioScreen")}
function showRoblox(){showOnly("robloxScreen")}
function backStart(){showOnly("startScreen")}
function backVerify(){showOnly("verifyScreen")}

function copyCode(){
 const code=document.getElementById("bioCode").textContent;
 if(navigator.clipboard && window.isSecureContext){
  navigator.clipboard.writeText(code).then(()=>{
   document.getElementById("bioMessage").textContent="Código copiado!";
  }).catch(()=>{
   document.getElementById("bioMessage").textContent="Copie o código manualmente.";
  });
 }else{
  document.getElementById("bioMessage").textContent="Copie o código manualmente.";
 }
}

function openPage(id,button){
 document.querySelectorAll(".page").forEach(p=>p.classList.remove("active"));
 document.getElementById(id).classList.add("active");
 document.querySelectorAll(".menu").forEach(b=>b.classList.remove("active"));
 button.classList.add("active");
}

const ranks=[
"Recruta",
"Soldado",
"Cabo",
"Terceiro Combatente",
"Segundo Combatente",
"Primeiro Combatente",
"Cadete",
"Aspirante a Oficial",
"Segundo Tenente",
"Primeiro Tenente",
"Capitão",
"Major",
"Coronel",
"General de Brigada",
"General de Divisão",
"General de Exército",
"Elite Militar",
"Elite Secreta",
"Elite Real",
"Vice-Presidente",
"Marechal",
"Subcomandante",
"Comandante",
"Presidente"
];

document.getElementById("rankList").innerHTML=
ranks.map((rank,i)=>`<div class="rank">${i+1}º — ${rank}</div>`).join("");
</script>

</body>
</html>
