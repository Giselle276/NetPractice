# NetPractice

<p data-start="0" data-end="294">Este proyecto te ense&ntilde;a <strong data-start="163" data-end="204">los fundamentos de redes (networking)</strong> a trav&eacute;s de ejercicios pr&aacute;cticos de configuraci&oacute;n de IPs, m&aacute;scaras de subred y routing.</p>
<h2 data-start="301" data-end="330">🧠 Objetivo de NetPractice</h2>
<p data-start="331" data-end="432">El objetivo es entender <strong data-start="355" data-end="403">c&oacute;mo las m&aacute;quinas se comunican en una red IP</strong>, configurando correctamente:</p>
<ul data-start="433" data-end="518">
<li data-start="433" data-end="449">
<p data-start="435" data-end="449">Direcciones IP</p>
</li>
<li data-start="450" data-end="470">
<p data-start="452" data-end="470">M&aacute;scaras de subred</p>
</li>
<li data-start="471" data-end="500">
<p data-start="473" data-end="500">Puertas de enlace (gateway)</p>
</li>
<li data-start="501" data-end="518">
<p data-start="503" data-end="518">Rutas (routing)</p>
</li>
</ul>
<p data-start="520" data-end="624">Tu meta: conseguir que <strong data-start="543" data-end="593">todas las m&aacute;quinas puedan comunicarse entre s&iacute;</strong>, seg&uacute;n el escenario planteado.</p>

<h2 data-start="631" data-end="660">🧩 Conceptos Fundamentales</h2>
<h3 data-start="662" data-end="685">1. <strong data-start="669" data-end="685">Direcci&oacute;n IP</strong></h3>
<p data-start="686" data-end="790">Una IP identifica a un dispositivo dentro de una red.<br data-start="739" data-end="742" /> Formato: <code data-start="751" data-end="760">A.B.C.D</code> (por ejemplo, <code data-start="775" data-end="789">192.168.1.10</code>)</p>
<p data-start="792" data-end="825">Las IPs se dividen en dos partes:</p>
<ul data-start="826" data-end="930">
<li data-start="826" data-end="873">
<p data-start="828" data-end="873"><strong data-start="828" data-end="835">Red</strong>: identifica el grupo de dispositivos.</p>
</li>
<li data-start="874" data-end="930">
<p data-start="876" data-end="930"><strong data-start="876" data-end="884">Host</strong>: identifica el dispositivo dentro de esa red.</p>
</li>
</ul>
<p><strong>Ejemplo:</strong><br data-start="942" data-end="945" /> IP: <code data-start="951" data-end="965">192.168.1.10</code><br data-start="965" data-end="968" /> M&aacute;scara: <code data-start="979" data-end="994">255.255.255.0</code><br data-start="994" data-end="997" /> &rarr; Red: <code data-start="1006" data-end="1019">192.168.1.0</code><br data-start="1019" data-end="1022" /> &rarr; Host: <code data-start="1032" data-end="1036">10</code></p>

<h3 data-start="1043" data-end="1071">2. <strong data-start="1050" data-end="1071">M&aacute;scara de Subred</strong></h3>
<p data-start="1072" data-end="1130">Define cu&aacute;ntos bits pertenecen a la red y cu&aacute;ntos al host.</p>
<div class="_tableContainer_1rjym_1">
<div class="group _tableWrapper_1rjym_13 flex w-fit flex-col-reverse" tabindex="-1">
<table class="w-fit min-w-(--thread-content-width)" data-start="1132" data-end="1374">
<thead data-start="1132" data-end="1190">
<tr data-start="1132" data-end="1190">
<th data-start="1132" data-end="1150" data-col-size="sm">M&aacute;scara decimal</th>
<th data-start="1150" data-end="1166" data-col-size="sm">Notaci&oacute;n CIDR</th>
<th data-start="1166" data-end="1190" data-col-size="sm">N&ordm; hosts disponibles</th>
</tr>
</thead>
<tbody data-start="1251" data-end="1374">
<tr data-start="1251" data-end="1280">
<td data-start="1251" data-end="1267" data-col-size="sm">255.255.255.0</td>
<td data-start="1267" data-end="1273" data-col-size="sm">/24</td>
<td data-start="1273" data-end="1280" data-col-size="sm">254</td>
</tr>
<tr data-start="1281" data-end="1312">
<td data-start="1281" data-end="1299" data-col-size="sm">255.255.255.128</td>
<td data-start="1299" data-end="1305" data-col-size="sm">/25</td>
<td data-start="1305" data-end="1312" data-col-size="sm">126</td>
</tr>
<tr data-start="1313" data-end="1343">
<td data-start="1313" data-end="1331" data-col-size="sm">255.255.255.192</td>
<td data-start="1331" data-end="1337" data-col-size="sm">/26</td>
<td data-start="1337" data-end="1343" data-col-size="sm">62</td>
</tr>
<tr data-start="1344" data-end="1374">
<td data-start="1344" data-end="1362" data-col-size="sm">255.255.255.224</td>
<td data-start="1362" data-end="1368" data-col-size="sm">/27</td>
<td data-start="1368" data-end="1374" data-col-size="sm">30</td>
</tr>
</tbody>
</table>
</div>
</div>
<p><strong>Ejemplo:</strong><br data-start="1386" data-end="1389" /> <code data-start="1391" data-end="1407">192.168.1.0/26</code> &rarr; hosts v&aacute;lidos: <code data-start="1425" data-end="1438">192.168.1.1</code> a <code data-start="1441" data-end="1455">192.168.1.62</code></p>

