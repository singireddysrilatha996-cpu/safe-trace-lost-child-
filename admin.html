/* ================================================================
   SafeTrace — data.js
   ALL data is stored in localStorage so it persists across
   page reloads and navigations within the same browser.

   WHAT IS STORED:
     st_users    → registered users (array)
     st_cases    → missing child reports (array)
     st_sightings→ sighting reports (array)
     st_alerts   → alert feed (array)
     st_session  → currently logged-in user (object)
   ================================================================ */

// ── Seed default data on first-ever visit ───────────────────────
(function seedIfEmpty() {
  if (!localStorage.getItem('st_seeded')) {

    var defaultUsers = [
      { id: 1, name: 'Admin SafeTrace', email: 'admin@safetrace.com',
        password: 'admin1234', role: 'admin',
        phone: '+91 98765 43210', joined: '2025-01-10' },
      { id: 2, name: 'Ravi Kumar', email: 'user@safetrace.com',
        password: 'user123', role: 'parent',
        phone: '+91 90000 12345', joined: '2025-03-15' }
    ];
   

    var defaultCases = [
      { id: 1, fname:'Aarav', lname:'Sharma', age:8, gender:'Male', emoji:'👦',
        desc:'Blue school uniform, short black hair, small scar on left cheek.',
        location:'Jubilee Hills, Hyderabad', date:'2025-03-20', time:'14:30',
        context:'Was playing in the park.',
        reporter:'Sunita Sharma', phone:'+91 98001 11111', relation:'Parent',
        status:'missing', verified:true, createdAt: Date.now() - 7200000 },
      { id: 2, fname:'Meera', lname:'Singh', age:5, gender:'Female', emoji:'👧',
        desc:'Pink frock, pigtails, small red schoolbag.',
        location:'Begumpet Metro Station', date:'2025-03-21', time:'09:15',
        context:'Separated from mother during morning rush.',
        reporter:'Rajesh Singh', phone:'+91 98002 22222', relation:'Parent',
        status:'missing', verified:true, createdAt: Date.now() - 64800000 },
      { id: 3, fname:'Priya', lname:'Reddy', age:6, gender:'Female', emoji:'👧',
        desc:'Green dress, curly hair, dimples on both cheeks.',
        location:'Banjara Hills, Hyderabad', date:'2025-03-18', time:'16:00',
        context:'Returned home safely.',
        reporter:'Anita Reddy', phone:'+91 98003 33333', relation:'Parent',
        status:'found', verified:true, createdAt: Date.now() - 172800000 },
      { id: 4, fname:'Rohan', lname:'Kumar', age:10, gender:'Male', emoji:'👦',
        desc:'School uniform, grey trousers, white shirt.',
        location:'Secunderabad Bus Stand', date:'2025-03-22', time:'07:45',
        context:'Did not return from school.',
        reporter:'Mohan Kumar', phone:'+91 98004 44444', relation:'Parent',
        status:'missing', verified:false, createdAt: Date.now() - 3600000 }
    ];

    var defaultSightings = [
      { id: 1, caseId:1, childName:'Aarav Sharma',
        location:'Near Hitech City Metro', time:'2025-03-22 11:30',
        desc:'Boy in blue near food court.', reporter:'Volunteer Priya',
        phone:'+91 91111 00000', createdAt: Date.now() - 1800000 },
      { id: 2, caseId:4, childName:'Rohan Kumar',
        location:'Banjara Hills Road No.12', time:'2025-03-22 15:00',
        desc:'School-uniform boy near park, seemed lost.', reporter:'Kiran M',
        phone:'+91 92222 11111', createdAt: Date.now() - 3600000 }
    ];

    var defaultAlerts = [
      { id: 1, type:'missing',  name:'Aarav Sharma', desc:'8yr boy missing from Jubilee Hills. Blue school uniform.', time:'2 hrs ago',   area:'Hyderabad', createdAt: Date.now()-7200000 },
      { id: 2, type:'sighting', name:'Rohan Kumar',  desc:'Sighting near Banjara Hills Road No.12 at 3PM.',           time:'1 hr ago',    area:'Hyderabad', createdAt: Date.now()-3600000 },
      { id: 3, type:'found',    name:'Priya Reddy',  desc:'6yr girl returned home safely.',                            time:'2 days ago',  area:'Hyderabad', createdAt: Date.now()-172800000 },
      { id: 4, type:'missing',  name:'Meera Singh',  desc:'5yr girl missing, Begumpet Metro.',                         time:'18 hrs ago',  area:'Hyderabad', createdAt: Date.now()-64800000 }
    ];

    localStorage.setItem('st_users',     JSON.stringify(defaultUsers));
    localStorage.setItem('st_cases',     JSON.stringify(defaultCases));
    localStorage.setItem('st_sightings', JSON.stringify(defaultSightings));
    localStorage.setItem('st_alerts',    JSON.stringify(defaultAlerts));
    localStorage.setItem('st_seeded',    '1');
  }
})();

