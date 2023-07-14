<body>
    <div id="time">
      <div class="circle">
        <div class="dots sec_dot c1" style="--clr: #fff"></div>
        <svg>
          <circle cx="120" cy="120" r="120" id="ss" stroke="#fff"></circle>
        </svg>
      </div>
      <div class="circle">
        <div class="dots min_dot c2" style="--clr: #fff"></div>
        <svg>
          <circle cx="100" cy="100" r="100" id="mm" stroke="#fff"></circle>
        </svg>
      </div>
      <div class="circle">
        <div class="dots hr_dot c3" style="--clr: #fff"></div>
        <svg>
          <circle cx="80" cy="80" r="80" id="hh" stroke="#fff"></circle>
        </svg>
      </div>

      <div class="timeBx">
        <div id="hours" style="--c: fff">00</div>
        <div id="minutes" style="--c: fff">00</div>
        <div id="seconds" style="--c: fff">00</div>
        <div class="ap" style="--c: #fff"><div id="ampm"></div></div>
      </div>
    </div>

    <script src="script.js"></script>

  </body>

setInterval(() => {
let hh = document.getElementById('hh');
let mm = document.getElementById('mm');
let ss = document.getElementById('ss');

let sec_dot = document.querySelector('.sec-dot');
let min_dot = document.querySelector('.min-dot');
let hr_dot = document.querySelector('.hr-dot');

let hours = document.getElementById('hours');
let minutes = document.getElementById('minutes');
let seconds = document.getElementById('seconds');
let ampm = document.getElementById('ampm');

let h = new Date().getHours();
let m = new Date().getMinutes();
let s = new Date().getSeconds();

let am = h >= 12 ? 'PM' : 'AM';

h = h < 10 ? '0' + h : h;
m = m < 10 ? '0' + m : m;
s = s < 10 ? '0' + s : s;

hours.innerHTML = h;
minutes.innerHTML = m;
seconds.innerHTML = s;
ampm.innerHTML = am;

hh.style.strokeDashoffset = 510 - (510 _ (h > 12 ? h - 12 : h)) / 12;
mm.style.strokeDashoffset = 630 - (630 _ m) / 60;
ss.style.strokeDashoffset = 760(760 \* s) / 60;

sec_dot.style.transform = `rotateZ(${s * 6}deg)`;
min_dot.style.transform = `rotateZ(${m * 6}deg)`;
hr_dot.style.transform = `rotateZ(${h * 6}deg)`;
});
