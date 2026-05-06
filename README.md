
Action: file_editor str_replace /app/frontend/src/App.js --old-str "const YT_VIDEO_ID = "vSYzilP-bnQ"; // Yung Lean — Ginseng Strip 2002

function MusicBox() {
const [playing, setPlaying] = useState(false);
const toggle = () => setPlaying((p) => !p);
return (
<section className="section music" data-testid="music-section">
<div className="music-card">
<div className="vinyl" data-spinning={playing ? "true" : "false"}>
<div className="vinyl-inner" />
</div>
<div className="music-info">
<span className="kicker">— bizim şarkımız</span>
<h3>Ginseng Strip 2002</h3>
<p>
Yung Lean. Aşağıdaki butona bas, sayfa bu şarkıyla daha güzel
kokmaya başlasın.
</p>
<button
className="btn btn-primary"
onClick={toggle}
data-testid="music-toggle-btn"
>
{playing ? <Pause size={16} /> : <Music2 size={16} />}
{playing ? "Duraklat" : "Çal"}
</button>
</div>
</div>
{playing && (
<iframe
title="background-music"
className="yt-hidden"
src={https://www.youtube.com/embed/${YT_VIDEO_ID}?autoplay=1&loop=1&playlist=${YT_VIDEO_ID}&controls=0&modestbranding=1&playsinline=1}
allow="autoplay; encrypted-media"
data-testid="yt-iframe"
/>
)}
</section>
);
}" --new-str "const YT_VIDEO_ID = "vSYzilP-bnQ"; // Yung Lean — Ginseng Strip 2002

function MusicBox({ playing, setPlaying }) {
const toggle = () => setPlaying((p) => !p);
return (
<section className="section music" data-testid="music-section">
<div className="music-card">
<div className="vinyl" data-spinning={playing ? "true" : "false"}>
<div className="vinyl-inner" />
</div>
<div className="music-info">
<span className="kicker">— bizim şarkımız</span>
<h3>Ginseng Strip 2002</h3>
<p>
Yung Lean. Sayfaya girer girmez çalmaya başlar; sessiz olursa
herhangi bir yere bir kez dokun, gelir.
</p>
<button
className="btn btn-primary"
onClick={toggle}
data-testid="music-toggle-btn"
>
{playing ? <Pause size={16} /> : <Music2 size={16} />}
{playing ? "Duraklat" : "Çal"}
</button>
</div>
</div>
</section>
);
}"
Observation: Edit was successful.

Site yap