// ================================================================
//  DATA ACCESS HELPERS
//  These read/write directly to localStorage every call,
//  so changes made on one page are visible on every other page.
// ================================================================

function getUsers()     { return JSON.parse(localStorage.getItem('st_users')     || '[]'); }
function getCases()     { return JSON.parse(localStorage.getItem('st_cases')     || '[]'); }
function getSightings() { return JSON.parse(localStorage.getItem('st_sightings') || '[]'); }
function getAlerts()    { return JSON.parse(localStorage.getItem('st_alerts')    || '[]'); }

function saveUsers(arr)     { localStorage.setItem('st_users',     JSON.stringify(arr)); }
function saveCases(arr)     { localStorage.setItem('st_cases',     JSON.stringify(arr)); }
function saveSightings(arr) { localStorage.setItem('st_sightings', JSON.stringify(arr)); }
function saveAlerts(arr)    { localStorage.setItem('st_alerts',    JSON.stringify(arr)); }

// ── Generate a unique numeric ID ────────────────────────────────
function nextId(arr) {
  if (!arr || !arr.length) return 1;
  return Math.max.apply(null, arr.map(function(x){ return x.id || 0; })) + 1;
}

// ── Time-ago string ─────────────────────────────────────────────
function timeAgo(ts) {
  var diff = Math.floor((Date.now() - ts) / 1000);
  if (diff < 60)   return 'Just now';
  if (diff < 3600) return Math.floor(diff/60) + ' mins ago';
  if (diff < 86400)return Math.floor(diff/3600) + ' hrs ago';
  return Math.floor(diff/86400) + ' days ago';
}

// ================================================================
//  USER REGISTRATION
//  Adds a new user to localStorage and returns it (or error msg).
// ================================================================
function registerUser(fname, lname, email, password, phone, role) {
  var users = getUsers();
  if (users.find(function(u){ return u.email.toLowerCase() === email.toLowerCase(); })) {
    return { error: 'This email is already registered. Please login.' };
  }
  var newUser = {
    id:     nextId(users),
    name:   fname + ' ' + lname,
    email:  email,
    password: password,
    role:   role || 'parent',
    phone:  phone || '',
    joined: new Date().toISOString().split('T')[0]
  };
  users.push(newUser);
  saveUsers(users);
  return { user: newUser };
}

// ================================================================
//  USER LOGIN
//  Returns the user object or null.
// ================================================================
function loginUser(email, password) {
  var users = getUsers();
  for (var i = 0; i < users.length; i++) {
    if (users[i].email.toLowerCase() === email.toLowerCase() &&
        users[i].password === password) {
      return users[i];
    }
  }
  return null;
}

// ================================================================
//  REPORT A MISSING CHILD
// ================================================================
function addCase(data) {
  var cases = getCases();
  var newCase = {
    id:        nextId(cases),
    fname:     data.fname,
    lname:     data.lname,
    age:       parseInt(data.age),
    gender:    data.gender,
    emoji:     data.gender === 'Male' ? '👦' : '👧',
    desc:      data.desc,
    location:  data.location,
    date:      data.date,
    time:      data.time     || '',
    context:   data.context  || '',
    reporter:  data.reporter,
    phone:     data.phone,
    relation:  data.relation || 'Parent',
    email:     data.email    || '',
    status:    'missing',
    verified:  false,
    createdAt: Date.now()
  };
  cases.unshift(newCase);   // newest first
  saveCases(cases);

  // Auto-create an alert
  addAlert({
    type:  'missing',
    name:  newCase.fname + ' ' + newCase.lname,
    desc:  newCase.age + 'yr old ' + newCase.gender.toLowerCase() +
           ' reported missing from ' + newCase.location + '.',
    area:  newCase.location,
    caseId: newCase.id
  });

  return newCase;
}

