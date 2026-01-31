<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>KIM C 256 | Official Artist Store & Sound Box Studio</title>
  <script src="https://cdn.tailwindcss.com"></script>
  <link rel="preconnect" href="https://fonts.googleapis.com" />
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin />
  <link href="https://fonts.googleapis.com/css2?family=Oswald:wght@200;400;700&family=Inter:wght@300;400;700;900&display=swap" rel="stylesheet" />
  <style>
    body { font-family: 'Inter', sans-serif; }
    .oswald { font-family: 'Oswald', sans-serif; }
    @keyframes spin-slow { from { transform: rotate(0deg); } to { transform: rotate(360deg); } }
    .animate-spin-slow { animation: spin-slow 8s linear infinite; }
    @keyframes marquee { 0% { transform: translateX(0); } 100% { transform: translateX(-50%); } }
    .animate-marquee { animation: marquee 20s linear infinite; }
    ::selection { background: #dc2626; color: white; }
    .no-scrollbar::-webkit-scrollbar { display: none; }
    .no-scrollbar { -ms-overflow-style: none; scrollbar-width: none; }
  </style>
</head>
<body class="bg-white text-black antialiased">

<div id="root"></div>

<!-- React + ReactDOM CDN -->
<script src="https://unpkg.com/react@19/umd/react.development.js"></script>
<script src="https://unpkg.com/react-dom@19/umd/react-dom.development.js"></script>

<!-- Lucide Icons -->
<script src="https://cdn.jsdelivr.net/npm/lucide@0.475.0/dist/lucide.min.js"></script>

<script>
const { useState, useRef } = React;
const {
  Instagram, Facebook, Youtube, Music, ArrowRight, Play, Pause, Send, ShoppingBag, X, Menu, ChevronLeft, Plus, Minus, CheckCircle2
} = lucide;

// --- Constants & Data ---
const SOCIAL_LINKS = {
  instagram: 'https://instagram.com/kimc_ug',
  facebook: 'https://facebook.com/kimcugofficial',
  youtube: 'https://youtube.com/c/kimcug',
  soundcloud: 'https://soundcloud.com/kimcuganda'
};

const SERVICES = [
  { id: 'vocal-training', name: 'Vocal Training' },
  { id: 'song-writing', name: 'Song Writing' },
  { id: 'backing', name: 'Backing Vocals' },
  { id: 'mixing-mastering', name: 'Mixing & Mastering' },
  { id: 'production-lessons', name: 'Production Lessons' },
  { id: 'audio-production', name: 'Audio Production' }
];

const GENRES = ['AFRO', 'DANCEHALL', 'RAGGA', 'SOUL', 'ZOUK', 'HIPHOP'];

const PRODUCTS = [
  { id: '2025-1', name: 'Mbigatamu nga tebiwera', price: 150000, image: 'https://images.unsplash.com/photo-1459749411177-042180ceea72?auto=format&fit=crop&q=80&w=800', description: '2025 Afro-Dancehall anthem.', audioUrl: 'https://www.soundhelix.com/examples/mp3/SoundHelix-Song-1.mp3' },
  { id: '2025-2', name: 'Nkwagala Bisinga', price: 150000, image: 'https://images.unsplash.com/photo-1516280440614-37939bbacd81?auto=format&fit=crop&q=80&w=800', description: 'Soulful 2025 reggae ballad.', audioUrl: 'https://www.soundhelix.com/examples/mp3/SoundHelix-Song-2.mp3' }
];

// --- Components ---
function AnnouncementBar() {
  return (
    React.createElement('div', { className: "bg-red-600 text-white py-2 overflow-hidden whitespace-nowrap border-b border-red-700" },
      React.createElement('div', { className: "flex animate-marquee" },
        Array.from({length:10}).map((_,i) =>
          React.createElement('span', { key:i, className:"oswald font-black uppercase tracking-[0.3em] text-[10px] mx-12" },
            "BOOK YOUR SESSION: 0702838224 — SOUND BOX RECORDS KONGE POSTER ROAD — BEXX NATION GEAR RESTOCKED —"
          )
        )
      )
    )
  );
}

function MiniPlayer() {
  const [isPlaying, setIsPlaying] = useState(false);
  const audioRef = useRef(null);
  const track = { name: "Mbigatamu nga tebiwera", artist: "Kim*C" };
  const toggle = () => {
    if(isPlaying) audioRef.current.pause(); else audioRef.current.play();
    setIsPlaying(!isPlaying);
  };
  return (
    React.createElement('div', { className:"fixed bottom-6 left-6 z-[45] bg-black text-white p-4 shadow-2xl border border-white/10 flex items-center gap-4" },
      React.createElement('audio', { ref:audioRef, src:track.audioUrl }),
      React.createElement('button', { onClick:toggle, className:"w-12 h-12 bg-red-600 flex items-center justify-center hover:bg-white hover:text-red-600 transition-all" },
        isPlaying ? React.createElement(Pause, { size:20, fill:"currentColor" }) : React.createElement(Play, { size:20, fill:"currentColor", className:"ml-1" })
      ),
      React.createElement('div', { className:"pr-4" },
        React.createElement('p', { className:"text-[10px] font-black uppercase tracking-widest text-red-600" }, "Streaming Now"),
        React.createElement('p', { className:"oswald text-sm font-bold uppercase truncate max-w-[140px]" }, track.name)
      )
    )
  );
}

function Header({ cartCount, onCartToggle, onNavigate, currentPage }) {
  const [isMobileMenuOpen, setIsMobileMenuOpen] = useState(false);
  const navItems = [ { id:'home', label:'Home'}, {id:'shop', label:'Vault'}, {id:'studio', label:'Sound Box'}, {id:'about', label:'Story'} ];
  return (
    React.createElement('header', { className:"fixed top-0 left-0 right-0 z-50 bg-white/80 backdrop-blur-xl border-b border-gray-100" },
      React.createElement('div', { className:"max-w-7xl mx-auto px-6 h-20 flex items-center justify-between" },
        React.createElement('button', { onClick:()=>onNavigate('home'), className:"oswald text-3xl font-black uppercase tracking-tighter" }, "KIM", React.createElement('span',{className:"text-red-600"},"*C")),
        React.createElement('nav', { className:"hidden md:flex items-center space-x-10" },
          navItems.map(item =>
            React.createElement('button', { key:item.id, onClick:()=>onNavigate(item.id), className:`text-[10px] font-black uppercase tracking-[0.3em] transition-colors ${currentPage===item.id?'text-red-600':'text-gray-400 hover:text-black'}` }, item.label)
          )
        ),
        React.createElement('div', { className:"flex items-center space-x-6" },
          React.createElement('button', { onClick:onCartToggle, className:"relative p-2 hover:bg-gray-50 rounded-full transition-colors" },
            React.createElement(ShoppingBag, { size:20 }),
            cartCount>0 && React.createElement('span', { className:"absolute top-0 right-0 bg-red-600 text-white text-[9px] font-black w-5 h-5 flex items-center justify-center rounded-full border-2 border-white shadow-sm" }, cartCount)
          ),
          React.createElement('button', { onClick:()=>setIsMobileMenuOpen(!isMobileMenuOpen), className:"md:hidden p-2 hover:bg-gray-50 rounded-full" }, isMobileMenuOpen ? React.createElement(X,{size:20}) : React.createElement(Menu,{size:20}))
        )
      ),
      isMobileMenuOpen && React.createElement('div', { className:"md:hidden bg-white border-t border-gray-100 p-6 space-y-6" },
        navItems.map(item =>
          React.createElement('button', { key:item.id, onClick:()=>{onNavigate(item.id); setIsMobileMenuOpen(false)}, className:`block w-full text-left oswald text-4xl font-black uppercase tracking-tight ${currentPage===item.id?'text-red-600':'text-black'}` }, item.label)
        )
      )
    )
  );
}

// --- Home Page ---
function HomePage({ onNavigate }) {
  return (
    React.createElement('div', { className:"space-y-0" },
      React.createElement('section', { className:"relative h-[95vh] bg-black overflow-hidden flex items-center justify-center pt-20" },
        React.createElement('img',{src:'https://images.unsplash.com/photo-1598488035139-bdbb2231ce04?auto=format&fit=crop&q=80&w=2000', className:"absolute inset-0 w-full h-full object-cover opacity-50 grayscale"}),
        React.createElement('div', { className:"absolute inset-0 bg-gradient-to-t from-black via-transparent to-black" }),
        React.createElement('div', { className:"relative z-10 w-full max-w-7xl px-6 flex flex-col lg:flex-row items-center gap-16" },
          React.createElement('div', { className:"w-full lg:w-1/2 flex justify-center" },
            React.createElement('div', { className:"relative p-2 bg-white shadow-2xl transform -rotate-2 group" },
              React.createElement('img', { src:'https://images.unsplash.com/photo-1516280440614-37939bbacd81?auto=format&fit=crop&q=80&w=1200', className:"w-full aspect-[3/4] object-cover border-[8px] border-black grayscale group-hover:grayscale-0 transition-all duration-700" })
            )
          ),
          React.createElement('div', { className:"w-full lg:w-1/2 space-y-12 text-center lg:text-left text-white" },
            React.createElement('div', { className:"space-y-4" },
              React.createElement('p', { className:"oswald text-sm font-bold tracking-[0.6em] text-red-600 uppercase" }, "Producer Kim C Presents"),
              React.createElement('h1', { className:"oswald text-8xl md:text-[10rem] font-black uppercase tracking-tighter leading-[0.8]" }, "SOUND BOX", React.createElement('br',{}), React.createElement('span', {className:"text-red-600 italic"}, "RECORDS"))
            ),
            React.createElement('button', { onClick:()=>onNavigate('studio'), className:"bg-red-600 text-white px-12 py-7 font-black uppercase tracking-widest text-xs hover:bg-white hover:text-red-600 transition-all active:scale-95 shadow-2xl" },
              "BOOK YOUR SESSION ", React.createElement(ArrowRight,{size:18})
            )
          )
        )
      )
    )
  );
}

// --- App ---
function App() {
  const [currentPage, setCurrentPage] = useState('home');
  const [cartItems, setCartItems] = useState([]);
  const cartCount = cartItems.reduce((sum, i)=>sum+i.quantity,0);

  const navigateTo = (page) => { setCurrentPage(page); window.scrollTo(0,0); };
  return (
    React.createElement('div', { className:"min-h-screen bg-white" },
      React.createElement('div', { className:"fixed top-0 left-0 right-0 z-50" },
        React.createElement(AnnouncementBar,{}),
        React.createElement(Header,{cartCount, onCartToggle:()=>{}, onNavigate:navigateTo, currentPage})
      ),
      React.createElement('main',{} , currentPage==='home' && React.createElement(HomePage,{onNavigate:navigateTo})),
      React.createElement(MiniPlayer,{})
    )
  );
}

// --- Render ---
ReactDOM.createRoot(document.getElementById('root')).render(React.createElement(App));
</script>

</body>
</html>
