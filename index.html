<!DOCTYPE html>
<html lang="zh-TW">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
    <title>數學王國：道館挑戰</title>
    
    <script src="https://unpkg.com/react@18/umd/react.development.js" crossorigin></script>
    <script src="https://unpkg.com/react-dom@18/umd/react-dom.development.js" crossorigin></script>
    <script src="https://unpkg.com/@babel/standalone/babel.min.js"></script>
    <script src="https://cdn.tailwindcss.com"></script>

    <style>
        @import url('https://fonts.googleapis.com/css2?family=Noto+Sans+TC:wght=400;700&family=Press+Start+2P&display=swap');

        body {
            font-family: 'Noto Sans TC', sans-serif;
            background-color: #1a1a1a;
            overflow: hidden;
            user-select: none;
            touch-action: manipulation;
        }
        
        .pixel-font { font-family: 'Press Start 2P', cursive; }

        /* VFX Animations */
        @keyframes fire-burst { 0% { transform: scale(0); opacity: 1; } 50% { opacity: 0.8; } 100% { transform: scale(3); opacity: 0; } }
        @keyframes water-stream { 0% { width: 0; opacity: 0.8; transform: rotate(-45deg); } 100% { width: 150%; opacity: 0; transform: rotate(-45deg) translate(-100px, -100px); } }
        @keyframes thunder-bolt { 0% { height: 0; opacity: 1; } 50% { height: 100%; opacity: 1; } 100% { height: 100%; opacity: 0; } }
        @keyframes leaf-spin { 0% { transform: translate(0, 0) rotate(0deg); opacity: 1; } 100% { transform: translate(100px, 100px) rotate(720deg); opacity: 0; } }
        @keyframes shockwave { 0% { transform: scale(0.1); border-width: 20px; opacity: 1; } 100% { transform: scale(2); border-width: 0px; opacity: 0; } }
        @keyframes shake-anim { 0%, 100% { transform: translateX(0); } 25% { transform: translateX(-15px); } 75% { transform: translateX(15px); } }

        .anim-fire { animation: fire-burst 0.6s ease-out forwards; }
        .anim-water { animation: water-stream 0.5s cubic-bezier(0.1, 0.7, 1.0, 0.1) forwards; }
        .anim-thunder-bolt { animation: thunder-bolt 0.3s ease-out forwards; }
        .anim-leaf { animation: leaf-spin 0.8s ease-out forwards; }
        .anim-shockwave { animation: shockwave 0.6s ease-out forwards; }

        /* Pokemon Animations */
        .monster-idle { animation: float 3s ease-in-out infinite; }
        .animate-shake { animation: shake-anim 0.3s ease-in-out; }
        @keyframes float { 0%, 100% { transform: translateY(0); } 50% { transform: translateY(-10px); } }

        .game-screen {
            max-width: 600px; margin: 0 auto; height: 100dvh;
            display: flex; flex-direction: column; background: #2d3748;
            position: relative; box-shadow: 0 0 40px rgba(0,0,0,0.7);
        }
        
        .hp-container {
            background: rgba(0, 0, 0, 0.7);
            backdrop-filter: blur(2px);
            border: 2px solid #fff;
            border-radius: 8px;
            padding: 4px 8px;
            width: 200px; 
            margin-bottom: 4px;
            box-shadow: 0 4px 6px rgba(0,0,0,0.5);
        }
    </style>