<h3 data-start="1462" data-end="1499">3. <strong data-start="1469" data-end="1499">Puerta de Enlace (Gateway)</strong></h3>
<p data-start="1500" data-end="1634">Es la direcci&oacute;n IP del <strong data-start="1523" data-end="1533">router</strong> que conecta una red con otra.<br data-start="1563" data-end="1566" /> Los dispositivos la usan para enviar paquetes fuera de su red local.</p>
<p><strong>Ejemplo:</strong><br data-start="1646" data-end="1649" /> Si PC1 (192.168.1.2) quiere hablar con PC2 (10.0.0.3),<br data-start="1705" data-end="1708" /> usar&aacute; su <strong data-start="1719" data-end="1744">gateway (192.168.1.1)</strong> para que el router reenv&iacute;e los paquetes.</p>
<h3 data-start="1792" data-end="1810">4. <strong data-start="1799" data-end="1810">Routing</strong></h3>
<p data-start="1811" data-end="1919">Los routers mantienen una <strong data-start="1837" data-end="1855">tabla de rutas</strong> indicando hacia d&oacute;nde enviar los paquetes seg&uacute;n la red destino.</p>

LEVEL 1

<img width="900" height="768" alt="image" src="https://github.com/user-attachments/assets/3185910c-6810-48b3-9a21-139c3400a397" />

LEVEL 2

<img width="900" height="757" alt="image" src="https://github.com/user-attachments/assets/b55c1e3e-b977-4dc9-93b7-5ee5937450ab" />

LEVEL 3

<img width="900" height="121" alt="image" src="https://github.com/user-attachments/assets/06546228-dc38-4d68-80c0-855086462b70" />
<img width="900" height="810" alt="image" src="https://github.com/user-attachments/assets/39b87faa-e524-4e2e-9c3e-123fd09b839b" />

LEVEL 4

<img width="900" height="120" alt="image" src="https://github.com/user-attachments/assets/9531c366-d99d-42fe-96b8-d0665450ca9b" />
<img width="900" height="817" alt="image" src="https://github.com/user-attachments/assets/3dc00892-2268-4db3-b923-e302703694b2" />

LEVEL 5

<img width="900" height="114" alt="image" src="https://github.com/user-attachments/assets/658ef50e-37a8-4e78-a7a8-5d1d8951f717" />
<img width="900" height="813" alt="image" src="https://github.com/user-attachments/assets/3ae0d788-1358-4e92-9083-fdae814ecbcd" />

LEVEL 6

<img width="900" height="84" alt="image" src="https://github.com/user-attachments/assets/79abe0a9-1a46-448f-8c7e-ec5b40d09ff5" />
<img width="900" height="815" alt="image" src="https://github.com/user-attachments/assets/80d9518d-51e6-4dbd-ad30-eb99fd3a4cf2" />

LEVEL 7

<img width="900" height="82" alt="image" src="https://github.com/user-attachments/assets/f6ff248b-a99a-4950-af34-b6a9040c034e" />
<img width="900" height="821" alt="image" src="https://github.com/user-attachments/assets/02b19490-c762-4696-b8c4-97c68e9b027a" />

LEVEL 8

<img width="900" height="122" alt="image" src="https://github.com/user-attachments/assets/ef0130bb-83f4-4f1c-9838-8764a19eb1ae" />
<img width="900" height="893" alt="image" src="https://github.com/user-attachments/assets/65ec3efb-8fb9-462a-8740-99214599d916" />

LEVEL 9

<img width="900" height="137" alt="image" src="https://github.com/user-attachments/assets/2f8ed1bd-9021-45d1-9174-286aeda90658" />
<img width="900" height="944" alt="image" src="https://github.com/user-attachments/assets/b8332d84-a017-472c-b0c3-de86c97417f3" />

<h2 data-start="2846" data-end="2894">📘 Level 10 &ndash; Topolog&iacute;a de Red y Enrutamiento</h2>
<p data-start="2896" data-end="3213">Este ejercicio consiste en analizar y comprender una topolog&iacute;a de red formada por varios routers, hosts y subredes interconectadas. El objetivo es interpretar c&oacute;mo fluye la informaci&oacute;n entre los distintos dispositivos y c&oacute;mo las rutas configuradas permiten que cada red pueda comunicarse con las dem&aacute;s y con Internet.</p>
<h3 data-start="3215" data-end="3248">🔍 &iquest;Qu&eacute; incluye la topolog&iacute;a?</h3>
<ul data-start="3250" data-end="3561">
    <li data-start="3250" data-end="3315">
        <p data-start="3252" data-end="3315">Un enlace a Internet que se conecta al router principal (R1).</p>
    </li>
    <li data-start="3316" data-end="3383">
        <p data-start="3318" data-end="3383">Un switch que distribuye la red interna para los hosts H1 y H2.</p>
    </li>
    <li data-start="3384" data-end="3476">
        <p data-start="3386" data-end="3476">Un segundo router (R2) que administra dos subredes internas donde se encuentran H3 y H4.</p>
    </li>
    <li data-start="3477" data-end="3561">
        <p data-start="3479" data-end="3561">Tablas de rutas en cada router y host para determinar el camino de los paquetes.</p>
    </li>
</ul>

<img width="900" height="164" alt="image" src="https://github.com/user-attachments/assets/b62379e3-8fd3-4018-b21c-7c0f698ee5a0" />
<img width="900" height="938" alt="image" src="https://github.com/user-attachments/assets/1bef5de7-5058-467d-9209-53d7198941e2" />












