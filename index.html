<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Street Adventure</title>

<style>
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

body {
  overflow: hidden;
  background: #111;
  font-family: Arial, sans-serif;
}

canvas {
  display: block;
  background: #5d8f4d;
}

#hud {
  position: fixed;
  top: 15px;
  left: 15px;
  z-index: 5;
  color: white;
  background: rgba(0,0,0,.65);
  padding: 12px 16px;
  border-radius: 10px;
  min-width: 180px;
}

#mission {
  margin-top: 8px;
  color: #ffd84d;
  font-size: 14px;
}

#help {
  position: fixed;
  bottom: 15px;
  left: 15px;
  z-index: 5;
  color: white;
  background: rgba(0,0,0,.65);
  padding: 10px;
  border-radius: 8px;
  font-size: 13px;
}

#message {
  position: fixed;
  top: 50%;
  left: 50%;
  transform: translate(-50%,-50%);
  color: white;
  background: rgba(0,0,0,.85);
  padding: 20px 30px;
  border-radius: 12px;
  font-size: 22px;
  display: none;
  z-index: 10;
}
</style>
</head>

<body>

<canvas id="game"></canvas>

<div id="hud">
  <b>STREET ADVENTURE</b>
  <div>💰 Coins: <span id="coins">0</span></div>
  <div>🚗 Car: <span id="carStatus">No</span></div>
  <div id="mission">Mission: Find the yellow marker</div>
</div>

<div id="help">
  WASD / Arrow Keys = Move<br>
  E = Enter / Exit Car<br>
  Collect coins and reach the yellow marker
</div>

<div id="message"></div>

<script>
const canvas = document.getElementById("game");
const ctx = canvas.getContext("2d");

function resize() {
  canvas.width = window.innerWidth;
  canvas.height = window.innerHeight;
}

resize();
window.addEventListener("resize", resize);

const keys = {};

window.addEventListener("keydown", e => {
  keys[e.key.toLowerCase()] = true;

  if (e.key.toLowerCase() === "e") {
    toggleCar();
  }
});

window.addEventListener("keyup", e => {
  keys[e.key.toLowerCase()] = false;
});

const world = {
  width: 2400,
  height: 1800
};

const player = {
  x: 350,
  y: 350,
  size: 22,
  speed: 4,
  inCar: false
};

let coins = 0;

const car = {
  x: 520,
  y: 390,
  width: 58,
  height: 32,
  speed: 6
};

const mission = {
  x: 1900,
  y: 1350,
  radius: 35,
  complete: false
};

const buildings = [];
const coinList = [];

function createCity() {

  const roadsX = [200, 600, 1000, 1400, 1800, 2200];
  const roadsY = [180, 500, 820, 1140, 1460];

  for (let x of roadsX) {
    for (let y of roadsY) {

      buildings.push({
        x: x + 70,
        y: y + 60,
        w: 150,
        h: 120
      });

      buildings.push({
        x: x + 245,
        y: y + 55,
        w: 110,
        h: 150
      });
    }
  }

  for (let i = 0; i < 25; i++) {

    coinList.push({
      x: 150 + Math.random() * 2050,
      y: 120 + Math.random() * 1500,
      collected: false
    });
  }
}

createCity();

function drawRoads() {

  ctx.fillStyle = "#444";

  for (let x = 0; x < world.width; x += 400) {
    ctx.fillRect(x, 0, 70, world.height);
  }

  for (let y = 0; y < world.height; y += 320) {
    ctx.fillRect(0, y, world.width, 70);
  }

  ctx.strokeStyle = "#ddd";
  ctx.lineWidth = 3;
  ctx.setLineDash([20, 20]);

  for (let x = 35; x < world.width; x += 400) {
    ctx.beginPath();
    ctx.moveTo(x, 0);
    ctx.lineTo(x, world.height);
    ctx.stroke();
  }

  for (let y = 35; y < world.height; y += 320) {
    ctx.beginPath();
    ctx.moveTo(0, y);
    ctx.lineTo(world.width, y);
    ctx.stroke();
  }

  ctx.setLineDash([]);
}

function drawBuildings() {

  for (const b of buildings) {

    ctx.fillStyle = "#777";
    ctx.fillRect(b.x, b.y, b.w, b.h);

    ctx.fillStyle = "#9c9c9c";
    ctx.fillRect(b.x + 8, b.y + 8, b.w - 16, 12);

    ctx.fillStyle = "#bde7ff";

    for (let wx = b.x + 15; wx < b.x + b.w - 10; wx += 28) {
      for (let wy = b.y + 35; wy < b.y + b.h - 10; wy += 30) {
        ctx.fillRect(wx, wy, 12, 14);
      }
    }
  }
}

function drawCoins() {

  for (const c of coinList) {

    if (c.collected) continue;

    ctx.beginPath();
    ctx.arc(c.x, c.y, 9, 0, Math.PI * 2);

    ctx.fillStyle = "#ffd700";
    ctx.fill();

    ctx.strokeStyle = "#fff";
    ctx.stroke();
  }
}

