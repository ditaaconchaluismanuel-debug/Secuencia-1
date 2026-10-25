[secuencia1_laboratorio_del_azar.html](https://github.com/user-attachments/files/33928447/secuencia1_laboratorio_del_azar.html)
<!DOCTYPE html>
<html lang="es">
<head>
<meta charset="UTF-8"><meta name="viewport" content="width=device-width, initial-scale=1">
<title>Laboratorio del azar | Secuencia 1</title>
<style>
:root{--ink:#17243b;--muted:#5c6b82;--blue:#2457a7;--cyan:#dff4f5;--paper:#f5f8fc;--line:#dce4ef;--gold:#f5c65b}
*{box-sizing:border-box}body{margin:0;font:16px/1.55 system-ui,Segoe UI,Arial;color:var(--ink);background:var(--paper)}
header{background:linear-gradient(120deg,#163a70,#287d9b);color:white;padding:34px 20px}
.wrap{max-width:1050px;margin:auto;padding:0 18px}header h1{font-size:clamp(2rem,5vw,3.2rem);line-height:1.1;margin:8px 0}header p{max-width:720px;color:#e8f5ff}
.tag{display:inline-block;border:1px solid #ffffff80;border-radius:30px;padding:4px 12px;font-size:.85rem}
nav{display:flex;gap:8px;flex-wrap:wrap;margin:18px 0}nav a{color:white;text-decoration:none;border:1px solid #ffffff70;border-radius:20px;padding:7px 12px;font-size:.9rem}
main{padding:24px 0 50px}.card{background:white;border:1px solid var(--line);border-radius:16px;padding:22px;margin:16px 0;box-shadow:0 5px 18px #17345a0a}
h2{margin-top:0;color:#1e4d88}h3{color:#2457a7;margin-bottom:8px}.grid{display:grid;grid-template-columns:repeat(auto-fit,minmax(240px,1fr));gap:14px}
.note{background:#eef6ff;border-left:4px solid var(--blue);padding:12px 15px;border-radius:8px}.controls{display:flex;gap:10px;flex-wrap:wrap;align-items:center}
button,select,input{font:inherit;border-radius:9px;border:1px solid #b8c8dc;padding:9px 12px}button{background:var(--blue);color:white;border:0;cursor:pointer;font-weight:650}button.secondary{background:#eaf0f8;color:var(--ink)}button:hover{filter:brightness(1.08)}
.stat{background:#f1f6fc;padding:14px;border-radius:12px;text-align:center}.stat strong{font-size:1.8rem;display:block;color:#1f579d}
table{width:100%;border-collapse:collapse;margin-top:10px}td,th{padding:9px;border-bottom:1px solid var(--line);text-align:left}
.bar{height:18px;background:#e6edf6;border-radius:20px;overflow:hidden}.bar span{display:block;height:100%;background:#2d8a9e;width:0}
.question{padding:14px;background:#f7f9fc;border-radius:12px;margin:12px 0}.feedback{font-weight:650;margin-top:8px}
footer{color:var(--muted);padding:22px 0;text-align:center;font-size:.9rem}
</style></head>
<body>
<header><div class="wrap"><span class="tag">Matemáticas · Grado 10.º · Secuencia 1</span>
<h1>Laboratorio del azar</h1><p>Explora los experimentos aleatorios, el espacio muestral y la probabilidad. Predice, experimenta, registra y compara.</p>
<nav><a href="#conceptos">Conceptos</a><a href="#simulador">Simulador</a><a href="#reto">Reto</a><a href="#evaluacion">Comprueba lo aprendido</a></nav></div></header>
<main class="wrap">
<section class="card" id="conceptos"><h2>1. ¿Qué vamos a aprender?</h2>
<p>Al finalizar podrás reconocer experimentos aleatorios, describir sus resultados posibles, identificar eventos y calcular probabilidades sencillas. También compararás la probabilidad teórica con la frecuencia experimental.</p>
<div class="grid">
<div class="note"><b>Experimento aleatorio</b><br>Su resultado no se conoce con certeza antes de realizarlo. Ejemplo: lanzar una moneda.</div>
<div class="note"><b>Espacio muestral</b><br>Conjunto de todos los resultados posibles. En un dado: {1, 2, 3, 4, 5, 6}.</div>
<div class="note"><b>Evento</b><br>Resultado o conjunto de resultados que nos interesa. Ejemplo: obtener un número par.</div>
<div class="note"><b>Probabilidad clásica</b><br>Si los resultados son igualmente posibles: P(A) = casos favorables / casos posibles.</div></div>
<h3>Ejemplo guiado</h3><p>Al lanzar un dado, el evento “obtener un número par” tiene tres casos favorables: 2, 4 y 6. Por tanto, P(par) = 3/6 = 1/2 = 0,5 = 50 %.</p>
<p class="note"><b>Recuerda:</b> una probabilidad está entre 0 y 1. El 0 representa un evento imposible y el 1 un evento seguro.</p></section>

<section class="card" id="simulador"><h2>2. Simulador: lanzamiento de una moneda</h2>
<p>Antes de experimentar, predice: ¿qué porcentaje de caras esperas obtener? En muchos lanzamientos, la frecuencia relativa suele acercarse al 50 %, aunque no tiene que ser exactamente 50 %.</p>
<div class="controls"><label for="n">Número de lanzamientos:</label><select id="n"><option>10</option><option selected>50</option><option>100</option><option>500</option><option>1000</option></select><button onclick="toss()">Realizar experimento</button><button class="secondary" onclick="resetSim()">Reiniciar</button></div>
<div class="grid" style="margin-top:16px"><div class="stat"><strong id="heads">0</strong>Caras</div><div class="stat"><strong id="tails">0</strong>Sellos</div><div class="stat"><strong id="pct">0 %</strong>Frecuencia relativa de caras</div></div>
<h3>Representación de resultados</h3><p>Caras</p><div class="bar"><span id="headbar"></span></div><p>Sellos</p><div class="bar"><span id="tailbar"></span></div>
<p id="summary" class="note" aria-live="polite">Realiza el experimento para observar los resultados.</p>
</section>
<section class="card" id="reto"><h2>3. Actividad de exploración</h2>
<ol><li>Escribe tu predicción antes de lanzar la moneda.</li><li>Realiza el experimento con 50 lanzamientos y registra caras y sellos.</li><li>Calcula la frecuencia relativa de cada resultado: frecuencia / número total de lanzamientos.</li><li>Repite con 500 o 1.000 lanzamientos.</li><li>Compara los porcentajes y explica qué observas.</li></ol>
<h3>Preguntas para discutir</h3><ul><li>¿Los resultados fueron exactamente iguales?</li><li>¿Por qué la cantidad de caras y sellos puede ser diferente?</li><li>¿Qué ocurre con la frecuencia relativa cuando aumenta el número de lanzamientos?</li><li>¿En qué se diferencian la probabilidad teórica y la experimental?</li></ul>
<label for="reflection"><b>Escribe tu conclusión:</b></label><textarea id="reflection" rows="4" style="width:100%;margin-top:8px" placeholder="En mi experimento observé que..."></textarea>
<button class="secondary" onclick="copyReflection()">Copiar conclusión</button><span id="copymsg" aria-live="polite"></span>
</section>
<section class="card" id="evaluacion"><h2>4. Comprueba lo aprendido</h2>
<div class="question"><b>1. ¿Cuál es el espacio muestral al lanzar un dado de seis caras?</b><br><label><input type="radio" name="q1" value="a"> {1, 2, 3}</label><br><label><input type="radio" name="q1" value="b"> {1, 2, 3, 4, 5, 6}</label><br><label><input type="radio" name="q1" value="c"> {2, 4, 6}</label></div>
<div class="question"><b>2. ¿Cuál es la probabilidad de obtener un 5 al lanzar un dado equilibrado?</b><br><label><input type="radio" name="q2" value="a"> 1/6</label><br><label><input type="radio" name="q2" value="b"> 1/2</label><br><label><input type="radio" name="q2" value="c"> 5/6</label></div>
<div class="question"><b>3. Obtener un 8 al lanzar un dado de seis caras es un evento:</b><br><label><input type="radio" name="q3" value="a"> Seguro</label><br><label><input type="radio" name="q3" value="b"> Imposible</label><br><label><input type="radio" name="q3" value="c"> Probable</label></div>
<button onclick="grade()">Calificar respuestas</button><p class="feedback" id="result" aria-live="polite"></p>
</section>
<footer>Recurso didáctico interactivo · Probabilidad · Grado décimo</footer></main>
<script>
function toss(){let n=+document.getElementById('n').value,h=0;for(let i=0;i<n;i++)if(Math.random()<.5)h++;let t=n-h,p=h/n*100;
document.getElementById('heads').textContent=h;document.getElementById('tails').textContent=t;document.getElementById('pct').textContent=p.toFixed(1)+' %';
document.getElementById('headbar').style.width=p+'%';document.getElementById('tailbar').style.width=(100-p)+'%';
document.getElementById('summary').textContent=`En ${n} lanzamientos obtuviste ${h} caras y ${t} sellos. La frecuencia relativa de caras fue ${p.toFixed(1)} %. La probabilidad teórica de cara es 50 %.`;
}
function resetSim(){['heads','tails'].forEach(id=>document.getElementById(id).textContent='0');document.getElementById('pct').textContent='0 %';['headbar','tailbar'].forEach(id=>document.getElementById(id).style.width='0');document.getElementById('summary').textContent='Realiza el experimento para observar los resultados.'}
function grade(){let a={q1:'b',q2:'a',q3:'b'},s=0;for(let k in a){let x=document.querySelector(`input[name=${k}]:checked`);if(x&&x.value===a[k])s++}document.getElementById('result').textContent=`Obtuviste ${s} de 3 respuestas correctas. ${s===3?'¡Excelente!': 'Revisa los conceptos y vuelve a intentarlo.'}`}
function copyReflection(){let t=document.getElementById('reflection');t.select();try{document.execCommand('copy');document.getElementById('copymsg').textContent=' Conclusión copiada.'}catch(e){document.getElementById('copymsg').textContent=' Selecciona y copia el texto.'}}
</script></body></html>