</head>
<body>
    <audio id="bg-music" loop src="https://assets.mixkit.co/music/preview/mixkit-games-world-tracks-1319.mp3"></audio>

    <div id="root"></div>

    <script type="text/babel">
        const { useState, useEffect, useRef } = React;

        // --- Backgrounds ---
        const bgImages = {
            forest: "https://img.freepik.com/free-vector/hand-drawn-flat-design-forest-landscape_23-2149157285.jpg", 
            city: "https://img.freepik.com/free-vector/nature-landscape-with-road-city-horizon-trees-clouds-sky-summer-scene-with-empty-highway-green-fields-road-sign-town-buildings-vector-cartoon-illustration_107791-21641.jpg", 
            sky: "https://img.freepik.com/free-vector/blank-sky-night-scene-with-blank-flood-landscape_1308-60757.jpg"
        };

        const gyms = [
            { id: 1, monsterId: 150, name: "超夢", title: "神秘森林道館", bg: bgImages.forest },
            { id: 2, monsterId: 249, name: "洛奇亞", title: "歡樂市區道館", bg: bgImages.city },
            { id: 3, monsterId: 384, name: "烈空坐", title: "天空之城道館", bg: bgImages.sky }
        ];

        // --- 三位數讀法精選題庫 ---
        const questionDeck = [
            { q: "請輸入數字「246」的中文讀作什麼？", a: "二百四十六" },
            { q: "請輸入數字「358」的中文讀作什麼？", a: "三百五十八" },
            { q: "數字「682」應該怎麼唸呢？", a: "六百八十二" },
            { q: "數字「195」應該怎麼唸呢？", a: "一百九十五" },
            { q: "請輸入數字「409」的正確讀法：", a: "四百零九" },
            { q: "請輸入數字「802」的正確讀法：", a: "八百零二" },
            { q: "數字「503」中間有零，要怎麼唸？", a: "五百零三" },
            { q: "數字「701」中間有零，要怎麼唸？", a: "七百零一" },
            { q: "請輸入數字「780」的中文讀法（注意末尾不讀零）：", a: "七百八十" },
            { q: "請輸入數字「320」的中文讀法：", a: "三百二十" },
            { q: "數字「920」的尾巴有零，應該讀作什麼？", a: "九百二十" },
            { q: "數字「460」的尾巴有零，應該讀作什麼？", a: "四百六十" },
            { q: "請輸入數字「500」的正確中文讀法：", a: "五百" },
            { q: "請輸入數字「617」的中文讀法（注意十位數的一要讀出來）：", a: "六百一十七" },
            { q: "數字「800」的尾巴有兩個零，應該讀作什麼？", a: "八百" },
            { q: "請輸入數字「115」的正確完整讀法：", a: "一百一十五" },
            { q: "請輸入數字「910」的正確完整讀法：", a: "九百一十" },
            { q: "數字「306」應該怎麼唸呢？", a: "三百零六" },
            { q: "數字「250」應該怎麼唸呢？", a: "二百五十" },
            { q: "挑戰最後一題！數字「107」要怎麼唸？", a: "一百零七" }
        ];

        // --- Move Database ---
        const moveDatabase = {
            electric: [
                { name: "電擊", color: "bg-yellow-500" },
                { name: "十萬伏特", color: "bg-yellow-600" },
                { name: "電球", color: "bg-yellow-400" },
                { name: "打雷", color: "bg-yellow-700" }
            ],
            fire: [
                { name: "火花", color: "bg-red-500" },
                { name: "火焰輪", color: "bg-red-600" },
                { name: "噴射火焰", color: "bg-red-700" },
                { name: "大字爆炎", color: "bg-red-800" }
            ],
            water: [
                { name: "水槍", color: "bg-blue-500" },
                { name: "泡沫光線", color: "bg-blue-400" },
                { name: "衝浪", color: "bg-blue-600" },
                { name: "水炮", color: "bg-blue-700" }
            ],
            grass: [
                { name: "藤鞭", color: "bg-green-500" },
                { name: "飛葉快刀", color: "bg-green-600" },
                { name: "能量球", color: "bg-green-400" },
                { name: "陽光烈焰", color: "bg-green-700" }
            ]
        };

        const starterPool = [
            { id: 25, name: "皮卡丘", type: "electric" },
            { id: 6, name: "噴火龍", type: "fire" },
            { id: 9, name: "水箭龜", type: "water" },
            { id: 3, name: "妙蛙花", type: "grass" }
        ];

        const getSprite = (id, back=false) => 
            `https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-v/black-white/animated/${back ? 'back/' : ''}${id}.gif`;

        // --- 粵語發音核心函式 ---
        const speakCantonese = (text) => {
            if ('speechSynthesis' in window) {
                window.speechSynthesis.cancel(); 
                const utterance = new SpeechSynthesisUtterance(text);
                utterance.lang = 'zh-HK';
                utterance.rate = 1.0; 
                utterance.pitch = 1.0;
                window.speechSynthesis.speak(utterance);
            }
        };

        // --- 子組件：血條 ---
        const HPBar = ({ current, max, name }) => {
            const percentage = (current / max) * 100;
            const barColor = percentage > 50 ? 'bg-green-500' : percentage > 20 ? 'bg-yellow-500' : 'bg-red-500';
            return (
                <div className="hp-container text-white text-xs font-bold">
                    <div className="flex justify-between mb-1">
                        <span>{name}</span>
                        <span>{current}/{max} HP</span>
                    </div>
                    <div className="w-full bg-gray-700 h-2 rounded-full overflow-hidden border border-gray-500">
                        <div className={`h-full ${barColor} transition-all duration-300`} style={{ width: `${percentage}%` }}></div>
                    </div>
                </div>
            );
        };

        // --- 子組件：計時器 ---
        const Timer = ({ isActive, startTime }) => {
            const [seconds, setSeconds] = useState(0);
            useEffect(() => {
                let interval = null;
                if (isActive) {
                    interval = setInterval(() => {
                        setSeconds(Math.floor((Date.now() - startTime) / 1000));
                    }, 1000);
                }
                return () => clearInterval(interval);
            }, [isActive, startTime]);

            return (
                <div className="absolute top-3 left-3 bg-black/60 text-yellow-400 font-mono text-sm px-3 py-1 rounded-full border border-yellow-500 z-40 flex items-center gap-1 shadow-lg">
                    ⏱️ {seconds} 秒
                </div>
            );
        };

        // --- 子組件：特效動畫 ---
        const BattleVFX = ({ type, onComplete }) => {
            useEffect(() => {
                const timer = setTimeout(() => { onComplete(); }, 600);
                return () => clearTimeout(timer);
            }, [onComplete]);

            const effectClasses = {
                electric: "bg-yellow-300 anim-shockwave",
                fire: "bg-red-500 rounded-full anim-fire",
                water: "bg-blue-400 h-4 w-full absolute bottom-1/3 anim-water",
                grass: "bg-green-500 w-8 h-8 rounded-full anim-leaf"
            };

            return (
                <div className="absolute inset-0 z-20 flex items-center justify-center pointer-events-none overflow-hidden">
                    <div className={`w-16 h-16 opacity-0 ${effectClasses[type] || 'bg-white'}`}></div>
                </div>
            );
        };

        // --- 子組件：虛擬鍵盤 ---
        const Keypad = ({ onInput, onDelete, onEnter }) => {
            const keys = [
                "一", "二", "三", "百",
                "四", "五", "六", "十",
                "七", "八", "九", "個",
                "零", "退格", "清除"
            ];
            
            const handleKeyClick = (k) => {
                if (k === "退格") {
                    onDelete(false);
                } else if (k === "清除") {
                    onDelete(true);
                } else {
                    speakCantonese(k);
                    onInput(k);
                }
            };

            return (
                <div className="flex flex-col h-full gap-2">
                    <div className="grid grid-cols-4 gap-2 flex-1">
                        {keys.map((k) => {
                            let btnColor = "bg-gray-700 active:bg-gray-600 border-gray-800";
                            if (k === "退格" || k === "清除") {
                                btnColor = "bg-amber-700 active:bg-amber-800 border-amber-900";
                            } else if (["百", "十", "個", "零"].includes(k)) {
                                btnColor = "bg-indigo-700 active:bg-indigo-600 border-indigo-900";
                            }

                            return (
                                <button
                                    key={k}
                                    onClick={() => handleKeyClick(k)}
                                    className={`text-white text-lg md:text-xl font-bold rounded-xl shadow border-b-4 active:scale-95 active:border-b-0 transition-all flex items-center justify-center ${btnColor} ${k === "零" ? "col-span-2" : ""}`}
                                >
                                    {k}
                                </button>
                            );
                        })}
                    </div>
                    <button
                        onClick={onEnter}
                        className="w-full bg-emerald-600 hover:bg-emerald-500 active:bg-emerald-700 text-white font-bold py-3 rounded-xl text-lg shadow-md transition-all active:scale-[0.98] border-b-4 border-emerald-800 active:border-b-0"
                    >
                        💥 發動攻擊 (檢查答案)
                    </button>
                </div>
            );
        };

        // --- 主程式：Game 組件 ---
        const Game = () => {
            const [state, setState] = useState('intro'); 
            const [player, setPlayer] = useState(null);
            const [gymIdx, setGymIdx] = useState(0);
            const [deckIndex, setDeckIndex] = useState(0);
            const [input, setInput] = useState("");
            const [msg, setMsg] = useState("");
            const [mode, setMode] = useState('keypad'); 
            const [vfx, setVfx] = useState(null);
            const [shake, setShake] = useState(false);
            const [startTime, setStartTime] = useState(0);
            const [finalTime, setFinalTime] = useState(0);
            const [isMuted, setIsMuted] = useState(false);

            // 血量狀態
            const [pHP, setPHP] = useState(3);
            const [eHP, setEHP] = useState(3);

            // 音樂切換控制
            const toggleMusic = () => {
                const audio = document.getElementById('bg-music');
                if (audio) {
                    if (audio.paused) {
                        audio.play().catch(e => console.log("播放受限"));
                        setIsMuted(false);
                        audio.muted = false;
                    } else {
                        audio.muted = true;
                        setIsMuted(true);
                    }
                }
            };

            const startGame = (selectedStarter) => {
                const audio = document.getElementById('bg-music');
                if (audio && !isMuted) {
                    audio.play().catch(e => console.log("音樂自動播放受限"));
                }

                setPlayer(selectedStarter);
                setPHP(3);
                setEHP(3);
                setGymIdx(0);
                setDeckIndex(0);
                setInput("");
                setMsg("");
                setMode('keypad');
                setStartTime(Date.now());
                setState('battle');
            };

            const handleAnswer = () => {
                let currentQ = questionDeck[deckIndex % questionDeck.length];
                if (!currentQ) return;

                if (input.trim() === currentQ.a) {
                    setMode('move');
                    setMsg("答案正確！敵方防線崩潰，請點擊下方招式給予痛擊！");
                    speakCantonese("答對了");
                } else {
                    setShake(true);
                    setTimeout(() => setShake(false), 300);
                    setInput("");
                    setPHP(prev => {
                        const next = prev - 1;
                        if (next <= 0) {
                            setTimeout(() => setState('gameover'), 1500);
                            return 0;
                        }
                        return next;
                    });
                    setMsg(`讀音不對喔！正確讀法是「${currentQ.a}」。遭受反擊！`);
                    speakCantonese("答錯了");
                    setMode('wait');
                    setTimeout(() => {
                        setDeckIndex(i => i + 1);
                        setMsg("");
                        setMode('keypad');
                    }, 2500);
                }
            };

            const attack = (moveName) => {
                setMode('wait');
                setMsg(`${player.name} 使用了 ${moveName}！`);
                setVfx(player.type); 
                setInput("");
            };

            const onVfxEnd = () => {
                setVfx(null);
                setShake(true);
                setTimeout(() => setShake(false), 300);
                
                setEHP(prev => {
                    const next = prev - 1;
                    if (next <= 0) {
                        handleGymClear();
                        return 0;
                    } else {
                        setMsg("💥 命中要害！成功造成傷害！");
                        setDeckIndex(i => i + 1);
                        setTimeout(() => {
                            setMsg("");
                            setMode('keypad');
                        }, 1500);
                        return next;
                    }
                });
            };

            const handleGymClear = () => {
                setMsg(`🎉 太棒了！${gyms[gymIdx].name} 倒下了！成功突破此道館！`);
                setDeckIndex(i => i + 1);

                if (gymIdx < gyms.length - 1) {
                    setMode('wait');
                    setTimeout(() => {
                        setGymIdx(g => g + 1);
                        setEHP(3); 
                        setMsg(`🏁 踏入下一站目的地... ${gyms[gymIdx+1].title}！`);
                        setTimeout(() => {
                            setMsg("");
                            setMode('keypad');
                        }, 2000);
                    }, 2000);
                } else {
                    setFinalTime(Math.floor((Date.now() - startTime) / 1000));
                    setTimeout(() => setState('victory'), 2000);
                }
            };

            // --- Render ---

            if (state === 'intro') return (
                <div className="game-screen bg-gray-900 text-white items-center justify-center p-6 text-center">
                    <button onClick={toggleMusic} className="absolute top-4 right-4 bg-gray-800 p-2.5 rounded-full border border-gray-600 text-xl z-50">
                        {isMuted ? "🔇" : "🔊"}
                    </button>

                    <h1 className="text-3xl md:text-4xl text-yellow-400 pixel-font mb-4 leading-snug drop-shadow-lg animate-pulse">
                        數學王國<br/><span className="text-xl md:text-2xl text-white">三位數讀法挑戰</span>
                    </h1>
                    <p className="text-xs text-gray-400 max-w-xs mb-6">
                        請選擇你的寶可夢夥伴，聆聽正確的「中文讀數魔法（粵音）」擊碎道館守護獸吧！
                    </p>
                    <div className="text-gray-300 mb-4 font-bold text-sm">請選擇你的出戰夥伴：</div>
                    <div className="grid grid-cols-2 gap-3 w-full max-w-sm">
                        {starterPool.map(s => (
                            <button 
                                key={s.id} 
                                onClick={() => startGame(s)} 
                                className="bg-gray-800 p-3 rounded-xl border-2 border-gray-600 hover:border-yellow-400 hover:bg-gray-700 transition active:scale-95 flex flex-col items-center shadow-lg"
                            >
                                <img src={getSprite(s.id)} className="w-16 h-16 object-contain" alt={s.name} />
                                <div className="mt-1 font-bold text-sm text-yellow-300">{s.name}</div>
                                <div className="text-[10px] text-gray-400">屬性: {s.type}</div>
                            </button>
                        ))}
                    </div>
                </div>
            );

            if (state === 'battle') {
                const currentGym = gyms[gymIdx];
                let currentQ = questionDeck[deckIndex % questionDeck.length];

                return (
                    <div className="game-screen" style={{backgroundImage: `url(${currentGym.bg})`, backgroundSize: 'cover', backgroundPosition: 'center'}}>
                        {/* Timer */}
                        <Timer isActive={true} startTime={startTime} />

                        {/* 音樂控制按鈕 */}
                        <button onClick={toggleMusic} className="absolute top-3 right-32 bg-black/60 text-white p-1 px-2 rounded-full border border-gray-500 text-xs z-50 flex items-center gap-1">
                            {isMuted ? "🔇 靜音" : "🔊 音樂"}
                        </button>
                        
                        {/* VFX Overlay */}
                        {vfx && <BattleVFX type={vfx} onComplete={onVfxEnd} />}

                        {/* Battle Scene */}
                        <div className="flex-1 relative overflow-hidden">
                            <div className="absolute top-3 right-3 bg-blue-900/80 text-white text-[11px] font-bold px-3 py-1 rounded-md border border-blue-400 z-10 shadow">
                                🏰 {currentGym.title}
                            </div>

                            {/* Opponent */}
                            <div className={`absolute top-14 right-6 flex flex-col items-end transition-transform duration-100 ${shake ? 'animate-shake' : ''}`}>
                                <HPBar current={eHP} max={3} name={currentGym.name} />
                                <img src={getSprite(currentGym.monsterId)} className="w-28 h-28 md:w-36 md:h-36 object-contain drop-shadow-xl monster-idle" />
                            </div>

                            {/* Player */}
                            <div className={`absolute bottom-4 left-6 flex flex-col items-start transition-transform duration-100 ${shake ? 'animate-shake' : ''}`}>
                                <img src={getSprite(player.id, true)} className="w-28 h-28 md:w-36 md:h-36 object-contain drop-shadow-xl" />
                                <HPBar current={pHP} max={3} name={player.name} />
                            </div>
                        </div>

                        {/* UI Panel */}
                        <div className="bg-gray-900 border-t-4 border-yellow-500 p-3 rounded-t-3xl shadow-2xl h-[55%] md:h-[50%] flex flex-col z-30">
                            {/* Question/Message Box */}
                            <div className="bg-gray-800 p-2.5 rounded-lg border border-gray-600 mb-2 h-20 md:h-24 flex items-center justify-center text-center overflow-y-auto">
                                <span className="text-white font-bold text-sm md:text-base leading-relaxed px-1">
                                    {msg ? msg : (currentQ ? currentQ.q : "題目加載中...")}
                                </span>
                            </div>
                            
                            {/* Controls */}
                            <div className="flex-1">
                                {mode === 'keypad' && (
                                    <div className="h-full flex flex-col">
                                        <div className="bg-black text-green-400 font-mono text-base md:text-lg p-1.5 rounded mb-1.5 text-right tracking-widest border border-gray-700 h-10 flex items-center justify-end shadow-inner">
                                            {input || <span className="animate-pulse text-gray-600 text-sm">請按鍵輸入中文讀音_</span>}
                                        </div>
                                        <div className="flex-1">
                                            <Keypad 
                                                onInput={(k) => setInput(i => i + k)} 
                                                onDelete={(all) => setInput(i => all ? "" : i.slice(0, -1))}
                                                onEnter={handleAnswer} 
                                            />
                                        </div>
                                    </div>
                                )}
                                {mode === 'move' && (
                                    <div className="h-full flex flex-col justify-center animate-fade-in">
                                        <div className="text-yellow-400 font-bold text-center mb-2 text-xs md:text-sm animate-bounce">🎯 點擊招式釋放技能：</div>
                                        <div className="grid grid-cols-2 gap-2 flex-1 pb-1">
                                            {moveDatabase[player.type].map(m => (
                                                <button 
                                                    key={m.name} 
                                                    onClick={() => attack(m.name)} 
                                                    className={`${m.color} text-white rounded-xl font-bold text-base shadow-md border-b-4 border-black/30 active:scale-95 active:border-b-0 transition-all flex items-center justify-center`}
                                                >
                                                    ⚔️ {m.name}
                                                </button>
                                            ))}
                                        </div>
                                    </div>
                                )}
                                {mode === 'wait' && (
                                    <div className="h-full flex items-center justify-center">
                                        <div className="text-gray-400 text-sm md:text-base animate-pulse">
                                            ⏳ 數據計算與戰鬥處理中...
                                        </div>
                                    </div>
                                )}
                            </div>
                        </div>
                    </div>
                );
            }

            if (state === 'victory') return (
                <div className="game-screen bg-yellow-600 flex flex-col items-center justify-center text-white p-6 text-center relative overflow-hidden">
                    <div className="absolute inset-0 bg-yellow-500 opacity-30 animate-pulse"></div>
                    <div className="z-10 max-w-sm">
                        <h1 className="text-4xl md:text-5xl pixel-font mb-4 drop-shadow-xl text-yellow-200">VICTORY!</h1>
                        <p className="text-lg font-bold mb-2">🎉 恭喜你制霸所有數學道館！</p>
                        <p className="text-xs text-yellow-100 mb-6">你完美的掌握了三位數的讀法，全王國的人民都為你歡呼！</p>
                        <div className="text-xl font-mono bg-black/40 p-4 rounded-xl border-2 border-yellow-200 mb-8">
                            🏆 總通關耗時: <span className="text-yellow-300 font-bold">{finalTime}</span> 秒
                        </div>
                        <button 
                            onClick={() => window.location.reload()} 
                            className="bg-white text-yellow-800 px-8 py-3 rounded-full font-bold text-lg shadow-xl hover:scale-105 active:scale-95 transition-all border-4 border-yellow-300"
                        >
                            再次挑戰
                        </button>
                    </div>
                </div>
            );

            if (state === 'gameover') return (
                <div className="game-screen bg-gray-900 flex flex-col items-center justify-center text-white p-6 text-center">
                    <h1 className="text-4xl pixel-font text-red-500 mb-4 tracking-widest animate-pulse">GAME OVER</h1>
                    <p className="text-sm text-gray-400 max-w-xs mb-8">寶可夢體力耗盡了，吸取數字經驗後下次一定可以通關！</p>
                    <button 
                        onClick={() => window.location.reload()} 
                        className="bg-red-600 hover:bg-red-500 text-white px-8 py-3 rounded-full font-bold text-lg shadow-lg active:scale-95 transition-all"
                    >
                        重新開始 🔄
                    </button>
                </div>
            );

            return null;
        };

        const root = ReactDOM.createRoot(document.getElementById('root'));
        root.render(<Game />);
    </script>
</body>
</html>
