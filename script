document.addEventListener('DOMContentLoaded', function () {
  const form = document.getElementById('formulaire');
  if (form) {
    form.addEventListener('submit', function (e) {
      e.preventDefault();
      const prod = document.getElementById('production').value;
      const source = document.getElementById('source').value;
      const distance = parseFloat(document.getElementById('distance').value);

      let emission = 0;

      // Production
      if (prod === "electrolyse") emission += 50;
      if (prod === "vaporeformage") emission += 900;

      // Électricité
      if (source === "nucleaire") emission += 10;
      if (source === "charbon") emission += 900;
      if (source === "solaire") emission += 45;

      // Transport
      emission += (distance * 0.052); // 52g CO₂/t.km ≈ 0.052 g/km pour 1 kg

      // Sauvegarde et redirection
      localStorage.setItem('empreinte', emission.toFixed(2));
      window.location.href = "resultat.html";
    });
  }
});