function drawMission() {

  if (mission.complete) return;

  ctx.beginPath();
  ctx.arc(
    mission.x,
    mission.y,
    mission.radius,
    0,
    Math.PI * 2
  );

  ctx.fillStyle = "rgba(255,220,0,.3)";
  ctx.fill();

  ctx.strokeStyle = "#ffe000";
  ctx.lineWidth = 4;
  ctx.stroke();

  ctx.fillStyle = "#fff";
  ctx.font = "bold 18px Arial";
  ctx.fillText(
    "MISSION",
    mission.x - 38,
    mission.y + 5
  );
}

function drawCar() {

  ctx.save();

  ctx.translate(car.x, car.y);

  ctx.fillStyle = "#d92c35";
  ctx.fillRect(
    -car.width / 2,
    -car.height / 2,
    car.width,
    car.height
  );

  ctx.fillStyle = "#9ed8ef";
  ctx.fillRect(-15, -12, 28, 12);

  ctx.fillStyle = "#111";

  ctx.beginPath();
  ctx.arc(-20, 17, 8, 0, Math.PI * 2);
  ctx.fill();

  ctx.beginPath();
  ctx.arc(20, 17, 8, 0, Math.PI * 2);
  ctx.fill();

  ctx.restore();
}

function drawPlayer() {

  if (player.inCar) return;

  ctx.beginPath();
  ctx.arc(player.x, player.y, player.size, 0, Math.PI * 2);

  ctx.fillStyle = "#3d72ff";
  ctx.fill();

  ctx.strokeStyle = "#fff";
  ctx.lineWidth = 3;
  ctx.stroke();

  ctx.fillStyle = "#fff";
  ctx.beginPath();
  ctx.arc(player.x - 6, player.y - 4, 3, 0, Math.PI * 2);
  ctx.arc(player.x + 6, player.y - 4, 3, 0, Math.PI * 2);
  ctx.fill();
}

function distance(a, b) {

  return Math.hypot(
    a.x - b.x,
    a.y - b.y
  );
}

function toggleCar() {

  if (player.inCar) {

    player.inCar = false;

    player.x = car.x + 65;
    player.y = car.y;

    document.getElementById("carStatus").textContent = "No";

    return;
  }

  if (distance(player, car) < 80) {

    player.inCar = true;

    document.getElementById("carStatus").textContent = "Yes";
  }
}

function movePlayer() {

  let speed = player.inCar ? car.speed : player.speed;

  let dx = 0;
  let dy = 0;

  if (keys["w"] || keys["arrowup"]) dy -= speed;
  if (keys["s"] || keys["arrowdown"]) dy += speed;
  if (keys["a"] || keys["arrowleft"]) dx -= speed;
  if (keys["d"] || keys["arrowright"]) dx += speed;

  if (dx !== 0 && dy !== 0) {

    dx *= 0.707;
    dy *= 0.707;
  }

  if (player.inCar) {

    car.x += dx;
    car.y += dy;

    player.x = car.x;
    player.y = car.y;

  } else {

    player.x += dx;
    player.y += dy;
  }

  player.x = Math.max(20, Math.min(world.width - 20, player.x));
  player.y = Math.max(20, Math.min(world.height - 20, player.y));

  car.x = Math.max(30, Math.min(world.width - 30, car.x));
  car.y = Math.max(30, Math.min(world.height - 30, car.y));
}

function collectCoins() {

  for (const c of coinList) {

    if (c.collected) continue;

    if (distance(player, c) < 30) {

      c.collected = true;
      coins++;

      document.getElementById("coins").textContent = coins;
    }
  }
}

function checkMission() {

  if (mission.complete) return;

  if (distance(player, mission) < 60) {

    mission.complete = true;

    document.getElementById("mission").textContent =
      "Mission complete! 🎉";

    showMessage("MISSION COMPLETE!");

    setTimeout(() => {

      document.getElementById("message").style.display = "none";

    }, 1800);
  }
}

function showMessage(text) {

  const msg = document.getElementById("message");

  msg.textContent = text;
  msg.style.display = "block";
}

function camera() {

  let camX =
    player.x - canvas.width / 2;

  let camY =
    player.y - canvas.height / 2;

  camX = Math.max(
    0,
    Math.min(world.width - canvas.width, camX)
  );

  camY = Math.max(
    0,
    Math.min(world.height - canvas.height, camY)
  );

  return { x: camX, y: camY };
}

function draw() {

  const cam = camera();

  ctx.clearRect(
    0,
    0,
    canvas.width,
    canvas.height
  );

  ctx.save();

  ctx.translate(-cam.x, -cam.y);

  ctx.fillStyle = "#5d8f4d";
  ctx.fillRect(
    0,
    0,
    world.width,
    world.height
  );

  drawRoads();
  drawBuildings();
  drawCoins();
  drawMission();

  drawCar();
  drawPlayer();

  ctx.restore();
}

function gameLoop() {

  movePlayer();
  collectCoins();
  checkMission();
  draw();

  requestAnimationFrame(gameLoop);
}

gameLoop();
</script>

</body>
</html>
