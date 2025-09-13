<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>تطبيق حساب درجات السنة - طلاب الطب</title>
  <style>
    :root{
      --bg:#1f1a17; /* dark brown */
      --card:#2b231f;
      --muted:#c8bfb9;
      --accent:#b08968; /* warm beige */
      --glass: rgba(255,255,255,0.03);
      --success:#2ecc71;
      --danger:#e74c3c;
      --surface:#342a26;
    }
    *{box-sizing:border-box;font-family: "Segoe UI", Tahoma, Arial, sans-serif}
    html,body{height:100%;margin:0}
    body{
      background:linear-gradient(180deg,var(--bg),#120f0d);
      color:var(--muted);
      padding:24px;
      direction:rtl;
    }
    header{display:flex;gap:16px;align-items:center;justify-content:space-between}
    h1{margin:0;font-size:20px;color:var(--accent)}
    .container{display:grid;grid-template-columns:1fr 360px;gap:20px;margin-top:18px}
    .card{background:var(--card);border-radius:12px;padding:16px;box-shadow:0 6px 18px rgba(0,0,0,0.5)}
    .subject{border-radius:10px;padding:12px;margin-bottom:12px;background:var(--glass);}
    label{display:block;font-size:13px;margin-bottom:6px;color:var(--muted)}
    input[type=number]{width:100%;padding:10px;border-radius:8px;background:#1b1614;border:1px solid rgba(255,255,255,0.04);color:var(--muted)}
    .row{display:flex;gap:8px}
    .row > div{flex:1}
    .subject-title{display:flex;align-items:center;gap:8px;margin-bottom:8px}
    .color-bullet{width:14px;height:14px;border-radius:4px}
    .result{margin-top:10px;padding:10px;border-radius:8px;background:linear-gradient(180deg,rgba(255,255,255,0.02),transparent)}
    .grade{font-weight:700;font-size:16px}
    .controls{display:flex;gap:8px;flex-wrap:wrap}
    button{background:var(--accent);color:#111;padding:8px 12px;border-radius:10px;border:0;cursor:pointer}
    .ghost{background:transparent;border:1px solid rgba(255,255,255,0.05);color:var(--muted)}
    .small{font-size:12px;padding:6px 8px}
    .overall{position:sticky;top:20px}
    .progress{height:10px;background:#241b18;border-radius:999px;overflow:hidden}
    .progress > i{display:block;height:100%;background:var(--accent)}
    footer{margin-top:18px;color:#9b9189;font-size:13px}
    /* responsive */
    @media (max-width:900px){.container{grid-template-columns:1fr}}
  </style>
</head>
<body>
  <header>
    <h1>🧾 تطبيق حساب درجات السنة - كلية الطب</h1>
    <div>
      <button id="saveAll">💾 حفظ تلقائي</button>
      <button id="clearAll" class="ghost">🧹 مسح الحفظ</button>
    </div>
  </header>

  <div class="container">
    <main class="card">
      <p>هذا التطبيق يحسب النتيجة النهائية لكل مادة بناءً على أقسام الدرجات التي طلبتها. كل حقل له حد أقصى محدد — ضع درجاتك الفعلية داخل الحقول ثم اضغط <strong>احسب</strong>.</p>

      <!-- Subjects list -->
      <div id="subjects"></div>

      <div style="display:flex;gap:8px;align-items:center;margin-top:10px">
        <button id="compute">حساب النتائج</button>
        <button id="computeAll" class="ghost">حساب جميع المواد</button>
        <button id="reset" class="ghost small">إعادة تعيين الحقول</button>
      </div>

    </main>

    <aside class="card overall">
      <h3>الملخص العام</h3>
      <div style="margin-top:8px">
        <div style="display:flex;justify-content:space-between"><span>المواد المحسوبة:</span><span id="count">0</span></div>
        <div style="display:flex;justify-content:space-between"><span>المعدل العام:</span><span id="avg">0%</span></div>
        <div style="margin-top:8px" class="progress"><i id="avgBar" style="width:0%"></i></div>
        <div style="margin-top:10px;display:flex;gap:8px;flex-wrap:wrap">
          <button id="export" class="small ghost">تصدير كـ JSON</button>
          <button id="import" class="small ghost">استيراد من JSON</button>
        </div>
      </div>

      <hr style="margin:12px 0;border:none;border-top:1px solid rgba(255,255,255,0.04)">
      <div id="legend">
        <div style="display:flex;gap:8px;align-items:center"><span style="width:12px;height:12px;background:var(--success);display:inline-block;border-radius:3px"></span><small>نجح</small></div>
        <div style="display:flex;gap:8px;align-items:center;margin-top:6px"><span style="width:12px;height:12px;background:var(--danger);display:inline-block;border-radius:3px"></span><small>راسب</small></div>
      </div>
    </aside>
  </div>

  <footer class="card">نُشِر بواسطة: مولد سريع • انسخ الملف واحفظه باسم <strong>index.html</strong> ثم افتحه في متصفحك. 💡 البيانات تُحفظ محليًا في المتصفح.</footer>

  <script>
    // تعريف المواد ومقاسات الأقسام (بالترتيب الذي طلبه المستخدم)
    const SUBJECTS = [
      {
        id:'anat', name:'التشريح (Anatomy)', color:'#6b4b3a', parts:[
          {k:'practical_mid',label:'العملي - مد (Max 10)',max:10},
          {k:'theory_mid',label:'النظري - مد (Max 20)',max:20},
          {k:'practical_final',label:'العملي - فاينل (Max 20)',max:20},
          {k:'theory_final',label:'النظري - فاينل (Max 50)',max:50}
        ]
      },
      {
        id:'phys', name:'الفسلجة (Physiology)', color:'#5f6b52', parts:[
          {k:'practical_mid',label:'العملي - مد (Max 10)',max:10},
          {k:'theory_mid',label:'النظري - مد (Max 25)',max:25},
          {k:'theory_final',label:'النظري - فاينل (Max 50)',max:50},
          {k:'practical_final',label:'العملي - فاينل (Max 10) (6 أورال،4 سبوتات)',max:10},
          {k:'seminars',label:'سمنرات وكوزات (Max 5) (سمنر 2، كوزات 3)',max:5}
        ]
      },
      {
        id:'chem', name:'الكيمياء (Chemistry)', color:'#6e5a3b', parts:[
          {k:'practical_mid',label:'العملي - مد (Max 13)',max:13},
          {k:'theory_mid',label:'النظري - مد (Max 20)',max:20},
          {k:'practical_final',label:'العملي - فاينل (Max 13)',max:13},
          {k:'theory_final',label:'النظري - فاينل (Max 50)',max:50},
          {k:'seminar',label:'سمنر أو بوستر (Max 4)',max:4}
        ]
      },
      {
        id:'histo', name:'الأنسجة (Histology)', color:'#4b5661', parts:[
          {k:'practical_mid',label:'العملي - مد (Max 10)',max:10},
          {k:'theory_mid',label:'النظري - مد (Max 20)',max:20},
          {k:'practical_final',label:'العملي - فاينل (Max 13)',max:13},
          {k:'theory_final',label:'النظري - فاينل (Max 55)',max:55},
          {k:'lookbook',label:'لوك بوك (Max 2)',max:2}
        ]
      },
      {
        id:'embr', name:'الأجنة (Embryology)', color:'#764f8e', parts:[
          {k:'mid',label:'المد (Max 30)',max:30},
          {k:'final',label:'الفاينل (Max 70)',max:70}
        ]
      },
      {
        id:'eth', name:'أخلاقيات الطب (Ethics)', color:'#8a5d48', parts:[
          {k:'mid',label:'المد (Max 30)',max:30},
          {k:'final',label:'الفاينل (Max 70)',max:70}
        ]
      },
      {
        id:'crime', name:'جرائم حزب البعث', color:'#3d6b6b', parts:[
          {k:'mid',label:'المد (Max 40)',max:40},
          {k:'final',label:'الفاينل (Max 60)',max:60}
        ]
      }
    ];

    // عناصر DOM
    const subjectsDiv = document.getElementById('subjects');
    const countEl = document.getElementById('count');
    const avgEl = document.getElementById('avg');
    const avgBar = document.getElementById('avgBar');

    // إنشاء واجهة للمادة
    SUBJECTS.forEach(s => {
      const box = document.createElement('div');
      box.className = 'subject';
      box.id = 'box-'+s.id;

      // header
      const title = document.createElement('div'); title.className='subject-title';
      const bullet = document.createElement('span'); bullet.className='color-bullet'; bullet.style.background=s.color;
      const h = document.createElement('div'); h.innerHTML = `<strong style="color:${s.color}">${s.name}</strong>`;
      title.appendChild(bullet); title.appendChild(h);
      box.appendChild(title);

      // inputs
      const list = document.createElement('div');
      s.parts.forEach(p => {
        const field = document.createElement('div');
        const label = document.createElement('label'); label.innerText = p.label;
        const input = document.createElement('input'); input.type='number'; input.min=0; input.max=p.max; input.step='0.01'; input.dataset.max=p.max; input.id = s.id+'_'+p.k;
        // load saved value
        const saved = localStorage.getItem(input.id);
        if(saved) input.value = saved;
        field.appendChild(label); field.appendChild(input);
        list.appendChild(field);
      });
      box.appendChild(list);

      // controls and result area
      const res = document.createElement('div'); res.className='result'; res.id='res-'+s.id;
      res.innerHTML = `<div>النقاط: <span class="score">-</span> / 100</div><div>النسبة: <span class="percent">-</span>%</div><div class="grade">تقدير: <span class="gradeText">-</span></div>`;
      box.appendChild(res);

      subjectsDiv.appendChild(box);
    });

    // helpers
    function computeSubject(s){
      const box = document.getElementById('box-'+s.id);
      const resBox = document.getElementById('res-'+s.id);
      let total=0; let maxTotal=0; let anyInput=false;
      s.parts.forEach(p=>{
        const el = document.getElementById(s.id+'_'+p.k);
        const val = parseFloat(el.value);
        if(!isNaN(val)){
          anyInput=true;
          total += Math.max(0,Math.min(val, p.max));
        }
        maxTotal += p.max;
      });
      // Normalize to 100
      const percent = maxTotal>0 ? (total/maxTotal)*100 : 0;
      const score = (percent).toFixed(2);

      // grade mapping
      let gradeText='راسب';
      if(percent>=85) gradeText='ممتاز';
      else if(percent>=75) gradeText='جيد جدًا';
      else if(percent>=65) gradeText='جيد';
      else if(percent>=50) gradeText='مقبول';
      else gradeText='راسب';

      // color
      const passed = percent>=50;
      resBox.querySelector('.score').innerText = ( (total/maxTotal)*100 ).toFixed(2);
      resBox.querySelector('.percent').innerText = percent.toFixed(2);
      resBox.querySelector('.gradeText').innerText = gradeText;
      resBox.style.borderLeft = `6px solid ${passed? 'var(--success)' : 'var(--danger)'} `;

      return {id:s.id, name:s.name, percent: Number(percent.toFixed(2)), points: Number(((total/maxTotal)*100).toFixed(2)), passed}
    }

    // حساب كل المواد
    function computeAll(){
      const results = [];
      SUBJECTS.forEach(s => {
        // save inputs
        s.parts.forEach(p=>{
          const el = document.getElementById(s.id+'_'+p.k);
          if(el && el.value!=='') localStorage.setItem(el.id, el.value);
        });
        results.push(computeSubject(s));
      });

      const counted = results.filter(r=>!isNaN(r.percent));
      const avg = counted.length? (counted.reduce((a,b)=>a+b.percent,0)/counted.length):0;
      countEl.innerText = counted.length;
      avgEl.innerText = avg.toFixed(2)+'%';
      avgBar.style.width = Math.max(0,Math.min(100,avg))+'%';

      // show toast small
      return results;
    }

    // load saved and compute once at start
    window.addEventListener('load',()=>{
      computeAll();
    });

    // buttons
    document.getElementById('compute').addEventListener('click', ()=>{
      const sId = SUBJECTS[0].id; // default behavior: compute all (user wanted compute per subject but also all)
      computeAll();
      alert('تم حساب النتائج. مرر للأسفل لرؤية التقديرات لكل مادة.');
    });

    document.getElementById('computeAll').addEventListener('click', ()=>{
      computeAll();
    });

    document.getElementById('reset').addEventListener('click', ()=>{
      if(!confirm('هل تريد إعادة تعيين كل الحقول (سيبقى الحفظ محليًا حتى تمسحه)؟')) return;
      SUBJECTS.forEach(s=>{
        s.parts.forEach(p=>{
          const el = document.getElementById(s.id+'_'+p.k); if(el) el.value='';
        });
        const resBox = document.getElementById('res-'+s.id);
        resBox.querySelector('.score').innerText='-';
        resBox.querySelector('.percent').innerText='-';
        resBox.querySelector('.gradeText').innerText='-';
      });
      countEl.innerText='0'; avgEl.innerText='0%'; avgBar.style.width='0%';
    });

    // save button
    document.getElementById('saveAll').addEventListener('click', ()=>{
      SUBJECTS.forEach(s=>{
        s.parts.forEach(p=>{
          const el = document.getElementById(s.id+'_'+p.k); if(el && el.value!=='') localStorage.setItem(el.id, el.value);
        });
      });
      alert('تم حفظ القيم محليًا في المتصفح');
    });

    document.getElementById('clearAll').addEventListener('click', ()=>{
      if(!confirm('هل تود مسح جميع البيانات المحفوظة محليًا؟')) return;
      SUBJECTS.forEach(s=>{
        s.parts.forEach(p=>{
          localStorage.removeItem(s.id+'_'+p.k);
          const el = document.getElementById(s.id+'_'+p.k); if(el) el.value='';
        });
        const resBox = document.getElementById('res-'+s.id);
        resBox.querySelector('.score').innerText='-';
        resBox.querySelector('.percent').innerText='-';
        resBox.querySelector('.gradeText').innerText='-';
      });
      countEl.innerText='0'; avgEl.innerText='0%'; avgBar.style.width='0%';
      alert('تم المسح');
    });

    // export/import
    document.getElementById('export').addEventListener('click', ()=>{
      const data={};
      SUBJECTS.forEach(s=>{
        data[s.id]={};
        s.parts.forEach(p=>{
          const el = document.getElementById(s.id+'_'+p.k);
          data[s.id][p.k] = el && el.value? el.value : '';
        });
      });
      const text = JSON.stringify(data, null, 2);
      prompt('انسخ JSON التالي وهو نسخة من بياناتك (يمكن لصقه لاحقًا في زر استيراد):', text);
    });

    document.getElementById('import').addEventListener('click', ()=>{
      const raw = prompt('ألصق هنا JSON الذي نسخته سابقًا:');
      if(!raw) return;
      try{
        const data = JSON.parse(raw);
        SUBJECTS.forEach(s=>{
          s.parts.forEach(p=>{
            const el = document.getElementById(s.id+'_'+p.k);
            if(el && data[s.id] && data[s.id][p.k] !== undefined){ el.value = data[s.id][p.k]; localStorage.setItem(el.id, el.value);}          
          });
        });
        computeAll();
        alert('تم استيراد البيانات وحسابها');
      }catch(e){ alert('ملف JSON غير صالح'); }
    });

    // compute automatically when inputs change
    SUBJECTS.forEach(s=>{
      s.parts.forEach(p=>{
        const el = document.getElementById(s.id+'_'+p.k);
        el.addEventListener('input', ()=>{
          // clamp
          const max = parseFloat(el.dataset.max||100);
          if(el.value==='') { localStorage.removeItem(el.id); }
          else { if(Number(el.value) > max) el.value = max; if(Number(el.value) < 0) el.value = 0; localStorage.setItem(el.id, el.value); }
          computeAll();
        });
      });
    });
  </script>
</body>
</html>
