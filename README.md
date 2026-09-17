<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width,initial-scale=1.0">
<title>SpecVault — Compare Technology</title>

<style>
:root{
  --bg:#f7f7f5;
  --text:#111;
  --muted:#777;
  --card:#fff;
  --line:#deded9;
  --accent:#e51b23;
}

*{box-sizing:border-box;margin:0;padding:0}

html{scroll-behavior:smooth}

body{
  font-family:Arial,Helvetica,sans-serif;
  background:var(--bg);
  color:var(--text);
}

button,input,select{
  font:inherit;
}

button{cursor:pointer}

.nav{
  position:sticky;
  top:0;
  z-index:20;
  height:72px;
  display:flex;
  align-items:center;
  justify-content:space-between;
  padding:0 5vw;
  background:rgba(247,247,245,.86);
  backdrop-filter:blur(18px);
  border-bottom:1px solid var(--line);
}

.logo{
  font-size:20px;
  font-weight:800;
  letter-spacing:-.7px;
}

.navlinks{
  display:flex;
  gap:24px;
  color:#555;
  font-size:14px;
}

.navlinks a{
  color:inherit;
  text-decoration:none;
}

.hero{
  min-height:650px;
  display:grid;
  grid-template-columns:1.05fr .95fr;
  gap:30px;
  align-items:center;
  padding:70px 7vw;
}

.kicker{
  font-size:13px;
  letter-spacing:2px;
  text-transform:uppercase;
  color:var(--muted);
  margin-bottom:20px;
}

.hero h1{
  font-size:clamp(58px,8vw,120px);
  line-height:.88;
  letter-spacing:-7px;
  max-width:850px;
}

.hero h1 span{
  display:block;
  color:#aaa;
}

.hero p{
  margin-top:28px;
  max-width:520px;
  color:#666;
  font-size:18px;
  line-height:1.6;
}

.hero-actions{
  display:flex;
  gap:12px;
  margin-top:32px;
}

.btn{
  border:1px solid #111;
  background:#111;
  color:#fff;
  padding:14px 20px;
  border-radius:999px;
  transition:.2s;
}

.btn:hover{
  transform:translateY(-2px);
}

.btn.alt{
  color:#111;
  background:transparent;
}

.hero-phone{
  height:500px;
  display:flex;
  align-items:center;
  justify-content:center;
}

