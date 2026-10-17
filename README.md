# pllp-chili-cookoff
[2026_pllp_chili_cookoff_app (3).html](https://github.com/user-attachments/files/33605757/2026_pllp_chili_cookoff_app.3.html)
<!DOCTYPE html>
<html lang="en" class="h-full bg-slate-950 text-emerald-100 selection:bg-amber-600 selection:text-white">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>2026 PLLP Chili Cookoff</title>
  <!-- Tailwind CSS CDN -->
  <script src="https://cdn.tailwindcss.com"></script>
  <!-- Lucide Icons -->
  <script src="https://unpkg.com/lucide@latest"></script>
  <!-- Custom Styling & Theme Configuration -->
  <script>
    tailwind.config = {
      darkMode: 'class',
      theme: {
        extend: {
          colors: {
            forest: {
              950: '#07120c',
              900: '#0e2419',
              800: '#1b3b2b',
              700: '#27523d',
              600: '#346d51',
              500: '#438967',
            },
            bark: {
              950: '#140e0b',
              900: '#231813',
              800: '#3a2920',
              700: '#543c30',
            },
            amberfire: {
              400: '#f97316',
              500: '#e66a1f',
              600: '#d97706',
              700: '#b45309',
            }
          },
          fontFamily: {
            sans: ['Inter', 'sans-serif'],
          }
        }
      }
    }
  </script>
  <style>
    @import url('https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700;800;900&display=swap');
    
    ::-webkit-scrollbar {
      width: 6px;
    }
    ::-webkit-scrollbar-track {
      background: #07120c;
    }
    ::-webkit-scrollbar-thumb {
      background: #1b3b2b;
      border-radius: 3px;
    }

    .star-btn {
      transition: transform 0.15s ease, color 0.15s ease;
    }
    .star-btn:hover {
      transform: scale(1.25);
    }
    .no-scrollbar::-webkit-scrollbar {
      display: none;
    }
    .no-scrollbar {
      -ms-overflow-style: none;
      scrollbar-width: none;
    }
    .mist-bg {
      background-image: radial-gradient(ellipse at top, rgba(27,59,43,0.4) 0%, rgba(7,18,12,0.95) 75%);
    }
  </style>
</head>
<body class="h-full flex flex-col font-sans antialiased bg-forest-950 text-emerald-100 mist-bg pb-12">

  <!-- TOP HEADER WITH SASQUATCH BRANDING (TOP LEFT) -->
  <header class="bg-gradient-to-b from-forest-900 via-forest-900/90 to-forest-950 border-b border-forest-800/80 pt-5 pb-5 px-4 shadow-2xl relative overflow-hidden">
    <!-- Background Forest Silhouette Accents -->
    <div class="absolute inset-0 opacity-10 pointer-events-none flex justify-between items-end px-4 text-emerald-300 select-none">
      <span class="text-6xl">🌲</span>
      <span class="text-7xl">🐾</span>
      <span class="text-6xl">🌲</span>
    </div>

    <div class="max-w-4xl mx-auto flex flex-col sm:flex-row items-start sm:items-center justify-between gap-4 relative z-10">
      
      <!-- TOP LEFT BRANDING WITH SASQUATCH IMAGE/ICON & 2026 PLLP CHILI COOKOFF -->
      <div class="flex items-center gap-3">
        <!-- Sasquatch Avatar Image from Uploaded Image -->
        <div class="w-12 h-12 rounded-2xl bg-gradient-to-br from-bark-800 to-forest-950 border-2 border-amberfire-500/60 overflow-hidden shadow-lg shrink-0 flex items-center justify-center">
          <img src="input_file_0.png" alt="Sasquatch" class="w-full h-full object-cover object-center transform hover:scale-110 transition duration-300" onerror="this.onerror=null; this.src='https://placehold.co/100x100/1b3b2b/f97316?text=🐾';">
        </div>

        <div>
          <div class="inline-flex items-center gap-1.5 px-2.5 py-0.5 rounded-full bg-forest-800/80 border border-emerald-500/30 text-amberfire-400 text-[10px] font-bold uppercase tracking-wider mb-0.5">
            <span>🐾</span>
            <span>Official Voting App</span>
            <span>🌲</span>
          </div>
          <h1 class="text-2xl sm:text-3xl font-black text-white tracking-tight leading-none">
            2026 PLLP <span class="text-transparent bg-clip-text bg-gradient-to-r from-amberfire-400 via-amber-500 to-emerald-400">Chili Cookoff</span>
          </h1>
        </div>
      </div>

      <!-- Quick Stats & Coordinator Button -->
      <div class="flex items-center gap-3 bg-bark-900/90 border border-bark-700/80 p-2 rounded-2xl shadow-xl backdrop-blur-md self-stretch sm:self-auto justify-between sm:justify-start">
        <div class="text-center px-2.5 border-r border-bark-700">
          <span class="block text-lg font-black text-amberfire-400" id="stat-total-entrants">0</span>
          <span class="text-[9px] text-emerald-300/70 font-bold uppercase">Entries</span>
        </div>
        <div class="text-center px-2.5 border-r border-bark-700">
          <span class="block text-lg font-black text-emerald-400" id="stat-total-votes">0</span>
          <span class="text-[9px] text-emerald-300/70 font-bold uppercase">Votes</span>
        </div>
        <button id="admin-toggle-btn" class="flex items-center gap-1.5 px-3 py-2 bg-forest-800 hover:bg-forest-700 text-xs font-bold text-emerald-100 rounded-xl border border-forest-600 transition shadow">
          <i data-lucide="shield" class="w-3.5 h-3.5 text-amberfire-400"></i>
          <span>Coordinator</span>
        </button>
      </div>

    </div>
  </header>

  <!-- NAVIGATION TABS -->
  <div class="sticky top-0 z-30 bg-forest-950/90 backdrop-blur-md border-b border-forest-800/80 shadow-md">
    <div class="max-w-4xl mx-auto px-4 flex items-center justify-between">
      <nav class="flex space-x-4 sm:space-x-8 overflow-x-auto py-3 no-scrollbar" id="tab-nav">
        <button data-tab="directory" class="tab-btn active text-amberfire-400 border-b-2 border-amberfire-400 font-bold px-1 py-1 text-sm flex items-center gap-2 whitespace-nowrap">
          <i data-lucide="compass" class="w-4 h-4"></i> Chili Directory
        </button>
        <button data-tab="tracker" class="tab-btn text-emerald-300/70 hover:text-emerald-100 border-b-2 border-transparent font-bold px-1 py-1 text-sm flex items-center gap-2 whitespace-nowrap">
          <i data-lucide="footprints" class="w-4 h-4"></i> Vote Tracker
        </button>
        <button data-tab="favorites" class="tab-btn text-emerald-300/70 hover:text-emerald-100 border-b-2 border-transparent font-bold px-1 py-1 text-sm flex items-center gap-2 whitespace-nowrap">
          <i data-lucide="bookmark" class="w-4 h-4"></i> Saved & Notes (<span id="fav-count">0</span>)
        </button>
        <button id="leaderboard-tab-btn" data-tab="leaderboard" class="tab-btn hidden text-amber-400 hover:text-amber-300 border-b-2 border-transparent font-black px-1 py-1 text-sm flex items-center gap-2 whitespace-nowrap animate-pulse">
          <i data-lucide="trophy" class="w-4 h-4"></i> Bigfoot Champions
        </button>
      </nav>
    </div>
  </div>

  <!-- MAIN CONTENT CONTAINER -->
  <main class="max-w-4xl mx-auto px-4 py-6 flex-1 w-full">

    <!-- VIEW 1: ANONYMOUS SINGLE-LINE ENTRANTS DIRECTORY (NO SEARCH BAR) -->
    <section id="view-directory" class="tab-view space-y-4">
      
      <!-- Single-Line Rows List -->
      <div class="bg-forest-900/70 border border-forest-800/90 rounded-2xl overflow-hidden shadow-2xl backdrop-blur-sm">
        <div class="p-3 bg-forest-950/80 border-b border-forest-800 flex justify-between items-center text-xs font-bold text-emerald-400/80 uppercase tracking-wider">
          <span class="flex items-center gap-1.5"><i data-lucide="trees" class="w-3.5 h-3.5"></i> Entry # & Chili Title</span>
          <span class="pr-2">Action</span>
        </div>

        <div id="entrants-list" class="divide-y divide-forest-800/60">
          <!-- Single-line rows rendered dynamically -->
        </div>
      </div>

      <!-- Empty State -->
      <div id="no-results" class="hidden text-center py-12 bg-forest-900/40 rounded-3xl border border-dashed border-forest-800">
        <i data-lucide="ghost" class="w-8 h-8 mx-auto text-emerald-600 mb-2"></i>
        <h3 class="text-base font-bold text-emerald-200">No Chili Entries Found</h3>
        <p class="text-xs text-emerald-500 mt-1">Check back soon or ask the event coordinator to add entries.</p>
      </div>
    </section>

    <!-- VIEW 2: VOTE TRACKER & LOWEST VOTES HIGHLIGHT -->
    <section id="view-tracker" class="tab-view hidden space-y-6">
      
      <!-- Low Vote Alert Callout -->
      <div class="bg-gradient-to-r from-bark-900 via-forest-900 to-forest-900 border border-amberfire-500/40 p-4 sm:p-5 rounded-2xl shadow-xl relative overflow-hidden">
        <div class="flex items-center gap-2 text-amberfire-400 font-extrabold text-sm mb-1">
          <span>🐾</span>
          <span>Feast for Sasquatch — Lowest Vote Counts!</span>
        </div>
        <p class="text-xs text-emerald-200/90">
          Bigfoot wants a balanced cookoff! Sample these under-sampled chilis below so every pot gets enough votes before time runs out.
        </p>
      </div>

      <!-- Highlighted 3 Lowest Vote Cards -->
      <div class="grid grid-cols-1 sm:grid-cols-3 gap-3" id="lowest-votes-container">
        <!-- Rendered via JS -->
      </div>

      <!-- All Chili Vote Counts Single-Line List -->
      <div class="bg-forest-900/70 border border-forest-800/90 rounded-2xl overflow-hidden shadow-xl">
        <div class="p-4 border-b border-forest-800 bg-forest-950/80 flex justify-between items-center">
          <h3 class="text-xs font-black uppercase tracking-wider text-emerald-300">Total Votes per Entry</h3>
          <span class="text-xs text-emerald-500">Ordered by fewest votes</span>
        </div>
        <div class="divide-y divide-forest-800/60" id="vote-tracker-list">
          <!-- Rendered via JS -->
        </div>
      </div>
    </section>

    <!-- VIEW 3: PERSONAL TASTING NOTES / FAVORITES -->
    <section id="view-favorites" class="tab-view hidden space-y-4">
      <div class="bg-forest-900/60 p-4 rounded-2xl border border-forest-800">
        <h2 class="text-lg font-bold text-white flex items-center gap-2">
          <i data-lucide="bookmark" class="w-5 h-5 text-amberfire-400"></i> Saved Entries & Private Notes
        </h2>
        <p class="text-xs text-emerald-300/70 mt-0.5">Your private Sasquatch trail notes and bookmarked favorites.</p>
      </div>

      <div id="favorites-list" class="space-y-3">
        <!-- Rendered via JS -->
      </div>

      <div id="no-favorites" class="hidden text-center py-12 bg-forest-900/40 rounded-3xl border border-dashed border-forest-800">
        <i data-lucide="bookmark-x" class="w-8 h-8 mx-auto text-emerald-600 mb-2"></i>
        <h3 class="text-base font-bold text-emerald-200">No Saved Entries Yet</h3>
        <p class="text-xs text-emerald-500 mt-1">Bookmark any chili row to save it here!</p>
      </div>
    </section>

    <!-- VIEW 4: OFFICIAL LEADERBOARD (REVEALED WHEN VOTING IS CLOSED) -->
    <section id="view-leaderboard" class="tab-view hidden space-y-6">
      <div class="bg-gradient-to-r from-bark-900 via-forest-900 to-forest-900 border border-amberfire-500/50 p-6 rounded-3xl shadow-2xl text-center space-y-3 relative overflow-hidden">
        <div class="w-20 h-20 mx-auto rounded-full border-2 border-amberfire-400 shadow-xl overflow-hidden mb-1">
          <img src="input_file_0.png" alt="Sasquatch Champion" class="w-full h-full object-cover object-center" onerror="this.onerror=null; this.src='https://placehold.co/100x100/1b3b2b/f97316?text=🐾';">
        </div>
        <span class="px-3 py-1 bg-amberfire-500/20 text-amberfire-300 border border-amberfire-500/40 rounded-full text-xs font-black uppercase tracking-widest inline-block">
          Official Final Standings
        </span>
        <h2 class="text-3xl font-black text-white">Bigfoot Champion Standings</h2>
        <p class="text-xs text-emerald-200 max-w-md mx-auto">The Sasquatch search has ended! Here are the highest rated chilis based on 1-5 star averages.</p>
      </div>

      <!-- Top 3 Winners Podium -->
      <div class="grid grid-cols-1 sm:grid-cols-3 gap-4 items-end" id="podium-container">
        <!-- Rendered via JS -->
      </div>

      <!-- Standings Table -->
      <div class="bg-forest-900/70 border border-forest-800 rounded-2xl overflow-hidden shadow-xl">
        <div class="p-4 border-b border-forest-800 bg-forest-950/80 font-bold text-emerald-200 text-xs uppercase tracking-wider">
          Complete Final Rankings
        </div>
        <div class="overflow-x-auto">
          <table class="w-full text-left text-sm text-emerald-200">
            <thead class="bg-forest-950/90 text-xs font-semibold uppercase text-emerald-400 border-b border-forest-800">
              <tr>
                <th class="py-3 px-4 text-center">Rank</th>
                <th class="py-3 px-4">Entry # & Chili Title</th>
                <th class="py-3 px-4 text-center">Total Votes</th>
                <th class="py-3 px-4 text-center">Average Rating</th>
              </tr>
            </thead>
            <tbody id="leaderboard-tbody" class="divide-y divide-forest-800/80">
              <!-- Rendered via JS -->
            </tbody>
          </table>
        </div>
      </div>
    </section>

  </main>

  <!-- 1-5 STAR RATING & NOTES MODAL (DEFAULTS TO 0 STARS) -->
  <div id="rating-modal" class="fixed inset-0 z-50 flex items-center justify-center p-4 bg-black/80 backdrop-blur-md hidden opacity-0 transition-opacity duration-200">
    <div class="bg-forest-900 border border-forest-700/80 rounded-3xl max-w-sm w-full p-6 shadow-2xl relative flex flex-col space-y-4">
      
      <button id="close-rating-modal" class="absolute top-4 right-4 text-emerald-400 hover:text-white bg-forest-800 p-1.5 rounded-full border border-forest-700 z-10">
        <i data-lucide="x" class="w-4 h-4"></i>
      </button>

      <div class="border-b border-forest-800 pb-2 flex items-center gap-3">
        <img src="input_file_0.png" alt="Sasquatch" class="w-10 h-10 rounded-xl object-cover border border-amberfire-500/50 shrink-0" onerror="this.onerror=null; this.src='https://placehold.co/100x100/1b3b2b/f97316?text=🐾';">
        <div>
          <span class="text-xs font-black uppercase tracking-wider text-amberfire-400" id="rate-modal-entry-num">Entry #101</span>
          <h2 class="text-lg font-black text-white leading-tight" id="rate-modal-chili-name">Chili Name</h2>
        </div>
      </div>

      <!-- 1-5 Star Picker (Default 0 Stars) -->
      <div class="space-y-3">
        <div class="bg-forest-950 p-4 rounded-2xl border border-forest-800 text-center space-y-1">
          <label class="block text-xs font-extrabold uppercase tracking-wider text-emerald-300">
            Select Rating (1 to 5 Stars)
          </label>
          <div class="flex justify-center items-center gap-1.5 py-2" id="star-picker-container">
            <!-- Rendered via JS -->
          </div>
          <span class="text-xs font-bold text-amberfire-400 block h-4" id="rate-val-display">
            Tap a star to rate
          </span>
        </div>

        <!-- Personal Tasting Notes -->
        <div>
          <label for="rate-user-notes" class="block text-xs font-semibold text-emerald-200 mb-1">
            My Tasting Notes <span class="text-emerald-500 font-normal">(Private)</span>
          </label>
          <textarea id="rate-user-notes" rows="2" placeholder="Notes on heat, flavor, timberland spice..." class="w-full bg-forest-950 border border-forest-800 rounded-xl p-3 text-xs text-emerald-100 placeholder-emerald-700 focus:outline-none focus:border-amberfire-500"></textarea>
        </div>
      </div>

      <!-- Actions -->
      <div class="flex gap-2 pt-1">
        <button id="cancel-rating-btn" class="w-1/3 py-2.5 bg-forest-800 hover:bg-forest-700 text-emerald-200 font-semibold text-xs rounded-xl transition">
          Cancel
        </button>
        <button id="submit-rating-btn" class="w-2/3 py-2.5 bg-gradient-to-r from-amberfire-500 to-amber-600 hover:from-amberfire-400 hover:to-amber-500 text-white font-bold text-xs rounded-xl shadow-lg transition flex items-center justify-center gap-1.5">
          <i data-lucide="check" class="w-4 h-4"></i> Submit Rating
        </button>
      </div>

    </div>
  </div>

  <!-- COORDINATOR / ADMIN MODAL -->
  <div id="admin-modal" class="fixed inset-0 z-50 flex items-center justify-center p-4 bg-black/80 backdrop-blur-md hidden opacity-0 transition-opacity duration-200">
    <div class="bg-forest-900 border border-forest-700/80 rounded-3xl max-w-lg w-full p-6 shadow-2xl relative flex flex-col space-y-5 max-h-[90vh] overflow-y-auto">
      
      <button id="close-admin-modal" class="absolute top-4 right-4 text-emerald-400 hover:text-white bg-forest-800 p-1.5 rounded-full border border-forest-700">
        <i data-lucide="x" class="w-4 h-4"></i>
      </button>

      <div class="border-b border-forest-800 pb-3">
        <h2 class="text-xl font-black text-white flex items-center gap-2">
          <i data-lucide="shield" class="w-5 h-5 text-amberfire-400"></i> Event Coordinator Panel
        </h2>
        <p class="text-xs text-emerald-300/70">Manage chili entries and control voting reveal settings.</p>
      </div>

      <!-- Password Lock Screen -->
      <div id="admin-auth-screen" class="space-y-3 bg-forest-950 p-4 rounded-2xl border border-forest-800 text-center">
        <label class="block text-xs font-bold text-emerald-300 uppercase">Enter Coordinator PIN</label>
        <input type="password" id="admin-pin-input" placeholder="Default: 1234" class="w-32 mx-auto text-center bg-forest-900 border border-forest-700 rounded-xl py-2 text-sm text-white focus:outline-none focus:border-amberfire-500">
        <button id="admin-login-btn" class="block w-full py-2 bg-amberfire-500 hover:bg-amberfire-400 text-white text-xs font-bold rounded-xl shadow">Unlock Panel</button>
      </div>

      <!-- Authenticated Admin Screen -->
      <div id="admin-panel-content" class="hidden space-y-5">
        
        <!-- Toggle Voting State -->
        <div class="bg-forest-950 p-4 rounded-2xl border border-forest-800 flex items-center justify-between gap-3">
          <div>
            <span class="text-xs font-bold text-emerald-400 uppercase">Voting State</span>
            <p class="text-xs font-extrabold text-white" id="admin-voting-state-label">Voting is OPEN</p>
          </div>
          <button id="toggle-voting-state-btn" class="px-3 py-2 rounded-xl font-bold text-xs transition shadow-md bg-amberfire-500 hover:bg-amberfire-400 text-white">
            Close Voting & Reveal Champions
          </button>
        </div>

        <!-- Add/Edit Entry Form (Number & Name Only) -->
        <div class="space-y-3">
          <h3 class="text-xs font-bold text-emerald-300 uppercase">Add / Edit Entry (Entry # & Name Only)</h3>
          
          <form id="admin-entrant-form" class="space-y-3 bg-forest-950 p-4 rounded-2xl border border-forest-800">
            <input type="hidden" id="admin-entry-id" value="">
            <div>
              <label class="block text-xs text-emerald-400 mb-1">Entry Number</label>
              <input type="text" id="form-entry-num" required placeholder="Entry #109" class="w-full bg-forest-900 border border-forest-800 rounded-xl px-3 py-2 text-xs text-white focus:outline-none focus:border-amberfire-500">
            </div>
            <div>
              <label class="block text-xs text-emerald-400 mb-1">Chili Name</label>
              <input type="text" id="form-chili-name" required placeholder="Pine Needles & Pepper Brew" class="w-full bg-forest-900 border border-forest-800 rounded-xl px-3 py-2 text-xs text-white focus:outline-none focus:border-amberfire-500">
            </div>

            <div class="flex justify-end gap-2 pt-1">
              <button type="button" id="admin-reset-form-btn" class="px-3 py-1.5 bg-forest-800 text-emerald-200 rounded-xl text-xs font-semibold">Clear</button>
              <button type="submit" id="admin-save-btn" class="px-4 py-1.5 bg-amberfire-500 hover:bg-amberfire-400 text-white rounded-xl text-xs font-bold shadow-md">Save Entry</button>
            </div>
          </form>
        </div>

        <!-- Entrants Management List -->
        <div class="space-y-2">
          <h3 class="text-xs font-bold text-emerald-300 uppercase">Current Entries (<span id="admin-entry-count">0</span>)</h3>
          <div id="admin-manage-list" class="space-y-2 max-h-48 overflow-y-auto pr-1">
            <!-- Rendered dynamically -->
          </div>
        </div>

        <!-- Danger Reset Zone -->
        <div class="border-t border-forest-800 pt-3 flex items-center justify-between">
          <span class="text-[11px] text-emerald-500">Reset to initial sample entries.</span>
          <button id="admin-reset-all" class="px-3 py-1 bg-red-950 border border-red-800 text-red-300 hover:bg-red-900 text-xs font-semibold rounded-lg">
            Reset Data
          </button>
        </div>

      </div>

    </div>
  </div>

  <!-- TOAST CONTAINER -->
  <div id="toast-container" class="fixed bottom-4 right-4 z-50 flex flex-col gap-2 pointer-events-none"></div>

  <!-- APPLICATION LOGIC -->
  <script>
    // INITIAL SASQUATCH CRYPTID CHILI MOCK DATA
    const INITIAL_ENTRANTS = [
      { id: 'sq101', number: 'Entry #101', name: 'Squatch Foot Smokehouse', votesCount: 14, sumScore: 63 },
      { id: 'sq102', number: 'Entry #102', name: 'Misty Mountain Fire', votesCount: 18, sumScore: 82 },
      { id: 'sq103', number: 'Entry #103', name: 'Deep Woods Ember', votesCount: 4, sumScore: 18 },
      { id: 'sq104', number: 'Entry #104', name: 'Cryptid Cayenne', votesCount: 11, sumScore: 49 },
      { id: 'sq105', number: 'Entry #105', name: "Bigfoot's Secret Brew", votesCount: 3, sumScore: 14 },
      { id: 'sq106', number: 'Entry #106', name: 'Timberline Inferno', votesCount: 2, sumScore: 9 },
      { id: 'sq107', number: 'Entry #107', name: 'Campfire Howler Chili', votesCount: 9, sumScore: 38 },
      { id: 'sq108', number: 'Entry #108', name: 'Pine Needle Red Bean Blast', votesCount: 12, sumScore: 50 }
    ];

    // LOCAL STORAGE KEYS
    const STORAGE_ENTRANTS_KEY = 'pllp_sasquatch_entrants_2026';
    const STORAGE_FAVS_KEY = 'pllp_sasquatch_favs_2026';
    const STORAGE_MY_VOTES_KEY = 'pllp_sasquatch_votes_2026';
    const STORAGE_STATE_KEY = 'pllp_sasquatch_open_2026';

    // APP STATE
    let entrants = [];
    let favorites = new Set();
    let userVotes = {}; // entrantId -> { rating, notes }
    let isVotingOpen = true;
    let isAdminUnlocked = false;
    let currentRatingEntrantId = null;
    let currentDraftRating = 0; // DEFAULT TO 0 STARS FOR UNSELECTED RATING

    // DOM ELEMENTS
    const entrantsList = document.getElementById('entrants-list');
    const noResults = document.getElementById('no-results');

    // INITIALIZATION
    window.addEventListener('DOMContentLoaded', () => {
      loadState();
      setupTabs();
      setupEventListeners();
      renderAll();
      lucide.createIcons();
    });

    function loadState() {
      const savedEntrants = localStorage.getItem(STORAGE_ENTRANTS_KEY);
      if (savedEntrants) {
        try { entrants = JSON.parse(savedEntrants); } catch(e) { entrants = [...INITIAL_ENTRANTS]; }
      } else {
        entrants = [...INITIAL_ENTRANTS];
      }

      const savedFavs = localStorage.getItem(STORAGE_FAVS_KEY);
      if (savedFavs) {
        try { favorites = new Set(JSON.parse(savedFavs)); } catch(e) { favorites = new Set(); }
      }

      const savedVotes = localStorage.getItem(STORAGE_MY_VOTES_KEY);
      if (savedVotes) {
        try { userVotes = JSON.parse(savedVotes); } catch(e) { userVotes = {}; }
      }

      const savedState = localStorage.getItem(STORAGE_STATE_KEY);
      isVotingOpen = savedState !== null ? JSON.parse(savedState) : true;
    }

    function saveState() {
      localStorage.setItem(STORAGE_ENTRANTS_KEY, JSON.stringify(entrants));
      localStorage.setItem(STORAGE_FAVS_KEY, JSON.stringify(Array.from(favorites)));
      localStorage.setItem(STORAGE_MY_VOTES_KEY, JSON.stringify(userVotes));
      localStorage.setItem(STORAGE_STATE_KEY, JSON.stringify(isVotingOpen));
    }

    // TAB NAVIGATION
    function setupTabs() {
      const tabs = document.querySelectorAll('.tab-btn');
      const views = document.querySelectorAll('.tab-view');

      tabs.forEach(tab => {
        tab.addEventListener('click', () => {
          const targetView = tab.getAttribute('data-tab');

          tabs.forEach(t => {
            t.classList.remove('text-amberfire-400', 'border-amberfire-400', 'text-amber-400');
            t.classList.add('text-emerald-300/70', 'border-transparent');
          });

          if (targetView === 'leaderboard') {
            tab.classList.add('text-amber-400', 'border-amber-400');
          } else {
            tab.classList.add('text-amberfire-400', 'border-amberfire-400');
          }

          views.forEach(v => {
            if (v.id === `view-${targetView}`) {
              v.classList.remove('hidden');
            } else {
              v.classList.add('hidden');
            }
          });

          lucide.createIcons();
        });
      });
    }

    // MAIN RENDER CONTROLLER
    function renderAll() {
      renderHeaderStats();
      renderDirectory();
      renderTracker();
      renderFavorites();
      renderLeaderboard();
      updateVotingStatusUI();
    }

    function renderHeaderStats() {
      document.getElementById('stat-total-entrants').textContent = entrants.length;
      const totalVotes = entrants.reduce((acc, curr) => acc + (curr.votesCount || 0), 0);
      document.getElementById('stat-total-votes').textContent = totalVotes;
      document.getElementById('admin-entry-count').textContent = entrants.length;
      document.getElementById('fav-count').textContent = favorites.size;
    }

    function updateVotingStatusUI() {
      const leaderboardTab = document.getElementById('leaderboard-tab-btn');
      const adminLabel = document.getElementById('admin-voting-state-label');
      const adminToggleBtn = document.getElementById('toggle-voting-state-btn');

      if (isVotingOpen) {
        leaderboardTab.classList.add('hidden');
        adminLabel.textContent = "Voting is OPEN";
        adminToggleBtn.textContent = "Close Voting & Reveal Champions";
        adminToggleBtn.className = "px-3 py-2 rounded-xl font-bold text-xs transition shadow-md bg-amberfire-500 hover:bg-amberfire-400 text-white";
      } else {
        leaderboardTab.classList.remove('hidden');
        adminLabel.textContent = "Voting is CLOSED";
        adminToggleBtn.textContent = "Re-open Voting";
        adminToggleBtn.className = "px-3 py-2 rounded-xl font-bold text-xs transition shadow-md bg-emerald-600 hover:bg-emerald-500 text-white";
      }
      lucide.createIcons();
    }

    // DIRECTORY RENDER (ANONYMOUS SINGLE-LINE ROWS, NO SEARCH)
    function renderDirectory() {
      if (entrants.length === 0) {
        entrantsList.innerHTML = '';
        noResults.classList.remove('hidden');
        return;
      }

      noResults.classList.add('hidden');
      entrantsList.innerHTML = entrants.map(item => {
        const isFav = favorites.has(item.id);
        const myVote = userVotes[item.id];

        return `
          <div class="p-3 sm:p-4 flex items-center justify-between gap-3 hover:bg-forest-800/40 transition">
            
            <!-- Left: Entry # & Chili Title -->
            <div class="flex items-center gap-2.5 sm:gap-3 min-w-0">
              <span class="shrink-0 px-2.5 py-1 bg-forest-950 border border-forest-800 text-amberfire-400 text-xs font-black rounded-lg">
                ${item.number}
              </span>
              <h3 class="text-sm sm:text-base font-bold text-white truncate">${item.name}</h3>
            </div>

            <!-- Right: Actions & Optional Star Indicator -->
            <div class="flex items-center gap-2 shrink-0">
              ${myVote ? `
                <div class="hidden sm:block text-right mr-1">
                  <span class="text-[10px] text-emerald-400 font-bold block leading-none">Your Rating</span>
                  <span class="text-amber-400 font-bold text-xs">${'★'.repeat(myVote.rating)}</span>
                </div>
              ` : ''}

              <button onclick="toggleFavorite('${item.id}')" title="Save Chili" class="p-2 rounded-xl text-emerald-600 hover:text-amberfire-400 hover:bg-forest-800/60 transition">
                <i data-lucide="bookmark" class="w-4 h-4 ${isFav ? 'text-amberfire-400 fill-amberfire-400' : ''}"></i>
              </button>

              <button onclick="openRatingModal('${item.id}')" ${!isVotingOpen ? 'disabled' : ''} class="px-3 py-1.5 bg-gradient-to-r ${myVote ? 'from-forest-800 to-forest-700 text-amber-400 border border-amber-500/30' : 'from-amberfire-500 to-amber-600 text-white'} ${!isVotingOpen ? 'opacity-50 cursor-not-allowed' : ''} text-xs font-bold rounded-xl shadow transition flex items-center gap-1">
                <i data-lucide="star" class="w-3.5 h-3.5 fill-current"></i>
                <span>${!isVotingOpen ? 'Closed' : (myVote ? `${myVote.rating}★ Edit` : 'Rate')}</span>
              </button>
            </div>

          </div>
        `;
      }).join('');

      lucide.createIcons();
    }

    // VOTE TRACKER & LOWEST 3 VOTES HIGHLIGHT
    function renderTracker() {
      const lowestContainer = document.getElementById('lowest-votes-container');
      const listContainer = document.getElementById('vote-tracker-list');

      if (entrants.length === 0) return;

      // Sort by votes count ascending
      const sortedByVotes = [...entrants].sort((a, b) => (a.votesCount || 0) - (b.votesCount || 0));

      // Lowest 3 entries
      const lowestThree = sortedByVotes.slice(0, 3);

      lowestContainer.innerHTML = lowestThree.map(item => `
        <div class="bg-gradient-to-br from-bark-900 to-forest-900 border border-amberfire-500/50 p-3.5 rounded-2xl relative shadow-md flex flex-col justify-between">
          <div>
            <div class="flex justify-between items-center mb-1">
              <span class="text-xs font-black text-amberfire-400 bg-forest-950 px-2 py-0.5 rounded border border-forest-800">${item.number}</span>
              <span class="text-[10px] font-bold text-amberfire-300 uppercase tracking-wider bg-amberfire-500/20 px-2 py-0.5 rounded-full">Needs Tasters!</span>
            </div>
            <h4 class="text-sm font-black text-white mt-1">${item.name}</h4>
          </div>

          <div class="pt-2 mt-2 border-t border-forest-800 flex items-center justify-between">
            <span class="text-xs text-emerald-200 font-medium">
              Votes: <strong class="text-amberfire-400 font-black text-xs sm:text-sm">${item.votesCount || 0}</strong>
            </span>
            <button onclick="openRatingModal('${item.id}')" ${!isVotingOpen ? 'disabled' : ''} class="px-2.5 py-1 bg-amberfire-500 hover:bg-amberfire-400 text-white rounded-lg text-xs font-bold transition flex items-center gap-1">
              <i data-lucide="star" class="w-3 h-3"></i> Rate
            </button>
          </div>
        </div>
      `).join('');

      // All Entries Vote Count Single-Line List
      listContainer.innerHTML = sortedByVotes.map(item => `
        <div class="p-3 sm:p-3.5 flex items-center justify-between hover:bg-forest-800/30 transition">
          <div class="flex items-center gap-2.5">
            <span class="px-2 py-0.5 bg-forest-950 border border-forest-800 text-amberfire-400 text-xs font-black rounded">${item.number}</span>
            <h4 class="font-bold text-sm text-white">${item.name}</h4>
          </div>
          <div class="flex items-center gap-3">
            <div class="text-right">
              <span class="text-sm font-black text-amberfire-400">${item.votesCount || 0}</span>
              <span class="text-[10px] text-emerald-500 block -mt-1 uppercase">Votes</span>
            </div>
            <button onclick="openRatingModal('${item.id}')" ${!isVotingOpen ? 'disabled' : ''} class="p-1.5 bg-forest-800 hover:bg-forest-700 text-emerald-200 rounded-lg text-xs">
              <i data-lucide="star" class="w-3.5 h-3.5"></i>
            </button>
          </div>
        </div>
      `).join('');

      lucide.createIcons();
    }

    // TASTING NOTES / FAVORITES
    function renderFavorites() {
      const favList = document.getElementById('favorites-list');
      const noFavs = document.getElementById('no-favorites');

      const favItems = entrants.filter(item => favorites.has(item.id));

      if (favItems.length === 0) {
        favList.innerHTML = '';
        noFavs.classList.remove('hidden');
        return;
      }

      noFavs.classList.add('hidden');
      favList.innerHTML = favItems.map(item => {
        const myVote = userVotes[item.id];
        return `
          <div class="bg-bark-900 border border-forest-800 rounded-2xl p-4 shadow-lg flex flex-col justify-between space-y-3">
            <div class="flex items-center justify-between">
              <div class="flex items-center gap-2">
                <span class="px-2 py-0.5 bg-forest-950 text-amberfire-400 text-xs font-black rounded">${item.number}</span>
                <h3 class="text-base font-black text-white">${item.name}</h3>
              </div>
              <button onclick="toggleFavorite('${item.id}')" class="text-emerald-600 hover:text-amberfire-400 p-1">
                <i data-lucide="trash-2" class="w-4 h-4"></i>
              </button>
            </div>

            <div class="p-3 bg-forest-950 rounded-xl text-xs space-y-1.5 border border-forest-800">
              <div class="flex justify-between text-emerald-300">
                <span class="text-emerald-500 font-semibold">Your Rating:</span>
                <span class="font-bold text-amber-400">${myVote ? '★'.repeat(myVote.rating) : 'Not Rated'}</span>
              </div>
              <p class="text-emerald-100 italic bg-forest-900/80 p-2 rounded border border-forest-800/80">${myVote && myVote.notes ? `"${myVote.notes}"` : 'No private notes saved yet.'}</p>
            </div>

            <button onclick="openRatingModal('${item.id}')" ${!isVotingOpen ? 'disabled' : ''} class="w-full py-2 bg-amberfire-500 hover:bg-amberfire-400 text-white font-bold text-xs rounded-xl transition flex items-center justify-center gap-1">
              <i data-lucide="star" class="w-3.5 h-3.5"></i> ${myVote ? 'Edit Vote & Notes' : 'Rate This Chili'}
            </button>
          </div>
        `;
      }).join('');

      lucide.createIcons();
    }

    // LEADERBOARD (REVEALED WHEN VOTING IS CLOSED)
    function renderLeaderboard() {
      const podiumContainer = document.getElementById('podium-container');
      const tbody = document.getElementById('leaderboard-tbody');

      const sorted = [...entrants].map(item => {
        const count = item.votesCount || 0;
        const avgScore = count > 0 ? (item.sumScore / count) : 0;
        return { ...item, avgScore };
      }).sort((a, b) => b.avgScore - a.avgScore);

      if (sorted.length === 0) return;

      const top3 = sorted.slice(0, 3);
      podiumContainer.innerHTML = top3.map((item, idx) => {
        let titleBadge = 'Sasquatch Champion';
        let borderColor = 'border-amber-500';
        let crownColor = 'text-amber-400';

        if (idx === 1) {
          titleBadge = '2nd Place Cryptid';
          borderColor = 'border-slate-400';
          crownColor = 'text-slate-300';
        } else if (idx === 2) {
          titleBadge = '3rd Place Runner-Up';
          borderColor = 'border-amber-700';
          crownColor = 'text-amber-600';
        }

        return `
          <div class="bg-forest-900 border-2 ${borderColor} p-5 rounded-2xl text-center shadow-2xl relative flex flex-col justify-between">
            <div>
              <div class="inline-flex p-2.5 rounded-full bg-forest-950 border border-forest-800 mb-1 ${crownColor}">
                <i data-lucide="crown" class="w-6 h-6"></i>
              </div>
              <span class="block text-xs font-black uppercase tracking-wider text-emerald-300">${titleBadge}</span>
              <span class="inline-block mt-1 px-2 py-0.5 bg-forest-950 text-amberfire-400 text-xs font-black rounded">${item.number}</span>
              <h3 class="text-lg font-black text-white mt-1">${item.name}</h3>
            </div>

            <div class="mt-3 pt-2 border-t border-forest-800">
              <span class="text-xl font-black text-amber-400">${item.avgScore.toFixed(1)} ★</span>
              <span class="block text-[10px] text-emerald-400 uppercase">${item.votesCount} Votes</span>
            </div>
          </div>
        `;
      }).join('');

      tbody.innerHTML = sorted.map((item, index) => `
        <tr class="hover:bg-forest-800/40 transition-colors">
          <td class="py-3 px-4 text-center font-bold text-emerald-300">#${index + 1}</td>
          <td class="py-3 px-4">
            <span class="font-black text-amberfire-400 text-xs mr-1.5">${item.number}</span>
            <span class="font-bold text-white">${item.name}</span>
          </td>
          <td class="py-3 px-4 text-center text-xs font-semibold text-emerald-200">${item.votesCount || 0}</td>
          <td class="py-3 px-4 text-center font-black text-amber-400">${item.avgScore.toFixed(1)} ★</td>
        </tr>
      `).join('');

      lucide.createIcons();
    }

    // FAVORITES TOGGLE
    window.toggleFavorite = function(id) {
      if (favorites.has(id)) {
        favorites.delete(id);
        showToast('Removed from saved list', 'info');
      } else {
        favorites.add(id);
        showToast('Saved to your trail notes!', 'success');
      }
      saveState();
      renderAll();
    };

    // RATING MODAL INTERACTION (DEFAULT TO 0 STARS)
    window.openRatingModal = function(id) {
      if (!isVotingOpen) {
        showToast('Voting is currently closed', 'info');
        return;
      }

      const entrant = entrants.find(e => e.id === id);
      if (!entrant) return;

      currentRatingEntrantId = id;
      const existingVote = userVotes[id];

      // DEFAULT TO 0 STARS FOR NEW UNSELECTED VOTE
      currentDraftRating = existingVote ? (existingVote.rating || 0) : 0;

      document.getElementById('rate-modal-entry-num').textContent = entrant.number;
      document.getElementById('rate-modal-chili-name').textContent = entrant.name;
      document.getElementById('rate-user-notes').value = existingVote ? (existingVote.notes || '') : '';

      renderStarPicker();

      const modal = document.getElementById('rating-modal');
      modal.classList.remove('hidden');
      setTimeout(() => modal.classList.remove('opacity-0'), 10);
    };

    function closeRatingModal() {
      const modal = document.getElementById('rating-modal');
      modal.classList.add('opacity-0');
      setTimeout(() => modal.classList.add('hidden'), 200);
      currentRatingEntrantId = null;
    }

    function renderStarPicker() {
      const container = document.getElementById('star-picker-container');
      const valDisplay = document.getElementById('rate-val-display');

      if (currentDraftRating === 0) {
        valDisplay.textContent = 'Tap a star to rate (1 - 5 Stars)';
        valDisplay.className = 'text-xs font-bold text-amberfire-400 block h-4 animate-pulse';
      } else {
        valDisplay.textContent = `${currentDraftRating} Star${currentDraftRating > 1 ? 's' : ''}`;
        valDisplay.className = 'text-xs font-black text-amber-400 block h-4';
      }

      let html = '';
      for (let i = 1; i <= 5; i++) {
        const active = i <= currentDraftRating;
        html += `
          <button type="button" onclick="setDraftStar(${i})" class="star-btn focus:outline-none p-1 text-2xl">
            <i data-lucide="star" class="w-7 h-7 ${active ? 'text-amber-400 fill-amber-400' : 'text-forest-700'}"></i>
          </button>
        `;
      }
      container.innerHTML = html;
      lucide.createIcons();
    }

    window.setDraftStar = function(val) {
      currentDraftRating = val;
      renderStarPicker();
    };

    function submitRating() {
      if (!currentRatingEntrantId) return;

      if (currentDraftRating === 0) {
        showToast('Please select at least 1 star before submitting!', 'info');
        return;
      }

      const entrant = entrants.find(e => e.id === currentRatingEntrantId);
      if (!entrant) return;

      const notes = document.getElementById('rate-user-notes').value.trim();
      const existingVote = userVotes[currentRatingEntrantId];

      if (existingVote) {
        entrant.sumScore = (entrant.sumScore - existingVote.rating) + currentDraftRating;
      } else {
        entrant.votesCount = (entrant.votesCount || 0) + 1;
        entrant.sumScore = (entrant.sumScore || 0) + currentDraftRating;
      }

      userVotes[currentRatingEntrantId] = {
        rating: currentDraftRating,
        notes: notes
      };

      saveState();
      renderAll();
      closeRatingModal();
      showToast(`Vote recorded for ${entrant.number}! 🐾`, 'success');
    }

    // ADMIN CONTROLS
    function openAdminModal() {
      const modal = document.getElementById('admin-modal');
      modal.classList.remove('hidden');
      setTimeout(() => modal.classList.remove('opacity-0'), 10);
    }

    function closeAdminModal() {
      const modal = document.getElementById('admin-modal');
      modal.classList.add('opacity-0');
      setTimeout(() => modal.classList.add('hidden'), 200);
    }

    function renderAdminManageList() {
      const container = document.getElementById('admin-manage-list');
      container.innerHTML = entrants.map(e => `
        <div class="flex items-center justify-between p-2.5 bg-forest-950 border border-forest-800 rounded-xl">
          <div>
            <span class="font-bold text-amberfire-400 text-xs">${e.number}</span>
            <span class="font-bold text-white text-xs ml-2">${e.name}</span>
          </div>
          <div class="flex items-center gap-1.5">
            <button onclick="editAdminEntrant('${e.id}')" class="p-1 bg-forest-800 hover:bg-forest-700 text-emerald-200 rounded text-xs">
              <i data-lucide="edit-2" class="w-3.5 h-3.5"></i>
            </button>
            <button onclick="deleteAdminEntrant('${e.id}')" class="p-1 bg-red-950 border border-red-800 text-red-300 rounded text-xs">
              <i data-lucide="trash" class="w-3.5 h-3.5"></i>
            </button>
          </div>
        </div>
      `).join('');
      lucide.createIcons();
    }

    window.editAdminEntrant = function(id) {
      const e = entrants.find(item => item.id === id);
      if (!e) return;

      document.getElementById('admin-entry-id').value = e.id;
      document.getElementById('form-entry-num').value = e.number;
      document.getElementById('form-chili-name').value = e.name;
    };

    window.deleteAdminEntrant = function(id) {
      if (confirm('Delete this entry?')) {
        entrants = entrants.filter(e => e.id !== id);
        favorites.delete(id);
        delete userVotes[id];
        saveState();
        renderAll();
        renderAdminManageList();
        showToast('Entry deleted', 'info');
      }
    };

    // EVENT LISTENERS
    function setupEventListeners() {
      // Modal Listeners
      document.getElementById('close-rating-modal').addEventListener('click', closeRatingModal);
      document.getElementById('cancel-rating-btn').addEventListener('click', closeRatingModal);
      document.getElementById('submit-rating-btn').addEventListener('click', submitRating);

      // Admin Modal Triggers & Password Check
      document.getElementById('admin-toggle-btn').addEventListener('click', openAdminModal);
      document.getElementById('close-admin-modal').addEventListener('click', closeAdminModal);

      document.getElementById('admin-login-btn').addEventListener('click', () => {
        const pin = document.getElementById('admin-pin-input').value.trim();
        if (pin === '1234' || pin === '') {
          isAdminUnlocked = true;
          document.getElementById('admin-auth-screen').classList.add('hidden');
          document.getElementById('admin-panel-content').classList.remove('hidden');
          renderAdminManageList();
        } else {
          alert('Incorrect PIN (Default is 1234)');
        }
      });

      document.getElementById('admin-reset-form-btn').addEventListener('click', () => {
        document.getElementById('admin-entrant-form').reset();
        document.getElementById('admin-entry-id').value = '';
      });

      // Voting Toggle State
      document.getElementById('toggle-voting-state-btn').addEventListener('click', () => {
        isVotingOpen = !isVotingOpen;
        saveState();
        renderAll();
        showToast(isVotingOpen ? 'Voting OPEN' : 'Voting CLOSED & Bigfoot Champions Revealed!', isVotingOpen ? 'info' : 'success');
      });

      // Admin Save Form (Number & Name Only)
      document.getElementById('admin-entrant-form').addEventListener('submit', (e) => {
        e.preventDefault();
        const existingId = document.getElementById('admin-entry-id').value;

        if (existingId) {
          const idx = entrants.findIndex(i => i.id === existingId);
          if (idx !== -1) {
            entrants[idx].number = document.getElementById('form-entry-num').value.trim();
            entrants[idx].name = document.getElementById('form-chili-name').value.trim();
            showToast('Entry updated!', 'success');
          }
        } else {
          const newEntry = {
            id: 'sq_' + Date.now(),
            number: document.getElementById('form-entry-num').value.trim(),
            name: document.getElementById('form-chili-name').value.trim(),
            votesCount: 0,
            sumScore: 0
          };
          entrants.push(newEntry);
          showToast('New Sasquatch chili added!', 'success');
        }

        document.getElementById('admin-entrant-form').reset();
        document.getElementById('admin-entry-id').value = '';
        saveState();
        renderAll();
        renderAdminManageList();
      });

      // Admin Reset All
      document.getElementById('admin-reset-all').addEventListener('click', () => {
        if (confirm('Reset to initial sample entries?')) {
          localStorage.removeItem(STORAGE_ENTRANTS_KEY);
          localStorage.removeItem(STORAGE_FAVS_KEY);
          localStorage.removeItem(STORAGE_MY_VOTES_KEY);
          localStorage.removeItem(STORAGE_STATE_KEY);
          entrants = [...INITIAL_ENTRANTS];
          favorites = new Set();
          userVotes = {};
          isVotingOpen = true;
          saveState();
          renderAll();
          renderAdminManageList();
          showToast('Data reset to defaults', 'info');
        }
      });
    }

    // TOAST NOTIFICATIONS
    function showToast(message, type = 'success') {
      const container = document.getElementById('toast-container');
      const toast = document.createElement('div');

      const bgClass = type === 'success' ? 'bg-forest-900 border-amberfire-500 text-amberfire-300' : 'bg-bark-900 border-bark-700 text-emerald-200';

      toast.className = `flex items-center gap-2 px-3.5 py-2.5 rounded-xl border ${bgClass} shadow-2xl text-xs font-semibold backdrop-blur-md transition-all duration-300 transform translate-y-2 opacity-0`;
      toast.innerHTML = `<span>${message}</span>`;

      container.appendChild(toast);

      setTimeout(() => {
        toast.classList.remove('translate-y-2', 'opacity-0');
      }, 10);

      setTimeout(() => {
        toast.classList.add('opacity-0', 'translate-y-2');
        setTimeout(() => toast.remove(), 300);
      }, 3000);
    }
  </script>
</body>
</html>