// ================================================================
//  ADD A SIGHTING
// ================================================================
function addSighting(data) {
  var sightings = getSightings();
  var newS = {
    id:        nextId(sightings),
    caseId:    parseInt(data.caseId),
    childName: data.childName,
    location:  data.location,
    time:      data.time,
    desc:      data.desc,
    reporter:  data.reporter,
    phone:     data.phone,
    createdAt: Date.now()
  };
  sightings.unshift(newS);
  saveSightings(sightings);

  // Auto-create an alert
  addAlert({
    type:  'sighting',
    name:  data.childName,
    desc:  'Sighting reported near ' + data.location + '.',
    area:  data.location,
    caseId: parseInt(data.caseId)
  });

  return newS;
}

// ================================================================
//  ADD AN ALERT
// ================================================================
function addAlert(data) {
  var alerts = getAlerts();
  alerts.unshift({
    id:        nextId(alerts),
    type:      data.type,
    name:      data.name,
    desc:      data.desc,
    area:      data.area || 'Hyderabad',
    caseId:    data.caseId || null,
    createdAt: Date.now(),
    time:      'Just now'
  });
  saveAlerts(alerts);
}

// ================================================================
//  SESSION  —  uses sessionStorage (lives for the browser tab)
// ================================================================
var SESSION_KEY = 'st_session';

function setSession(userObj) {
  try { sessionStorage.setItem(SESSION_KEY, JSON.stringify(userObj)); } catch(e) {}
}
function getSession() {
  try {
    var raw = sessionStorage.getItem(SESSION_KEY);
    return raw ? JSON.parse(raw) : null;
  } catch(e) { return null; }
}
function clearSession() {
  sessionStorage.removeItem(SESSION_KEY);
}

// Redirect to login if not logged in; save return URL
function requireLogin() {
  if (!getSession()) {
    sessionStorage.setItem('st_redirect', window.location.href);
    window.location.href = 'login.html';
    return false;
  }
  return true;
}

// Only admin can access admin page
function requireAdmin() {
  var u = getSession();
  if (!u) {
    sessionStorage.setItem('st_redirect', window.location.href);
    window.location.href = 'login.html';
    return false;
  }
  if (u.role !== 'admin') {
    alert('Admin access only. You are logged in as: ' + u.role);
    window.location.href = 'index.html';
    return false;
  }
  return true;
}

function doLogout() {
  clearSession();
  window.location.href = 'index.html';
}

// ================================================================
//  NAV HELPER  —  call initNav() on each page to show user state
// ================================================================
function initNav() {
  var u       = getSession();
  var guestEl = document.getElementById('navGuest');
  var userEl  = document.getElementById('navUser');
  var greetEl = document.getElementById('navGreet');
  if (!guestEl) return;
  if (u) {
    guestEl.style.display = 'none';
    userEl.style.display  = 'flex';
    if (greetEl) greetEl.textContent = 'Hi, ' + u.name.split(' ')[0] +
      (u.role === 'admin' ? ' 🛡' : '');
  } else {
    guestEl.style.display = 'flex';
    userEl.style.display  = 'none';
  }
}

// ================================================================
//  TOAST  —  call toast('msg', 'success'|'error') on any page
// ================================================================
function toast(msg, type) {
  var el    = document.getElementById('toast');
  var icon  = document.getElementById('toastIcon');
  var msgEl = document.getElementById('toastMsg');
  if (!el) return;
  if (icon)  icon.textContent  = type === 'error' ? '❌' : '✅';
  if (msgEl) msgEl.textContent = msg;
  el.className = 'show ' + (type || 'success');
  clearTimeout(el._t);
  el._t = setTimeout(function(){ el.classList.remove('show'); }, 3600);
}