.phone{
  width:260px;
  height:520px;
  border-radius:42px;
  background:linear-gradient(150deg,#202020,#050505);
  box-shadow:0 30px 90px rgba(0,0,0,.22);
  position:relative;
  transform:rotate(9deg);
}

.phone:before{
  content:"";
  position:absolute;
  inset:12px;
  border-radius:34px;
  background:
    radial-gradient(circle at 50% 20%,rgba(255,255,255,.16),transparent 28%),
    linear-gradient(145deg,#262626,#080808);
}

.camera-bump{
  position:absolute;
  top:30px;
  left:30px;
  width:110px;
  height:110px;
  border-radius:28px;
  border:1px solid #444;
  background:#111;
  z-index:2;
}

.lens{
  width:30px;
  height:30px;
  border-radius:50%;
  background:#050505;
  border:5px solid #555;
  position:absolute;
}

.l1{top:15px;left:15px}
.l2{top:15px;right:15px}
.l3{bottom:15px;left:15px}

.section{
  padding:90px 7vw;
}

.section-head{
  display:flex;
  justify-content:space-between;
  align-items:end;
  gap:20px;
  margin-bottom:34px;
}

.section-head h2{
  font-size:clamp(40px,6vw,76px);
  letter-spacing:-4px;
}

.section-head p{
  color:var(--muted);
  max-width:400px;
  line-height:1.5;
}

.controls{
  display:grid;
  grid-template-columns:2fr 1fr 1fr 1fr;
  gap:12px;
  margin-bottom:28px;
}

.control{
  background:#fff;
  border:1px solid var(--line);
  border-radius:16px;
  padding:14px 16px;
}

.control label{
  display:block;
  font-size:11px;
  color:#888;
  text-transform:uppercase;
  letter-spacing:1px;
  margin-bottom:7px;
}

.control input,
.control select{
  width:100%;
  border:0;
  outline:0;
  background:transparent;
  color:#111;
}

.range-wrap{
  background:#fff;
  border:1px solid var(--line);
  border-radius:16px;
  padding:14px 16px;
}

.range-row{
  display:flex;
  justify-content:space-between;
  font-size:13px;
  margin-bottom:8px;
}

.range{
  width:100%;
}

.phone-grid{
  display:grid;
  grid-template-columns:repeat(4,1fr);
  gap:16px;
}

.card{
  background:var(--card);
  border:1px solid var(--line);
  border-radius:26px;
  overflow:hidden;
  transition:.25s;
}

.card:hover{
  transform:translateY(-5px);
  box-shadow:0 20px 50px rgba(0,0,0,.08);
}

.card-visual{
  height:300px;
  display:flex;
  justify-content:center;
  align-items:center;
  background:#ededeb;
}

.mini-phone{
  width:115px;
  height:225px;
  border-radius:22px;
  background:linear-gradient(160deg,#252525,#080808);
  box-shadow:0 20px 45px rgba(0,0,0,.2);
  position:relative;
}

.mini-screen{
  position:absolute;
  inset:7px;
  border-radius:17px;
  background:linear-gradient(160deg,#1e1e1e,#090909);
}

.card-body{
  padding:20px;
}

.brand{
  color:#888;
  font-size:11px;
  letter-spacing:1.4px;
  text-transform:uppercase;
  margin-bottom:7px;
}

.card h3{
  font-size:25px;
  letter-spacing:-1px;
}

.price{
  margin-top:10px;
  font-size:18px;
  font-weight:700;
}

.muted{
  color:#888;
  font-size:12px;
}

.spec-row{
  display:grid;
  grid-template-columns:1fr 1fr;
  gap:8px;
  margin-top:18px;
}

.spec{
  background:#f3f3f0;
  border-radius:12px;
  padding:10px;
}

.spec small{
  display:block;
  color:#888;
  font-size:10px;
  margin-bottom:4px;
}

.card-actions{
  display:flex;
  gap:8px;
  margin-top:18px;
}

.small-btn{
  flex:1;
  padding:11px 12px;
  border-radius:999px;
  border:1px solid #111;
  background:#111;
  color:#fff;
}

.small-btn.light{
  background:transparent;
  color:#111;
}

.compare-bar{
  position:fixed;
  bottom:18px;
  left:50%;
  transform:translateX(-50%) translateY(120px);
  width:min(720px,calc(100% - 30px));
  background:#111;
  color:#fff;
  border-radius:24px;
  padding:16px;
  display:flex;
  align-items:center;
  justify-content:space-between;
  gap:15px;
  z-index:50;
  box-shadow:0 20px 60px rgba(0,0,0,.25);
  transition:.3s;
}

.compare-bar.show{
  transform:translateX(-50%) translateY(0);
}

.compare-items{
  display:flex;
  gap:8px;
  flex-wrap:wrap;
}

.compare-chip{
  background:#292929;
  padding:8px 11px;
  border-radius:999px;
  font-size:12px;
}

.modal{
  position:fixed;
  inset:0;
  background:rgba(0,0,0,.58);
  backdrop-filter:blur(8px);
  display:none;
  align-items:center;
  justify-content:center;
  z-index:100;
  padding:20px;
}

.modal.show{
  display:flex;
}

.modal-box{
  width:min(1050px,100%);
  max-height:90vh;
  overflow:auto;
  background:#fff;
  border-radius:28px;
  padding:28px;
}

.modal-top{
  display:flex;
  justify-content:space-between;
  align-items:center;
  margin-bottom:22px;
}

.close{
  border:0;
  background:#eee;
  width:40px;
  height:40px;
  border-radius:50%;
}

.config{
  display:grid;
  grid-template-columns:1fr 1fr;
  gap:18px;
  margin-top:20px;
}

.config-box{
  border:1px solid var(--line);
  border-radius:18px;
  padding:16px;
}

.config-box h4{
  margin-bottom:12px;
}

.options{
  display:flex;
  flex-wrap:wrap;
  gap:8px;
}

.option{
  border:1px solid #ccc;
  background:#fff;
  border-radius:999px;
  padding:9px 12px;
}

.option.active{
  border-color:#111;
  background:#111;
  color:#fff;
}

.compare-table{
  width:100%;
  border-collapse:collapse;
  margin-top:25px;
}

.compare-table th,
.compare-table td{
  padding:14px;
  border-bottom:1px solid #ddd;
  text-align:left;
}

.compare-table th{
  font-size:12px;
  text-transform:uppercase;
  letter-spacing:1px;
  color:#888;
}

footer{
  padding:80px 7vw;
  border-top:1px solid var(--line);
  color:#777;
}

@media(max-width:1000px){
  .phone-grid{grid-template-columns:repeat(2,1fr)}
  .controls{grid-template-columns:1fr 1fr}
  .hero{grid-template-columns:1fr}
}

@media(max-width:650px){
  .navlinks{display:none}
  .hero{padding-top:45px}
  .hero h1{letter-spacing:-4px}
  .phone-grid{grid-template-columns:1fr}
  .controls{grid-template-columns:1fr}
  .config{grid-template-columns:1fr}
}
</style>
</head>

<body>

<nav class="nav">
  <div class="logo">SPECVAULT</div>

  <div class="navlinks">
    <a href="#phones">Phones</a>
    <a href="#compare">Compare</a>
    <a href="#about">About</a>
  </div>
</nav>

<section class="hero">
  <div>
    <div class="kicker">The phone database</div>

    <h1>
      Compare.
      <span>Your way.</span>
    </h1>

    <p>
      Search, filter and configure smartphones by the specifications
      that actually matter to you.
    </p>

    <div class="hero-actions">
      <button class="btn" onclick="document.getElementById('phones').scrollIntoView()">
        Explore phones
      </button>

      <button class="btn alt" onclick="openCompare()">
        Compare
      </button>
    </div>
  </div>

  <div class="hero-phone">
    <div class="phone">
      <div class="camera-bump">
        <div class="lens l1"></div>
        <div class="lens l2"></div>
        <div class="lens l3"></div>
      </div>
    </div>
  </div>
</section>

<section class="section" id="phones">

  <div class="section-head">
    <div>
      <div class="kicker">Explore</div>
      <h2>Find your phone.</h2>
    </div>

    <p>
      Filter the catalog by brand, price, display and storage.
      More filters can be added later.
    </p>
  </div>

  <div class="controls">

    <div class="control">
      <label>Search</label>
      <input id="search" type="text" placeholder="Search phones..." />
    </div>

    <div class="control">
      <label>Brand</label>
      <select id="brand">
        <option value="all">All brands</option>
      </select>
    </div>

    <div class="control">
      <label>Display</label>
      <select id="refresh">
        <option value="all">Any refresh rate</option>
        <option value="120">120 Hz+</option>
        <option value="90">90 Hz+</option>
      </select>
    </div>

    <div class="control">
      <label>Storage</label>
      <select id="storage">
        <option value="all">Any storage</option>
        <option value="256">256 GB+</option>
        <option value="512">512 GB+</option>
        <option value="1024">1 TB+</option>
      </select>
    </div>

  </div>

  <div class="range-wrap">
    <div class="range-row">
      <span>Maximum price</span>
      <strong id="priceLabel">CHF 2500</strong>
    </div>

    <input
      id="price"
      class="range"
      type="range"
      min="300"
      max="2500"
      step="50"
      value="2500"
    />
  </div>

  <div style="height:25px"></div>

  <div id="phoneGrid" class="phone-grid"></div>

</section>

<section class="section" id="compare">

  <div class="section-head">
    <div>
      <div class="kicker">Side by side</div>
      <h2>Compare.</h2>
    </div>

    <p>
      Select phones above and compare their main specifications.
    </p>
  </div>

  <div id="emptyCompare" class="card" style="padding:30px">
    <h3>No phones selected</h3>
    <p class="muted" style="margin-top:8px">
      Choose “Compare” on two or more phone cards.
    </p>
  </div>

  <div id="compareContent"></div>

</section>

<section class="section" id="about">
  <div class="section-head">
    <div>
      <div class="kicker">SpecVault</div>
      <h2>Technology,<br>your way.</h2>
    </div>

    <p>
      A clean comparison platform designed around your choices,
      not somebody else's ranking.
    </p>
  </div>
</section>

<footer>
  SPECVAULT © 2026
</footer>

<div id="compareBar" class="compare-bar">
  <div id="compareItems" class="compare-items"></div>

  <button class="small-btn" onclick="openCompare()">
    Compare now
  </button>
</div>

<div id="detailModal" class="modal">
  <div class="modal-box">

    <div class="modal-top">
      <div>
        <div id="modalBrand" class="brand"></div>
        <h2 id="modalName"></h2>
      </div>

      <button class="close" onclick="closeModal()">✕</button>
    </div>

    <div id="modalInfo"></div>

    <div class="config">

      <div class="config-box">
        <h4>Storage</h4>
        <div id="storageOptions" class="options"></div>
      </div>

      <div class="config-box">
        <h4>Colour</h4>
        <div id="colorOptions" class="options"></div>
      </div>

    </div>

  </div>
</div>

<script>
/*
  SPECVAULT PHONE DATABASE

  Add more phones by copying one object.
  The website is designed for 100+ phones.
*/

const phones = [

  {
    id:"iphone18pro",
    brand:"Apple",
    name:"iPhone 18 Pro",
    price:1299,
    display:"6.3\" OLED",
    refresh:120,
    chip:"A20 Pro",
    camera:"48 MP triple",
    battery:"Up to 43h video",
    storage:[256,512,1024,2048],
    colors:["Black","Silver","Polar","Burgundy"],
    os:"iOS",
    weight:"211 g",
    note:"Official Swiss starting price"
  },

  {
    id:"iphone18promax",
    brand:"Apple",
    name:"iPhone 18 Pro Max",
    price:1299,
    display:"6.9\" OLED",
    refresh:120,
    chip:"A20 Pro",
    camera:"48 MP triple",
    battery:"Up to 43h video",
    storage:[256,512,1024,2048],
    colors:["Black","Silver","Polar","Burgundy"],
    os:"iOS",
    weight:"249 g",
    note:"Official Swiss starting price"
  },

  {
    id:"iphoneduo",
    brand:"Apple",
    name:"iPhone Duo",
    price:1999,
    display:"7.6\" foldable",
    refresh:120,
    chip:"A20 Pro",
    camera:"48 MP dual",
    battery:"Up to 44h outer display",
    storage:[512,1024,2048],
    colors:["Night Sky","Starlight"],
    os:"iOS",
    weight:"—",
    note:"Official Swiss starting price"
  },

  {
    id:"iphoneair",
    brand:"Apple",
    name:"iPhone Air",
    price:1099,
    display:"6.5\" OLED",
    refresh:120,
    chip:"A19 Pro",
    camera:"48 MP",
    battery:"Up to 27h video",
    storage:[256,512,1024],
    colors:["Black","White","Blue","Gold"],
    os:"iOS",
    weight:"—",
    note:"Official Swiss starting price"
  },

  /* More current/recent catalog entries.
     These are ready for the database and can be replaced
     with verified regional pricing/spec data. */

  {
    id:"iphone17",
    brand:"Apple",
    name:"iPhone 17",
    price:899,
    display:"6.3\" OLED",
    refresh:120,
    chip:"A19",
    camera:"48 MP",
    battery:"All-day",
    storage:[256,512],
    colors:["Black","White","Blue","Green","Purple"],
    os:"iOS",
    weight:"—"
  },

  {
    id:"iphone17e",
    brand:"Apple",
    name:"iPhone 17e",
    price:699,
    display:"6.1\" OLED",
    refresh:60,
    chip:"A19",
    camera:"48 MP",
    battery:"All-day",
    storage:[128,256,512],
    colors:["Black","White"],
    os:"iOS",
    weight:"—"
  },

  {
    id:"s26ultra",
    brand:"Samsung",
    name:"Galaxy S26 Ultra",
    price:1399,
    display:"6.9\" AMOLED",
    refresh:120,
    chip:"Snapdragon flagship",
    camera:"200 MP multi-camera",
    battery:"5000 mAh",
    storage:[256,512,1024],
    colors:["Black","Silver","Blue"],
    os:"Android",
    weight:"—"
  },

  {
    id:"s26plus",
    brand:"Samsung",
    name:"Galaxy S26+",
    price:1199,
    display:"6.7\" AMOLED",
    refresh:120,
    chip:"Snapdragon flagship",
    camera:"50 MP multi-camera",
    battery:"—",
    storage:[256,512],
    colors:["Black","Silver","Blue"],
    os:"Android",
    weight:"—"
  },

  {
    id:"s26",
    brand:"Samsung",
    name:"Galaxy S26",
    price:999,
    display:"6.3\" AMOLED",
    refresh:120,
    chip:"Snapdragon flagship",
    camera:"50 MP multi-camera",
    battery:"—",
    storage:[128,256],
    colors:["Black","Silver","Blue"],
    os:"Android",
    weight:"—"
  },

  {
    id:"pixel10pro",
    brand:"Google",
    name:"Pixel 10 Pro",
    price:849,
    display:"6.3\" LTPO OLED",
    refresh:120,
    chip:"Tensor G5",
    camera:"Pro triple",
    battery:"—",
    storage:[128,256,512,1024],
    colors:["Moonstone","Jade","Porcelain","Obsidian"],
    os:"Android",
    weight:"207 g"
  },

  {
    id:"pixel10proxl",
    brand:"Google",
    name:"Pixel 10 Pro XL",
    price:949,
    display:"6.8\" LTPO OLED",
    refresh:120,
    chip:"Tensor G5",
    camera:"Pro triple",
    battery:"—",
    storage:[256,512,1024],
    colors:["Moonstone","Jade","Porcelain","Obsidian"],
    os:"Android",
    weight:"232 g"
  },

  {
    id:"nothingphone",
    brand:"Nothing",
    name:"Phone (current flagship)",
    price:699,
    display:"OLED",
    refresh:120,
    chip:"Flagship",
    camera:"Multi-camera",
    battery:"—",
    storage:[256,512],
    colors:["Black","White"],
    os:"Android",
    weight:"—"
  },

  {
    id:"oneplus",
    brand:"OnePlus",
    name:"OnePlus flagship",
    price:799,
    display:"AMOLED",
    refresh:120,
    chip:"Flagship Snapdragon",
    camera:"Triple camera",
    battery:"—",
    storage:[256,512],
    colors:["Black","Silver"],
    os:"Android",
    weight:"—"
  },

  {
    id:"xiaomi",
    brand:"Xiaomi",
    name:"Xiaomi flagship",
    price:899,
    display:"AMOLED",
    refresh:120,
    chip:"Flagship Snapdragon",
    camera:"Leica multi-camera",
    battery:"—",
    storage:[256,512,1024],
    colors:["Black","White","Blue"],
    os:"Android",
    weight:"—"
  },

  {
    id:"motorola",
    brand:"Motorola",
    name:"Motorola Edge flagship",
    price:699,
    display:"pOLED",
    refresh:144,
    chip:"Snapdragon",
    camera:"Multi-camera",
    battery:"—",
    storage:[256,512],
    colors:["Black","Blue"],
    os:"Android",
    weight:"—"
  }

];

/* -----------------------------
   Add brand names to filter
----------------------------- */

const brandSelect = document.getElementById("brand");

[...new Set(phones.map(p => p.brand))]
  .sort()
  .forEach(brand => {
    const option = document.createElement("option");
    option.value = brand;
    option.textContent = brand;
    brandSelect.appendChild(option);
  });


/* -----------------------------
   Rendering
----------------------------- */

const grid = document.getElementById("phoneGrid");

function renderPhones(){

  const query =
    document.getElementById("search").value
      .toLowerCase()
      .trim();

  const selectedBrand =
    document.getElementById("brand").value;

  const selectedRefresh =
    document.getElementById("refresh").value;

  const selectedStorage =
    document.getElementById("storage").value;

  const maxPrice =
    Number(document.getElementById("price").value);

  const filtered = phones.filter(phone => {

    const matchesSearch =
      phone.name.toLowerCase().includes(query) ||
      phone.brand.toLowerCase().includes(query);

    const matchesBrand =
      selectedBrand === "all" ||
      phone.brand === selectedBrand;

    const matchesRefresh =
      selectedRefresh === "all" ||
      phone.refresh >= Number(selectedRefresh);

    const matchesStorage =
      selectedStorage === "all" ||
      Math.max(...phone.storage) >= Number(selectedStorage);

    const matchesPrice =
      phone.price <= maxPrice;

    return (
      matchesSearch &&
      matchesBrand &&
      matchesRefresh &&
      matchesStorage &&
      matchesPrice
    );
  });

  grid.innerHTML = "";

  if(filtered.length === 0){
    grid.innerHTML = `
      <div class="card" style="padding:30px;grid-column:1/-1">
        <h3>No phones found.</h3>
        <p class="muted" style="margin-top:8px">
          Try changing your filters.
        </p>
      </div>
    `;
    return;
  }

  filtered.forEach(phone => {

    const card = document.createElement("article");
    card.className = "card";

    card.innerHTML = `
      <div class="card-visual">
        <div class="mini-phone">
          <div class="mini-screen"></div>
        </div>
      </div>

      <div class="card-body">

        <div class="brand">${phone.brand}</div>

        <h3>${phone.name}</h3>

        <div class="price">
          From CHF ${phone.price.toLocaleString()}
        </div>

        <div class="muted">
          ${phone.note || "Catalog entry"}
        </div>

        <div class="spec-row">

          <div class="spec">
            <small>DISPLAY</small>
            ${phone.display}
          </div>

          <div class="spec">
            <small>REFRESH</small>
            ${phone.refresh} Hz
          </div>

          <div class="spec">
            <small>CAMERA</small>
            ${phone.camera}
          </div>

          <div class="spec">
            <small>STORAGE</small>
            ${Math.max(...phone.storage)} GB+
          </div>

        </div>

        <div class="card-actions">

          <button class="small-btn light"
            onclick="openDetails('${phone.id}')">
            Configure
          </button>

          <button class="small-btn"
            onclick="toggleCompare('${phone.id}')">
            Compare
          </button>

        </div>

      </div>
    `;

    grid.appendChild(card);
  });
}


/* -----------------------------
   Filters
----------------------------- */

["search","brand","refresh","storage","price"]
.forEach(id => {

  document.getElementById(id)
    .addEventListener("input", () => {

      if(id === "price"){
        document.getElementById("priceLabel").textContent =
          "CHF " +
          Number(document.getElementById("price").value)
            .toLocaleString();
      }

      renderPhones();
    });

});


/* -----------------------------
   Configuration modal
----------------------------- */

let selectedPhone = null;

function openDetails(id){

  selectedPhone = phones.find(p => p.id === id);

  document.getElementById("modalBrand").textContent =
    selectedPhone.brand;

  document.getElementById("modalName").textContent =
    selectedPhone.name;

  document.getElementById("modalInfo").innerHTML = `
    <div class="spec-row">

      <div class="spec">
        <small>PRICE FROM</small>
        CHF ${selectedPhone.price.toLocaleString()}
      </div>

      <div class="spec">
        <small>DISPLAY</small>
        ${selectedPhone.display}
      </div>

      <div class="spec">
        <small>CHIP</small>
        ${selectedPhone.chip}
      </div>

      <div class="spec">
        <small>CAMERA</small>
        ${selectedPhone.camera}
      </div>

      <div class="spec">
        <small>BATTERY</small>
        ${selectedPhone.battery}
      </div>

      <div class="spec">
        <small>OS</small>
        ${selectedPhone.os}
      </div>

      <div class="spec">
        <small>WEIGHT</small>
        ${selectedPhone.weight}
      </div>

    </div>
  `;

  const storageOptions =
    document.getElementById("storageOptions");

  storageOptions.innerHTML = "";

  selectedPhone.storage.forEach((gb,index) => {

    const button = document.createElement("button");

    button.className =
      "option" + (index === 0 ? " active" : "");

    button.textContent =
      gb >= 1024
        ? (gb / 1024) + " TB"
        : gb + " GB";

    button.onclick = () => {

      storageOptions
        .querySelectorAll(".option")
        .forEach(b => b.classList.remove("active"));

      button.classList.add("active");

      /* Real product-style configuration price update */
      const extra =
        index === 0 ? 0 :
        index === 1 ? 200 :
        index === 2 ? 400 :
        700;

      document.querySelector("#modalInfo .spec")
        .textContent =
        "CHF " +
        (selectedPhone.price + extra)
          .toLocaleString();
    };

    storageOptions.appendChild(button);
  });


  const colorOptions =
    document.getElementById("colorOptions");

  colorOptions.innerHTML = "";

  selectedPhone.colors.forEach((color,index) => {

    const button = document.createElement("button");

    button.className =
      "option" + (index === 0 ? " active" : "");

    button.textContent = color;

    button.onclick = () => {

      colorOptions
        .querySelectorAll(".option")
        .forEach(b => b.classList.remove("active"));

      button.classList.add("active");
    };

    colorOptions.appendChild(button);

  });


  document
    .getElementById("detailModal")
    .classList.add("show");
}


function closeModal(){
  document
    .getElementById("detailModal")
    .classList.remove("show");
}


/* -----------------------------
   Compare system
----------------------------- */

let compareIds = [];

function toggleCompare(id){

  if(compareIds.includes(id)){
    compareIds =
      compareIds.filter(x => x !== id);
  }else{

    if(compareIds.length >= 4){
      alert("You can compare up to 4 phones.");
      return;
    }

    compareIds.push(id);
  }

  updateCompareBar();
  renderCompare();
}


function updateCompareBar(){

  const bar =
    document.getElementById("compareBar");

  const items =
    document.getElementById("compareItems");

  items.innerHTML =
    compareIds.map(id => {

      const phone =
        phones.find(p => p.id === id);

      return `
        <div class="compare-chip">
          ${phone.name}
        </div>
      `;

    }).join("");

  if(compareIds.length){
    bar.classList.add("show");
  }else{
    bar.classList.remove("show");
  }
}


function renderCompare(){

  const empty =
    document.getElementById("emptyCompare");

  const content =
    document.getElementById("compareContent");

  if(compareIds.length < 2){

    empty.style.display = "block";
    content.innerHTML = "";
    return;
  }

  empty.style.display = "none";

  const selected =
    compareIds.map(id =>
      phones.find(p => p.id === id)
    );

  const rows = [
    ["Price", p => "CHF " + p.price.toLocaleString()],
    ["Display", p => p.display],
    ["Refresh rate", p => p.refresh + " Hz"],
    ["Chip", p => p.chip],
    ["Camera", p => p.camera],
    ["Battery", p => p.battery],
    ["Storage", p => Math.max(...p.storage) + " GB+"],
    ["OS", p => p.os],
    ["Weight", p => p.weight]
  ];

  content.innerHTML = `
    <div class="card" style="padding:20px;overflow:auto">

      <table class="compare-table">

        <thead>
          <tr>
            <th>Specification</th>
            ${selected.map(p => `<th>${p.name}</th>`).join("")}
          </tr>
        </thead>

        <tbody>
          ${rows.map(([label,fn]) => `
            <tr>
              <th>${label}</th>
              ${selected.map(p => `<td>${fn(p)}</td>`).join("")}
            </tr>
          `).join("")}
        </tbody>

      </table>

    </div>
  `;
}


function openCompare(){

  document
    .getElementById("compare")
    .scrollIntoView({
      behavior:"smooth"
    });

  renderCompare();
}


/* -----------------------------
   Initial render
----------------------------- */

renderPhones();

</script>

</body>
</html>
