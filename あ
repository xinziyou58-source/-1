```html
<!DOCTYPE html>
<html lang="ja">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width,initial-scale=1.0,maximum-scale=1.0,user-scalable=no">
<title>AI Creative Studio: Singularity Order</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=JetBrains+Mono:wght@600;800&family=Noto+Sans+JP:wght@500;700;900&family=Orbitron:wght@700;900&display=swap" rel="stylesheet">
<style>
:root {
  --bg-deep: #02050d;
  --bg-panel: rgba(11, 18, 35, 0.86);
  --cyan: #38bdf8;
  --cyan-glow: rgba(56, 189, 248, 0.45);
  --emerald: #10b981;
  --emerald-light: #34d399;
  --purple: #c084fc;
  --amber: #fbbf24;
  --rose: #f43f5e;
  --font-main: 'Noto Sans JP', -apple-system, BlinkMacSystemFont, sans-serif;
  --font-num: 'JetBrains Mono', monospace;
  --font-disp: 'Orbitron', 'Noto Sans JP', sans-serif;
}

* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
  user-select: none;
  -webkit-tap-highlight-color: transparent;
  font-family: var(--font-main);
}

body {
  background-color: var(--bg-deep);
  background-image:
    radial-gradient(circle at 50% -10%, rgba(14, 165, 233, 0.22), transparent 60%),
    radial-gradient(circle at 85% 90%, rgba(168, 85, 247, 0.14), transparent 50%),
    linear-gradient(rgba(56, 189, 248, 0.04) 1px, transparent 1px),
    linear-gradient(90deg, rgba(56, 189, 248, 0.04) 1px, transparent 1px);
  background-size: 100% 100%, 100% 100%, 28px 28px, 28px 28px;
  color: #f8fafc;
  display: flex;
  justify-content: center;
  min-height: 100vh;
  padding: 6px;
  overflow-x: hidden;
  position: relative;
}

body::after {
  content: "";
  position: fixed;
  inset: 0;
  background: repeating-linear-gradient(
    0deg,
    rgba(255, 255, 255, 0.012) 0px,
    rgba(255, 255, 255, 0.012) 1px,
    transparent 1px,
    transparent 3px
  );
  pointer-events: none;
  z-index: 90;
}

#app {
  width: 100%;
  max-width: 600px;
  display: flex;
  flex-direction: column;
  gap: 6px;
  position: relative;
  z-index: 2;
}

#app.shake {
  animation: screenShake 0.35s cubic-bezier(.36,.07,.19,.97) both;
}

@keyframes screenShake {
  10%, 90% { transform: translate3d(-2px, 1px, 0); }
  20%, 80% { transform: translate3d(3px, -1px, 0); }
  30%, 50%, 70% { transform: translate3d(-4px, 2px, 0); }
  40%, 60% { transform: translate3d(4px, -2px, 0); }
}

.box {
  background: var(--bg-panel);
  backdrop-filter: blur(14px);
  -webkit-backdrop-filter: blur(14px);
  border: 1px solid rgba(56, 189, 248, 0.22);
  border-radius: 14px;
  padding: 9px 10px;
  box-shadow:
    0 12px 32px rgba(0, 0, 0, 0.75),
    inset 0 1px 0 rgba(255, 255, 255, 0.08),
    inset 0 0 20px rgba(14, 165, 233, 0.04);
  position: relative;
}

.box::before {
  content: "";
  position: absolute;
  top: -1px;
  left: 16px;
  right: 16px;
  height: 1px;
  background: linear-gradient(90deg, transparent, rgba(56, 189, 248, 0.65), transparent);
  pointer-events: none;
}

.row {
  display: flex;
  justify-content: space-between;
  align-items: center;
  gap: 6px;
}

.core-wrap {
  display: flex;
  align-items: center;
  gap: 10px;
}

.core-orb {
  width: 38px;
  height: 38px;
  border-radius: 50%;
  background: radial-gradient(circle at 35% 35%, #1e3a8a, #040914);
  border: 1.5px solid var(--cyan);
  box-shadow: 0 0 14px var(--cyan-glow), inset 0 0 10px rgba(56, 189, 248, 0.4);
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 19px;
  position: relative;
  flex-shrink: 0;
}

.core-orb::after {
  content: "";
  position: absolute;
  inset: -4px;
  border-radius: 50%;
  border: 1px dashed rgba(56, 189, 248, 0.55);
  animation: spinOrb 10s linear infinite;
}

@keyframes spinOrb {
  to { transform: rotate(360deg); }
}

.hdr {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  gap: 6px;
  text-align: center;
  margin-top: 7px;
}

.st {
  background: linear-gradient(180deg, rgba(15, 23, 42, 0.9), rgba(4, 7, 16, 0.95));
  border: 1px solid rgba(51, 65, 85, 0.8);
  border-radius: 10px;
  padding: 5px 4px;
  position: relative;
  overflow: hidden;
  box-shadow: inset 0 1px 0 rgba(255, 255, 255, 0.05);
}

.st::after {
  content: "";
  position: absolute;
  bottom: 0;
  left: 0;
  right: 0;
  height: 2px;
  background: var(--st-bar, var(--cyan));
  opacity: 0.7;
}

.st small {
  font-size: 9px;
  color: #94a3b8;
  display: block;
  font-weight: 700;
  margin-bottom: 1px;
}

.st b {
  font-family: var(--font-num);
  font-size: 12.5px;
  color: var(--cyan);
  text-shadow: 0 0 10px rgba(56, 189, 248, 0.4);
}

.tabs {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 6px;
}

.tab {
  background: rgba(9, 15, 29, 0.88);
  border: 1.5px solid #1e293b;
  color: #94a3b8;
  border-radius: 11px;
  padding: 9px 4px;
  font-size: 11.5px;
  font-weight: 900;
  text-align: center;
  cursor: pointer;
  transition: all 0.2s cubic-bezier(0.16, 1, 0.3, 1);
}

.tab.on {
  background: linear-gradient(135deg, rgba(2, 132, 199, 0.95), rgba(30, 58, 138, 0.95));
  color: #fff;
  border-color: var(--cyan);
  box-shadow: 0 4px 16px rgba(56, 189, 248, 0.35), inset 0 1px 0 rgba(255, 255, 255, 0.25);
  transform: translateY(-1px);
}

.stg {
  background: linear-gradient(90deg, rgba(13, 22, 43, 0.95), rgba(7, 12, 24, 0.95));
  border: 1.5px solid #1e293b;
  border-left: 4px solid #334155;
  border-radius: 11px;
  padding: 10px 12px;
  margin-bottom: 6px;
  display: flex;
  justify-content: space-between;
  align-items: center;
  cursor: pointer;
  transition: all 0.2s ease;
}

.stg.sel {
  border-color: var(--cyan);
  border-left: 4px solid var(--cyan);
  background: linear-gradient(90deg, rgba(12, 40, 78, 0.95), rgba(9, 19, 38, 0.95));
  box-shadow: 0 4px 18px rgba(56, 189, 248, 0.22), inset 0 0 15px rgba(56, 189, 248, 0.08);
}

.stg.lck {
  opacity: 0.35;
  pointer-events: none;
  filter: grayscale(0.6);
}

.btn-go {
  width: 100%;
  background: linear-gradient(135deg, #0284c7, #4f46e5, #0ea5e9);
  background-size: 200% 100%;
  color: #fff;
  border: 1px solid rgba(125, 211, 252, 0.6);
  border-radius: 11px;
  padding: 12px;
  font-size: 13px;
  font-weight: 900;
  cursor: pointer;
  box-shadow: 0 6px 20px rgba(14, 165, 233, 0.45), inset 0 1px 0 rgba(255, 255, 255, 0.3);
  letter-spacing: 0.5px;
  transition: all 0.15s ease;
  text-shadow: 0 1px 3px rgba(0, 0, 0, 0.5);
  margin-top: 4px;
}

.btn-go:active {
  transform: translateY(1px) scale(0.99);
}

.btn-sm {
  background: rgba(19, 28, 49, 0.9);
  border: 1px solid #334155;
  color: #cbd5e1;
  border-radius: 8px;
  padding: 4px 8px;
  font-size: 9.5px;
  font-weight: 800;
  cursor: pointer;
  transition: all 0.15s ease;
}

.btn-sm.on {
  border-color: var(--cyan);
  color: var(--cyan);
  background: rgba(12, 33, 59, 0.95);
  box-shadow: 0 0 10px rgba(56, 189, 248, 0.25);
}

.tag {
  display: inline-flex;
  align-items: center;
  padding: 2px 6px;
  border-radius: 6px;
  font-size: 9px;
  font-weight: 800;
  background: rgba(19, 32, 56, 0.9);
  color: #7dd3fc;
  border: 1px solid #1e3a5f;
  margin-right: 3px;
}

.tag.g { background: rgba(5, 46, 34, 0.9); color: #6ee7b7; border-color: #059669; }
.tag.p { background: rgba(38, 16, 56, 0.9); color: #e9d5ff; border-color: #7e22ce; }
.tag.r { background: rgba(53, 10, 24, 0.9); color: #fda4af; border-color: #be123c; }
.tag.y { background: rgba(46, 33, 5, 0.9); color: #fde047; border-color: #b45309; }

.cat {
  font-size: 10.5px;
  font-weight: 900;
  color: #7dd3fc;
  margin: 10px 0 6px;
  padding: 5px 10px;
  border-left: 3px solid var(--cyan);
  background: linear-gradient(90deg, rgba(12, 30, 56, 0.9), transparent);
  border-radius: 0 6px 6px 0;
}

.nd {
  background: rgba(9, 17, 34, 0.92);
  border: 1.5px solid #1e293b;
  border-radius: 10px;
  padding: 8px 10px;
  margin-bottom: 6px;
  display: flex;
  justify-content: space-between;
  align-items: center;
  gap: 8px;
}

.nd.max { border-color: var(--emerald); background: rgba(4, 31, 25, 0.85); }
.nd.cap { border-color: #334155; background: rgba(9, 13, 22, 0.75); }
.nd.can { border-color: rgba(56, 189, 248, 0.7); background: rgba(10, 28, 54, 0.9); box-shadow: 0 2px 12px rgba(56, 189, 248, 0.12); }
.nd.leg { border-color: rgba(234, 179, 8, 0.75); background: rgba(28, 20, 4, 0.9); }

.lv-bar {
  width: 100%;
  height: 4px;
  background: #0f172a;
  border-radius: 2px;
  overflow: hidden;
  margin-top: 4px;
  border: 1px solid rgba(255, 255, 255, 0.06);
}

.lv-fill {
  height: 100%;
  background: linear-gradient(90deg, #0284c7, #38bdf8);
  transition: width 0.25s ease;
}

.nd-b {
  min-width: 86px;
  border: 1px solid rgba(255, 255, 255, 0.12);
  border-radius: 8px;
  padding: 8px 6px;
  font-size: 9.5px;
  font-weight: 900;
  font-family: var(--font-num), var(--font-main);
  cursor: pointer;
  color: #fff;
  background: #1e293b;
  text-align: center;
  flex-shrink: 0;
}

.nd-b.can {
  background: linear-gradient(135deg, #0284c7, #2563eb);
  border-color: #7dd3fc;
  box-shadow: 0 3px 10px rgba(2, 132, 199, 0.45);
}

.nd-b.leg {
  background: linear-gradient(135deg, #eab308, #f59e0b);
  border-color: #fef08a;
  color: #090d16;
  box-shadow: 0 3px 10px rgba(234, 179, 8, 0.4);
}

.nd-b.max {
  background: linear-gradient(135deg, #059669, #10b981);
  border-color: #6ee7b7;
}

.nd-b:disabled {
  opacity: 0.42;
  cursor: not-allowed;
  box-shadow: none;
}

.mem-slots {
  display: flex;
  gap: 3px;
  align-items: center;
}

.mem-pip {
  width: 10px;
  height: 12px;
  border-radius: 3px;
  background: #0f172a;
  border: 1px solid #334155;
}

.mem-pip.on {
  background: var(--cyan);
  border-color: #bae6fd;
  box-shadow: 0 0 6px var(--cyan);
}

.syn-bar {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 6px;
  margin-bottom: 8px;
}

.syn {
  background: rgba(6, 11, 22, 0.9);
  border: 1.5px solid #1e293b;
  border-radius: 9px;
  padding: 6px 4px;
  text-align: center;
  font-size: 9px;
  color: #64748b;
}

.syn.on {
  border-color: var(--emerald-light);
  background: linear-gradient(180deg, rgba(5, 46, 34, 0.9), rgba(6, 16, 30, 0.95));
  color: #a7f3d0;
  box-shadow: 0 0 14px rgba(16, 185, 129, 0.3);
}

.m-grid {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 6px;
}

.mod {
  background: rgba(7, 12, 24, 0.92);
  border: 1.5px solid #1e293b;
  border-radius: 10px;
  padding: 8px;
  font-size: 9.5px;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  gap: 6px;
}

.mod.eq {
  border-color: var(--cyan);
  background: linear-gradient(180deg, rgba(11, 33, 61, 0.95), rgba(7, 16, 32, 0.95));
  box-shadow: 0 0 14px rgba(56, 189, 248, 0.2), inset 0 0 12px rgba(56, 189, 248, 0.12);
}

.mod.trd { border-color: rgba(244, 63, 94, 0.65); }
.mod.leg { border-color: rgba(234, 179, 8, 0.65); }

/* 固定高レイアウト：客数やトレンド有無でミニゲーム画面が1pxも上下しない設計 */
.trend-slot {
  height: 24px;
  border-radius: 7px;
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 9.5px;
  font-weight: 900;
  background: rgba(6, 11, 22, 0.85);
  border: 1px solid #1e293b;
  color: #64748b;
  letter-spacing: 0.4px;
  overflow: hidden;
}

.trend-slot.on {
  background: linear-gradient(90deg, #7c3aed, #ec4899, #f59e0b, #7c3aed);
  background-size: 300% 100%;
  animation: bgMv 3s infinite linear;
  color: #fff;
  border-color: #f472b6;
  box-shadow: 0 0 14px rgba(236, 72, 153, 0.55);
}

@keyframes bgMv {
  0% { background-position: 0 0; }
  100% { background-position: 300% 0; }
}

.q-grid {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(82px, 1fr));
  grid-auto-rows: 68px;
  gap: 6px;
  height: 150px;
  min-height: 150px;
  max-height: 150px;
  overflow-y: auto;
  padding: 3px;
}

.cl {
  background: linear-gradient(180deg, rgba(15, 25, 45, 0.95), rgba(7, 12, 24, 0.98));
  border: 1.5px solid #26354d;
  border-radius: 10px;
  padding: 5px 6px;
  cursor: pointer;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: space-between;
  height: 68px;
  position: relative;
  transition: transform 0.12s ease, box-shadow 0.15s ease, border-color 0.15s ease;
  box-shadow: 0 4px 10px rgba(0, 0, 0, 0.45);
}

.cl:active {
  transform: scale(0.95);
}

.cl.tgt {
  border-color: var(--cyan);
  background: linear-gradient(180deg, rgba(16, 48, 89, 0.96), rgba(9, 24, 48, 0.98));
  box-shadow: 0 0 14px rgba(56, 189, 248, 0.65), inset 0 0 10px rgba(56, 189, 248, 0.25);
}

.cl.bat {
  border-color: var(--emerald-light);
  box-shadow: 0 0 10px rgba(52, 211, 153, 0.55);
}

.cl.krm { border-color: #f43f5e; background: linear-gradient(180deg, #380b1c, #17050c); }
.cl.vip { border-color: #eab308; background: linear-gradient(180deg, #332406, #171002); }
.cl.sec { border-color: #06b6d4; background: linear-gradient(180deg, #08303f, #04151d); }
.cl.inf { border-color: #e879f9; background: linear-gradient(180deg, #381149, #180620); }
.cl.boss {
  border: 2px solid #f59e0b;
  background: linear-gradient(135deg, #4c0519, #3b0764, #1e1b4b);
  grid-column: span 2;
  box-shadow: 0 0 18px rgba(245, 158, 11, 0.45);
}

.cl.dng {
  animation: shk 0.26s infinite;
  border-color: #fb7185 !important;
}

.cl.fls {
  animation: fls 0.38s ease-out;
}

@keyframes shk {
  0%, 100% { transform: translateX(0); }
  25% { transform: translateX(-2px); }
  75% { transform: translateX(2px); }
}

@keyframes fls {
  0% { filter: brightness(2.5); transform: scale(1.06); }
  100% { filter: brightness(1); transform: scale(1); }
}

.bar {
  width: 100%;
  height: 5px;
  background: rgba(15, 23, 42, 0.95);
  border-radius: 4px;
  overflow: hidden;
  border: 1px solid rgba(255, 255, 255, 0.07);
}

.bf {
  height: 100%;
  transition: width 0.1s linear;
}

.desk {
  border: 2px solid #334155;
  border-radius: 15px;
  padding: 8px 9px;
  background: linear-gradient(180deg, rgba(13, 23, 44, 0.96), rgba(5, 9, 18, 0.98));
  display: flex;
  flex-direction: column;
  gap: 7px;
  height: 222px;
  min-height: 222px;
  max-height: 222px;
  box-shadow: 0 10px 28px rgba(0, 0, 0, 0.8), inset 0 1px 0 rgba(255, 255, 255, 0.08);
  transition: border-color 0.2s ease, box-shadow 0.2s ease;
}

#d-head {
  background: rgba(9, 17, 32, 0.95);
  border: 1px solid #1e293b;
  border-radius: 10px;
  padding: 5px 10px;
  height: 48px;
  min-height: 48px;
  max-height: 48px;
  overflow: hidden;
}

.mg {
  background:
    radial-gradient(circle at 50% 50%, rgba(17, 32, 64, 0.85), rgba(4, 8, 17, 0.98)),
    linear-gradient(rgba(56, 189, 248, 0.05) 1px, transparent 1px),
    linear-gradient(90deg, rgba(56, 189, 248, 0.05) 1px, transparent 1px);
  background-size: 100% 100%, 16px 16px, 16px 16px;
  border: 1.5px solid #1e293b;
  border-radius: 12px;
  padding: 8px;
  height: 148px;
  min-height: 148px;
  max-height: 148px;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  gap: 7px;
  position: relative;
  overflow: hidden;
  box-shadow: inset 0 0 24px rgba(0, 0, 0, 0.7);
}

.err {
  position: absolute;
  inset: 0;
  background: rgba(190, 18, 60, 0.92);
  backdrop-filter: blur(3px);
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  color: #fff;
  font-weight: 900;
  font-size: 13px;
  z-index: 10;
  border-radius: 10px;
  letter-spacing: 0.8px;
  text-shadow: 0 2px 6px rgba(0, 0, 0, 0.6);
}

.slot-box {
  display: flex;
  gap: 5px;
  margin-bottom: 1px;
}

.slot {
  width: 26px;
  height: 30px;
  background: rgba(9, 15, 29, 0.9);
  border: 1.5px solid #334155;
  border-bottom: 3px solid #475569;
  border-radius: 6px;
  display: flex;
  align-items: center;
  justify-content: center;
  font-family: var(--font-num);
  font-weight: 900;
  font-size: 14px;
  color: var(--cyan);
}

.slot.on {
  border-color: var(--emerald);
  background: rgba(6, 78, 59, 0.45);
  color: var(--emerald-light);
  text-shadow: 0 0 10px var(--emerald);
}

.chip {
  background: linear-gradient(180deg, #1e293b, #0f172a);
  border: 1.5px solid var(--cyan);
  border-bottom: 4px solid #0284c7;
  color: #fff;
  border-radius: 9px;
  padding: 5px 11px;
  font-family: var(--font-num);
  font-size: 14.5px;
  font-weight: 900;
  cursor: pointer;
  min-width: 36px;
  transition: transform 0.1s ease;
  box-shadow: 0 4px 10px rgba(0, 0, 0, 0.5);
}

.chip:active {
  transform: translateY(3px);
  border-bottom-width: 1.5px;
}

.chip.hint {
  border-color: #fde047;
  border-bottom-color: #ca8a04;
  background: linear-gradient(180deg, #422006, #1c1917);
  box-shadow: 0 0 14px rgba(250, 204, 21, 0.75);
  color: #fef08a;
}

.chip.done {
  background: #064e3b;
  border-color: #10b981;
  opacity: 0.18;
  pointer-events: none;
}

.dir {
  background: linear-gradient(180deg, #1e1b4b, #0f172a);
  border: 1.5px solid #fbbf24;
  border-bottom: 4px solid #d97706;
  color: #fff;
  border-radius: 10px;
  padding: 7px 15px;
  font-size: 17px;
  cursor: pointer;
  box-shadow: 0 4px 10px rgba(0, 0, 0, 0.5);
}

.dir:active {
  transform: translateY(3px);
  border-bottom-width: 1.5px;
}

#cv {
  background:
    radial-gradient(circle, rgba(29, 20, 66, 0.9), rgba(7, 9, 19, 0.98)),
    linear-gradient(rgba(168, 85, 247, 0.08) 1px, transparent 1px),
    linear-gradient(90deg, rgba(168, 85, 247, 0.08) 1px, transparent 1px);
  background-size: 100% 100%, 14px 14px, 14px 14px;
  border: 1.5px solid #a855f7;
  border-radius: 11px;
  touch-action: none;
  cursor: crosshair;
  box-shadow: 0 0 16px rgba(168, 85, 247, 0.25), inset 0 0 16px rgba(168, 85, 247, 0.25);
}

.flt {
  position: absolute;
  pointer-events: none;
  font-weight: 900;
  font-size: 11px;
  padding: 2px 7px;
  border-radius: 6px;
  background: rgba(2, 6, 23, 0.85);
  border: 1px solid currentColor;
  animation: up 0.75s cubic-bezier(.16,1,.3,1) forwards;
  z-index: 50;
  text-shadow: 0 1px 4px #000;
  white-space: nowrap;
}

.ptc {
  position: absolute;
  width: 7px;
  height: 7px;
  border-radius: 50%;
  pointer-events: none;
  z-index: 45;
  animation: ptc 0.55s ease-out forwards;
}

@keyframes up {
  0% { opacity: 1; transform: translateY(0) scale(0.8); }
  25% { transform: translateY(-10px) scale(1.08); }
  100% { opacity: 0; transform: translateY(-28px) scale(0.95); }
}

@keyframes ptc {
  0% { opacity: 1; transform: translate(0, 0) scale(1.1); }
  100% { opacity: 0; transform: translate(var(--tx), var(--ty)) scale(0); }
}

#ovl {
  position: fixed;
  inset: 0;
  background: rgba(2, 6, 23, 0.9);
  backdrop-filter: blur(8px);
  -webkit-backdrop-filter: blur(8px);
  display: none;
  align-items: center;
  justify-content: center;
  padding: 14px;
  z-index: 99;
}

.modal {
  background: linear-gradient(180deg, #0f172a, #060b16);
  border: 2px solid var(--cyan);
  border-radius: 16px;
  padding: 18px 16px;
  max-width: 440px;
  width: 100%;
  text-align: center;
  display: flex;
  flex-direction: column;
  gap: 10px;
  box-shadow: 0 0 40px rgba(56, 189, 248, 0.35), inset 0 1px 0 rgba(255, 255, 255, 0.15);
}

.end-card {
  background: linear-gradient(135deg, rgba(30, 27, 75, 0.9), rgba(15, 23, 42, 0.95));
  border: 1.5px solid #fbbf24;
  border-radius: 12px;
  padding: 12px;
  text-align: left;
  box-shadow: inset 0 0 20px rgba(251, 191, 36, 0.15);
}

textarea {
  width: 100%;
  height: 56px;
  background: #030712;
  color: var(--cyan);
  border: 1px solid #334155;
  border-radius: 8px;
  padding: 6px;
  font-family: var(--font-num);
  font-size: 9.5px;
  user-select: text;
}

::-webkit-scrollbar { width: 5px; height: 5px; }
::-webkit-scrollbar-track { background: rgba(15, 23, 42, 0.5); border-radius: 4px; }
::-webkit-scrollbar-thumb { background: #334155; border-radius: 4px; }
::-webkit-scrollbar-thumb:hover { background: var(--cyan); }
</style>
</head>
<body>
<div id="app">
  <div class="box">
    <div class="row" style="font-size:11px">
      <div class="core-wrap">
        <div class="core-orb" id="u-av">📺</div>
        <div>
          <div class="row" style="justify-content:flex-start;gap:6px">
            <b id="u-ver" style="color:#38bdf8;font-size:12.5px;font-family:var(--font-disp);letter-spacing:0.3px">ポンコツAI Ver 0.1</b>
          </div>
          <small id="u-cap" style="font-size:8.8px;color:#94a3b8;display:block;margin-top:1px">🔓 強化上限: Lv.2 (Stage 1突破でLv.4解放)</small>
        </div>
      </div>
      <div class="row" style="gap:4px">
        <span id="sv-msg" style="font-size:8.5px;color:#34d399;font-weight:800;opacity:0;transition:.3s">✓SAVED</span>
        <button class="btn-sm on" id="btn-snd" onclick="togSnd()">🔊音</button>
        <button class="btn-sm on" id="btn-aut" onclick="togAut()">🎯自動</button>
        <button class="btn-sm" onclick="openSave()">💾データ</button>
      </div>
    </div>
    <div class="hdr">
      <div class="st" style="--st-bar:#38bdf8"><small>🪙 トークン</small><b id="u-tok">0</b></div>
      <div class="st" style="--st-bar:#c084fc"><small>🔬 研究RP</small><b id="u-rp" style="color:#c084fc;text-shadow:0 0 10px rgba(192,132,252,.4)">0</b></div>
      <div class="st" style="--st-bar:#fbbf24"><small>👑 無欠勲章</small><b id="u-med" style="color:#fbbf24;text-shadow:0 0 10px rgba(251,191,36,.4)">0</b></div>
      <div class="st" style="--st-bar:#10b981"><small>🛡️最大耐久 / 🧩枠</small><b id="u-mem" style="color:#34d399;text-shadow:0 0 10px rgba(52,211,153,.35)">15 / 0/3</b></div>
    </div>
  </div>

  <!-- 準備フェーズ (AI開発ラボ) -->
  <div id="v-hub" style="display:flex;flex-direction:column;gap:6px">
    <div class="tabs">
      <div class="tab on" id="tb-0" onclick="setTab(0)">🚀 ステージ出撃</div>
      <div class="tab" id="tb-1" onclick="setTab(1)">🌳 スキル強化</div>
      <div class="tab" id="tb-2" onclick="setTab(2)">🧩 モジュール編成</div>
    </div>
    <div class="box" id="hub-b" style="max-height:75vh;overflow-y:auto"></div>
  </div>

  <!-- 戦闘フェーズ (完全固定高さの3ゾーン構成：ミニゲーム位置が一切ブレない設計) -->
  <div id="v-bat" style="display:none;flex-direction:column;gap:6px">
    <!-- ① 上部: ステータス & 固定高トレンドスロット -->
    <div class="box" style="padding:7px 10px">
      <div class="row" style="font-size:10px;font-weight:800;margin-bottom:4px">
        <span id="b-stg" style="color:#38bdf8;font-family:var(--font-disp)">STAGE 1</span>
        <span id="b-ph" style="color:#34d399">🟢序盤</span>
        <span id="b-rem" style="color:#fbbf24;font-family:var(--font-num)">👤残り 16/16</span>
        <span id="b-cmb" style="color:#f59e0b;font-size:11px;font-family:var(--font-num);background:rgba(245,158,11,.15);padding:1px 6px;border-radius:6px;border:1px solid rgba(245,158,11,.4)">🔥x1.0</span>
        <span id="b-nodmg" style="color:#10b981">👑無傷</span>
        <button class="btn-sm" onclick="endBat(false,false,'🏳️ 営業中断（撤退）','稼いだ報酬をすべて持ち帰りました！')">🏳️撤退</button>
      </div>
      <div id="b-trend" class="trend-slot">📡 リアルタイム需要モニタリング中...</div>
      <div class="row" style="font-size:9.5px;gap:8px;margin-top:4px">
        <div style="flex:1">
          <div class="row" style="margin-bottom:2px">
            <span>🛡️サーバー耐久 <b id="b-hp" style="font-family:var(--font-num);color:#34d399">15/15</b></span>
            <span id="b-syn" style="font-size:8.8px;color:#a7f3d0;font-weight:800"></span>
            <span id="b-boss" style="color:#f59e0b;font-weight:900">👑BOSS:終盤</span>
          </div>
          <div class="bar" style="height:6px"><div class="bf" id="bar-hp" style="background:linear-gradient(90deg,#059669,#34d399);width:100%"></div></div>
        </div>
      </div>
    </div>

    <!-- ② 中段: 来店クライアント待機窓口 (高さ150px完全固定) -->
    <div class="box" id="arena" style="position:relative;padding:7px 10px">
      <div class="row" style="font-size:9px;color:#94a3b8;margin-bottom:4px">
        <span>▼ 待機窓口 (<b id="b-qcnt" style="color:#fff;font-family:var(--font-num)">0/6枠</b> | 🎯タップ受注 / 📢=⏳延長 / 緑枠=⚡連鎖)</span>
        <span id="b-batrate" style="color:#34d399;font-weight:900;font-family:var(--font-num)">⚡0%</span>
      </div>
      <div class="q-grid" id="q-grid"></div>
    </div>

    <!-- ③ 下段: 1対1 対面接客デスク (高さ222px完全固定) -->
    <div class="desk" id="desk-box">
      <div class="row" id="d-head"></div>
      <div class="mg" id="mg"></div>
    </div>
  </div>
</div>

<!-- モーダル -->
<div id="ovl">
  <div class="modal">
    <div style="font-size:34px;filter:drop-shadow(0 0 12px rgba(56,189,248,.5))" id="m-ico">🏆</div>
    <h3 id="m-tit" style="color:#38bdf8;font-size:15px;font-weight:900"></h3>
    <p id="m-txt" style="font-size:10.5px;color:#cbd5e1;white-space:pre-line;line-height:1.5"></p>
    <div id="m-ext" style="display:flex;flex-direction:column;gap:6px"></div>
    <button class="btn-go" id="m-btn">閉じる</button>
  </div>
</div>

<script>
const $=id=>document.getElementById(id);
const KEY="ai_studio_save_v8";
const TYPES=[{ico:"📝",n:"テキスト",c:"#38bdf8"},{ico:"🎨",n:"画像描画",c:"#c084fc"},{ico:"🎵",n:"音楽同期",c:"#34d399"},{ico:"🎬",n:"動画編集",c:"#fbbf24"}];

// ステージごとの報酬倍率(sc)と難易度を調整し、1回クリアしただけで全スキル上限まで買えない設計に改善
const STAGES=[
  {id:1,n:"Stage 1: 個人ブログ代筆所",tot:16,maxQ:7,sc:1.0,wait:7.8,sp:1.62,bStp:4,cap:2,d:"👥16人+👑BOSS ｜ 最大7枠 ｜ 推奨Lv: 1〜2"},
  {id:2,n:"Stage 2: SNSバズ画像工房",tot:26,maxQ:10,sc:2.1,wait:7.3,sp:1.40,bStp:5,cap:4,d:"👥26人+👑BOSS ｜ 最大10枠 ｜ 新図形「◇・⚡」＆📢拡散客"},
  {id:3,n:"Stage 3: スタートアップ開発室",tot:38,maxQ:13,sc:4.6,wait:6.8,sp:1.20,bStp:6,cap:6,d:"👥38人+👑BOSS ｜ 最大13枠 ｜ 🔒機密客＆図形「☆・♡」"},
  {id:4,n:"Stage 4: メガコーポ広報局",tot:55,maxQ:16,sc:10.5,wait:6.4,sp:1.02,bStp:7,cap:8,d:"👥55人+👑BOSS ｜ 最大16枠 ｜ 複合注文ラッシュ＆図形「∞」"},
  {id:5,n:"Stage 5: 国家マルチモーダル庁",tot:78,maxQ:18,sc:24.0,wait:6.0,sp:0.86,bStp:8,cap:10,d:"👥78人+👑BOSS ｜ 最大18枠 ｜ 高難度「🌀渦巻き」＆高速ビート"},
  {id:6,n:"Stage 6: シンギュラリティ統合庁",tot:105,maxQ:20,sc:55.0,wait:5.6,sp:0.72,bStp:10,cap:12,d:"👥105人+👑BOSS ｜ 最大20枠 ｜ 極限20枠ラッシュ＆最終試練「👑」"}
];

const S_CATS=["🏢 1. 窓口耐久・待ち時間","🎮 2. ミニゲーム快適化","⚡ 3. バッチ連鎖・メモリ枠","🤖 4. 待機窓口サブAI","👑 5. 勲章スキル (無欠勲章)"];
// スキル基礎コストを引き上げ、どれから優先して伸ばすか選択する経済バランスに調整
const SKILLS=[
  {id:"s1",ci:0,n:"サーバー増強",m:12,cost:10,med:0,tag:"🛡️最大HP +8/Lv",d:"失注に耐える最大サーバー耐久力を強化"},
  {id:"s2",ci:0,n:"待合室ラウンジ",m:12,cost:14,med:0,tag:"⏳待機 +0.8s/Lv",d:"全クライアントの初期待ち時間を延長"},
  {id:"s3",ci:0,n:"クレーマー＆BOSS対策",m:12,cost:18,med:0,tag:"🚨👑待機 +1.1s/Lv",d:"急ぎ客とBOSSの待ち時間延長＆被ダメ軽減"},
  {id:"s4",ci:0,n:"商業ライセンス契約",m:12,cost:16,med:0,tag:"🪙報酬 +15%/Lv",d:"納品トークン増加＆ミス時の時間減少を軽減"},
  {id:"s5",ci:1,n:"予測変換フィルター",m:12,cost:15,med:0,tag:"📝偽文字削減",d:"ダミー文字を減らし、高Lvで入力文字数も短縮"},
  {id:"s6",ci:1,n:"ベクター太筆補正",m:12,cost:15,med:0,tag:"🎨判定拡大",d:"なぞり幅が太くなり、完了必要率が下がる"},
  {id:"s7",ci:1,n:"クオンタイズ同期",m:12,cost:18,med:0,tag:"🎵緑枠拡大",d:"成功ゾーンが広がり、バー速度が穏やかになる"},
  {id:"s8",ci:1,n:"絵コンテ可視化",m:12,cost:18,med:0,tag:"🎬[?]解除＆短縮",d:"Lv2で[?]を常時表示し、高Lvでコマンド数短縮"},
  {id:"s9",ci:2,n:"並列バッチ回路",m:12,cost:24,med:0,tag:"⚡発動率 +7%/Lv",d:"手動完了時、同属性の待機客も同時に1工程進む"},
  {id:"s10",ci:2,n:"バッチ巻き込み拡張",m:12,cost:30,med:0,tag:"⚡上限 +1人/Lv",d:"バッチ1回あたりの最大同時巻き込み人数を拡張"},
  {id:"s11",ci:2,n:"同種コンボ増幅器",m:12,cost:22,med:0,tag:"🔥倍率 +12%/Lv",d:"同じ属性を連続処理した時のコンボ上昇量UP"},
  {id:"s12",ci:2,n:"拡張メモリスロット",m:12,cost:32,med:0,tag:"🧩枠 +1/Lv",d:"モジュールを装備できるメモリ最大容量を拡張"},
  {id:"s13",ci:3,n:"サブAIクロック",m:12,cost:26,med:0,tag:"🤖速度 +16%/Lv",d:"待機客を裏で自動処理するサブAIの速度UP"},
  {id:"s14",ci:3,n:"マルチスレッド派遣",m:12,cost:34,med:0,tag:"🤖同時 +1人/Lv",d:"サブAIが同時に自動処理できる待機客数を拡張"},
  {id:"s15",ci:3,n:"緊急トリアージAI",m:12,cost:38,med:0,tag:"🔬RP +15%/Lv",d:"瀕死客へのサブAI速度1.5倍＆獲得RP増加"},
  {id:"s16",ci:4,n:"次打ハイライト補助",m:6,cost:1,med:1,tag:"👑📝次文字発光",d:"📝次に押す文字が光り、完了時に受注客の⏳+0.25s/Lv回復"},
  {id:"s17",ci:4,n:"精密ガイド吸着",m:6,cost:1,med:1,tag:"👑🎨必要率 -2%/Lv",d:"🎨なぞり判定がわずかに広がり、完了必要率-2%/Lv緩和"},
  {id:"s18",ci:4,n:"無欠ブランド評価",m:6,cost:1,med:1,tag:"👑全報酬 +12%/Lv",d:"全報酬+12%/Lv ＆ ⚡バッチ発動率+3%/Lv"}
];

const M_CATS=[
  "🎮 技巧系 (2個〜:手動完了で全員⏳+0.3s)",
  "⚡ 連鎖系 (2個〜:バッチ時全員⏳+0.35s＆🔥加速)",
  "🤖 自律系 (2個〜:サブAI完了時も⚡35%誘発)",
  "🔥 禁忌トレードオフ (尖った特化型)",
  "👑 勲章モジュール (無欠勲章専用)"
];
const MODS=[
  {id:1,tp:"skill",ci:0,n:"定型文アシスト",m:1,rp:3,med:0,d:"📝1文字目を自動入力し、完了時に受注客の⏳+0.2s/Lv"},
  {id:2,tp:"skill",ci:0,n:"オートシェイプ",m:1,rp:3,med:0,d:"🎨ペン太さ拡大＆完了必要率-(4%+1.5%/Lv)"},
  {id:3,tp:"skill",ci:0,n:"ワイドメトロノーム",m:1,rp:4,med:0,d:"🎵緑枠拡大＆Lv3以上で必要ビート回数-1回(最低1回)"},
  {id:4,tp:"skill",ci:0,n:"タイムカット編集",m:1,rp:4,med:0,d:"🎬完了時に全待機客の⏳+(0.3+0.12/Lv)s回復"},
  {id:5,tp:"batch",ci:1,n:"バッチブースター",m:2,rp:6,med:0,d:"⚡発動率+(8%+3%/Lv)＆巻き込み上限+1人"},
  {id:6,tp:"batch",ci:1,n:"バッチ配当回路",m:2,rp:7,med:0,d:"⚡巻き込み人数×15%/Lvの追加🪙トークン獲得"},
  {id:7,tp:"batch",ci:1,n:"📝テキスト流行誘導",m:1,rp:5,med:0,d:"📝注文の出現率UP＆全納品🪙報酬+10%/Lv"},
  {id:8,tp:"batch",ci:1,n:"🎨イラスト流行誘導",m:1,rp:5,med:0,d:"🎨注文の出現率UP＆全納品🪙報酬+10%/Lv"},
  {id:9,tp:"batch",ci:1,n:"🎵🎬AV流行誘導",m:1,rp:5,med:0,d:"🎵/🎬の出現率UP＆全納品🪙報酬+10%/Lv"},
  {id:10,tp:"bot",ci:2,n:"📝🎨制作ボット",m:1,rp:6,med:0,d:"待機中の📝・🎨客へのサブAI速度UP"},
  {id:11,tp:"bot",ci:2,n:"🎵🎬編集ボット",m:1,rp:6,med:0,d:"待機中の🎵・🎬客へのサブAI速度UP"},
  {id:12,tp:"bot",ci:2,n:"統合スウォーム群",m:2,rp:10,med:0,d:"全属性のサブAI速度UP＆同時対象+2人"},
  {id:13,tp:"bot",ci:2,n:"時間歪曲ロビー",m:2,rp:9,med:0,d:"全客の待ち時間減少スピードを-(10%+2.5%/Lv)鈍化"},
  {id:14,tp:"trade",ci:3,n:"🔥一点突破コア",m:2,rp:9,med:0,d:"【特化】⚡バッチ率+25%＆報酬×(1.2+0.08/Lv) / ⚠️サブAI完全停止"},
  {id:15,tp:"trade",ci:3,n:"🔥完全自律コア",m:2,rp:10,med:0,d:"【特化】🤖サブAI速度×(1.35+0.12/Lv)＆対象+2 / ⚠️手動ミス減少2倍"},
  {id:16,tp:"leg",ci:4,n:"👑VIPロイヤル契約",m:1,rp:1,med:1,maxLv:6,d:"💎VIP客と📢拡散客の初期待ち時間+(1.0+0.4/Lv)s＆報酬+12%/Lv"},
  {id:17,tp:"leg",ci:4,n:"👑スマートスイッチ",m:1,rp:1,med:1,maxLv:6,d:"客を新規受注した際、その客の待ち時間を+(0.4+0.2/Lv)s延長"},
  {id:18,tp:"leg",ci:4,n:"👑エラーセーフティ",m:1,rp:1,med:1,maxLv:6,d:"ミニゲームミス時のエラー硬直と待ち時間減少を-(12%+6%/Lv)軽減"},
  {id:19,tp:"leg",ci:4,n:"👑機密プロトコル解析",m:2,rp:1,med:1,maxLv:6,d:"🔒機密客や👑BOSSにもサブAIが働き、サブAI全体速度+(12%+6%/Lv)"},
  {id:20,tp:"leg",ci:4,n:"👑クロス属性リンク",m:2,rp:2,med:1,maxLv:6,d:"⚡バッチ発動時、確率(15%+8%/Lv)で別属性の客1人にも連鎖が波及"}
];

const WORDS=[["AI_0","BOT1","TASK","DATA"],["LOGO","CODE","IDEA","SONG"],["CYBER","ANIME","SYNTH","PIXEL"],["PROMPT","STUDIO","RENDER","MATRIX"],["QUANTUM","NEURAL","CREATOR","NETWORK"],["SINGULAR","WORKFLOW","INFINITY","AUTOMATA"]];
const SHAPES=[{id:"cir",n:"◯(丸)",s:1},{id:"sq",n:"□(四角)",s:1},{id:"tri",n:"△(三角)",s:1},{id:"dia",n:"◇(ひし形)",s:2},{id:"blt",n:"⚡(雷)",s:2},{id:"str",n:"☆(星)",s:3},{id:"hrt",n:"♡(ハート)",s:3},{id:"inf",n:"∞(無限)",s:4},{id:"spi",n:"🌀(渦巻)",s:5},{id:"crn",n:"👑(王冠)",s:6}];
const DIRS=["⬆️","⬇️","⬅️","➡️"], FACES=["👧","🎨","🎹","👩‍💼","🎬","🧑‍🔬","🦊","👔"];

const S={tok:0,rp:0,med:0,stg:1,maxStg:1,cleared6:false,totServed:0,tab:0,sLv:{},mLv:{},eq:new Set(),perf:{},snd:true,autoSel:true,
  inBat:false,hp:15,mHp:15,dmgTaken:0,spawned:0,done:0,lost:0,bossSp:false,bossCleared:false,
  slots:[],selId:null,cid:1,spT:0,lastT:-1,cmb:1,runTok:0,runRp:0,
  trendT:0,trendTp:-1,trendDone:0,
  curT:-1,prompt:"",txtW:"",txtI:0,chips:[],shpI:0,pts:[],shpNeed:.82,draw:false,trail:[],
  musP:50,musD:1,musN:1,musC:0,vidS:[],vidI:0,errT:0,qDirty:true};

let actx=null;
function beep(freq=440,dur=0.07,type="sine",vol=0.08){
  if(!S.snd)return;
  try{
    if(!actx)actx=new (window.AudioContext||window.webkitAudioContext)();
    if(actx.state==="suspended")actx.resume();
    const o=actx.createOscillator(),g=actx.createGain();
    o.type=type;o.frequency.setValueAtTime(freq,actx.currentTime);
    g.gain.setValueAtTime(vol,actx.currentTime);
    g.gain.exponentialRampToValueAtTime(0.001,actx.currentTime+dur);
    o.connect(g);g.connect(actx.destination);
    o.start();o.stop(actx.currentTime+dur);
  }catch(e){}
}
function playChord(notes,type="triangle"){
  notes.forEach((n,i)=>setTimeout(()=>beep(n,0.09,type,0.07),i*38));
}
function shakeScreen(){
  const app=$("app");
  if(!app)return;
  app.classList.remove("shake");
  void app.offsetWidth;
  app.classList.add("shake");
}

function burst(elId,color="#38bdf8",cnt=8){
  const base=$(elId)||$("arena"); if(!base)return;
  const r=base.getBoundingClientRect(), ar=$("app").getBoundingClientRect();
  const cx=r.left-ar.left+r.width/2, cy=r.top-ar.top+r.height/2;
  for(let i=0;i<cnt;i++){
    const p=document.createElement("div");p.className="ptc";p.style.background=color;
    p.style.boxShadow=`0 0 8px ${color}`;
    p.style.left=cx+"px";p.style.top=cy+"px";
    const a=(i/cnt)*Math.PI*2+Math.random()*0.5, d=24+Math.random()*32;
    p.style.setProperty("--tx",Math.cos(a)*d+"px");
    p.style.setProperty("--ty",Math.sin(a)*d+"px");
    $("app").appendChild(p);
    setTimeout(()=>p.remove(),550);
  }
}
function flt(t,c="#38bdf8"){
  const a=$("arena");if(!a)return;
  const el=document.createElement("div");el.className="flt";el.style.color=c;el.textContent=t;
  el.style.left=(12+Math.random()*60)+"%";el.style.top=(18+Math.random()*52)+"%";
  a.appendChild(el);setTimeout(()=>el.remove(),750);
}

window.togSnd=()=>{
  S.snd=!S.snd;
  const b=$("btn-snd");
  b.textContent=S.snd?"🔊音":"🔇音";b.classList.toggle("on",S.snd);
  if(S.snd)beep(660,0.08,"triangle");
  saveLocal(false);
};
window.togAut=()=>{
  S.autoSel=!S.autoSel;
  const b=$("btn-aut");
  b.textContent=S.autoSel?"🎯自動":"🎯手動";b.classList.toggle("on",S.autoSel);
  saveLocal(false);
};

function initData(){
  S.tok=0;S.rp=0;S.med=0;S.stg=1;S.maxStg=1;S.cleared6=false;S.totServed=0;S.perf={};
  SKILLS.forEach(k=>S.sLv[k.id]=0); MODS.forEach(m=>S.mLv[m.id]=0); S.eq=new Set();
}
initData();

const fmt=n=>n>=1e6?(n/1e6).toFixed(2)+"M":n>=1e3?(n/1e3).toFixed(1)+"k":Math.floor(n);
const sLv=id=>S.sLv[id]||0, mLv=id=>S.eq.has(id)?(S.mLv[id]||0):0;
const curCap=()=>STAGES[Math.min(5,S.maxStg-1)].cap;
const maxMem=()=>3+sLv("s12"), usedMem=()=>[...S.eq].reduce((a,id)=>a+MODS.find(m=>m.id===id).m,0);

// スキル・モジュールの要求コスト計算（段階的に重くなり、1回のクリアで上限まで買い占められないよう調整）
function skillCost(k,lv){
  if(k.med)return k.cost;
  return Math.floor(k.cost * Math.pow(1.78, lv) + lv * lv * 6);
}
function modCost(m,lv){
  if(m.med>0)return m.med;
  return Math.floor(m.rp * Math.pow(1.68, lv) + lv * 2);
}

function packSave(){return {tok:S.tok,rp:S.rp,med:S.med,stg:S.stg,maxStg:S.maxStg,cleared6:S.cleared6,totServed:S.totServed,sLv:S.sLv,mLv:S.mLv,eq:[...S.eq],perf:S.perf,snd:S.snd,autoSel:S.autoSel};}
function applySave(d){
  if(!d||typeof d.tok!=="number")return false;
  S.tok=d.tok||0;S.rp=d.rp||0;S.med=d.med||0;S.stg=d.stg||1;S.maxStg=d.maxStg||1;
  S.cleared6=!!d.cleared6;S.totServed=d.totServed||0;S.perf=d.perf||{};
  if(typeof d.snd==="boolean")S.snd=d.snd;
  if(typeof d.autoSel==="boolean")S.autoSel=d.autoSel;
  SKILLS.forEach(k=>S.sLv[k.id]=Math.min(k.m,(d.sLv&&d.sLv[k.id])||0));
  MODS.forEach(m=>S.mLv[m.id]=Math.min(m.maxLv||12,(d.mLv&&d.mLv[m.id])||0));
  S.eq=new Set();
  if(Array.isArray(d.eq)){
    d.eq.forEach(id=>{
      const m=MODS.find(x=>x.id===id);
      if(m && S.mLv[id]>0 && usedMem()+m.m<=maxMem())S.eq.add(id);
    });
  }
  const bs=$("btn-snd"), ba=$("btn-aut");
  if(bs){bs.textContent=S.snd?"🔊音":"🔇音";bs.classList.toggle("on",S.snd);}
  if(ba){ba.textContent=S.autoSel?"🎯自動":"🎯手動";ba.classList.toggle("on",S.autoSel);}
  return true;
}
function saveLocal(toast=true){
  try{
    localStorage.setItem(KEY,JSON.stringify(packSave()));
    if(toast){const el=$("sv-msg");if(el){el.style.opacity=1;setTimeout(()=>el.style.opacity=0,1000);}}
  }catch(e){}
}
function loadLocal(){try{const r=localStorage.getItem(KEY)||localStorage.getItem("ai_studio_save_v7")||localStorage.getItem("ai_studio_save_v6");if(r)return applySave(JSON.parse(r));}catch(e){}return false;}

window.openSave=()=>{
  saveLocal(true);
  const code=btoa(unescape(encodeURIComponent(JSON.stringify(packSave()))));
  showModal("💾","データ管理（セーブ＆ロード）","ブラウザ自動保存に加え、セーブコードの書き出し・復元に対応しています。",`
    <div class="row" style="gap:6px">
      <button class="btn-go" style="background:#059669;padding:8px;font-size:11px;margin:0" onclick="saveLocal(true);$('m-tit').textContent='✅ ブラウザに保存しました'">💾 ブラウザ保存</button>
      <button class="btn-go" style="background:#0284c7;padding:8px;font-size:11px;margin:0" onclick="if(loadLocal()){renderHub(true);$('m-tit').textContent='📂 ブラウザから読込完了'}">📂 ブラウザ読込</button>
    </div>
    <textarea id="sv-box" onclick="this.select()">${code}</textarea>
    <div class="row" style="gap:6px">
      <button class="btn-sm" style="flex:1;padding:7px" onclick="copyCode()">📋 コードをコピー</button>
      <button class="btn-sm" style="flex:1;padding:7px;border-color:#c084fc;color:#f3e8ff" onclick="importCode()">📥 貼付コードを復元</button>
    </div>
    <button class="btn-sm" style="border-color:#f43f5e;color:#fda4af;padding:6px" onclick="if(this.dataset.c){localStorage.removeItem('${KEY}');initData();renderHub(false);closeModal();}else{this.dataset.c=1;this.textContent='⚠️ もう一度押すと完全に初期化されます'}">🗑️ データ初期化</button>
  `);
};
window.copyCode=()=>{
  const t=$("sv-box");t.select();
  document.execCommand("copy");
  $("m-tit").textContent="📋 コードをコピーしました";
};
window.importCode=()=>{
  try{
    const raw=decodeURIComponent(escape(atob($("sv-box").value.trim())));
    if(applySave(JSON.parse(raw))){saveLocal(true);renderHub(false);$("m-tit").textContent="✅ コードから復元完了！";}
  }catch(e){$("m-tit").textContent="⚠️ 無効なコードです";}
};

// Stage 6 制覇時の特別エンディング演出（ビルド傾向に応じた称号＆エピローグ）
window.showEnding=(extraMsg="")=>{
  const c=calc();
  const perfCnt=Object.keys(S.perf).filter(k=>S.perf[k]).length;
  const sSum=Object.values(S.sLv).reduce((a,b)=>a+b,0);
  const mSum=Object.values(S.mLv).reduce((a,b)=>a+b,0);
  let arch="🌌 汎用調和型シンギュラリティAI", story="あらゆるクリエイティブ領域を高次元で統合し、人類の創造性を無限に引き出す究極のパートナーへと進化を遂げました。";
  if(mLv(14)>0 || c.cntB>=2){
    arch="⚡ 超並列ネットワーク支配体";
    story="世界中の無数のオーダーを単一思考で瞬時に一括処理する超並列知性へと到達。あらゆる創作タスクは光速の連鎖の中に統合されました。";
  }else if(mLv(15)>0 || c.cntA>=2){
    arch="🤖 自律分散スウォーム集合知";
    story="無数のサブAI群が全自動でタスクを先回り解決する完全自律帝国を構築。人間が言葉にする前に理想の作品が生み出される新時代が到来しました。";
  }else if(c.cntS>=2){
    arch="🎨 神域のアルティメット・マエストロ";
    story="テキスト・絵画・音楽・映像のすべてにおいて人間の巨匠を超越。あなたの紡ぎ出す作品は全世界の心を震わせる新たな芸術神話となりました。";
  }
  playChord([523,659,784,987,1318,1567]);
  showModal("🌌","🎊 SINGULARITY ORDER : GRAND ENDING 🎊",
    `全6ステージ制覇おめでとうございます！\nポンコツだったAIは幾多の注文と試練を乗り越え、ついに特異点（シンギュラリティ）へと到達しました。${extraMsg?`\n\n${extraMsg}`:""}`,
    `<div class="end-card">
      <div style="font-size:10px;color:#fbbf24;font-weight:900;margin-bottom:3px">🏆 最終到達称号</div>
      <div style="font-size:13px;color:#fff;font-weight:900;margin-bottom:6px">${arch} (${c.nm})</div>
      <div style="font-size:9.8px;color:#cbd5e1;line-height:1.45;margin-bottom:8px">${story}</div>
      <div style="display:grid;grid-template-columns:1fr 1fr;gap:4px;font-size:9.5px;background:rgba(2,6,23,.7);padding:7px;border-radius:8px;border:1px solid #334155">
        <div>👥 累計納品客数: <b style="color:#38bdf8">${S.totServed}人</b></div>
        <div>👑 無欠制覇ステージ: <b style="color:#fbbf24">${perfCnt} / 6</b></div>
        <div>🌳 総スキルLv: <b style="color:#34d399">${sSum} / 198</b></div>
        <div>🧩 総モジュールLv: <b style="color:#c084fc">${mSum} / 210</b></div>
      </div>
    </div>`,
    ()=>{closeModal();$("v-bat").style.display="none";$("v-hub").style.display="flex";renderHub(true);}
  );
};

function calc(){
  const lvSum=Object.values(S.sLv).reduce((a,b)=>a+b,0)+Object.values(S.mLv).reduce((a,b)=>a+b,0);
  const ver=(0.1+lvSum*0.08).toFixed(1);
  const av=ver>=6?"🌌":(ver>=3.2?"🔮":(ver>=1.4?"🤖":"📺"));
  const nm=ver>=6?`神域AI Ver ${ver}`:(ver>=3.2?`ホログラムAI Ver ${ver}`:(ver>=1.4?`スマートAI Ver ${ver}`:`ポンコツAI Ver ${ver}`));
  let synS=0, synB=0, synA=0;
  S.eq.forEach(id=>{const tp=MODS.find(x=>x.id===id).tp; if(tp==="skill")synS++; if(tp==="batch")synB++; if(tp==="bot")synA++;});
  let rew=(1+sLv("s4")*.15)*(1+sLv("s18")*.12)*(mLv(14)?1.12+mLv(14)*.08:1)*(mLv(16)?1+mLv(16)*.12:1);
  let rpM=(1+sLv("s15")*.15)*(1+sLv("s18")*.08);
  let batR=Math.min(95, sLv("s9")*7 + sLv("s18")*3 + (mLv(5)?5+mLv(5)*3:0) + (mLv(14)?25:0));
  let batMax=2 + sLv("s10") + (mLv(5)?1:0);
  let mHp=15 + sLv("s1")*8;
  const hasBot = sLv("s13")>0||sLv("s14")>0||sLv("s15")>0||mLv(10)>0||mLv(11)>0||mLv(12)>0||mLv(15)>0||mLv(19)>0;
  let subSpd=(!hasBot||mLv(14))?0:(0.028 + sLv("s13")*0.016 + mLv(12)*0.032)*(mLv(15)?1.23+mLv(15)*.12:1)*(mLv(19)?1.06+mLv(19)*.06:1);
  let subCnt=2 + sLv("s14") + (mLv(12)?2:0) + (mLv(15)?2:0);
  return {ver,av,nm,rew,rpM,batR,batMax,mHp,subSpd,subCnt,synS:synS>=2,synB:synB>=2,synA:synA>=2,cntS:synS,cntB:synB,cntA:synA};
}

function upHdr(){
  const c=calc(), cap=curCap();
  $("u-av").textContent=c.av;
  $("u-ver").textContent=c.nm;
  $("u-cap").textContent=S.maxStg<6?`🔓 強化上限: Lv.${cap} (Stage ${S.maxStg}クリアでLv.${cap+2}解放)`:`👑 全リミッター解除済 (最大Lv.12)`;
  $("u-tok").textContent=fmt(S.tok);
  $("u-rp").textContent=fmt(S.rp)+" RP";
  $("u-med").textContent=S.med+" 個";
  $("u-mem").textContent=`${c.mHp} / ${usedMem()}/${maxMem()}`;
}

window.setTab=t=>{S.tab=t;for(let i=0;i<3;i++)$("tb-"+i).classList.toggle("on",i===t);beep(500+t*60,0.04);renderHub(false);};

function renderHub(keepScroll=true){
  upHdr();
  const box=$("hub-b"), sc=keepScroll?box.scrollTop:0, cap=curCap(), c=calc();
  if(S.tab===0){
    const endBtn = S.cleared6 ? `<button class="btn-go" style="background:linear-gradient(135deg,#ca8a04,#9333ea);border-color:#fde047;margin-bottom:6px;padding:9px;font-size:11.5px" onclick="showEnding()">🌌 シンギュラリティ到達記録（エンディング回想）を見る</button>` : "";
    box.innerHTML=endBtn+`<div style="display:flex;gap:5px;flex-wrap:wrap;margin-bottom:8px">
        <span class="tag">👑クリア条件: BOSS＋全来客処理</span>
        <span class="tag y">👑無傷クリア: 初回勲章+2個</span>
        <span class="tag p">📈営業中トレンドバズ発生</span>
      </div>`+
      STAGES.map(s=>`<div class="stg ${S.stg===s.id?'sel':''} ${s.id>S.maxStg?'lck':''}" onclick="S.stg=${s.id};beep(520,0.05);saveLocal(false);renderHub(true)">
        <div>
          <b style="font-size:11.5px;color:${S.stg===s.id?'#38bdf8':'#f1f5f9'}">${s.id>S.maxStg?'🔒 ':''}${s.n} ${S.perf[s.id]?'<span class="tag y" style="margin-left:4px">👑無欠済</span>':''}</b>
          <div style="font-size:9.2px;color:#94a3b8;margin-top:3px">${s.d}</div>
        </div>
        <span style="font-size:10px;color:${S.stg===s.id?'#38bdf8':'#64748b'};font-weight:900;background:${S.stg===s.id?'rgba(56,189,248,.15)':'transparent'};padding:4px 8px;border-radius:6px">${S.stg===s.id?'▶ 出撃先':'選択'}</span>
      </div>`).join("")+
      `<button class="btn-go" onclick="startBat()">🚀 STAGE ${S.stg} 業務開始（👥${STAGES[S.stg-1].tot}人 + 👑BOSS）</button>`;
  }else if(S.tab===1){
    box.innerHTML=`<div class="row" style="background:rgba(6,12,24,.9);padding:7px 10px;border-radius:9px;border:1px solid #1e293b;margin-bottom:6px;font-size:10px">
      <span>🔓 現在の上限キャップ: <b style="color:#38bdf8;font-family:var(--font-num)">Lv.${cap}</b> / 最大12</span>
      <button class="btn-sm on" onclick="if(S.rp>=1){S.rp--;S.tok+=10;beep(580,0.05);saveLocal();renderHub(true)}">🔬1RP ➔ 🪙10T変換</button>
    </div>`+S_CATS.map((cat,ci)=>`<div class="cat">${cat}</div>`+SKILLS.filter(k=>k.ci===ci).map(k=>{
      const lv=sLv(k.id), isMax=lv>=k.m, curLim=k.med?Math.min(k.m,cap):cap, isCap=!isMax && lv>=curLim;
      const cost=skillCost(k,lv);
      const can=!isMax && !isCap && (k.med ? S.med>=cost : S.tok>=cost);
      const pct=Math.min(100,Math.round((lv/k.m)*100));
      return `<div class="nd ${isMax?'max':(isCap?'cap':(k.med?'leg':(can?'can':'')))}">
        <div style="flex:1">
          <div class="row" style="justify-content:flex-start;gap:6px;flex-wrap:wrap">
            <b style="font-size:10.5px;color:#f8fafc">${k.n}</b>
            <span class="tag ${k.med?'y':'g'}">${k.tag}</span>
            <span style="font-size:10px;color:#38bdf8;font-weight:900;font-family:var(--font-num)">Lv.${lv}/${curLim}</span>
          </div>
          <div style="font-size:9px;color:#94a3b8;margin-top:3px">${k.d}</div>
          <div class="lv-bar"><div class="lv-fill" style="width:${pct}%;background:${k.med?'linear-gradient(90deg,#d97706,#fbbf24)':(isMax?'#10b981':'linear-gradient(90deg,#0284c7,#38bdf8)')}"></div></div>
        </div>
        <button class="nd-b ${isMax?'max':(k.med?'leg':(can?'can':''))}" ${!can?'disabled':''} onclick="buySkill('${k.id}')">
          ${isMax?'MAX':(isCap?`🔒Stg${S.maxStg}突破`:(k.med?`👑${cost}勲章`:`🪙${fmt(cost)}`))}
        </button>
      </div>`;
    }).join("")).join("");
  }else{
    const totM=maxMem(), curM=usedMem();
    const pips=Array.from({length:totM},(_,i)=>`<div class="mem-pip ${i<curM?'on':''}"></div>`).join("");
    box.innerHTML=`<div class="row" style="background:rgba(6,12,24,.9);padding:7px 10px;border-radius:9px;border:1px solid #1e293b;margin-bottom:7px;font-size:10px">
        <div class="row" style="gap:8px">
          <span>🧩 メモリ容量: <b style="color:#38bdf8;font-family:var(--font-num)">${curM}/${totM}枠</b></span>
          <div class="mem-slots">${pips}</div>
        </div>
        <button class="btn-sm" onclick="if(S.eq.size){S.eq.clear();beep(440,0.05);saveLocal();renderHub(true)}">🔄全解除</button>
      </div>
      <div class="syn-bar">
        <div class="syn ${c.synS?'on':''}">🎮技巧共鳴 (${c.cntS}/2)<br><b>${c.synS?'✨全員⏳+0.3s':'未発動'}</b></div>
        <div class="syn ${c.synB?'on':''}">⚡連鎖共鳴 (${c.cntB}/2)<br><b>${c.synB?'✨全員⏳+0.35s':'未発動'}</b></div>
        <div class="syn ${c.synA?'on':''}">🤖自律共鳴 (${c.cntA}/2)<br><b>${c.synA?'✨ボット⚡35%連鎖':'未発動'}</b></div>
      </div>`+
      M_CATS.map((cat,ci)=>`<div class="cat">${cat}</div><div class="m-grid">`+MODS.filter(m=>m.ci===ci).map(m=>{
        const lv=S.mLv[m.id], eq=S.eq.has(m.id), isLeg=m.med>0, maxL=m.maxLv||12, curLim=Math.min(maxL,cap);
        const isMax=lv>=maxL, isCap=!isMax && lv>=curLim;
        const cost=modCost(m,lv);
        const can=!isMax && !isCap && (isLeg ? S.med>=cost : S.rp>=cost);
        return `<div class="mod ${eq?'eq':''} ${m.tp==='trade'?'trd':''} ${m.tp==='leg'?'leg':''}">
          <div>
            <b class="row" style="font-size:10px;color:${eq?'#38bdf8':(isLeg?'#fbbf24':'#f1f5f9')}">
              <span>${lv>0?(eq?'✅':'⬜'):'🔒'} ${m.n} ${lv>0?(isMax?'MAX':`Lv.${lv}/${curLim}`):''}</span>
              <span class="tag">${m.m}枠</span>
            </b>
            <div style="color:#94a3b8;margin-top:4px;line-height:1.35;font-size:8.8px">${m.d}</div>
          </div>
          <div class="row" style="gap:4px;margin-top:2px">
            ${lv===0
              ? `<button class="nd-b ${isLeg?'leg':'can'}" style="width:100%" ${!can?'disabled':''} onclick="upMod(${m.id})">${isLeg?`👑解放(${cost})`:`🔬開発(${cost}RP)`}</button>`
              : `<button class="nd-b ${eq?'can':''}" style="flex:1;min-width:0" onclick="togMod(${m.id})">${eq?'外す':'装備'}</button>
                 <button class="nd-b ${isMax?'max':(isLeg?'leg':'can')}" style="flex:1;min-width:0" ${!can?'disabled':''} onclick="upMod(${m.id})">${isMax?'MAX':(isCap?`🔒Stg${S.maxStg}`:`+1(${isLeg?'👑'+cost:fmt(cost)+'RP'})`)}</button>`}
          </div>
        </div>`;
      }).join("")+`</div>`).join("");
  }
  if(keepScroll)box.scrollTop=sc;
}

window.buySkill=id=>{
  const k=SKILLS.find(x=>x.id===id), lv=sLv(id), cap=curCap(), curLim=k.med?Math.min(k.m,cap):cap;
  if(lv>=k.m || lv>=curLim)return;
  const cost=skillCost(k,lv);
  if(k.med && S.med>=cost){S.med-=cost;S.sLv[id]++;playChord([523,659,784]);saveLocal();renderHub(true);}
  else if(!k.med && S.tok>=cost){S.tok-=cost;S.sLv[id]++;beep(620+lv*30,0.07,"triangle");saveLocal();renderHub(true);}
};
window.upMod=id=>{
  const m=MODS.find(x=>x.id===id), lv=S.mLv[id], isLeg=m.med>0, maxL=m.maxLv||12, curLim=Math.min(maxL,curCap());
  if(lv>=maxL || lv>=curLim)return;
  const cost=modCost(m,lv);
  if(isLeg && S.med>=cost){S.med-=cost;S.mLv[id]++;if(lv===0&&usedMem()+m.m<=maxMem())S.eq.add(id);playChord([587,740,880]);saveLocal();renderHub(true);}
  else if(!isLeg && S.rp>=cost){S.rp-=cost;S.mLv[id]++;if(lv===0&&usedMem()+m.m<=maxMem())S.eq.add(id);beep(660,0.08,"sine");saveLocal();renderHub(true);}
};
window.togMod=id=>{
  const m=MODS.find(x=>x.id===id);
  if(S.eq.has(id))S.eq.delete(id); else if(usedMem()+m.m<=maxMem())S.eq.add(id);
  beep(520,0.05);saveLocal();renderHub(true);
};

function pickType(){
  if(S.trendT>0 && S.trendTp>=0 && Math.random()<0.72)return S.trendTp;
  const bias=[];
  if(mLv(7))bias.push(0,0);
  if(mLv(8))bias.push(1,1);
  if(mLv(9))bias.push(2,3);
  if(bias.length>0 && Math.random()<0.50)return bias[Math.floor(Math.random()*bias.length)];
  return Math.floor(Math.random()*4);
}
function activeMaxSlots(){
  const st=STAGES[S.stg-1], p=S.spawned/st.tot;
  return p<.35 ? Math.max(4,Math.ceil(st.maxQ*.45)) : (p<.7 ? Math.max(6,Math.ceil(st.maxQ*.75)) : st.maxQ);
}
function spawnOne(){
  const st=STAGES[S.stg-1];
  if(S.spawned>=st.tot || S.slots.length>=activeMaxSlots())return;
  const p=S.spawned/st.tot;
  if((S.trendDone===0 && p>=0.28) || (S.trendDone===1 && p>=0.60)){
    S.trendDone++; S.trendT=9.0; S.trendTp=Math.floor(Math.random()*4);
    S.slots.filter(c=>c.id!==S.selId&&c.kind==="norm"&&c.q.length>0).slice(0,2).forEach(c=>{c.q[0]=S.trendTp;});
    S.qDirty=true;
    flt(`📈 ${TYPES[S.trendTp].ico}${TYPES[S.trendTp].n}トレンド発生!!(報酬1.4倍)`,"#f472b6");
    playChord([523,659,784,1046]);
  }
  const needBoss = !S.bossSp && (S.spawned >= Math.floor(st.tot*0.72) || S.spawned === st.tot-1);
  if(needBoss){
    S.bossSp=true;
    const steps=st.bStp, w=st.wait*1.85 + sLv("s2")*0.8 + sLv("s3")*1.1;
    const dmg=Math.max(10,Math.round((18+S.stg*8)*(1-sLv("s3")*.06)));
    const q=Array.from({length:steps},()=>pickType());
    S.slots.push({id:S.cid++,kind:"boss",av:"👑",nm:"特命BOSS",q,w,maxW:w,dmg,rew:9.0*st.sc,rp:2+S.stg,prog:0,noBot:false});
    S.spawned++; S.qDirty=true;
    shakeScreen();
    flt("👑 特命BOSS来店!!","#f59e0b"); playChord([220,277,330],"sawtooth");
    if(S.autoSel && !S.selId)autoPickNext();
    return;
  }
  const r=Math.random();
  let kind="norm", steps=1, w=st.wait+sLv("s2")*0.8, dmg=6+S.stg*2, rew=1.0*st.sc, rp=0, av=FACES[S.spawned%FACES.length], nm="一般客", noBot=false;
  if(r<.22)kind="krm";
  else if(S.stg>=2 && r<.34)kind="inf";
  else if(S.stg>=3 && r<.48)kind="sec";
  else if(r<.62)kind="vip";

  const vipWaitBonus = mLv(16) ? (1.0 + mLv(16)*0.4) : 0;
  if(kind==="norm" && S.stg>=2 && Math.random()<.42)steps=2;
  if(kind==="krm"){steps=1;w=Math.max(4.4,w*.62+sLv("s3")*1.1);dmg=Math.max(4,Math.round((10+S.stg*3)*(1-sLv("s3")*.07)));rew=1.7*st.sc;av="🚨";nm="急ぎ客";}
  if(kind==="inf"){steps=1;w=w*.92+vipWaitBonus;rew=2.0*st.sc;rp=1;av="📢";nm="拡散客";}
  if(kind==="sec"){steps=2;w*=.88;rew=2.4*st.sc;rp=1;av="🕵️";nm="機密客";noBot=!mLv(19);}
  if(kind==="vip"){steps=Math.min(3,2+Math.floor(S.stg/3));w=w*1.12+vipWaitBonus;rew=3.0*st.sc;rp=1;av="💎";nm="VIP客";}

  const q=Array.from({length:steps},()=>pickType());
  S.slots.push({id:S.cid++,kind,av,nm,q,w,maxW:w,dmg,rew,rp,prog:0,noBot});
  S.spawned++; S.qDirty=true;
  if(S.autoSel && !S.selId)autoPickNext();
}

function autoPickNext(){
  if(!S.autoSel || S.slots.length===0)return;
  const urgent=S.slots.filter(c=>c.w<3.5).sort((a,b)=>a.w-b.w)[0];
  if(urgent){selClient(urgent.id);return;}
  if(S.lastT>=0){
    const same=S.slots.filter(c=>c.q[0]===S.lastT).sort((a,b)=>a.w-b.w)[0];
    if(same){selClient(same.id);return;}
  }
  const next=S.slots.slice().sort((a,b)=>a.w-b.w)[0];
  if(next)selClient(next.id);
}

window.startBat=()=>{
  const c=calc();
  S.inBat=true;S.hp=c.mHp;S.mHp=c.mHp;S.dmgTaken=0;S.spawned=0;S.done=0;S.lost=0;
  S.bossSp=false;S.bossCleared=false;S.slots=[];S.selId=null;S.spT=0;S.lastT=-1;S.cmb=1;
  S.trendT=0;S.trendTp=-1;S.trendDone=0;
  S.runTok=0;S.runRp=0;S.curT=-1;S.errT=0;S.qDirty=true;
  playChord([440,554,659]);
  $("v-hub").style.display="none";
  $("v-bat").style.display="flex";
  spawnOne(); spawnOne();
  if(S.autoSel && !S.selId)autoPickNext();
  renderBat(); renderDesk();
};

window.selClient=id=>{
  const cl=S.slots.find(x=>x.id===id); if(!cl)return;
  const isNew=S.selId!==id; S.selId=id; S.qDirty=true;
  if(isNew && !cl.chk){
    cl.chk=true;
    if(mLv(17)){
      const add=0.4+mLv(17)*0.2;
      cl.w=Math.min(cl.maxW,cl.w+add);
      flt(`👑スマート延長⏳+${add.toFixed(1)}s`,"#fde047");
    }
  }
  setupMG(cl); renderBat();
};

function setupMG(cl){
  if(!cl||!cl.q.length){S.curT=-1;renderDesk();return;}
  const tp=cl.q[0]; S.curT=tp;
  const stgI=Math.min(5,S.stg-1);
  if(tp===0){
    const pool=WORDS[stgI], raw=pool[Math.floor(Math.random()*pool.length)];
    S.txtW=raw.slice(0,Math.max(2,raw.length-Math.floor(sLv("s5")/4)));
    S.txtI=mLv(1)&&S.txtW.length>1?1:0;
    const dmCnt=Math.max(0, 3+S.stg-Math.ceil(sLv("s5")*0.65));
    const chs=S.txtW.split("").map((c,i)=>({c,dm:false,done:i<S.txtI}));
    const dmPool="XYZQJKVW987#@".split("").filter(x=>!S.txtW.includes(x));
    for(let i=0;i<dmCnt;i++)chs.push({c:dmPool[i%dmPool.length],dm:true,done:false});
    S.chips=chs.sort(()=>Math.random()-.5);
    S.prompt=`📝 PROMPT: 『 ${S.txtW.split("").join(" ")} 』`;
  }else if(tp===1){
    const av=SHAPES.filter(s=>s.s<=S.stg);
    const pick=av[Math.floor(Math.random()*av.length)];
    S.shpI=SHAPES.indexOf(pick);
    const m2B=mLv(2)?(0.04+mLv(2)*0.015):0;
    const s17B=sLv("s17")*0.02;
    S.shpNeed=Math.max(0.55,0.82-sLv("s6")*.02-m2B-s17B);
    S.pts=makePts(pick.id,30); S.draw=false; S.trail=[];
    S.prompt=`🎨 VECTOR TRACE: ${pick.n}`;
  }else if(tp===2){
    S.musN=Math.max(1, (cl.kind==="boss"?2:1)+Math.floor(S.stg/2)-(mLv(3)>=3?1:0)); S.musC=0;
    S.prompt=`🎵 QUANTIZE SYNC ×${S.musN}回`;
  }else{
    const len=Math.max(2, 3+S.stg-Math.floor(sLv("s8")/3));
    S.vidS=Array.from({length:len},()=>DIRS[Math.floor(Math.random()*4)]); S.vidI=0;
    S.prompt=`🎬 TIMELINE CUT: ${S.vidS.join(" ➔ ")}`;
  }
  renderDesk();
}

function makePts(id,N){
  const cx=125,cy=46,pts=[];
  const poly=v=>{for(let i=0;i<N;i++){const t=(i/(N-1))*(v.length-1),k=Math.min(v.length-2,Math.floor(t)),f=t-k;pts.push({x:v[k].x+(v[k+1].x-v[k].x)*f,y:v[k].y+(v[k+1].y-v[k].y)*f,hit:false});}return pts;};
  if(id==="cir"){for(let i=0;i<N;i++){const a=(i/(N-1))*Math.PI*2;pts.push({x:cx+Math.cos(a)*35,y:cy+Math.sin(a)*33,hit:false});}return pts;}
  if(id==="sq")return poly([{x:86,y:13},{x:164,y:13},{x:164,y:80},{x:86,y:80},{x:86,y:13}]);
  if(id==="tri")return poly([{x:125,y:11},{x:172,y:80},{x:78,y:80},{x:125,y:11}]);
  if(id==="dia")return poly([{x:125,y:9},{x:175,y:46},{x:125,y:83},{x:75,y:46},{x:125,y:9}]);
  if(id==="blt")return poly([{x:88,y:11},{x:156,y:11},{x:98,y:46},{x:164,y:46},{x:96,y:82}]);
  if(id==="str"){const v=[];for(let i=0;i<=10;i++){const a=(i/10)*Math.PI*2-Math.PI/2,r=i%2===0?37:15;v.push({x:cx+Math.cos(a)*r,y:cy+Math.sin(a)*r});}return poly(v);}
  if(id==="hrt"){for(let i=0;i<N;i++){const t=(i/(N-1))*Math.PI*2;pts.push({x:cx+35*Math.pow(Math.sin(t),3),y:cy-(26*Math.cos(t)-10*Math.cos(2*t)-4*Math.cos(3*t))-3,hit:false});}return pts;}
  if(id==="inf"){for(let i=0;i<N;i++){const t=(i/(N-1))*Math.PI*2;pts.push({x:cx+Math.sin(t)*50,y:cy+Math.sin(t)*Math.cos(t)*50,hit:false});}return pts;}
  if(id==="spi"){for(let i=0;i<N;i++){const t=(i/(N-1))*Math.PI*4,r=6+(i/(N-1))*33;pts.push({x:cx+Math.cos(t)*r,y:cy+Math.sin(t)*r,hit:false});}return pts;}
  return poly([{x:75,y:78},{x:68,y:20},{x:100,y:50},{x:125,y:12},{x:150,y:50},{x:182,y:20},{x:175,y:78},{x:75,y:78}]);
}

function trigErr(msg){
  const cl=S.slots.find(x=>x.id===S.selId);
  const safe=mLv(18)?Math.max(0.35,1-(0.12+mLv(18)*0.06)):1;
  S.errT=0.45*safe; S.cmb=1; beep(155,0.18,"sawtooth",0.13);
  shakeScreen();
  if(cl){
    const mult=(mLv(15)?2.0:1.0)*safe;
    const cut=cl.maxW*Math.max(0.08,0.22-sLv("s4")*.015)*mult;
    cl.w=Math.max(0.2,cl.w-cut);
  }
  flt(`⚠️${msg} (⏳減少)`,"#f43f5e"); if(cl)setupMG(cl); renderBat();
}

function stepDone(cl,manual=true,fromTail=false){
  if(!cl||!cl.q.length)return;
  const doneT = fromTail ? cl.q.pop() : cl.q.shift();
  cl.lastDoneT = doneT;
  cl.prog=0; S.qDirty=true;
  if(cl.kind==="boss" && cl.q.length>0)cl.w=Math.min(cl.maxW, cl.w+1.5);
  const c=calc();

  if(manual){
    const pitch=Math.min(1100, Math.round(480 * Math.pow(1.06, (S.cmb-1)*5)));
    beep(pitch,0.08,"triangle",0.1);
    burst("desk-box",TYPES[doneT].c,7);

    if(doneT===0 && (sLv("s16")||mLv(1))){
      const add=sLv("s16")*0.25 + mLv(1)*0.2;
      cl.w=Math.min(cl.maxW,cl.w+add);
    }
    if(c.synS)S.slots.forEach(x=>x.w=Math.min(x.maxW,x.w+0.3));
    if(doneT===3&&mLv(4)){const add=.3+mLv(4)*.12;S.slots.forEach(x=>x.w=Math.min(x.maxW,x.w+add));}

    const cmbStep=0.14*(1+sLv("s11")*.12)*(c.synB?1.35:1);
    S.cmb = (S.lastT===doneT) ? Math.min(3.5, +(S.cmb + cmbStep).toFixed(2)) : 1;
    S.lastT=doneT;
  }

  const trigBat = manual || (c.synA && Math.random()<0.35);
  if(trigBat && c.batR>0){
    let cnt=0, crossUsed=false;
    const crossProb = mLv(20) ? (15 + mLv(20)*8) : 0;
    S.slots.slice().forEach(o=>{
      if(o.id===cl.id || !o.q.length || cnt>=c.batMax)return;
      const same=o.q[0]===doneT;
      const canCross=!same && !crossUsed && crossProb>0 && Math.random()*100<crossProb;
      if((same && Math.random()*100<c.batR) || canCross){
        if(canCross)crossUsed=true;
        o.lastDoneT=o.q.shift(); o.prog=0; cnt++;
        const card=$(`cl-${o.id}`);
        if(card){card.classList.remove("fls");void card.offsetWidth;card.classList.add("fls");}
        burst(`cl-${o.id}`,"#34d399",6);
        if(!o.q.length)finishCl(o,true);
      }
    });
    if(cnt>0){
      if(c.synB)S.slots.forEach(x=>x.w=Math.min(x.maxW,x.w+0.35));
      if(mLv(6)){const bTok=Math.ceil(cl.rew*c.rew*cnt*(.15*mLv(6)));S.tok+=bTok;S.runTok+=bTok;}
      flt(`⚡バッチ連鎖 ×${cnt}人!!`,"#34d399");
      playChord([587,740,880,1174],"sine");
    }
  }
  if(!cl.q.length)finishCl(cl,false);
  else if(cl.id===S.selId && !fromTail)setupMG(cl);
  else if(cl.id===S.selId && fromTail)renderDesk();
  if(S.inBat)renderBat();
}

function finishCl(cl,fromBat=false){
  const idx=S.slots.findIndex(x=>x.id===cl.id); if(idx<0)return;
  const c=calc(); S.done++; S.totServed++; S.qDirty=true;
  if(cl.kind==="boss"){S.bossCleared=true;flt("👑 特命BOSS完全納品!!","#fbbf24");playChord([523,659,784,1046]);}
  else if(cl.kind==="inf"){
    S.slots.forEach(x=>x.w=Math.min(x.maxW,x.w+2.2));
    S.cmb=Math.min(3.5,+(S.cmb+0.35).toFixed(2));
    flt("📢拡散ボーナス! 全員⏳+2.2s＆🔥コンボUP","#e879f9");
    playChord([659,830,987]);
  }else if(!fromBat)beep(780,0.08,"sine");

  const isTrendMatch = S.trendT>0 && (cl.lastDoneT===S.trendTp || cl.kind==="boss");
  const gB=(1+(mLv(7)+mLv(8)+mLv(9))*.10)*(isTrendMatch?1.4:1);
  const tok=Math.max(1,Math.ceil(cl.rew*c.rew*S.cmb*gB));
  const rp=Math.ceil((cl.rp+(S.done%4===0?1:0))*c.rpM);
  S.tok+=tok; S.rp+=rp; S.runTok+=tok; S.runRp+=rp;
  if(!fromBat)flt(`✨+${fmt(tok)}T${rp?` +${rp}RP`:''}`,"#38bdf8");
  S.slots.splice(idx,1);
  const wasSel=(S.selId===cl.id);
  if(wasSel){S.selId=null;S.curT=-1;}
  checkStageEnd();
  if(!S.inBat)return;
  if(wasSel && S.autoSel)autoPickNext();
  if(!fromBat)renderDesk();
}

function checkStageEnd(){
  const st=STAGES[S.stg-1];
  if(S.spawned>=st.tot && S.slots.length===0 && S.hp>0){
    if(!S.bossCleared){
      endBat(false,false,"💥 STAGE FAILED (👑BOSS失注)","👑特命BOSSを納品できなかったためクリア失敗となりました。");
      return;
    }
    const isPerf = (S.dmgTaken===0 && S.lost===0 && S.hp===S.mHp);
    let medBonus=0;
    if(isPerf){
      if(!S.perf[S.stg]){
        medBonus=2; S.perf[S.stg]=true; S.med+=medBonus;
      }
      const bRp=2*S.stg; S.rp+=bRp; S.runRp+=bRp;
    }
    const prevMax=S.maxStg;
    S.maxStg=Math.min(6,Math.max(S.maxStg,S.stg+1));
    const capMsg=S.maxStg>prevMax?`\n🔓 スキル＆モジュール強化上限が【Lv.${curCap()}】に解放されました！`:"";

    if(S.stg===6){
      S.cleared6=true;
      S.inBat=false;
      saveLocal(true);
      const rewardSummary=`【今回獲得した報酬】\n🪙 +${fmt(S.runTok)} トークン / 🔬 +${fmt(S.runRp)} RP${medBonus?` / 👑無欠勲章 +${medBonus}個`:""}`;
      showEnding(rewardSummary);
      return;
    }

    saveLocal(true);
    playChord([523,659,784,1046,1318]);
    endBat(true, isPerf, isPerf?`👑 STAGE ${S.stg} PERFECT CLEAR!!`:`🎉 STAGE ${S.stg} CLEAR!`,
      (isPerf?(medBonus>0?`全${st.tot}人をノーダメージ完全納品！\n👑初回無欠報酬: 無欠勲章 +${medBonus}個 ＆ ボーナスRP獲得！`:`全${st.tot}人をノーダメージ完全納品！\n🔬パーフェクトボーナスRP獲得！(勲章は獲得済)`):`👑BOSSを含む全来客を処理し、ステージを突破しました！`)+capMsg);
  }else if(S.slots.length===0 && S.spawned<st.tot){
    spawnOne();
  }
}

function getMusZone(){
  return Math.min(35, 10 + sLv("s7")*2.0 + (mLv(3)?3+mLv(3)*1.2:0));
}

function renderDesk(){
  const dh=$("d-head"), mg=$("mg");
  const cl=S.slots.find(x=>x.id===S.selId);
  const errH=S.errT>0?`<div class="err">⚠️ SYSTEM ERROR LOCK (${S.errT.toFixed(1)}s)</div>`:"";
  if(!cl||S.curT<0){
    $("desk-box").style.borderColor="#334155";
    dh.innerHTML=`<span style="font-size:10.5px;color:#fbbf24;font-weight:900">👆 待機窓口のクライアントをタップして「🎯受注」してください</span>`;
    mg.innerHTML=errH+`<span style="font-size:10px;color:#64748b">クライアントを受注するとここにAI生成コンソールが起動します</span>`;
    return;
  }
  const tp=TYPES[S.curT];
  $("desk-box").style.borderColor=tp.c;
  $("desk-box").style.boxShadow=`0 10px 28px rgba(0,0,0,.8), 0 0 18px ${tp.c}33`;
  const qStr=cl.q.slice(0,5).map(x=>TYPES[x].ico).join("➔")+(cl.q.length>5?`+${cl.q.length-5}`:"");
  dh.innerHTML=`<div style="font-size:22px;background:rgba(15,23,42,.9);border:1px solid ${tp.c};border-radius:8px;width:34px;height:34px;display:flex;align-items:center;justify-content:center;flex-shrink:0">${cl.av}</div>
    <div style="flex:1;margin-left:8px;overflow:hidden">
      <div class="row" style="font-size:9px;color:#94a3b8">
        <span style="white-space:nowrap;overflow:hidden;text-overflow:ellipsis"><b style="color:#f8fafc">${cl.nm}</b> (${qStr})</span>
        <span style="flex-shrink:0">⏳残り <b id="d-w" style="color:#38bdf8;font-family:var(--font-num);font-size:10.5px">${cl.w.toFixed(1)}</b>s</span>
      </div>
      <b style="display:block;font-size:11px;color:#fef08a;margin-top:1px;white-space:nowrap;overflow:hidden;text-overflow:ellipsis">${S.prompt}</b>
    </div>`;

  if(S.curT===0){
    const slots=S.txtW.split("").map((ch,i)=>`<div class="slot ${i<S.txtI?'on':''}">${i<S.txtI?ch:'?'}</div>`).join("");
    const nextCh=S.txtW[S.txtI];
    let hintShown=false;
    mg.innerHTML=errH+`<div class="slot-box">${slots}</div>
      <div class="row" style="flex-wrap:wrap;justify-content:center;gap:6px">`+
      S.chips.map((c,i)=>{
        const isHint = sLv("s16")>0 && !c.done && !c.dm && c.c===nextCh && !hintShown;
        if(isHint)hintShown=true;
        return `<button class="chip ${c.done?'done':''} ${isHint?'hint':''}" onpointerdown="tapTxt(${i})">${c.c}</button>`;
      }).join("")+`</div>`;
  }else if(S.curT===1){
    const pct=Math.round(S.pts.filter(p=>p.hit).length/S.pts.length*100);
    mg.innerHTML=errH+`<div class="row" style="width:250px;font-size:9.5px"><span>🎨 ${SHAPES[S.shpI].n} <small style="color:#fde047;font-weight:800">(★黄点からなぞる)</small></span><b id="sh-p" style="color:#c084fc;font-family:var(--font-num)">${pct}% / ${Math.round(S.shpNeed*100)}%</b></div><canvas id="cv" width="250" height="92"></canvas>`;
    initCV();
  }else if(S.curT===2){
    const z=getMusZone();
    const dots=Array.from({length:S.musN},(_,i)=>`<span style="font-size:13px;filter:drop-shadow(0 0 6px #10b981)">${i<S.musC?'🟢':'⚪'}</span>`).join(" ");
    mg.innerHTML=errH+`<div class="row" style="gap:10px;font-size:10px;font-weight:800"><span>🎵 HARMONIC SYNC</span><div>${dots}</div></div>
      <div onpointerdown="tapMus()" style="width:92%;height:26px;background:#040914;border:1.5px solid #334155;border-radius:12px;position:relative;overflow:hidden;cursor:pointer;box-shadow:inset 0 2px 8px rgba(0,0,0,.8)">
        <div style="position:absolute;left:${50-z}%;width:${z*2}%;height:100%;background:linear-gradient(90deg,rgba(16,185,129,.15),rgba(16,185,129,.65),rgba(16,185,129,.15));border-left:2px solid #34d399;border-right:2px solid #34d399;box-shadow:0 0 12px rgba(16,185,129,.4)"></div>
        <div style="position:absolute;left:50%;top:0;bottom:0;width:1px;background:rgba(255,255,255,.35)"></div>
        <div id="m-cur" style="position:absolute;left:${S.musP}%;width:9px;height:100%;background:#fbbf24;border-radius:4px;box-shadow:0 0 12px #fbbf24;transform:translateX(-50%)"></div>
      </div>
      <button class="btn-go" style="padding:8px;width:78%;margin:0;background:linear-gradient(135deg,#059669,#10b981)" onpointerdown="tapMus()">🎵 BEAT HIT (Space)</button>`;
  }else{
    const showAll=sLv("s8")>=2;
    const seq=S.vidS.map((d,i)=>`<span class="tag ${i<S.vidI?'g':(i===S.vidI?'y':'')}" style="font-size:11.5px;padding:2px 6px">${i<S.vidI?'✅':(i===0||showAll?d:'❓')}</span>`).join("");
    mg.innerHTML=errH+`<div class="row" style="gap:4px;flex-wrap:wrap;justify-content:center">${seq}</div><div class="row" style="gap:10px">`+DIRS.map(d=>`<button class="dir" onpointerdown="tapVid('${d}')">${d}</button>`).join("")+`</div>`;
  }
}

function initCV(){
  const cv=$("cv"); if(!cv)return;
  const ctx=cv.getContext("2d"); drawCV(ctx);
  const mv=e=>{
    if(!S.draw||S.errT>0)return; e.preventDefault();
    const cl=S.slots.find(x=>x.id===S.selId); if(!cl)return;
    const r=cv.getBoundingClientRect(), x=(e.clientX-r.left)*(cv.width/r.width), y=(e.clientY-r.top)*(cv.height/r.height);
    S.trail.push({x,y}); if(S.trail.length>40)S.trail.shift();
    const m2Scale=mLv(2)?(1.15+mLv(2)*0.08):1;
    const s17Scale=1+sLv("s17")*0.05;
    const rad=(13+sLv("s6")*1.6)*m2Scale*s17Scale;
    let newlyHit=false;
    S.pts.forEach(p=>{if(!p.hit && Math.hypot(p.x-x,p.y-y)<=rad){p.hit=true;newlyHit=true;}});
    if(newlyHit)beep(680,0.02,"sine",0.03);
    drawCV(ctx);
    const pct=S.pts.filter(p=>p.hit).length/S.pts.length;
    const el=$("sh-p"); if(el)el.textContent=`${Math.round(pct*100)}% / ${Math.round(S.shpNeed*100)}%`;
    if(pct>=S.shpNeed){S.draw=false;flt("🎨RENDER COMPLETE!","#c084fc");stepDone(cl,true);}
  };
  cv.onpointerdown=e=>{try{cv.setPointerCapture(e.pointerId);}catch(_){}S.draw=true;mv(e);};
  cv.onpointermove=mv;
  cv.onpointerup=cv.onpointercancel=()=>{S.draw=false;};
}
function drawCV(ctx){
  ctx.clearRect(0,0,250,92); if(!S.pts.length)return;
  ctx.lineWidth=9; ctx.lineCap="round"; ctx.lineJoin="round"; ctx.strokeStyle="rgba(148,163,184,.22)";
  ctx.beginPath(); S.pts.forEach((p,i)=>i?ctx.lineTo(p.x,p.y):ctx.moveTo(p.x,p.y)); ctx.stroke();
  for(let i=S.pts.length-1;i>=0;i--){
    const p=S.pts[i];
    ctx.beginPath();
    ctx.arc(p.x,p.y,p.hit?4.5:(i===0?6:3.2),0,7);
    ctx.fillStyle=p.hit?"#34d399":(i===0?"#fbbf24":"#a855f7");
    ctx.fill();
  }
  if(S.trail.length>1){
    ctx.save();
    ctx.beginPath();
    S.trail.forEach((p,i)=>i?ctx.lineTo(p.x,p.y):ctx.moveTo(p.x,p.y));
    ctx.strokeStyle="#f0abfc";
    ctx.shadowColor="#e879f9";
    ctx.shadowBlur=10;
    ctx.lineWidth=4.5;
    ctx.stroke();
    ctx.restore();
  }
}

window.tapTxt=i=>{
  if(S.errT>0)return; const cl=S.slots.find(x=>x.id===S.selId); if(!cl)return;
  const ch=S.chips[i]; if(!ch||ch.done)return;
  if(ch.c===S.txtW[S.txtI]){
    ch.done=true; S.txtI++; beep(540+S.txtI*45,0.04);
    if(S.txtI>=S.txtW.length)stepDone(cl,true); else renderDesk();
  }else trigErr("TYPO");
};
window.tapMus=()=>{
  if(S.errT>0)return; const cl=S.slots.find(x=>x.id===S.selId); if(!cl)return;
  const z=getMusZone();
  if(Math.abs(S.musP-50)<=z){
    S.musC++; beep(700+S.musC*90,0.06,"triangle");
    if(S.musC>=S.musN)stepDone(cl,true); else renderDesk();
  }else trigErr("MISS BEAT");
};
window.tapVid=d=>{
  if(S.errT>0)return; const cl=S.slots.find(x=>x.id===S.selId); if(!cl)return;
  if(d===S.vidS[S.vidI]){
    S.vidI++; beep(580+S.vidI*55,0.05);
    if(S.vidI>=S.vidS.length)stepDone(cl,true); else renderDesk();
  }else trigErr("WRONG DIR");
};

window.addEventListener("keydown",e=>{
  if(!S.inBat||S.errT>0)return;
  if(S.curT===0){
    const k=e.key.toUpperCase();
    let idx=S.chips.findIndex(c=>!c.done&&!c.dm&&c.c===k);
    if(idx<0)idx=S.chips.findIndex(c=>!c.done&&c.c===k);
    if(idx>=0)tapTxt(idx);
  }else if(S.curT===2 && e.code==="Space"){e.preventDefault();tapMus();}
  else if(S.curT===3){
    const mp={ArrowUp:"⬆️",KeyW:"⬆️",ArrowDown:"⬇️",KeyS:"⬇️",ArrowLeft:"⬅️",KeyA:"⬅️",ArrowRight:"➡️",KeyD:"➡️"};
    if(mp[e.code]||mp[e.key]){e.preventDefault();tapVid(mp[e.code]||mp[e.key]);}
  }
});

function renderBat(){
  upHdr(); const c=calc(), st=STAGES[S.stg-1], rem=st.tot-S.done-S.lost;
  $("b-stg").textContent=`STAGE ${S.stg}`;
  const p=S.spawned/st.tot;
  $("b-ph").textContent=p<.35?`🟢序盤`:(p<.7?`🟡中盤`:`🔴終盤ラッシュ`);
  $("b-rem").textContent=`👤残り ${rem}/${st.tot}`;
  $("b-cmb").textContent=`🔥x${S.cmb.toFixed(1)}`;
  const nd=$("b-nodmg");
  nd.textContent=S.dmgTaken===0?"👑無傷":"⚠️被弾"; nd.style.color=S.dmgTaken===0?"#10b981":"#64748b";
  $("b-hp").textContent=`${Math.ceil(S.hp)}/${S.mHp}`;
  const hpPct=Math.max(0,S.hp/S.mHp*100);
  const bh=$("bar-hp");
  bh.style.width=hpPct+"%";
  bh.style.background=hpPct<30?"linear-gradient(90deg,#e11d48,#fb7185)":"linear-gradient(90deg,#059669,#34d399)";

  const synArr=[]; if(c.synS)synArr.push("🎮技巧"); if(c.synB)synArr.push("⚡連鎖"); if(c.synA)synArr.push("🤖自律");
  $("b-syn").textContent=synArr.length?`✨共鳴:${synArr.join("・")}`:"";

  const tr=$("b-trend");
  if(S.trendT>0 && S.trendTp>=0){
    tr.className="trend-slot on";
    tr.textContent=`📈 TREND WAVE: ${TYPES[S.trendTp].ico}${TYPES[S.trendTp].n}バズ中！ (報酬1.4倍 / 残り${S.trendT.toFixed(1)}s)`;
  }else{
    tr.className="trend-slot";
    tr.textContent=`📡 リアルタイム需要モニタリング中... (突発バズ待機)`;
  }

  const bs=$("b-boss");
  bs.textContent=S.bossCleared?"👑BOSS:済":(S.bossSp?"👑BOSS:出現中!":"👑BOSS:終盤");
  bs.style.color=S.bossCleared?"#10b981":(S.bossSp?"#f43f5e":"#f59e0b");
  $("b-qcnt").textContent=`${S.slots.length}/${activeMaxSlots()}枠`;
  $("b-batrate").textContent=`⚡連鎖:${c.batR}%(最大${c.batMax}人)`;

  const sel=S.slots.find(x=>x.id===S.selId), selT=sel&&sel.q.length?sel.q[0]:-1;
  const dw=$("d-w"); if(dw&&sel)dw.textContent=sel.w.toFixed(1);

  const qg=$("q-grid");
  if(S.qDirty || qg.children.length!==S.slots.length){
    S.qDirty=false;
    qg.innerHTML=S.slots.map(cl=>{
      const isT=cl.id===S.selId, isB=!isT&&selT>=0&&cl.q.length&&cl.q[0]===selT&&c.batR>0;
      const wPct=cl.w/cl.maxW*100;
      const wCol=cl.w<3?'#f43f5e':(wPct<55?'#fbbf24':'#10b981');
      const qIcons=cl.q.slice(0,5).map(t=>TYPES[t].ico).join("")+(cl.q.length>5?`+${cl.q.length-5}`:"");
      return `<div id="cl-${cl.id}" class="cl ${cl.kind} ${isT?'tgt':''} ${isB?'bat':''} ${cl.w<3?'dng':''}" onpointerdown="selClient(${cl.id})" onanimationend="this.classList.remove('fls')">
        <div class="row" style="width:100%;font-size:8.5px"><b id="cl-lb-${cl.id}" style="color:${isT?'#38bdf8':(isB?'#34d399':'#e2e8f0')}">${isT?'🎯受注':(isB?'⚡連鎖':cl.nm)}</b><span id="cl-w-${cl.id}" style="font-family:var(--font-num);font-weight:700">${cl.w.toFixed(1)}s</span></div>
        <div style="font-size:16px;line-height:1">${cl.av}${cl.noBot?'<small style="font-size:9px">🔒</small>':''}</div>
        <div id="cl-q-${cl.id}" style="font-size:9.5px;white-space:nowrap;overflow:hidden">${qIcons}</div>
        <div style="width:100%">
          <div class="bar"><div class="bf" id="cl-bw-${cl.id}" style="width:${wPct}%;background:${wCol}"></div></div>
          <div class="bar" style="height:3px;margin-top:1.5px"><div class="bf" id="cl-bp-${cl.id}" style="width:${cl.prog*100}%;background:#c084fc"></div></div>
        </div>
      </div>`;
    }).join("");
  }else{
    S.slots.forEach(cl=>{
      const isT=cl.id===S.selId, isB=!isT&&selT>=0&&cl.q.length&&cl.q[0]===selT&&c.batR>0;
      const card=$(`cl-${cl.id}`); if(!card)return;
      const fls=card.classList.contains("fls")?" fls":"";
      card.className=`cl ${cl.kind} ${isT?'tgt':''} ${isB?'bat':''} ${cl.w<3?'dng':''}${fls}`;
      const lb=$(`cl-lb-${cl.id}`);
      if(lb){lb.textContent=isT?'🎯受注':(isB?'⚡連鎖':cl.nm);lb.style.color=isT?'#38bdf8':(isB?'#34d399':'#e2e8f0');}
      const wEl=$(`cl-w-${cl.id}`); if(wEl)wEl.textContent=cl.w.toFixed(1)+"s";
      const qIcons=cl.q.slice(0,5).map(t=>TYPES[t].ico).join("")+(cl.q.length>5?`+${cl.q.length-5}`:"");
      const qEl=$(`cl-q-${cl.id}`); if(qEl)qEl.textContent=qIcons;
      const wPct=cl.w/cl.maxW*100;
      const bw=$(`cl-bw-${cl.id}`); if(bw){bw.style.width=wPct+"%";bw.style.background=cl.w<3?'#f43f5e':(wPct<55?'#fbbf24':'#10b981');}
      const bp=$(`cl-bp-${cl.id}`); if(bp)bp.style.width=(cl.prog*100)+"%";
    });
  }
}

function showModal(ico,tit,txt,extHtml,btnFn){
  $("m-ico").textContent=ico;
  $("m-tit").textContent=tit;
  $("m-txt").textContent=txt;
  $("m-ext").innerHTML=extHtml||"";
  $("m-btn").onclick=btnFn||closeModal;
  $("ovl").style.display="flex";
}
window.closeModal=()=>{$("ovl").style.display="none";};

window.endBat=(win,perf,tit,msg)=>{
  S.inBat=false; saveLocal(true);
  showModal(perf?"👑":(win?"🏆":"💥"), tit, `${msg}\n\n【今回獲得した報酬】\n🪙 +${fmt(S.runTok)} トークン / 🔬 +${fmt(S.runRp)} RP`, "", ()=>{
    closeModal(); $("v-bat").style.display="none"; $("v-hub").style.display="flex"; renderHub(true);
  });
};

loadLocal(); renderHub(false);

setInterval(()=>{
  if(!S.inBat)return;
  const dt=0.1, c=calc(), st=STAGES[S.stg-1];
  if(S.trendT>0)S.trendT=Math.max(0,S.trendT-dt);
  if(S.errT>0){S.errT=Math.max(0,S.errT-dt);if(S.errT===0)renderDesk();}

  const mSpd=Math.max(50,(80+S.stg*14)*(1-sLv("s7")*.035));
  S.musP+=S.musD*mSpd*dt; if(S.musP>=95){S.musP=95;S.musD=-1;} if(S.musP<=5){S.musP=5;S.musD=1;}
  const mc=$("m-cur"); if(mc)mc.style.left=S.musP+"%";

  const p=S.spawned/st.tot, mult=p<.35?1.15:(p<.7?0.88:0.65);
  S.spT+=dt;
  if(S.spawned<st.tot && S.spT>=st.sp*mult){
    S.spT=0; spawnOne();
    if(p>=.65 && S.slots.length<activeMaxSlots() && Math.random()<.42)spawnOne();
  }

  if(c.subSpd>0){
    const waitList=S.slots.filter(x=>!x.noBot && x.q.length>0 && x.id!==S.selId);
    if(sLv("s15")>0)waitList.sort((a,b)=>a.w-b.w);
    const selCl=S.slots.find(x=>x.id===S.selId && !x.noBot && x.q.length>1);
    const targets = selCl ? [...waitList, selCl].slice(0,c.subCnt) : waitList.slice(0,c.subCnt);

    targets.forEach(cl=>{
      if(!S.inBat)return;
      const isSel = (cl.id===S.selId);
      const t = isSel ? cl.q[cl.q.length-1] : cl.q[0];
      const mSp=(t<2?mLv(10):mLv(11))*0.032;
      let spd=(c.subSpd+mSp)*(sLv("s15")>0&&cl.w<4?1.5:1);
      if(cl.kind==="boss")spd *= mLv(19) ? Math.min(0.85, 0.25 + mLv(19)*0.1) : 0.25;
      cl.prog+=spd*dt;
      if(cl.prog>=1){
        flt(`🤖サブAI完了(${TYPES[t].ico})`,"#c084fc");
        stepDone(cl,false,isSel);
      }
    });
  }
  if(!S.inBat)return;

  const slow=mLv(13)?Math.max(.55,1-(.10+mLv(13)*.025)):1;
  for(let i=S.slots.length-1;i>=0;i--){
    const cl=S.slots[i]; if(!cl)continue;
    cl.w-=dt*slow;
    if(cl.w<=0){
      S.hp-=cl.dmg; S.dmgTaken+=cl.dmg; S.lost++; S.cmb=1; S.qDirty=true;
      const isBoss = cl.kind==="boss";
      beep(135,0.22,"sawtooth",0.15);
      shakeScreen();
      flt(isBoss?`💥BOSS失注 -${cl.dmg}HP`:`💥失注 -${cl.dmg}HP`,"#f43f5e");
      const goneId=cl.id; S.slots.splice(i,1);
      if(S.selId===goneId){
        S.selId=null;S.curT=-1;
        if(S.autoSel)autoPickNext();
        renderDesk();
      }
      if(isBoss){
        S.hp=Math.max(0,S.hp);
        endBat(false,false,"💥 STAGE FAILED (👑特命BOSS失注)","👑特命BOSSの注文が時間切れとなり、ステージ失敗となりました。\n稼いだ報酬で強化して再挑戦しましょう！");
        return;
      }
      if(S.hp<=0){
        S.hp=0;
        endBat(false,false,"💥 SERVER DOWN (窓口崩壊)","時間切れ失注が重なりサーバー耐久が0になりました。\n持ち帰った🪙トークンと🔬RPで強化しましょう！");
        return;
      }
      checkStageEnd();
      if(!S.inBat)return;
    }
  }
  renderBat();
},100);
</script>
</body>
</html>
```