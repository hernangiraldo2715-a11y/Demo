# Demo
<!DOCTYPE html>
<html lang="es">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1, viewport-fit=cover">
<title>Citalia · Demo de reservas (datos ficticios)</title>
<style>
:root{--brand:#2F5D50;--ink:#1F2430;--mut:#5B6270;--line:#E4E0D8;--bg:#F8F7F4;--card:#fff;--r:10px}
*{box-sizing:border-box}
html{scroll-behavior:smooth}
body{margin:0;font-family:Arial,Helvetica,sans-serif;background:var(--bg);color:var(--ink);line-height:1.45;-webkit-text-size-adjust:100%}
button,input{font-family:Arial,Helvetica,sans-serif;font-size:16px;color:var(--ink)}
button{cursor:pointer}
:focus-visible{outline:3px solid var(--ink);outline-offset:2px}
.wrap{max-width:1080px;margin:0 auto;padding:0 16px}
h1,h2,h3,p{margin:0}
.lbl{font-size:12px;text-transform:uppercase;letter-spacing:.12em;color:var(--mut);font-weight:700}
.top{background:#fff;border-bottom:1px solid var(--line)}
.topin{display:flex;flex-wrap:wrap;gap:10px;align-items:center;justify-content:space-between;padding-top:10px;padding-bottom:10px}
.mark{display:flex;align-items:center;gap:8px;font-weight:700;font-size:18px}
.mk{width:22px;height:22px;background:var(--ink);display:inline-block;border-radius:6px}
.demo{font-size:11px;letter-spacing:.1em;border:1px solid var(--ink);padding:2px 6px;border-radius:6px}
.tools{display:flex;gap:8px;flex-wrap:wrap;align-items:center}
.seg{display:inline-flex;border:1px solid var(--line);border-radius:var(--r);overflow:hidden;background:#fff}
.seg button{border:0;background:#fff;min-height:44px;padding:0 14px;font-weight:700;font-size:14px;transition:background .15s,color .15s;display:flex;align-items:center;gap:8px}
.seg button+button{border-left:1px solid var(--line)}
.seg button[aria-pressed=true]{background:var(--ink);color:#fff}
.banner{background:#FFF4D6;color:#5C4300;font-size:13px;text-align:center;padding:8px 16px;border-bottom:1px solid #EBD9A4;font-weight:700}
nav.tabs{position:sticky;top:0;z-index:20;background:rgba(255,255,255,.96);border-bottom:1px solid var(--line);overflow-x:auto}
nav.tabs .wrap{display:flex;gap:4px}
nav.tabs button{border:0;background:none;min-height:50px;padding:0 16px;font-weight:700;font-size:15px;color:var(--mut);border-bottom:3px solid transparent;white-space:nowrap;transition:color .15s,border-color .15s}
nav.tabs button[aria-current=page]{color:var(--ink);border-bottom-color:var(--brand)}
.bizbar{display:flex;align-items:center;gap:10px;flex-wrap:wrap;padding-top:14px}
.dot{width:10px;height:10px;border-radius:50%;display:inline-block}
.btn{min-height:50px;padding:0 22px;border-radius:var(--r);border:1px solid var(--brand);background:var(--brand);color:#fff;font-weight:700;font-size:16px;transition:transform .12s,opacity .15s}
.btn:active{transform:scale(.98)}
.btn:disabled{opacity:.45;cursor:not-allowed}
.btn.ghost{background:#fff;color:var(--brand)}
.btn.sm{min-height:44px;padding:0 14px;font-size:14px}
.btn.dark{background:var(--ink);border-color:var(--ink);color:#fff}
.btn.dark.ghost{background:#fff;color:var(--ink)}
main{padding:18px 16px 56px;max-width:1080px;margin:0 auto;animation:fade .18s ease-out}
@keyframes fade{from{opacity:0;transform:translateY(6px)}to{opacity:1;transform:none}}
.hero{display:grid;gap:28px;padding-top:12px}
.hero h1{font-size:36px;line-height:1.08;letter-spacing:-.02em;margin:8px 0 12px;text-wrap:balance}
.lead{color:var(--mut);font-size:17px;max-width:520px}
.row{display:flex;gap:10px;flex-wrap:wrap;margin:20px 0}
.benefits{list-style:none;padding:0;margin:0;border-top:1px solid var(--line)}
.benefits li{display:flex;gap:14px;padding:14px 0;border-bottom:1px solid var(--line)}
.benefits .n{font-weight:700;color:var(--brand);font-size:20px;min-width:28px}
.benefits b{display:block;font-size:17px}
.benefits span{color:var(--mut);font-size:14px}
.bizcards{display:grid;gap:10px;margin:10px 0 18px}
.bizcard{display:flex;align-items:center;gap:14px;text-align:left;padding:14px;background:#fff;border:2px solid var(--line);border-radius:var(--r);min-height:72px;transition:border-color .15s,transform .12s}
.bizcard[aria-pressed=true]{border-color:var(--brand)}
.bizcard:active{transform:scale(.99)}
.bizcard b{display:block;font-size:17px}
.bizcard small{color:var(--mut);font-size:13px}
.logo{width:var(--s);height:var(--s);border-radius:calc(var(--s)*.26);display:inline-flex;align-items:center;justify-content:center;flex:none;border:2px solid #fff}
.logo svg{width:60%;height:60%}
.phone{background:#fff;border:1px solid var(--line);border-radius:18px;overflow:hidden;max-width:340px;margin:0 auto}
.phone .band{background:var(--brand);color:#fff;padding:18px;display:flex;gap:12px;align-items:center;transition:background .2s}
.phone .band b{font-size:18px;display:block;word-break:break-word}
.phone .band small{opacity:.9;font-size:13px}
.phone .body{padding:6px 16px 16px}
.phone .sv{display:flex;justify-content:space-between;padding:11px 0;border-bottom:1px solid var(--line);font-size:15px}
.phone .sv small{color:var(--mut);display:block}
.phone .sv b{color:var(--brand)}
.phone .btn{width:100%;margin-top:14px}
.sect{margin-top:26px}
.sect h2{font-size:22px;margin-bottom:12px}
.step{background:#fff;border:1px solid var(--line);border-radius:var(--r);padding:16px;margin-bottom:14px}
.step h3{font-size:16px;display:flex;gap:10px;align-items:center;margin-bottom:12px}
.step h3 i{font-style:normal;background:var(--brand);color:#fff;width:26px;height:26px;border-radius:50%;display:inline-flex;align-items:center;justify-content:center;font-size:13px}
.opt{display:flex;width:100%;align-items:center;gap:12px;text-align:left;min-height:56px;padding:10px 14px;background:#fff;border:2px solid var(--line);border-radius:var(--r);margin-bottom:8px;transition:border-color .15s,background .15s}
.opt[aria-pressed=true]{border-color:var(--brand);background:color-mix(in srgb,var(--brand) 9%,#fff)}
.opt .g{flex:1}
.opt small{display:block;color:var(--mut);font-size:13px}
.opt b.pr{color:var(--brand);font-variant-numeric:tabular-nums}
.av{width:36px;height:36px;border-radius:50%;display:inline-flex;align-items:center;justify-content:center;font-weight:700;font-size:13px;flex:none;color:var(--ink)}
.strip{display:grid;grid-template-columns:repeat(7,1fr);gap:6px;margin-bottom:14px}
.strip button{border:2px solid var(--line);background:#fff;border-radius:var(--r);min-height:64px;padding:6px 2px;display:flex;flex-direction:column;align-items:center;justify-content:center;gap:1px;transition:border-color .15s,background .15s}
.strip button span{font-size:11px;text-transform:uppercase;color:var(--mut);letter-spacing:.04em}
.strip button b{font-size:18px}
.strip button em{font-style:normal;font-size:11px;color:var(--mut);font-variant-numeric:tabular-nums}
.strip button[aria-pressed=true]{border-color:var(--brand);background:color-mix(in srgb,var(--brand) 9%,#fff)}
.slots{display:grid;grid-template-columns:repeat(auto-fill,minmax(88px,1fr));gap:8px}
.slot{min-height:48px;border:2px solid var(--line);background:#fff;border-radius:var(--r);font-weight:700;font-size:15px;transition:border-color .15s,background .15s,color .15s;font-variant-numeric:tabular-nums}
.slot:hover:not(:disabled){border-color:var(--brand)}
.slot[aria-pressed=true]{background:var(--brand);border-color:var(--brand);color:#fff}
.slot:disabled{background:#F1EFEA;color:#8A8F99;text-decoration:line-through;cursor:not-allowed;font-weight:400}
.note{font-size:13px;color:var(--mut)}
input[type=text],input[type=number]{width:100%;min-height:50px;border:2px solid var(--line);border-radius:var(--r);padding:0 14px;background:#fff}
input:focus{border-color:var(--brand);outline:none}
label.f{display:block;font-size:14px;font-weight:700;margin:0 0 6px}
.field{margin-bottom:14px}
.book-grid{display:grid;gap:16px}
.sum{background:#fff;border:2px solid var(--brand);border-radius:var(--r);padding:16px}
.sum dl{margin:12px 0}
.sum dl div{display:flex;justify-content:space-between;gap:10px;padding:9px 0;border-bottom:1px solid var(--line);font-size:15px}
.sum dt{color:var(--mut)}
.sum dd{margin:0;font-weight:700;text-align:right}
.cover{display:flex;gap:14px;align-items:center;background:var(--brand);color:#fff;border-radius:var(--r);padding:18px}
.cover h2{font-size:24px;word-break:break-word}
.cover p{opacity:.92;font-size:14px}
.ok{text-align:center;background:#fff;border:1px solid var(--line);border-radius:var(--r);padding:28px 18px;max-width:520px;margin:10px auto}
.ok svg.c{width:84px;height:84px}
.ok circle{fill:none;stroke:var(--brand);stroke-width:4;stroke-dasharray:190;stroke-dashoffset:190;animation:dash .5s .05s forwards}
.ok path{fill:none;stroke:var(--brand);stroke-width:5;stroke-linecap:round;stroke-linejoin:round;stroke-dasharray:50;stroke-dashoffset:50;animation:dash .35s .45s forwards}
@keyframes dash{to{stroke-dashoffset:0}}
.ok h2{margin:12px 0 4px;font-size:24px}
.ok dl{text-align:left;margin:16px 0}
.ok dl div{display:flex;justify-content:space-between;padding:9px 0;border-bottom:1px solid var(--line)}
.ok dt{color:var(--mut)}.ok dd{margin:0;font-weight:700}
.kpis{display:grid;grid-template-columns:1fr 1fr;background:#fff;border:1px solid var(--line);border-radius:var(--r);overflow:hidden}
.kpis div{padding:14px;border-bottom:1px solid var(--line)}
.kpis div:nth-child(odd){border-right:1px solid var(--line)}
.kpis b{display:block;font-size:26px;font-variant-numeric:tabular-nums;margin-top:2px}
.kpis small{color:var(--mut);font-size:12px}
.sim{display:inline-block;font-size:11px;font-weight:700;letter-spacing:.06em;text-transform:uppercase;background:#FFF4D6;color:#5C4300;padding:3px 8px;border-radius:6px;margin-left:6px;vertical-align:middle}
.pgrid{display:grid;gap:18px}
.bar{display:flex;gap:10px;align-items:center;margin:10px 0;font-size:14px}
.bar .t{flex:1;height:10px;background:#ECE9E2;border-radius:6px;overflow:hidden}
.bar .t i{display:block;height:100%;background:var(--brand);transition:width .3s}
.bar span{min-width:110px}
.bar b{min-width:20px;text-align:right;font-variant-numeric:tabular-nums}
.alist{list-style:none;padding:0;margin:0;background:#fff;border:1px solid var(--line);border-radius:var(--r)}
.arow{border-bottom:1px solid var(--line)}
.arow:last-child{border-bottom:0}
.arowbtn{display:flex;gap:12px;align-items:center;width:100%;text-align:left;background:none;border:0;padding:12px 14px;min-height:62px}
.tm{font-weight:700;min-width:62px;font-variant-numeric:tabular-nums}
.who{flex:1;min-width:0}
.who b{margin-right:6px}
.who small{display:block;color:var(--mut);font-size:13px}
.tag{font-style:normal;font-size:11px;font-weight:700;background:var(--brand);color:#fff;padding:2px 7px;border-radius:6px;vertical-align:middle}
.chip{font-size:12px;font-weight:700;padding:4px 9px;border-radius:999px;white-space:nowrap}
.st-confirmed{background:#E6EEF8;color:#1F4E79}
.st-arrived{background:#FBF1DC;color:#7A4E0E}
.st-done{background:#E3F1E8;color:#1F5B38}
.st-noshow{background:#ECECEC;color:#4A4A4A}
.st-cancelled{background:#F7E3E3;color:#8A2B2B}
.arow.cx .who b,.arow.cx .tm{text-decoration:line-through;color:#8A8F99}
.arow.hl{animation:flash 1.6s ease-out}
@keyframes flash{0%,40%{background:color-mix(in srgb,var(--brand) 18%,#fff)}100%{background:transparent}}
.detail{padding:4px 14px 14px;display:flex;flex-wrap:wrap;gap:8px;align-items:center;animation:fade .15s}
.detail p{width:100%;font-size:13px;color:var(--mut)}
.sbtn{min-height:44px;padding:0 12px;border:2px solid var(--line);background:#fff;border-radius:var(--r);font-weight:700;font-size:13px}
.sbtn[aria-pressed=true]{border-color:var(--ink);background:var(--ink);color:#fff}
.sbtn.danger{border-color:#C98A8A;color:#8A2B2B}
.empty{background:#fff;border:1px dashed #BDB8AD;border-radius:var(--r);padding:30px 18px;text-align:center}
.empty p{margin-bottom:14px;color:var(--mut)}
.wk{display:grid;grid-template-columns:repeat(auto-fit,minmax(150px,1fr));gap:10px}
.wcol{background:#fff;border:1px solid var(--line);border-radius:var(--r);padding:10px}
.wcol header{display:flex;justify-content:space-between;font-weight:700;font-size:14px;margin-bottom:6px}
.wcol header small{font-weight:400;color:var(--mut)}
.wline{display:block;width:100%;text-align:left;border:0;border-left:4px solid;background:#F5F3EE;padding:6px 8px;margin-bottom:5px;border-radius:6px;font-size:12px;min-height:40px}
.wline.st-cancelled{text-decoration:line-through;opacity:.7}
.wline.st-confirmed{border-color:#1F4E79}.wline.st-arrived{border-color:#B8791A}.wline.st-done{border-color:#2E7D4F}.wline.st-noshow{border-color:#777}.wline.st-cancelled{border-color:#B55}
.toolrow{display:flex;gap:8px;flex-wrap:wrap;margin:12px 0}
.next{list-style:none;padding:0;margin:8px 0 0}
.next li{display:flex;justify-content:space-between;gap:8px;padding:10px 0;border-bottom:1px solid var(--line);font-size:14px}
.next small{color:var(--mut);display:block}
.card{background:#fff;border:1px solid var(--line);border-radius:var(--r);padding:16px}
.sw{display:flex;gap:10px;flex-wrap:wrap;align-items:center}
.sw button{width:48px;height:48px;border-radius:50%;border:3px solid #fff;outline:2px solid var(--line);transition:transform .12s}
.sw button[aria-pressed=true]{outline:3px solid var(--ink)}
.sw input[type=color]{width:48px;height:48px;border:0;padding:0;background:none}
.lg{display:grid;grid-template-columns:repeat(3,1fr);gap:10px}
.lg button{border:2px solid var(--line);background:#fff;border-radius:var(--r);min-height:72px;display:flex;align-items:center;justify-content:center}
.lg button[aria-pressed=true]{border-color:var(--ink)}
.two{display:grid;gap:14px}
.ba{padding:18px;border-radius:var(--r);border:1px solid var(--line);background:#fff}
.ba.after{border:2px solid var(--brand)}
.ba h3{font-size:20px;margin-bottom:8px}
.ba ul{list-style:none;padding:0;margin:0}
.ba li{display:flex;gap:10px;padding:12px 0;border-bottom:1px solid var(--line);align-items:flex-start}
.ba li:last-child{border-bottom:0}
.ba svg{width:22px;height:22px;flex:none;margin-top:1px}
.plans{display:grid;gap:12px}
.plan{background:#fff;border:1px solid var(--line);border-radius:var(--r);padding:18px}
.plan.hot{border:2px solid var(--brand)}
.plan h3{font-size:18px}
.plan .pp{display:flex;align-items:center;gap:6px;margin:10px 0;font-size:18px;font-weight:700}
.plan .pp input{width:90px;min-height:44px;font-weight:700}
.plan ul{padding-left:18px;margin:8px 0 0;color:var(--mut);font-size:14px}
.msg{background:#E3F1E8;color:#1F5B38;padding:12px 14px;border-radius:var(--r);margin-top:12px;font-weight:700;font-size:14px}
footer.fin{border-top:1px solid var(--line);padding:22px 16px 40px;text-align:center;color:var(--mut);font-size:13px}
#tour{position:fixed;left:0;right:0;bottom:0;z-index:50;background:var(--ink);color:#fff;padding:14px 16px calc(14px + env(safe-area-inset-bottom));animation:fade .15s}
#tour .in{max-width:680px;margin:0 auto}
#tour .lbl{color:#C9CDD6}
#tour h3{font-size:19px;margin:3px 0 4px}
#tour p{font-size:14px;color:#E6E8EE}
#tour .acts{display:flex;gap:8px;margin-top:12px;align-items:center}
#tour .btn{background:#fff;color:var(--ink);border-color:#fff;flex:1}
#tour .btn.q{background:transparent;color:#fff;border-color:#8A90A0;flex:none}
#tour .btn:disabled{opacity:.4}
#toast{position:fixed;left:50%;bottom:20px;transform:translate(-50%,30px);background:var(--ink);color:#fff;padding:12px 18px;border-radius:var(--r);font-size:14px;font-weight:700;opacity:0;pointer-events:none;transition:all .2s;z-index:60;max-width:92vw;text-align:center}
#toast.on{opacity:1;transform:translate(-50%,0)}
#toast.up{bottom:190px}
.pad{padding-bottom:190px}
@media(min-width:760px){
 .hero{grid-template-columns:1.15fr .85fr;align-items:start;gap:44px}
 .hero h1{font-size:54px}
 .two{grid-template-columns:1fr 1fr}
 .plans{grid-template-columns:repeat(3,1fr)}
 .pgrid{grid-template-columns:1.7fr 1fr;align-items:start}
 .kpis{grid-template-columns:repeat(4,1fr)}
 .kpis div{border-right:1px solid var(--line);border-bottom:0}
 .kpis div:last-child{border-right:0}
 .book-grid{grid-template-columns:1fr 340px;align-items:start}
 .book-grid .sum{position:sticky;top:70px}
 .split{display:grid;grid-template-columns:1fr 1fr;gap:26px;align-items:start}
}
@media(prefers-reduced-motion:reduce){*{animation:none!important;transition:none!important}html{scroll-behavior:auto}}
</style>
</head>
<body>
<div id="app"></div>
<div id="tour"></div>
<div id="toast" role="status" aria-live="polite"></div>
<script>
/* =====================================================================
   CONFIGURACIÓN EDITABLE (textos, servicios, profesionales, colores)
   TODO es ficticio. Para cambiar la demo, edita este bloque BIZ.
   ===================================================================== */
const BIZ={
 norte:{
  name:"Norte Barber Studio",color:"#2F5D50",logo:"north",
  type:{es:"Barbería",en:"Barbershop"},
  tag:{es:"Cortes y barba con cita, sin esperas.",en:"Cuts and beards by appointment, no waiting."},
  svcs:[
   {id:"cut",es:"Corte",en:"Haircut",p:30,m:30},
   {id:"beard",es:"Barba",en:"Beard",p:20,m:20},
   {id:"combo",es:"Corte + barba",en:"Cut + beard",p:45,m:50}],
  pros:[
   {id:"n1",name:"Mateo R.",role:{es:"Barbero",en:"Barber"},c:"#CFE3DA"},
   {id:"n2",name:"Andrés V.",role:{es:"Barbero",en:"Barber"},c:"#D6DEF0"},
   {id:"n3",name:"Iván C.",role:{es:"Barbero",en:"Barber"},c:"#F0D9D2"}],
  /* [díaDesdeHoy, "HH:MM", servicio, profesional, cliente, estado?] */
  seed:[[0,"10:30","cut","n1","Diego L."],[0,"11:00","combo","n2","Samuel P."],[0,"12:00","beard","n3","Tomás G."],[0,"13:30","cut","n1","Bruno A."],[0,"15:00","combo","n3","Leo M."],[0,"16:30","cut","n2","Nico F."],
   [1,"09:30","cut","n1","Hugo B."],[1,"11:00","beard","n2","Ariel D."],[1,"14:00","combo","n1","Marcos T."],[1,"17:00","cut","n3","Esteban R."],
   [2,"10:00","combo","n3","Joel K."],[2,"12:30","cut","n2","Pablo N."],[2,"15:00","cut","n1","Lucas W.","cancelled"],
   [3,"09:00","cut","n1","Rafa S."],[3,"15:30","beard","n2","Iker V."],[4,"11:30","combo","n1","Darío C."],[4,"16:00","cut","n3","Felipe H."],
   [5,"10:00","cut","n2","Axel O."],[5,"13:00","combo","n1","Gael M."],[6,"09:30","beard","n3","Omar T."]],
  names:["Bruno Z.","Renzo A.","Kevin P.","Dante M.","Alan G."]
 },
 luna:{
  name:"Luna Beauty Studio",color:"#8A3B5E",logo:"moon",
  type:{es:"Estética no médica",en:"Non-medical beauty studio"},
  tag:{es:"Manicura, peinado y cejas con horarios claros.",en:"Nails, styling and brows with clear time slots."},
  svcs:[
   {id:"nails",es:"Manicura",en:"Manicure",p:35,m:45},
   {id:"hair",es:"Peinado",en:"Hairstyling",p:55,m:60},
   {id:"brows",es:"Cejas",en:"Brows",p:20,m:20}],
  pros:[
   {id:"l1",name:"Camila S.",role:{es:"Estilista",en:"Stylist"},c:"#F0D9E3"},
   {id:"l2",name:"Valeria M.",role:{es:"Estilista",en:"Stylist"},c:"#E3D6EC"}],
  seed:[[0,"10:00","nails","l1","Sofía R."],[0,"11:30","hair","l2","Paula M."],[0,"13:00","brows","l1","Elena V."],[0,"14:30","nails","l2","Marta C."],[0,"16:00","hair","l1","Lucía D."],
   [1,"09:30","brows","l2","Inés P."],[1,"11:00","hair","l1","Carla G."],[1,"15:00","nails","l2","Nora B."],
   [2,"10:30","nails","l1","Julia F."],[2,"13:00","hair","l2","Irene S."],[2,"16:00","brows","l2","Tess W.","cancelled"],
   [3,"12:00","brows","l1","Alba T."],[3,"16:30","nails","l2","Rosa H."],[4,"10:00","hair","l1","Mía K."],[4,"14:00","nails","l1","Vera L."],
   [5,"11:00","brows","l2","Dana O."],[5,"15:00","hair","l2","Ana Q."],[6,"10:00","nails","l1","Clara N."]],
  names:["Gema T.","Olga F.","Noa B.","Aitana C.","Lola P."]
 }
};
const PRICE_DEFAULT={basic:19,biz:39,prem:69};
const PALETTE=["#2F5D50","#1F4E79","#8A3B5E","#7A4E2D","#4B3F8F","#1F2430"];
const OPEN=540,CLOSE=1140,NOW=600; /* 09:00-19:00 · "hora actual" simulada: 10:00 */
const LOGOS={
 north:'<path d="M12 3l5.5 16L12 15.5 6.5 19z"/>',
 scissors:'<circle cx="6" cy="6.5" r="2.6" fill="none"/><circle cx="6" cy="17.5" r="2.6" fill="none"/><path d="M8 8l12 9M8 16L20 7" fill="none"/>',
 moon:'<path d="M20 14.5A8.5 8.5 0 1 1 9.5 4 6.8 6.8 0 0 0 20 14.5z"/>',
 sparkle:'<path d="M12 3l2.2 6.8L21 12l-6.8 2.2L12 21l-2.2-6.8L3 12l6.8-2.2z"/>',
 leaf:'<path d="M5 19C5 10 10 5 20 4c0 10-5 15-15 15z"/>',
 crown:'<path d="M4 18L3 8l5 4 4-7 4 7 5-4-1 10z"/>'
};
const LS="citalia-demo-ficticio-v1"; /* almacenamiento local SOLO de esta demo */

/* ============================ TEXTOS ES / EN ============================ */
const T={es:{
 banner:"DEMOSTRACIÓN · Datos ficticios · No se envía, cobra ni guarda nada real",
 home:"Inicio",book:"Reserva",panel:"Panel",brand:"Marca",value:"Valor",
 tour:"Recorrido guiado",reset:"Restablecer demo",try:"Probar demo",
 eyebrow:"Plataforma de reservas · Demo",h1:"Tu negocio, tus reservas, tu marca",
 lead:"Una página de reservas con tu nombre, tus servicios y tus colores. Compruébalo en menos de 3 minutos.",
 b1:"Reservas 24/7",b1d:"Tus clientes eligen servicio y hora desde Instagram o un QR, a cualquier hora.",
 b2:"Agenda organizada",b2d:"Cada cita aparece al instante en tu calendario, con profesional y estado.",
 b3:"Tu marca al frente",b3d:"Cambia nombre, color y logo y mira la vista previa en tiempo real.",
 pick:"Elige un negocio de ejemplo",min:"min",
 book1:"Servicio",book2:"Profesional",book3:"Fecha y hora",book4:"Tus datos",any:"Cualquiera disponible",anyd:"Te asignamos el primero libre",
 free:"horarios libres",busy:"Ocupado",noslots:"Sin horarios libres este día. Prueba otro día.",
 name:"Nombre",demoClient:"Cliente Demo",ph:"Ej. Cliente Demo",
 sumT:"Resumen de tu cita",sSvc:"Servicio",sPro:"Profesional",sWhen:"Fecha",sTime:"Hora",sTot:"Total (ejemplo)",
 confirm:"Confirmar reserva",pickTime:"Elige un horario",
 okT:"¡Reserva confirmada!",okD:"Reserva simulada: no se envió ningún mensaje ni se cobró nada.",toAgenda:"Ver en la agenda del dueño",again:"Reservar otra cita",
 coverBadge:"Reservas en línea · Demo",
 panelT:"Panel del dueño",simData:"Datos simulados",kApp:"Citas",kNew:"Nuevas",kCx:"Canceladas",kRev:"Ingresos estimados",
 day:"Día",week:"Semana",today:"Hoy",nextC:"Próximos clientes",pop:"Servicios populares",simNew:"Simular nueva reserva",simCx:"Simular cancelación",
 noAppt:"No hay citas este día.",newTag:"Nueva",
 confirmed:"Confirmada",arrived:"Llegó",done:"Completada",noshow:"No asistió",cancelled:"Cancelada",
 cancel:"Cancelar cita",restore:"Restaurar",state:"Estado",freed:"Cita cancelada: horario liberado",restored:"Cita restaurada",taken:"Ese horario ya fue ocupado",
 simNewOk:"Nueva reserva simulada recibida",simCxOk:"Cancelación simulada: horario liberado",noCx:"No hay citas por cancelar",full:"Sin horarios libres",
 brandT:"Personaliza tu marca",brandD:"Cambia los datos y mira el resultado al instante.",bName:"Nombre del negocio",bColor:"Color de marca",bLogo:"Logo de ejemplo",bPrev:"Vista previa en tiempo real",bBook:"Reservar",
 resetOk:"Demo restablecida",
 beforeT:"Antes",afterT:"Después",
 bf:["Mensajes para cada cita","Llamadas para confirmar horarios","Citas anotadas a mano"],
 af:["Reservas 24/7 desde un enlace o QR","Agenda organizada por profesional","Menos tiempo administrativo"],
 disc:"Los resultados dependen de cada negocio. Esta demo no promete ni garantiza resultados financieros.",
 priceT:"Precios de ejemplo (editables)",priceN:"Precios ilustrativos sujetos a cambios. En esta demo no se cobra nada.",mo:"/mes",pop2:"Más elegido (ejemplo)",
 plans:{basic:["Básico",["Página de reservas","Agenda día y semana","1 profesional"]],biz:["Negocio",["Todo lo de Básico","Hasta 5 profesionales","Marca personalizada"]],prem:["Premium",["Todo lo de Negocio","Profesionales ilimitados","Soporte prioritario"]]},
 ctaT:"Solicitar mi página de reservas",cName:"Tu nombre",cBiz:"Nombre de tu negocio",cCon:"Teléfono o email",cSend:"Solicitar mi página de reservas",
 cOk:"Solicitud simulada. No se guardó ni se envió ningún dato.",cPriv:"Demo sin backend: nada se almacena ni se envía. Si se conecta un servicio real, se pedirá aprobación y se añadirá aviso de privacidad y consentimiento.",
 foot:"Demostración con datos ficticios. Los cambios se guardan solo en este navegador (almacenamiento local de la demo).",
 step:"Paso",of:"de",prev:"Anterior",next:"Siguiente",end:"Finalizar",close:"Cerrar",
 tt:["Cliente reserva","Dueño recibe","Negocio personaliza"],
 td:["Así reserva un cliente: elige servicio, profesional y hora, y confirma. Prueba reservar una cita.","La cita aparece al instante en la agenda. Cambia su estado o cancélala y el horario queda libre. Si no reservaste, usa Simular nueva reserva.","Cambia nombre, color y logo. La vista previa se actualiza en tiempo real."]
},en:{
 banner:"DEMONSTRATION · Fictional data · Nothing real is sent, charged or stored",
 home:"Home",book:"Booking",panel:"Dashboard",brand:"Brand",value:"Value",
 tour:"Guided tour",reset:"Reset demo",try:"Try demo",
 eyebrow:"Booking platform · Demo",h1:"Your business, your bookings, your brand",
 lead:"A booking page with your name, your services and your colors. See it in under 3 minutes.",
 b1:"24/7 bookings",b1d:"Clients pick a service and time from Instagram or a QR code, any hour.",
 b2:"Organized calendar",b2d:"Every appointment shows up instantly in your calendar, with staff and status.",
 b3:"Your brand up front",b3d:"Change name, color and logo and watch the live preview.",
 pick:"Pick a sample business",min:"min",
 book1:"Service",book2:"Professional",book3:"Date and time",book4:"Your details",any:"Any available",anyd:"We assign the first free one",
 free:"free slots",busy:"Taken",noslots:"No free slots this day. Try another day.",
 name:"Name",demoClient:"Demo Client",ph:"E.g. Demo Client",
 sumT:"Your appointment",sSvc:"Service",sPro:"Professional",sWhen:"Date",sTime:"Time",sTot:"Total (sample)",
 confirm:"Confirm booking",pickTime:"Pick a time",
 okT:"Booking confirmed!",okD:"Simulated booking: no message was sent and nothing was charged.",toAgenda:"See it in the owner's calendar",again:"Book another",
 coverBadge:"Online booking · Demo",
 panelT:"Owner dashboard",simData:"Simulated data",kApp:"Appointments",kNew:"New",kCx:"Cancelled",kRev:"Estimated revenue",
 day:"Day",week:"Week",today:"Today",nextC:"Upcoming clients",pop:"Popular services",simNew:"Simulate new booking",simCx:"Simulate cancellation",
 noAppt:"No appointments this day.",newTag:"New",
 confirmed:"Confirmed",arrived:"Arrived",done:"Completed",noshow:"No-show",cancelled:"Cancelled",
 cancel:"Cancel appointment",restore:"Restore",state:"Status",freed:"Appointment cancelled: slot freed",restored:"Appointment restored",taken:"That slot was already taken",
 simNewOk:"New simulated booking received",simCxOk:"Simulated cancellation: slot freed",noCx:"No appointments to cancel",full:"No free slots",
 brandT:"Customize your brand",brandD:"Change the details and see the result instantly.",bName:"Business name",bColor:"Brand color",bLogo:"Sample logo",bPrev:"Live preview",bBook:"Book now",
 resetOk:"Demo reset",
 beforeT:"Before",afterT:"After",
 bf:["Messages for every appointment","Calls to confirm times","Appointments written by hand"],
 af:["24/7 bookings from a link or QR","Calendar organized by professional","Less administrative time"],
 disc:"Results depend on each business. This demo does not promise or guarantee financial results.",
 priceT:"Sample pricing (editable)",priceN:"Illustrative prices, subject to change. Nothing is charged in this demo.",mo:"/mo",pop2:"Most chosen (sample)",
 plans:{basic:["Basic",["Booking page","Day and week calendar","1 professional"]],biz:["Business",["Everything in Basic","Up to 5 professionals","Custom branding"]],prem:["Premium",["Everything in Business","Unlimited professionals","Priority support"]]},
 ctaT:"Request my booking page",cName:"Your name",cBiz:"Your business name",cCon:"Phone or email",cSend:"Request my booking page",
 cOk:"Simulated request. No data was saved or sent.",cPriv:"Demo without a backend: nothing is stored or sent. If a real service is connected, approval will be requested and a privacy notice and consent will be added.",
 foot:"Demonstration with fictional data. Changes are saved only in this browser (demo local storage).",
 step:"Step",of:"of",prev:"Previous",next:"Next",end:"Finish",close:"Close",
 tt:["Client books","Owner receives","Business customizes"],
 td:["This is how a client books: pick service, professional and time, then confirm. Try booking an appointment.","The appointment shows up instantly in the calendar. Change its status or cancel it and the slot is freed. If you did not book, use Simulate new booking.","Change name, color and logo. The preview updates in real time."]
}};

/* ============================ ESTADO ============================ */
const pad2=n=>String(n).padStart(2,"0");
const now0=new Date();
const todayISO=now0.getFullYear()+"-"+pad2(now0.getMonth()+1)+"-"+pad2(now0.getDate());
const hm=s=>{const a=s.split(":");return +a[0]*60+ +a[1]};
function fresh(){const d={};for(const k in BIZ){d[k]={cfg:{name:BIZ[k].name,color:BIZ[k].color,logo:BIZ[k].logo},seq:0,
 appts:BIZ[k].seed.map((s,i)=>({id:k+"-s"+i,day:s[0],start:hm(s[1]),svc:s[2],pro:s[3],client:s[4],status:s[5]||"confirmed",isNew:(i%4===0&&s[0]<=1&&!s[5])}))};}return d}
function newP(lang){return{lang:lang||"es",date:todayISO,data:fresh(),prices:Object.assign({},PRICE_DEFAULT)}}
function load(){try{const r=JSON.parse(localStorage.getItem(LS)||"null");if(r&&r.date===todayISO&&r.data&&r.data.norte&&r.data.luna&&r.prices)return r}catch(e){}return null}
function save(){try{localStorage.setItem(LS,JSON.stringify(P))}catch(e){}}
let P=load()||newP("es");
const U={tab:"home",biz:"norte",view:"day",day:0,open:null,hl:null,tour:0,book:null};
function bookDefault(){return{svc:BIZ[U.biz].svcs[0].id,pro:"any",day:0,time:null,name:"",done:null}}
U.book=bookDefault();

/* ============================ HELPERS ============================ */
const t=k=>{const v=T[P.lang][k];return v!==undefined?v:T.es[k]};
const loc=()=>P.lang==="es"?"es-US":"en-US";
const D=()=>P.data[U.biz];
const B=()=>BIZ[U.biz];
const esc=s=>String(s).replace(/[&<>"']/g,c=>({"&":"&","<":"<",">":">",'"':""","'":"'"}[c]));
const svcOf=id=>B().svcs.find(s=>s.id===id);
const proOf=id=>B().pros.find(p=>p.id===id);
const sName=s=>s[P.lang];
const active=a=>a.status!=="cancelled";
const counts=a=>a.status==="confirmed"||a.status==="arrived"||a.status==="done";
const money=n=>"$"+n;
function fmtT(m){const h=Math.floor(m/60),mm=pad2(m%60);if(P.lang==="es")return pad2(h)+":"+mm;const h12=h%12||12;return h12+":"+mm+(h<12?" AM":" PM")}
function dateOf(off){const d=new Date();d.setHours(12,0,0,0);d.setDate(d.getDate()+off);return d}
const dLong=o=>dateOf(o).toLocaleDateString(loc(),{weekday:"long",month:"short",day:"numeric"});
const dShort=o=>dateOf(o).toLocaleDateString(loc(),{weekday:"short",month:"short",day:"numeric"});
function isFree(proId,day,start,dur,ignore){return !D().appts.some(a=>a.pro===proId&&a.day===day&&active(a)&&a.id!==ignore&&a.start<start+dur&&start<a.start+svcOf(a.svc).m)}
function freePro(day,start,dur,sel){const ids=sel==="any"?B().pros.map(p=>p.id):[sel];return ids.find(id=>isFree(id,day,start,dur))||null}
function slots(day,svcId,sel){const dur=svcOf(svcId).m,out=[];for(let s=OPEN;s+dur<=CLOSE;s+=30){if(day===0&&s<NOW)continue;out.push({t:s,pro:freePro(day,s,dur,sel)})}return out}
function logo(cfg,sz){return '<span class="logo" style="--s:'+sz+'px;background:'+cfg.color+'"><svg viewBox="0 0 24 24" fill="#fff" stroke="#fff" stroke-width="1.4" stroke-linejoin="round" stroke-linecap="round" aria-hidden="true">'+LOGOS[cfg.logo]+'</svg></span>'}
const initials=n=>n.split(" ").map(w=>w[0]).join("").slice(0,2);
function avatar(p){return '<span class="av" style="background:'+p.c+'" aria-hidden="true">'+initials(p.name)+'</span>'}
let tt;function toast(m){const el=document.getElementById("toast");el.textContent=m;el.className="on"+(U.tour?" up":"");clearTimeout(tt);tt=setTimeout(()=>{el.className=U.tour?"up":""},2600)}

/* ============================ VISTAS ============================ */
function preview(k){const c=P.data[k].cfg,b=BIZ[k];
 return '<div class="phone" style="--brand:'+c.color+'" aria-label="'+t("bPrev")+'"><div class="band">'+logo(c,52)+'<div><b>'+esc(c.name)+'</b><small>'+b.type[P.lang]+'</small></div></div><div class="body">'+
 b.svcs.map(s=>'<div class="sv"><span>'+sName(s)+'<small>'+s.m+' '+t("min")+'</small></span><b>'+money(s.p)+'</b></div>').join("")+
 '<button class="btn" data-act="tab" data-v="book">'+t("bBook")+'</button></div></div>'}

function vHome(){
 const cards=Object.keys(BIZ).map(k=>{const c=P.data[k].cfg;return '<button class="bizcard" data-act="biz" data-v="'+k+'" aria-pressed="'+(U.biz===k)+'" style="--brand:'+c.color+'">'+logo(c,48)+'<span><b data-bn="'+k+'">'+esc(c.name)+'</b><small>'+BIZ[k].type[P.lang]+' · '+BIZ[k].svcs.length+' · '+BIZ[k].pros.length+' '+(P.lang==="es"?"profesionales":"professionals")+'</small></span></button>'}).join("");
 return '<section class="hero"><div><p class="lbl">'+t("eyebrow")+'</p><h1>'+t("h1")+'</h1><p class="lead">'+t("lead")+'</p>'+
 '<div class="row"><button class="btn" data-act="start">'+t("try")+'</button><button class="btn ghost" data-act="tour">'+t("tour")+'</button></div>'+
 '<ul class="benefits"><li><span class="n">1</span><div><b>'+t("b1")+'</b><span>'+t("b1d")+'</span></div></li><li><span class="n">2</span><div><b>'+t("b2")+'</b><span>'+t("b2d")+'</span></div></li><li><span class="n">3</span><div><b>'+t("b3")+'</b><span>'+t("b3d")+'</span></div></li></ul></div>'+
 '<div><p class="lbl">'+t("pick")+'</p><div class="bizcards">'+cards+'</div><div id="preview">'+preview(U.biz)+'</div></div></section>'}

function vBook(){
 const bk=U.book,b=B(),c=D().cfg;
 if(bk.done)return vDone();
 const svc=svcOf(bk.svc),sl=slots(bk.day,bk.svc,bk.pro),freeN=sl.filter(s=>s.pro).length;
 const days=[0,1,2,3,4,5,6].map(o=>{const d=dateOf(o);return '<button data-act="bday" data-v="'+o+'" aria-pressed="'+(bk.day===o)+'" aria-label="'+dLong(o)+'"><span>'+(o===0?t("today"):d.toLocaleDateString(loc(),{weekday:"short"}))+'</span><b>'+d.getDate()+'</b></button>'}).join("");
 const sel=bk.time!==null?sl.find(s=>s.t===bk.time):null;
 const pro=sel&&sel.pro?proOf(sel.pro):null;
 return '<div class="cover">'+logo(c,64)+'<div><h2>'+esc(c.name)+'</h2><p>'+b.type[P.lang]+' · '+b.tag[P.lang]+'</p></div></div>'+
 '<p class="note" style="margin:8px 0 16px">'+t("coverBadge")+' · '+t("simData")+'</p>'+
 '<div class="book-grid"><div>'+
 '<div class="step"><h3><i>1</i>'+t("book1")+'</h3>'+b.svcs.map(s=>'<button class="opt" data-act="bsvc" data-v="'+s.id+'" aria-pressed="'+(bk.svc===s.id)+'"><span class="g"><b>'+sName(s)+'</b><small>'+s.m+' '+t("min")+'</small></span><b class="pr">'+money(s.p)+'</b></button>').join("")+'</div>'+
 '<div class="step"><h3><i>2</i>'+t("book2")+'</h3><button class="opt" data-act="bpro" data-v="any" aria-pressed="'+(bk.pro==="any")+'"><span class="av" style="background:#ECE9E2">*</span><span class="g"><b>'+t("any")+'</b><small>'+t("anyd")+'</small></span></button>'+
 b.pros.map(p=>'<button class="opt" data-act="bpro" data-v="'+p.id+'" aria-pressed="'+(bk.pro===p.id)+'">'+avatar(p)+'<span class="g"><b>'+p.name+'</b><small>'+p.role[P.lang]+'</small></span></button>').join("")+'</div>'+
 '<div class="step"><h3><i>3</i>'+t("book3")+'</h3><div class="strip">'+days+'</div><p class="note" style="margin-bottom:10px"><b>'+dLong(bk.day)+'</b> · '+freeN+' '+t("free")+'</p>'+
 (freeN?'<div class="slots">'+sl.map(s=>'<button class="slot" data-act="btime" data-v="'+s.t+'" '+(s.pro?'':'disabled aria-label="'+fmtT(s.t)+' '+t("busy")+'"')+' aria-pressed="'+(bk.time===s.t)+'">'+fmtT(s.t)+'</button>').join("")+'</div>':'<div class="empty"><p>'+t("noslots")+'</p></div>')+'</div>'+
 '<div class="step"><h3><i>4</i>'+t("book4")+'</h3><div class="field"><label class="f" for="cname">'+t("name")+'</label><input type="text" id="cname" maxlength="30" autocomplete="off" placeholder="'+t("ph")+'" value="'+esc(bk.name)+'"></div><p class="note">'+t("okD")+'</p></div>'+
 '</div><aside class="sum"><h3>'+t("sumT")+'</h3><dl><div><dt>'+t("sSvc")+'</dt><dd>'+sName(svc)+'</dd></div><div><dt>'+t("sPro")+'</dt><dd>'+(pro?pro.name:(bk.pro==="any"?t("any"):proOf(bk.pro).name))+'</dd></div><div><dt>'+t("sWhen")+'</dt><dd>'+dShort(bk.day)+'</dd></div><div><dt>'+t("sTime")+'</dt><dd>'+(bk.time!==null?fmtT(bk.time):"—")+'</dd></div><div><dt>'+t("sTot")+'</dt><dd>'+money(svc.p)+'</dd></div></dl>'+
 '<button class="btn" style="width:100%" data-act="confirm" '+(bk.time===null?'disabled':'')+'>'+(bk.time===null?t("pickTime"):t("confirm"))+'</button></aside></div>'}

function vDone(){
 const a=D().appts.find(x=>x.id===U.book.done);if(!a){U.book.done=null;return vBook()}
 const s=svcOf(a.svc),p=proOf(a.pro);
 return '<div class="ok"><svg class="c" viewBox="0 0 64 64" aria-hidden="true"><circle cx="32" cy="32" r="30"/><path d="M18 33l9 9 19-20"/></svg><h2>'+t("okT")+'</h2><p class="note">'+esc(D().cfg.name)+'</p>'+
 '<dl><div><dt>'+t("sSvc")+'</dt><dd>'+sName(s)+'</dd></div><div><dt>'+t("sPro")+'</dt><dd>'+p.name+'</dd></div><div><dt>'+t("sWhen")+'</dt><dd>'+dShort(a.day)+' · '+fmtT(a.start)+'</dd></div><div><dt>'+t("name")+'</dt><dd>'+esc(a.client)+'</dd></div></dl>'+
 '<p class="msg" style="margin:0 0 16px;text-align:left">'+t("okD")+'</p><div class="row" style="justify-content:center;margin:0"><button class="btn" data-act="toAgenda">'+t("toAgenda")+'</button><button class="btn ghost" data-act="again">'+t("again")+'</button></div></div>'}

function rowHTML(a,showDay){
 const s=svcOf(a.svc),p=proOf(a.pro),open=U.open===a.id;
 let det="";
 if(open){det='<div class="detail"><p>'+sName(s)+' · '+s.m+' '+t("min")+' · '+money(s.p)+' ('+t("simData").toLowerCase()+') · '+fmtT(a.start)+'–'+fmtT(a.start+s.m)+'</p>';
  if(active(a)){det+=["confirmed","arrived","done","noshow"].map(st=>'<button class="sbtn" data-act="status" data-id="'+a.id+'" data-v="'+st+'" aria-pressed="'+(a.status===st)+'">'+t(st)+'</button>').join("")+'<button class="sbtn danger" data-act="cancel" data-id="'+a.id+'">'+t("cancel")+'</button>'}
  else det+='<button class="sbtn" data-act="restore" data-id="'+a.id+'">'+t("restore")+'</button>';
  det+='</div>'}
 return '<li class="arow'+(a.status==="cancelled"?" cx":"")+(U.hl===a.id?" hl":"")+'"><button class="arowbtn" data-act="open" data-id="'+a.id+'" aria-expanded="'+open+'"><span class="tm">'+fmtT(a.start)+'</span><span class="who"><b>'+esc(a.client)+'</b>'+(a.isNew?'<i class="tag">'+t("newTag")+'</i>':'')+'<small>'+sName(s)+' · '+p.name+(showDay?' · '+dShort(a.day):'')+'</small></span><span class="chip st-'+a.status+'">'+t(a.status)+'</span></button>'+det+'</li>'}

function vPanel(){
 const d=D(),days=U.view==="day"?[U.day]:[0,1,2,3,4,5,6];
 const list=d.appts.filter(a=>days.includes(a.day)).sort((x,y)=>x.day-y.day||x.start-y.start);
 const act=list.filter(active);
 const rev=list.filter(counts).reduce((s,a)=>s+svcOf(a.svc).p,0);
 const nw=list.filter(a=>a.isNew&&active(a)).length,cx=list.length-act.length;
 const all=d.appts.filter(active);const pc=B().svcs.map(s=>({s:s,n:all.filter(a=>a.svc===s.id).length}));const mx=Math.max.apply(null,pc.map(x=>x.n).concat([1]));
 const nxt=d.appts.filter(a=>(a.status==="confirmed"||a.status==="arrived")&&(a.day>0||a.start>=NOW)).sort((x,y)=>x.day-y.day||x.start-y.start).slice(0,4);
 const strip='<div class="strip">'+[0,1,2,3,4,5,6].map(o=>{const dd=dateOf(o);const n=d.appts.filter(a=>a.day===o&&active(a)).length;return '<button data-act="pday" data-v="'+o+'" aria-pressed="'+(U.day===o)+'" aria-label="'+dLong(o)+'"><span>'+(o===0?t("today"):dd.toLocaleDateString(loc(),{weekday:"short"}))+'</span><b>'+dd.getDate()+'</b><em>'+n+'</em></button>'}).join("")+'</div>';
 let body;
 if(U.view==="day"){body=list.length?'<ul class="alist">'+list.map(a=>rowHTML(a,false)).join("")+'</ul>':'<div class="empty"><p>'+t("noAppt")+'</p><button class="btn sm" data-act="simnew">'+t("simNew")+'</button></div>'}
 else{body='<div class="wk">'+days.map(o=>{const L=list.filter(a=>a.day===o);const r=L.filter(counts).reduce((s,a)=>s+svcOf(a.svc).m*0+svcOf(a.svc).p,0);
  return '<div class="wcol"><header><span>'+(o===0?t("today"):dateOf(o).toLocaleDateString(loc(),{weekday:"short"}))+' '+dateOf(o).getDate()+'</span><small>'+money(r)+'</small></header>'+(L.length?L.map(a=>'<button class="wline st-'+a.status+'" data-act="goDay" data-v="'+o+'" data-id="'+a.id+'"><b>'+fmtT(a.start)+'</b> '+esc(a.client)+'<br>'+sName(svcOf(a.svc))+'</button>').join(""):'<p class="note">—</p>')+'</div>'}).join("")+'</div>'}
 return '<div class="lbl">'+t("panelT")+' · '+esc(d.cfg.name)+'<span class="sim">'+t("simData")+'</span></div>'+
 '<div class="kpis" style="margin-top:12px"><div><small>'+t("kApp")+'</small><b>'+act.length+'</b></div><div><small>'+t("kNew")+'</small><b>'+nw+'</b></div><div><small>'+t("kCx")+'</small><b>'+cx+'</b></div><div><small>'+t("kRev")+'</small><b>'+money(rev)+'</b></div></div>'+
 '<div class="toolrow"><div class="seg"><button data-act="view" data-v="day" aria-pressed="'+(U.view==="day")+'">'+t("day")+'</button><button data-act="view" data-v="week" aria-pressed="'+(U.view==="week")+'">'+t("week")+'</button></div><button class="btn sm" data-act="simnew">'+t("simNew")+'</button><button class="btn sm ghost" data-act="simcx">'+t("simCx")+'</button></div>'+
 (U.view==="day"?strip:'')+
 '<div class="pgrid"><div>'+body+'</div><div><div class="card"><h3>'+t("nextC")+'</h3><ul class="next">'+(nxt.length?nxt.map(a=>'<li><span><b>'+esc(a.client)+'</b><small>'+sName(svcOf(a.svc))+' · '+proOf(a.pro).name+'</small></span><b>'+(a.day===0?t("today"):dShort(a.day))+' '+fmtT(a.start)+'</b></li>').join(""):'<li>—</li>')+'</ul></div>'+
 '<div class="card" style="margin-top:14px"><h3>'+t("pop")+' <span class="sim">'+t("simData")+'</span></h3>'+pc.sort((a,b)=>b.n-a.n).map(x=>'<div class="bar"><span>'+sName(x.s)+'</span><div class="t"><i style="width:'+Math.round(x.n/mx*100)+'%"></i></div><b>'+x.n+'</b></div>').join("")+'</div></div></div>'}

function vBrand(){
 const c=D().cfg;
 return '<h2 style="font-size:26px">'+t("brandT")+'</h2><p class="note" style="margin:4px 0 16px">'+t("brandD")+'</p><div class="split"><div class="card">'+
 '<div class="field"><label class="f" for="brandName">'+t("bName")+'</label><input type="text" id="brandName" maxlength="28" value="'+esc(c.name)+'"></div>'+
 '<div class="field"><p class="f">'+t("bColor")+'</p><div class="sw">'+PALETTE.map(col=>'<button style="background:'+col+'" data-act="color" data-v="'+col+'" aria-label="'+col+'" aria-pressed="'+(c.color.toLowerCase()===col.toLowerCase())+'"></button>').join("")+'<input type="color" id="colorPick" value="'+c.color+'" aria-label="'+t("bColor")+'"></div></div>'+
 '<div class="field"><p class="f">'+t("bLogo")+'</p><div class="lg">'+Object.keys(LOGOS).map(k=>'<button data-act="logo" data-v="'+k+'" aria-pressed="'+(c.logo===k)+'" aria-label="logo '+k+'">'+logo({color:c.color,logo:k},44)+'</button>').join("")+'</div></div>'+
 '<button class="btn dark ghost" style="width:100%" data-act="reset">'+t("reset")+'</button></div>'+
 '<div><p class="lbl" style="margin-bottom:10px">'+t("bPrev")+'</p><div id="preview">'+preview(U.biz)+'</div></div></div>'}

const OKI='<svg viewBox="0 0 24 24" fill="none" stroke="#1F5B38" stroke-width="2.5" stroke-linecap="round" stroke-linejoin="round" aria-hidden="true"><path d="M5 12.5l4.5 4.5L19 7"/></svg>';
const XI='<svg viewBox="0 0 24 24" fill="none" stroke="#8A2B2B" stroke-width="2.5" stroke-linecap="round" aria-hidden="true"><path d="M6 6l12 12M18 6L6 18"/></svg>';
function vValue(){
 const pl=t("plans");
 return '<div class="two"><div class="ba"><p class="lbl">'+t("beforeT")+'</p><h3>'+t("bf")[0].split(" ")[0]+'…</h3><ul>'+t("bf").map(x=>'<li>'+XI+'<span>'+x+'</span></li>').join("")+'</ul></div>'+
 '<div class="ba after"><p class="lbl">'+t("afterT")+'</p><h3>'+t("b1")+'</h3><ul>'+t("af").map(x=>'<li>'+OKI+'<span>'+x+'</span></li>').join("")+'</ul></div></div>'+
 '<p class="note" style="margin-top:12px">'+t("disc")+'</p>'+
 '<div class="sect"><h2>'+t("priceT")+'</h2><div class="plans">'+["basic","biz","prem"].map(k=>'<div class="plan'+(k==="biz"?" hot":"")+'">'+(k==="biz"?'<p class="lbl">'+t("pop2")+'</p>':'')+'<h3>'+pl[k][0]+'</h3><div class="pp">$<input type="number" min="0" max="999" inputmode="numeric" data-plan="'+k+'" value="'+P.prices[k]+'" aria-label="'+pl[k][0]+'"><span>'+t("mo")+'</span></div><ul>'+pl[k][1].map(x=>'<li>'+x+'</li>').join("")+'</ul></div>').join("")+'</div><p class="note" style="margin-top:10px">'+t("priceN")+'</p></div>'+
 '<div class="sect card" id="contact" style="border:2px solid var(--brand)"><h2>'+t("ctaT")+'</h2><form id="lead" autocomplete="off"><div class="field"><label class="f" for="l1">'+t("cName")+'</label><input type="text" id="l1" required></div><div class="field"><label class="f" for="l2">'+t("cBiz")+'</label><input type="text" id="l2" required></div><div class="field"><label class="f" for="l3">'+t("cCon")+'</label><input type="text" id="l3" required></div><button class="btn" type="submit" style="width:100%">'+t("cSend")+'</button><div id="leadmsg" role="status"></div></form><p class="note" style="margin-top:12px">'+t("cPriv")+'</p></div>'}

function renderTour(){
 const el=document.getElementById("tour");
 if(!U.tour){el.innerHTML="";el.style.display="none";return}
 el.style.display="block";const i=U.tour-1;
 el.innerHTML='<div class="in"><p class="lbl">'+t("step")+' '+U.tour+' '+t("of")+' 3</p><h3>'+U.tour+'. '+t("tt")[i]+'</h3><p>'+t("td")[i]+'</p><div class="acts"><button class="btn q" data-act="tourEnd" aria-label="'+t("close")+'">'+t("close")+'</button><button class="btn" data-act="tourPrev" '+(U.tour===1?"disabled":"")+'>'+t("prev")+'</button><button class="btn" data-act="tourNext">'+(U.tour===3?t("end"):t("next"))+'</button></div></div>'}

const VIEWS={home:vHome,book:vBook,panel:vPanel,brand:vBrand,value:vValue};
function render(){
 document.documentElement.lang=P.lang;
 document.documentElement.style.setProperty("--brand",D().cfg.color);
 const tabs=["home","book","panel","brand","value"];
 document.getElementById("app").className=U.tour?"pad":"";
 document.getElementById("app").innerHTML=
 '<header class="top"><div class="wrap topin"><div class="mark"><span class="mk"></span>Citalia<span class="demo">DEMO</span></div><div class="tools"><div class="seg" role="group" aria-label="Idioma / Language"><button data-act="lang" data-v="es" aria-pressed="'+(P.lang==="es")+'">ES</button><button data-act="lang" data-v="en" aria-pressed="'+(P.lang==="en")+'">EN</button></div><button class="btn sm dark" data-act="tour">'+t("tour")+'</button><button class="btn sm dark ghost" data-act="reset">'+t("reset")+'</button></div></div></header>'+
 '<div class="banner">'+t("banner")+'</div>'+
 '<nav class="tabs" aria-label="Demo"><div class="wrap">'+tabs.map(k=>'<button data-act="tab" data-v="'+k+'" '+(U.tab===k?'aria-current="page"':'')+'>'+t(k)+'</button>').join("")+'</div></nav>'+
 '<div class="wrap bizbar"><span class="lbl">'+(P.lang==="es"?"Negocio":"Business")+'</span><div class="seg" role="group">'+Object.keys(BIZ).map(k=>'<button data-act="biz" data-v="'+k+'" aria-pressed="'+(U.biz===k)+'"><span class="dot" data-bd="'+k+'" style="background:'+P.data[k].cfg.color+'"></span><span data-bn="'+k+'">'+esc(P.data[k].cfg.name)+'</span></button>').join("")+'</div></div>'+
 '<main id="main">'+VIEWS[U.tab]()+'</main><footer class="fin">'+t("foot")+'</footer>';
 renderTour();
}
function liveBrand(){
 document.documentElement.style.setProperty("--brand",D().cfg.color);
 const pv=document.getElementById("preview");if(pv)pv.innerHTML=preview(U.biz);
 document.querySelectorAll("[data-bn]").forEach(e=>e.textContent=P.data[e.dataset.bn].cfg.name);
 document.querySelectorAll("[data-bd]").forEach(e=>e.style.background=P.data[e.dataset.bd].cfg.color);
}
function go(tab){U.tab=tab;render();window.scrollTo(0,0)}
function cancelAppt(a){a.status="cancelled"}

/* ============================ ACCIONES ============================ */
const TOURTAB=["book","panel","brand"];
function tourShow(){go(TOURTAB[U.tour-1])}
const A={
 lang:v=>{P.lang=v.v;save();render()},
 tab:v=>go(v.v),
 start:()=>go("book"),
 biz:v=>{if(U.biz===v.v)return;U.biz=v.v;U.book=bookDefault();U.open=null;U.hl=null;U.day=0;render()},
 bsvc:v=>{U.book.svc=v.v;U.book.time=null;render()},
 bpro:v=>{U.book.pro=v.v;U.book.time=null;render()},
 bday:v=>{U.book.day=+v.v;U.book.time=null;render()},
 btime:v=>{U.book.time=+v.v;render();const s=document.querySelector(".sum");if(s&&window.innerWidth<760)s.scrollIntoView({behavior:"smooth",block:"center"})},
 confirm:()=>{const bk=U.book,s=svcOf(bk.svc);if(bk.time===null)return;
  const pid=freePro(bk.day,bk.time,s.m,bk.pro);if(!pid){toast(t("taken"));bk.time=null;render();return}
  const d=D(),a={id:U.biz+"-n"+(++d.seq),day:bk.day,start:bk.time,svc:bk.svc,pro:pid,client:(bk.name.trim()||t("demoClient")),status:"confirmed",isNew:true};
  d.appts.push(a);save();bk.done=a.id;U.hl=a.id;U.open=a.id;U.day=a.day;render();window.scrollTo(0,0)},
 again:()=>{U.book=bookDefault();render();window.scrollTo(0,0)},
 toAgenda:()=>{U.view="day";go("panel")},
 view:v=>{U.view=v.v;render()},
 pday:v=>{U.day=+v.v;U.open=null;render()},
 goDay:v=>{U.view="day";U.day=+v.v;U.open=v.id;render()},
 open:v=>{U.open=U.open===v.id?null:v.id;U.hl=null;render()},
 status:v=>{const a=D().appts.find(x=>x.id===v.id);if(a){a.status=v.v;save();U.hl=null;render()}},
 cancel:v=>{const a=D().appts.find(x=>x.id===v.id);if(a){cancelAppt(a);save();render();toast(t("freed")+" · "+fmtT(a.start))}},
 restore:v=>{const a=D().appts.find(x=>x.id===v.id);if(!a)return;if(!isFree(a.pro,a.day,a.start,svcOf(a.svc).m,a.id)){toast(t("taken"));return}a.status="confirmed";save();render();toast(t("restored"))},
 simnew:()=>{const d=D(),b=B();let day=U.view==="day"?U.day:Math.floor(Math.random()*7),s=b.svcs[Math.floor(Math.random()*b.svcs.length)];
  for(let i=0;i<7;i++){const dd=(day+i)%7;const free=slots(dd,s.id,"any").filter(x=>x.pro);
   if(free.length){const pick=free[Math.floor(Math.random()*free.length)];const a={id:U.biz+"-n"+(++d.seq),day:dd,start:pick.t,svc:s.id,pro:pick.pro,client:b.names[Math.floor(Math.random()*b.names.length)],status:"confirmed",isNew:true};
    d.appts.push(a);save();if(U.view==="day")U.day=dd;U.open=a.id;U.hl=a.id;render();toast(t("simNewOk")+" · "+fmtT(a.start));return}}
  toast(t("full"))},
 simcx:()=>{const days=U.view==="day"?[U.day]:[0,1,2,3,4,5,6];const c=D().appts.filter(a=>a.status==="confirmed"&&days.includes(a.day)&&(a.day>0||a.start>=NOW));
  if(!c.length){toast(t("noCx"));return}const a=c[Math.floor(Math.random()*c.length)];cancelAppt(a);save();U.open=a.id;U.hl=null;render();toast(t("simCxOk")+" · "+fmtT(a.start))},
 color:v=>{D().cfg.color=v.v;save();render()},
 logo:v=>{D().cfg.logo=v.v;save();render()},
 reset:()=>{const l=P.lang;P=newP(l);save();U.biz=U.biz;U.view="day";U.day=0;U.open=null;U.hl=null;U.book=bookDefault();render();toast(t("resetOk"))},
 tour:()=>{U.tour=1;tourShow()},
 tourNext:()=>{if(U.tour>=3){U.tour=0;render();return}U.tour++;tourShow()},
 tourPrev:()=>{if(U.tour>1){U.tour--;tourShow()}},
 tourEnd:()=>{U.tour=0;render()}
};
document.addEventListener("click",e=>{const el=e.target.closest("[data-act]");if(!el)return;const f=A[el.dataset.act];if(f)f(el.dataset)});
document.addEventListener("input",e=>{const el=e.target;
 if(el.id==="cname")U.book.name=el.value;
 else if(el.id==="brandName"){D().cfg.name=el.value.slice(0,28)||BIZ[U.biz].name;save();liveBrand()}
 else if(el.id==="colorPick"){D().cfg.color=el.value;save();liveBrand();document.querySelectorAll(".sw button").forEach(b=>b.setAttribute("aria-pressed","false"))}});
document.addEventListener("change",e=>{const el=e.target;if(el.dataset&&el.dataset.plan){let n=Math.max(0,Math.min(999,parseInt(el.value,10)||0));P.prices[el.dataset.plan]=n;el.value=n;save()}});
document.addEventListener("submit",e=>{if(e.target.id==="lead"){e.preventDefault();/* simulado: NO se almacena ni se envía nada */e.target.reset();document.getElementById("leadmsg").innerHTML='<p class="msg">'+t("cOk")+'</p>'}});
document.addEventListener("keydown",e=>{if(e.key==="Escape"&&U.tour){U.tour=0;render()}});
save();render();
</script>
</body>
</html>
