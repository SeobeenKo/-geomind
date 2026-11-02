<!DOCTYPE html>
<html lang="ko">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>마음자리 GEO-MIND | 4가지 이동 수단 통합 심리 경로 추천 시스템</title>

    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <link href="https://fonts.googleapis.com/css2?family=Noto+Sans+KR:wght@300;400;600;700&display=swap" rel="stylesheet">

    <style>
        :root {
            --primary: #4a7c59;
            --primary-light: #e8f5e9;
            --danger: #e53935;
            --warning: #fb8c00;
            --dark: #263238;
            --gray: #78909c;
            --light-bg: #f4f6f8;
            --panel-bg: rgba(255, 255, 255, 0.97);
        }

        * { box-sizing: border-box; margin: 0; padding: 0; font-family: 'Noto Sans KR', sans-serif; }
        body, html { width: 100%; height: 100%; overflow: hidden; }
        #app-container { display: flex; width: 100vw; height: 100vh; position: relative; }
        #map-area { flex: 1; height: 100%; position: relative; z-index: 1; }
        #kakao-map { width: 100%; height: 100%; background: #e5e9ec; }

        #sidebar {
            width: 420px; height: 100%; background: var(--panel-bg);
            box-shadow: 2px 0 15px rgba(0,0,0,0.15); z-index: 10;
            display: flex; flex-direction: column;
        }
        .header { background: var(--primary); color: white; padding: 18px 20px; }
        .header h1 { font-size: 1.3rem; font-weight: 700; display: flex; align-items: center; gap: 10px; }
        .header span.subtitle { font-size: 0.8rem; opacity: 0.85; font-weight: 300; }
        .content { padding: 16px 20px; overflow-y: auto; flex: 1; display: flex; flex-direction: column; gap: 14px; }

        .card { background: white; border-radius: 12px; padding: 14px; box-shadow: 0 2px 8px rgba(0,0,0,0.05); border: 1px solid #e2e8f0; }
        .card-title { font-size: 0.9rem; font-weight: 700; color: var(--dark); margin-bottom: 10px; display: flex; align-items: center; gap: 8px; }

        .search-box { display: flex; flex-direction: column; gap: 8px; }
        .search-row { position: relative; }
        .search-input-group { display: flex; gap: 6px; align-items: center; }
        .search-input-group .pin { width: 22px; height: 22px; border-radius: 50%; color: #fff; font-size: 0.7rem; font-weight: 700; display: flex; align-items: center; justify-content: center; flex-shrink: 0; }
        .pin.start { background: #1e88e5; }
        .pin.end { background: #e53935; }
        .search-input-group input { flex: 1; min-width: 0; padding: 8px 10px; border: 1px solid #cbd5e1; border-radius: 6px; font-size: 0.85rem; }
        .search-input-group input:focus { outline: 2px solid var(--primary-light); border-color: var(--primary); }
        .selected-place { font-size: 0.72rem; color: var(--primary); margin: 3px 0 0 28px; min-height: 1em; }
        .search-results {
            position: absolute; top: 40px; left: 28px; right: 0; background: #fff; border: 1px solid #cbd5e1;
            border-radius: 8px; box-shadow: 0 6px 16px rgba(0,0,0,0.12); z-index: 50; max-height: 240px; overflow-y: auto; display: none;
        }
        .search-results div { padding: 8px 10px; font-size: 0.8rem; cursor: pointer; border-bottom: 1px solid #f1f5f9; }
        .search-results div:hover { background: var(--primary-light); }
        .search-results small { display: block; color: var(--gray); font-size: 0.7rem; }

        .transport-tabs, .emotion-selector { display: grid; grid-template-columns: repeat(4, 1fr); gap: 6px; }
        .transport-tab, .emotion-btn {
            padding: 8px 4px; border: 1px solid #cbd5e1; border-radius: 8px; background: white;
            cursor: pointer; font-size: 0.75rem; display: flex; flex-direction: column; align-items: center; gap: 4px;
        }
        .transport-tab.active, .emotion-btn.active { border-color: var(--primary); background: var(--primary-light); color: var(--primary); font-weight: 700; }

        .slider-group { display: flex; flex-direction: column; gap: 8px; }
        .slider-item { display: flex; flex-direction: column; gap: 2px; }
        .slider-label { display: flex; justify-content: space-between; font-size: 0.78rem; color: #475569; }
        .slider-item input[type=range] { width: 100%; accent-color: var(--primary); }

        .btn {
            padding: 11px; border: none; border-radius: 8px; font-weight: 700; cursor: pointer;
            font-size: 0.88rem; display: inline-flex; align-items: center; justify-content: center; gap: 8px; width: 100%;
        }
        .btn:disabled { opacity: 0.6; cursor: not-allowed; }
        .btn-primary { background: var(--primary); color: white; }
        .btn-location { background: #fff; border: 1px solid #cbd5e1; color: var(--dark); }
        .btn-small { width: auto; padding: 8px 10px; font-size: 0.8rem; }

        #result-section { display: none; }
        .stats-grid { display: grid; grid-template-columns: repeat(3, 1fr); gap: 6px; margin-top: 6px; }
        .stat-box { background: var(--light-bg); padding: 8px; border-radius: 8px; text-align: center; }
        .stat-box .val { font-size: 0.95rem; font-weight: 700; color: var(--primary); }
        .stat-box .lbl { font-size: 0.68rem; color: var(--gray); }
        .score-bar { height: 8px; background: #e2e8f0; border-radius: 4px; overflow: hidden; margin: 4px 0 8px; }
        .score-bar > div { height: 100%; background: var(--primary); transition: width .4s; }
        .reason { font-size: 0.74rem; color: #475569; margin-top: 8px; line-height: 1.55; }
        .reason li { margin-left: 16px; }
        .cand-list { margin-top: 10px; display: flex; flex-direction: column; gap: 6px; }
        .cand { display: flex; justify-content: space-between; align-items: center; padding: 7px 10px; border: 1px solid #e2e8f0; border-radius: 8px; font-size: 0.76rem; cursor: pointer; }
        .cand:hover { border-color: var(--primary); }
        .cand.active { border-color: var(--primary); background: var(--primary-light); font-weight: 700; }
        .cand .sc { color: var(--primary); font-weight: 700; }
        .note { font-size: 0.68rem; color: var(--gray); margin-top: 8px; }

        #loading-overlay {
            position: fixed; inset: 0; background: rgba(255, 255, 255, 0.94); z-index: 9999;
            display: none; flex-direction: column; align-items: center; justify-content: center;
        }
        .spinner { width: 44px; height: 44px; border: 4px solid #e2e8f0; border-top: 4px solid var(--primary); border-radius: 50%; animation: spin 1s linear infinite; margin-bottom: 12px; }
        @keyframes spin { to { transform: rotate(360deg); } }

        #toast {
            position: fixed; left: 50%; bottom: 30px; transform: translateX(-50%) translateY(20px); opacity: 0;
            background: var(--dark); color: #fff; padding: 10px 18px; border-radius: 8px; font-size: 0.85rem;
            z-index: 10000; transition: all .25s; pointer-events: none; max-width: 90vw; text-align: center;
        }
        #toast.show { opacity: 1; transform: translateX(-50%) translateY(0); }
        #toast.error { background: var(--danger); }

        .map-error { position: absolute; inset: 0; display: none; align-items: center; justify-content: center; padding: 30px; text-align: center; color: #475569; font-size: 0.9rem; line-height: 1.7; z-index: 5; }

        .legend {
            position: absolute; bottom: 20px; right: 20px; background: rgba(255, 255, 255, 0.95);
            padding: 12px 16px; border-radius: 8px; box-shadow: 0 2px 10px rgba(0,0,0,0.15); z-index: 100; font-size: 0.78rem;
        }
        .legend-item { display: flex; align-items: center; gap: 8px; margin-bottom: 4px; }
        .legend-color { width: 14px; height: 14px; border-radius: 3px; }

        /* 모바일: 지도 위, 패널 아래 */
        @media (max-width: 768px) {
            body, html { overflow: auto; }
            #app-container { flex-direction: column-reverse; height: auto; }
            #map-area { height: 55vh; flex: none; }
            #sidebar { width: 100%; height: auto; }
            .content { overflow: visible; }
            .legend { bottom: 10px; right: 10px; font-size: 0.7rem; padding: 8px 10px; }
        }
    </style>
</head>
<body>

<div id="app-container">
    <div id="sidebar">
        <div class="header">
            <h1><i class="fa-solid fa-brain"></i> 마음자리 GEO-MIND</h1>
            <span class="subtitle">4가지 이동 수단 통합 심리 맞춤 경로 추천</span>
        </div>

        <div class="content">
            <!-- 출발지 / 목적지 -->
            <div class="card">
                <div class="card-title"><i class="fa-solid fa-magnifying-glass-location"></i> 출발지 / 목적지 설정</div>
                <div class="search-box">
                    <div class="search-row">
                        <div class="search-input-group">
                            <span class="pin start">출</span>
                            <input type="text" id="start-keyword" placeholder="출발지 입력 (예: 서울시청)">
                            <button class="btn btn-location btn-small" onclick="searchPlace('start')">검색</button>
                        </div>
                        <div class="search-results" id="start-results"></div>
                        <div class="selected-place" id="start-selected">서울시청 (기본값)</div>
                    </div>
                    <div class="search-row">
                        <div class="search-input-group">
                            <span class="pin end">도</span>
                            <input type="text" id="end-keyword" placeholder="목적지 입력 (예: 경복궁)">
                            <button class="btn btn-location btn-small" onclick="searchPlace('end')">검색</button>
                        </div>
                        <div class="search-results" id="end-results"></div>
                        <div class="selected-place" id="end-selected">경복궁 (기본값)</div>
                    </div>
                    <div style="display:flex;gap:6px">
                        <button class="btn btn-location" onclick="getCurrentLocation()">
                            <i class="fa-solid fa-location-crosshairs" style="color: var(--primary);"></i> 현재 위치로 출발
                        </button>
                        <button class="btn btn-location" style="width:auto;padding:0 12px" onclick="swapPoints()" title="출발/도착 바꾸기">
                            <i class="fa-solid fa-arrow-right-arrow-left"></i>
                        </button>
                    </div>
                    <div style="font-size:0.7rem;color:#64748b">💡 지도를 직접 눌러서 출발지·도착지를 정할 수도 있어요</div>
                </div>
            </div>

            <!-- 이동 수단 -->
            <div class="card">
                <div class="card-title"><i class="fa-solid fa-route"></i> 이동 수단 선택</div>
                <div class="transport-tabs">
                    <button class="transport-tab" data-mode="walk" onclick="setTransport('walk', this)">
                        <i class="fa-solid fa-person-walking" style="font-size: 1.1rem;"></i><span>보행/산책</span>
                    </button>
                    <button class="transport-tab active" data-mode="bike" onclick="setTransport('bike', this)">
                        <i class="fa-solid fa-bicycle" style="font-size: 1.1rem;"></i><span>자전거</span>
                    </button>
                    <button class="transport-tab" data-mode="transit" onclick="setTransport('transit', this)">
                        <i class="fa-solid fa-bus" style="font-size: 1.1rem;"></i><span>대중교통</span>
                    </button>
                    <button class="transport-tab" data-mode="car" onclick="setTransport('car', this)">
                        <i class="fa-solid fa-car" style="font-size: 1.1rem;"></i><span>자동차</span>
                    </button>
                </div>
            </div>

            <!-- 심리 상태 -->
            <div class="card">
                <div class="card-title"><i class="fa-solid fa-face-smile"></i> 현재 내 심리 상태</div>
                <div class="emotion-selector">
                    <button class="emotion-btn active" onclick="setEmotion('calm', this)">
                        <i class="fa-solid fa-face-smile" style="color: #43a047;"></i><span>평온함</span>
                    </button>
                    <button class="emotion-btn" onclick="setEmotion('stress', this)">
                        <i class="fa-solid fa-face-frown" style="color: #fb8c00;"></i><span>스트레스</span>
                    </button>
                    <button class="emotion-btn" onclick="setEmotion('anxiety', this)">
                        <i class="fa-solid fa-face-flushed" style="color: #e53935;"></i><span>불안/공황</span>
                    </button>
                    <button class="emotion-btn" onclick="setEmotion('fatigue', this)">
                        <i class="fa-solid fa-face-tired" style="color: #8e24aa;"></i><span>피로</span>
                    </button>
                </div>
            </div>

            <!-- 공간 가중치 -->
            <div class="card">
                <div class="card-title"><i class="fa-solid fa-sliders"></i> 공간 가중치 설정</div>
                <div class="slider-group">
                    <div class="slider-item">
                        <div class="slider-label"><span>소음/정체 회피성</span><span id="weight-noise-val">70%</span></div>
                        <input type="range" id="weight-noise" min="0" max="100" value="70" oninput="updateWeights()">
                    </div>
                    <div class="slider-item">
                        <div class="slider-label"><span>녹지/공원 선호도</span><span id="weight-green-val">80%</span></div>
                        <input type="range" id="weight-green" min="0" max="100" value="80" oninput="updateWeights()">
                    </div>
                    <div class="slider-item">
                        <div class="slider-label"><span>유동인구 회피성</span><span id="weight-crowd-val">50%</span></div>
                        <input type="range" id="weight-crowd" min="0" max="100" value="50" oninput="updateWeights()">
                    </div>
                </div>
            </div>

            <button class="btn btn-primary" id="search-btn" onclick="requestIntegratedRoute()">
                <i class="fa-solid fa-route"></i> 통합 심리 맞춤 경로 탐색
            </button>

            <!-- 결과 -->
            <div class="card" id="result-section">
                <div class="card-title"><i class="fa-solid fa-chart-pie"></i> 추천 경로 분석 리포트</div>
                <div style="font-size: 0.82rem; font-weight: bold; color: var(--primary);" id="route-recommend-title">분석 대기 중</div>
                <div class="score-bar"><div id="score-fill" style="width:0%"></div></div>
                <div class="stats-grid">
                    <div class="stat-box"><div class="val" id="stat-distance">-</div><div class="lbl">이동 거리</div></div>
                    <div class="stat-box"><div class="val" id="stat-duration">-</div><div class="lbl">소요 시간</div></div>
                    <div class="stat-box"><div class="val" id="stat-extra">-</div><div class="lbl" id="stat-extra-lbl">기타</div></div>
                </div>
                <ul class="reason" id="recommend-reason"></ul>
                <div class="cand-list" id="cand-list"></div>
                <div class="note">* 녹지·혼잡도는 경로 주변 카카오 장소 데이터(공원, 음식점·카페 밀집도)를 기반으로 추정한 값입니다.</div>
            </div>
        </div>
    </div>

    <div id="map-area">
        <div id="kakao-map"></div>
        <div class="map-error" id="map-error"></div>
        <div class="legend">
            <div style="font-weight: 700; margin-bottom: 6px;">공간 심리 쾌적도 범례</div>
            <div class="legend-item"><div class="legend-color" style="background: #4a7c59;"></div><span>추천 경로</span></div>
            <div class="legend-item"><div class="legend-color" style="background: #9e9e9e;"></div><span>다른 후보 경로</span></div>
            <div class="legend-item"><div class="legend-color" style="background: rgba(67,160,71,0.4); border: 1px solid #43a047;"></div><span>녹지·공원 구간</span></div>
            <div class="legend-item"><div class="legend-color" style="background: rgba(229,57,53,0.4); border: 1px solid #e53935;"></div><span>혼잡·소음 주의 구간</span></div>
        </div>
    </div>
</div>

<div id="loading-overlay">
    <div class="spinner"></div>
    <div style="font-size: 1.4rem; font-weight: 700; color: var(--primary);">마음자리 GEO-MIND</div>
    <div style="font-size: 0.85rem; color: #64748b; margin-top: 6px;" id="loading-text">경로 데이터를 불러오는 중...</div>
</div>
<div id="toast"></div>

<script>
/* =====================================================================
 *  ★ 설정 (키는 여기 한 곳에서만 바꾸면 됩니다)
 * ===================================================================== */
const CONFIG = {
    // 카카오 개발자센터 > 내 애플리케이션 > 앱 키 > "JavaScript 키"  (지도 + 장소검색)
    KAKAO_JS_KEY: "af7950a915f4a156460c375d45600c1b",
    // 카카오 개발자센터 > 앱 키 > "REST API 키"  (자동차 길찾기 - 카카오모빌리티)
    KAKAO_REST_KEY: "3261428ad5a92dd6c922c3826add9d3b",
    // ODsay LAB(lab.odsay.com) 에서 발급받은 "Web 키"  (대중교통 길찾기)
    ODSAY_KEY: "dqB+ZOdAw7ApS6ZIZ9YZyQ",
    // 보행·자전거 길찾기 서버 (OpenStreetMap 기반 무료 OSRM, 키 불필요)
    OSRM_WALK: "https://routing.openstreetmap.de/routed-foot/route/v1/foot",
    OSRM_BIKE: "https://routing.openstreetmap.de/routed-bike/route/v1/bike"
};

/* ===================================================================== */
let map = null, ps = null;
let startPoint = null, endPoint = null;
let startMarker = null, endMarker = null;
let routeOverlays = [];     // 지도 위 경로 선
let envOverlays = [];       // 녹지/혼잡 원
let lastResult = null;      // { mode, scored: [...] }

let selectedTransport = 'bike';
let selectedEmotion = 'calm';

const MODE_LABEL = { walk: '보행', bike: '자전거', transit: '대중교통', car: '자동차' };
const EMOTION_LABEL = { calm: '평온함', stress: '스트레스', anxiety: '불안/공황', fatigue: '피로' };

/* ---------- 카카오 지도 SDK 로드 (키를 CONFIG에서 읽어 동적으로 로드) ---------- */
(function loadKakaoSdk() {
    const s = document.createElement('script');
    s.src = `https://dapi.kakao.com/v2/maps/sdk.js?appkey=${CONFIG.KAKAO_JS_KEY}&libraries=services&autoload=false`;
    s.onload = () => {
        if (!window.kakao || !kakao.maps) return showMapError();
        kakao.maps.load(initMap);
    };
    s.onerror = showMapError;
    document.head.appendChild(s);
})();

function showMapError() {
    const el = document.getElementById('map-error');
    el.style.display = 'flex';
    el.innerHTML = `<div><i class="fa-solid fa-triangle-exclamation" style="font-size:2rem;color:#fb8c00"></i><br>
        카카오 지도를 불러오지 못했습니다.<br>
        카카오 개발자센터 → 내 애플리케이션 → <b>플랫폼 → Web</b>에<br>
        <b>${location.origin}</b> 이 등록되어 있는지,<br>JavaScript 키가 맞는지 확인해 주세요.</div>`;
}

function initMap() {
    map = new kakao.maps.Map(document.getElementById('kakao-map'), {
        center: new kakao.maps.LatLng(37.5700, 126.9770),
        level: 5
    });
    ps = new kakao.maps.services.Places();
    map.addControl(new kakao.maps.ZoomControl(), kakao.maps.ControlPosition.RIGHT);

    // 기본값: 서울시청 → 경복궁 (원래 덕수궁은 300m 거리라 대중교통 검색이 안 됨)
    setPoint('start', new kakao.maps.LatLng(37.5665, 126.9780), '서울시청 (기본값)');
    setPoint('end', new kakao.maps.LatLng(37.5796, 126.9770), '경복궁 (기본값)');
    document.getElementById('start-keyword').value = confirmedText.start = '서울시청';
    document.getElementById('end-keyword').value = confirmedText.end = '경복궁';

    kakao.maps.event.addListener(map, 'click', onMapClick);

    // 엔터키로 검색 / 입력을 바꾸면 "미확정" 표시
    ['start', 'end'].forEach(t => {
        const input = document.getElementById(`${t}-keyword`);
        input.addEventListener('keydown', e => {
            if (e.key === 'Enter' && !e.isComposing) { e.preventDefault(); searchPlace(t); }
        });
        input.addEventListener('input', () => {
            const sel = document.getElementById(`${t}-selected`);
            if (input.value.trim() !== confirmedText[t]) {
                sel.textContent = '⚠ 검색 버튼(또는 Enter)을 눌러야 적용돼요';
                sel.style.color = '#fb8c00';
            } else {
                sel.style.color = '';
            }
        });
    });
    // 바깥 클릭 시 검색 결과 닫기
    document.addEventListener('click', e => {
        if (!e.target.closest('.search-row')) document.querySelectorAll('.search-results').forEach(r => r.style.display = 'none');
    });
}

/* ---------- 공용 UI ---------- */
let toastTimer = null;
function toast(msg, isError = false) {
    const t = document.getElementById('toast');
    t.textContent = msg;
    t.className = 'show' + (isError ? ' error' : '');
    clearTimeout(toastTimer);
    toastTimer = setTimeout(() => t.className = '', isError ? 4500 : 2500);
}
function setLoading(on, text) {
    document.getElementById('loading-overlay').style.display = on ? 'flex' : 'none';
    document.getElementById('search-btn').disabled = on;
    if (text) document.getElementById('loading-text').textContent = text;
}
function ensureMap() {
    if (!map) { toast('지도가 아직 로드되지 않았습니다. 잠시 후 다시 시도해 주세요.', true); return false; }
    return true;
}

/* ---------- 마커 ---------- */
function makeMarkerImage(color, text) {
    const svg = `<svg xmlns="http://www.w3.org/2000/svg" width="34" height="44" viewBox="0 0 34 44">
        <path d="M17 0C7.6 0 0 7.6 0 17c0 12.7 17 27 17 27s17-14.3 17-27C34 7.6 26.4 0 17 0z" fill="${color}"/>
        <circle cx="17" cy="17" r="11" fill="#fff"/>
        <text x="17" y="22" font-size="13" font-weight="700" text-anchor="middle" fill="${color}" font-family="sans-serif">${text}</text></svg>`;
    return new kakao.maps.MarkerImage('data:image/svg+xml;charset=utf-8,' + encodeURIComponent(svg),
        new kakao.maps.Size(34, 44), { offset: new kakao.maps.Point(17, 44) });
}
function setPoint(type, latlng, label) {
    if (type === 'start') {
        startPoint = latlng;
        if (startMarker) startMarker.setMap(null);
        startMarker = new kakao.maps.Marker({ map, position: latlng, image: makeMarkerImage('#1e88e5', '출'), zIndex: 5 });
    } else {
        endPoint = latlng;
        if (endMarker) endMarker.setMap(null);
        endMarker = new kakao.maps.Marker({ map, position: latlng, image: makeMarkerImage('#e53935', '도'), zIndex: 5 });
    }
    const sel = document.getElementById(`${type}-selected`);
    sel.textContent = label ? '✔ ' + label : '';
    sel.style.color = '';
}

/* ---------- 장소 검색 ----------
 *  검색하면 첫 번째 결과로 바로 설정되고, 아래 목록에서 다른 장소로 바꿀 수 있음 */
const confirmedText = { start: '', end: '' };   // 마지막으로 확정된 입력값

function keywordSearchAsync(keyword) {
    return new Promise(resolve => {
        ps.keywordSearch(keyword, (data, status) => {
            if (status === kakao.maps.services.Status.OK) return resolve({ ok: true, data });
            // 장소명이 없으면 주소로 한 번 더 검색 (예: "세종대로 110")
            new kakao.maps.services.Geocoder().addressSearch(keyword, (d2, s2) => {
                if (s2 === kakao.maps.services.Status.OK) {
                    resolve({ ok: true, data: d2.map(a => ({ place_name: a.address_name, address_name: a.address_name, x: a.x, y: a.y, id: a.address_name })) });
                } else {
                    resolve({ ok: false, status: s2 === kakao.maps.services.Status.ZERO_RESULT ? status : s2 });
                }
            });
        });
    });
}

function applyPlace(type, place) {
    const loc = new kakao.maps.LatLng(Number(place.y), Number(place.x));
    setPoint(type, loc, place.place_name);
    document.getElementById(`${type}-keyword`).value = place.place_name;
    confirmedText[type] = place.place_name;
    clearMapRoutes();
    fitPoints();
}

async function searchPlace(type, silent = false) {
    if (!ensureMap()) return false;
    const input = document.getElementById(`${type}-keyword`);
    const keyword = input.value.trim();
    const box = document.getElementById(`${type}-results`);
    if (!keyword) { toast('검색어를 입력해 주세요.'); return false; }

    const res = await keywordSearchAsync(keyword);
    if (!res.ok) {
        box.style.display = 'none';
        if (res.status === kakao.maps.services.Status.ZERO_RESULT) {
            toast(`"${keyword}" 검색 결과가 없습니다. 다른 이름으로 검색해 보세요.`, true);
        } else {
            toast('장소 검색 오류: 카카오 개발자센터에서 "카카오맵" 사용 설정이 켜져 있는지 확인해 주세요.', true);
        }
        return false;
    }

    applyPlace(type, res.data[0]);   // 첫 번째 결과로 바로 설정
    toast(`${type === 'start' ? '출발지' : '도착지'}: ${res.data[0].place_name}`);

    if (!silent && res.data.length > 1) {
        box.innerHTML = '<div style="color:#64748b;font-size:0.72rem;cursor:default;background:#f8fafc">다른 장소였나요? 아래에서 고르세요</div>';
        res.data.slice(0, 7).forEach((place, i) => {
            const item = document.createElement('div');
            item.innerHTML = `${i === 0 ? '✔ ' : ''}${place.place_name}<small>${place.road_address_name || place.address_name || ''}</small>`;
            item.onclick = (e) => {
                e.stopPropagation();
                applyPlace(type, place);
                box.style.display = 'none';
            };
            box.appendChild(item);
        });
        box.style.display = 'block';
    }
    return true;
}

/* 출발/도착 바꾸기 */
function swapPoints() {
    if (!ensureMap()) return;
    const s = startPoint, e = endPoint;
    const sl = document.getElementById('start-selected').textContent.replace('✔ ', '');
    const el = document.getElementById('end-selected').textContent.replace('✔ ', '');
    const sk = document.getElementById('start-keyword').value, ek = document.getElementById('end-keyword').value;
    setPoint('start', e, el); setPoint('end', s, sl);
    document.getElementById('start-keyword').value = ek; document.getElementById('end-keyword').value = sk;
    [confirmedText.start, confirmedText.end] = [confirmedText.end, confirmedText.start];
    clearMapRoutes();
}

/* 지도를 눌러서 출발/도착 정하기 */
let clickOverlay = null;
function onMapClick(mouseEvent) {
    const latlng = mouseEvent.latLng;
    if (clickOverlay) clickOverlay.setMap(null);
    const el = document.createElement('div');
    el.style.cssText = 'background:#fff;border-radius:8px;box-shadow:0 2px 10px rgba(0,0,0,.25);padding:6px;display:flex;gap:6px;transform:translateY(-12px)';
    el.innerHTML = `<button data-t="start" style="border:none;background:#1e88e5;color:#fff;border-radius:6px;padding:6px 10px;font-weight:700;cursor:pointer">여기서 출발</button>
                    <button data-t="end" style="border:none;background:#e53935;color:#fff;border-radius:6px;padding:6px 10px;font-weight:700;cursor:pointer">여기로 도착</button>
                    <button data-t="x" style="border:none;background:#eceff1;border-radius:6px;padding:6px 8px;cursor:pointer">✕</button>`;
    el.addEventListener('click', ev => {
        ev.stopPropagation();
        const t = ev.target.dataset.t;
        if (!t) return;
        clickOverlay.setMap(null); clickOverlay = null;
        if (t === 'x') return;
        setPoint(t, latlng, '지도에서 선택한 위치');
        reverseLabel(t, latlng);
        clearMapRoutes();
    });
    ['mousedown', 'touchstart', 'dblclick'].forEach(n => el.addEventListener(n, ev => ev.stopPropagation()));
    clickOverlay = new kakao.maps.CustomOverlay({ map, position: latlng, content: el, yAnchor: 1, zIndex: 20 });
}

/* 좌표 → 주소 이름 (입력칸에 표시) */
function reverseLabel(type, latlng) {
    new kakao.maps.services.Geocoder().coord2Address(latlng.getLng(), latlng.getLat(), (res, status) => {
        if (status !== kakao.maps.services.Status.OK || !res[0]) return;
        const a = res[0].road_address?.address_name || res[0].address?.address_name;
        if (!a) return;
        document.getElementById(`${type}-keyword`).value = a;
        document.getElementById(`${type}-selected`).textContent = '✔ ' + a;
        confirmedText[type] = a;
    });
}

function fitPoints() {
    if (!startPoint || !endPoint) return;
    const b = new kakao.maps.LatLngBounds();
    b.extend(startPoint); b.extend(endPoint);
    map.setBounds(b, 80, 80, 80, 80);
}

function getCurrentLocation() {
    if (!ensureMap()) return;
    if (!navigator.geolocation) return toast('이 브라우저는 위치 정보를 지원하지 않습니다.', true);
    toast('현재 위치를 확인하는 중...');
    navigator.geolocation.getCurrentPosition(pos => {
        const loc = new kakao.maps.LatLng(pos.coords.latitude, pos.coords.longitude);
        setPoint('start', loc, '현재 내 위치');
        document.getElementById('start-keyword').value = '현재 내 위치';
        confirmedText.start = '현재 내 위치';
        reverseLabel('start', loc);
        clearMapRoutes();
        fitPoints();
        toast('현재 위치가 출발지로 설정되었습니다.');
    }, err => {
        toast(err.code === 1 ? '위치 권한이 거부되었습니다. 브라우저 설정에서 허용해 주세요.' : '위치 정보를 가져올 수 없습니다.', true);
    }, { enableHighAccuracy: true, timeout: 10000 });
}

/* ---------- 선택 UI ---------- */
function setTransport(mode, btn) {
    document.querySelectorAll('.transport-tab').forEach(b => b.classList.remove('active'));
    btn.classList.add('active');
    selectedTransport = mode;
}
function setEmotion(type, btn) {
    document.querySelectorAll('.emotion-btn').forEach(b => b.classList.remove('active'));
    btn.classList.add('active');
    selectedEmotion = type;
    if (lastResult) rescoreAndRender();   // 결과가 있으면 즉시 재평가
}
function updateWeights() {
    ['noise', 'green', 'crowd'].forEach(k => {
        document.getElementById(`weight-${k}-val`).innerText = document.getElementById(`weight-${k}`).value + '%';
    });
    clearTimeout(updateWeights.t);
    updateWeights.t = setTimeout(() => { if (lastResult) rescoreAndRender(); }, 200);
}

/* =====================================================================
 *  메인: 통합 경로 탐색
 * ===================================================================== */
async function requestIntegratedRoute() {
    if (!ensureMap()) return;
    if (!startPoint || !endPoint) return toast('출발지와 목적지를 설정해 주세요.', true);

    // 글자만 바꾸고 검색을 안 눌렀으면 자동으로 검색해서 적용
    for (const t of ['start', 'end']) {
        const v = document.getElementById(`${t}-keyword`).value.trim();
        if (v && v !== confirmedText[t]) {
            const ok = await searchPlace(t, true);
            if (!ok) return;
        }
    }

    const straight = haversine(startPoint.getLat(), startPoint.getLng(), endPoint.getLat(), endPoint.getLng());
    if (straight < 30) return toast('출발지와 목적지가 너무 가깝습니다.', true);

    setLoading(true, `${MODE_LABEL[selectedTransport]} 경로 데이터를 불러오는 중...`);
    try {
        let candidates = [];
        if (selectedTransport === 'walk') candidates = await fetchOsrmRoutes('walk');
        else if (selectedTransport === 'bike') candidates = await fetchOsrmRoutes('bike');
        else if (selectedTransport === 'car') candidates = await fetchCarRoutes();
        else if (selectedTransport === 'transit') candidates = await fetchTransitRoutes();

        if (!candidates.length) throw new Error('탐색 가능한 경로가 없습니다.');
        candidates = candidates.slice(0, 4);

        setLoading(true, '경로 주변 녹지·혼잡도 분석 중...');
        await analyzeEnvironment(candidates);

        lastResult = { mode: selectedTransport, candidates, selectedIdx: null };
        rescoreAndRender(true);
    } catch (err) {
        console.error('[GEO-MIND] 경로 탐색 오류:', err);
        clearMapRoutes();
        toast(err.message || '경로 탐색 중 오류가 발생했습니다.', true);
    } finally {
        setLoading(false);
    }
}

/* ---------- 1·2. 보행 / 자전거 : OSRM (OpenStreetMap) ---------- */
async function fetchOsrmRoutes(mode) {
    const base = mode === 'walk' ? CONFIG.OSRM_WALK : CONFIG.OSRM_BIKE;
    const coords = `${startPoint.getLng()},${startPoint.getLat()};${endPoint.getLng()},${endPoint.getLat()}`;
    const url = `${base}/${coords}?overview=full&geometries=geojson&alternatives=3&steps=false`;

    let data;
    try {
        const res = await fetch(url);
        data = await res.json();
    } catch (e) {
        throw new Error(`${MODE_LABEL[mode]} 경로 서버에 연결할 수 없습니다. 네트워크를 확인해 주세요.`);
    }
    if (data.code !== 'Ok' || !data.routes?.length) throw new Error(`${MODE_LABEL[mode]} 경로를 찾을 수 없습니다.`);

    // OSRM 기본 속도 보정 (보행 4.5km/h, 자전거 15km/h 기준으로 현실화)
    const speed = mode === 'walk' ? 1.25 : 4.2; // m/s
    return data.routes.map((r, i) => ({
        type: mode,
        name: i === 0 ? '기본 경로' : `대안 경로 ${i}`,
        distance: r.distance,
        duration: Math.max(r.duration, r.distance / speed),
        segments: [{ path: r.geometry.coordinates.map(([x, y]) => new kakao.maps.LatLng(y, x)), color: null }]
    }));
}

/* ---------- 3. 자동차 : 카카오모빌리티 길찾기 ---------- */
async function fetchCarRoutes() {
    const priorities = ['RECOMMEND', 'TIME', 'DISTANCE'];
    const origin = `${startPoint.getLng()},${startPoint.getLat()}`;
    const dest = `${endPoint.getLng()},${endPoint.getLat()}`;

    const results = await Promise.all(priorities.map(async p => {
        try {
            const res = await fetch(`https://apis-navi.kakaomobility.com/v1/directions?origin=${origin}&destination=${dest}&priority=${p}&summary=false`,
                { headers: { Authorization: `KakaoAK ${CONFIG.KAKAO_REST_KEY}` } });
            if (res.status === 401) throw new Error('auth');
            if (!res.ok) return null;
            const data = await res.json();
            const r = data.routes?.[0];
            if (!r || r.result_code !== 0) return null;
            return { r, p };
        } catch (e) {
            if (e.message === 'auth') throw new Error('카카오 REST API 키 인증 실패 (카카오모빌리티 길찾기 사용 설정 확인)');
            return null;
        }
    }));

    const seen = new Set();
    const names = { RECOMMEND: '추천 경로', TIME: '최단 시간', DISTANCE: '최단 거리' };
    const out = [];
    for (const item of results) {
        if (!item) continue;
        const { r, p } = item;
        const key = `${r.summary.distance}-${r.summary.duration}`;
        if (seen.has(key)) continue;   // 같은 경로 중복 제거
        seen.add(key);

        const path = [];
        let jam = 0, total = 0;
        r.sections.forEach(sec => sec.roads.forEach(road => {
            for (let i = 0; i < road.vertexes.length; i += 2) path.push(new kakao.maps.LatLng(road.vertexes[i + 1], road.vertexes[i]));
            total += road.distance;
            if ([1, 2, 3, 6].includes(road.traffic_state)) jam += road.distance; // 정체·지체·서행·사고
        }));
        out.push({
            type: 'car', name: names[p],
            distance: r.summary.distance, duration: r.summary.duration,
            toll: r.summary.fare?.toll || 0,
            congestion: total ? jam / total : 0,
            segments: [{ path, color: null }]
        });
    }
    if (!out.length) throw new Error('자동차 경로를 찾을 수 없습니다.');
    return out;
}

/* ---------- 4. 대중교통 : ODsay ---------- */
async function fetchTransitRoutes() {
    if (!CONFIG.ODSAY_KEY) {
        throw new Error('대중교통 검색에는 ODsay API 키가 필요합니다. 코드 상단 CONFIG.ODSAY_KEY에 키를 넣어 주세요.');
    }
    const url = `https://api.odsay.com/v1/api/searchPubTransPathT?SX=${startPoint.getLng()}&SY=${startPoint.getLat()}&EX=${endPoint.getLng()}&EY=${endPoint.getLat()}&apiKey=${encodeURIComponent(CONFIG.ODSAY_KEY)}`;
    let data;
    try {
        data = await (await fetch(url)).json();
    } catch (e) {
        throw new Error('대중교통 서버(ODsay)에 연결할 수 없습니다.');
    }
    if (data.error) {
        const err = Array.isArray(data.error) ? data.error[0] : data.error;
        const code = String(err.code);
        if (code === '-98') throw new Error('출발지와 목적지가 700m 이내라 대중교통 경로가 없습니다. 보행을 이용해 보세요.');
        if (code === '500' || /key|ApiKey|auth/i.test(err.message || err.msg || '')) throw new Error('ODsay API 키 또는 등록된 도메인(URI)을 확인해 주세요.');
        throw new Error('대중교통 경로 오류: ' + (err.message || err.msg || code));
    }
    const paths = data.result?.path || [];
    if (!paths.length) throw new Error('대중교통 경로를 찾을 수 없습니다.');

    return paths.map((p, idx) => {
        const info = p.info;
        const segments = [];
        let cursor = startPoint;
        const subs = p.subPath;

        subs.forEach((sp, i) => {
            if (sp.trafficType === 3) {           // 도보: 이전 지점 → 다음 탑승 지점
                const next = subs.slice(i + 1).find(s => s.trafficType !== 3);
                const to = next ? new kakao.maps.LatLng(next.startY, next.startX) : endPoint;
                if (sp.distance > 0) segments.push({ path: [cursor, to], color: '#78909c', dashed: true, kind: 'walk' });
                cursor = to;
            } else {
                const st = sp.passStopList?.stations || [];
                const path = st.length ? st.map(s => new kakao.maps.LatLng(s.y, s.x))
                                       : [new kakao.maps.LatLng(sp.startY, sp.startX), new kakao.maps.LatLng(sp.endY, sp.endX)];
                const lane = sp.lane?.[0] || {};
                segments.push({
                    path,
                    color: sp.trafficType === 1 ? subwayColor(lane.subwayCode) : '#00A86B',
                    kind: sp.trafficType === 1 ? 'subway' : 'bus',
                    label: sp.trafficType === 1 ? lane.name : (lane.busNo + '번 버스')
                });
                cursor = path[path.length - 1];
            }
        });

        const rides = subs.filter(s => s.trafficType !== 3).map(s => s.trafficType === 1 ? (s.lane?.[0]?.name || '지하철') : ((s.lane?.[0]?.busNo || '') + '번'));
        const transfers = Math.max(0, (info.busTransitCount || 0) + (info.subwayTransitCount || 0) - 1);
        return {
            type: 'transit',
            name: rides.join(' → ') || `경로 ${idx + 1}`,
            distance: info.totalDistance,
            duration: info.totalTime * 60,
            fare: info.payment || 0,
            transferCount: transfers,
            walkDistance: info.totalWalk || 0,
            segments
        };
    });
}
function subwayColor(code) {
    const c = { 1: '#0052A4', 2: '#00A84D', 3: '#EF7C1C', 4: '#00A5DE', 5: '#996CAC', 6: '#CD7C2F', 7: '#747F00', 8: '#E6186C', 9: '#BDB092' };
    return c[code] || '#0052A4';
}

/* =====================================================================
 *  주변 환경 분석 (카카오 장소검색으로 녹지 / 혼잡 추정)
 * ===================================================================== */
const envCache = new Map();
function placesQuery(kind, latlng) {
    const key = `${kind}:${latlng.getLat().toFixed(3)},${latlng.getLng().toFixed(3)}`;
    if (envCache.has(key)) return envCache.get(key);
    const p = new Promise(resolve => {
        const opts = { location: latlng, radius: kind === 'park' ? 400 : 250, size: 15 };
        const cb = (data, status, pagination) => {
            if (status !== kakao.maps.services.Status.OK) return resolve({ count: 0, items: [] });
            resolve({ count: pagination?.totalCount ?? data.length, items: data });
        };
        if (kind === 'park') ps.keywordSearch('공원', cb, opts);
        else ps.categorySearch(kind, cb, opts);   // FD6 음식점, CE7 카페
    });
    envCache.set(key, p);
    return p;
}
function samplePoints(path, n) {
    if (path.length <= 2) return path.slice();
    const pts = [];
    for (let i = 1; i <= n; i++) pts.push(path[Math.floor((path.length - 1) * i / (n + 1))]);
    return pts;
}
async function analyzeEnvironment(candidates) {
    await Promise.all(candidates.map(async cand => {
        const full = cand.segments.flatMap(s => s.path);
        const pts = samplePoints(full, 4);
        const res = await Promise.all(pts.map(async pt => {
            const [park, food, cafe] = await Promise.all([placesQuery('park', pt), placesQuery('FD6', pt), placesQuery('CE7', pt)]);
            return { pt, park, busy: food.count + cafe.count };
        }));
        // 0~1 정규화
        cand.greenScore = Math.min(1, res.reduce((a, r) => a + Math.min(r.park.count, 4), 0) / (pts.length * 4));
        cand.crowdScore = Math.min(1, res.reduce((a, r) => a + Math.min(r.busy, 60), 0) / (pts.length * 60));
        cand.envSpots = res;
    }));
}

/* =====================================================================
 *  심리 상태 × 이동 수단 × 공간 가중치 평가
 * ===================================================================== */
const EMOTION_FACTOR = {
    //          시간   녹지   혼잡   소음   환승   도보부담
    calm:    { time: 0.8, green: 1.3, crowd: 0.8, noise: 0.8, transfer: 1.0, walk: 0.8 },
    stress:  { time: 1.0, green: 1.1, crowd: 1.3, noise: 1.4, transfer: 1.2, walk: 1.0 },
    anxiety: { time: 0.9, green: 1.0, crowd: 1.7, noise: 1.2, transfer: 1.6, walk: 1.0 },
    fatigue: { time: 1.6, green: 0.6, crowd: 1.0, noise: 1.0, transfer: 1.4, walk: 1.6 }
};

function scoreCandidates(candidates, mode) {
    const w = {
        noise: +document.getElementById('weight-noise').value / 100,
        green: +document.getElementById('weight-green').value / 100,
        crowd: +document.getElementById('weight-crowd').value / 100
    };
    const f = EMOTION_FACTOR[selectedEmotion];
    const minDur = Math.min(...candidates.map(c => c.duration));

    return candidates.map(c => {
        const reasons = [];
        // 시간: 가장 빠른 경로 대비 늘어난 비율만큼 감점 (최대 30점)
        const timePen = Math.min(30, (c.duration / minDur - 1) * 60 * f.time);
        // 녹지: 가산점 (최대 25점)
        const greenBonus = c.greenScore * 25 * w.green * f.green;
        // 혼잡(유동인구): 감점 (최대 25점)
        const crowdPen = c.crowdScore * 25 * w.crowd * f.crowd;
        // 소음/정체: 자동차는 실제 정체 구간 비율, 그 외는 상권 밀집도로 추정
        const noiseLevel = mode === 'car' ? c.congestion : c.crowdScore * 0.7;
        const noisePen = noiseLevel * 20 * w.noise * f.noise;

        let modePen = 0;
        if (mode === 'transit') {
            modePen += c.transferCount * 6 * f.transfer;
            modePen += Math.min(10, c.walkDistance / 150) * (f.walk - 0.5);
        } else if (mode === 'walk' && selectedEmotion === 'fatigue') {
            modePen += Math.min(10, c.distance / 500);
        }

        const score = Math.max(0, Math.min(100, 75 - timePen + greenBonus - crowdPen - noisePen - modePen));

        if (c.greenScore > 0.4) reasons.push(`경로 주변에 공원·녹지가 많습니다 (녹지 지수 ${Math.round(c.greenScore * 100)}).`);
        if (c.crowdScore > 0.5) reasons.push(`상권 밀집 구간을 지나 유동인구가 많을 수 있습니다 (혼잡 지수 ${Math.round(c.crowdScore * 100)}).`);
        else reasons.push(`비교적 한적한 구간 위주입니다 (혼잡 지수 ${Math.round(c.crowdScore * 100)}).`);
        if (mode === 'car') reasons.push(`정체·서행 구간 비율 ${Math.round(c.congestion * 100)}% (실시간 교통 정보).`);
        if (mode === 'transit') reasons.push(`환승 ${c.transferCount}회, 도보 ${c.walkDistance}m.`);

        return { ...c, finalScore: score, reasons };
    }).sort((a, b) => b.finalScore - a.finalScore);
}

function emotionSummary(mode) {
    switch (selectedEmotion) {
        case 'calm': return `평온한 상태를 유지할 수 있도록 녹지가 많은 쾌적한 ${MODE_LABEL[mode]} 경로에 가산점을 주었습니다.`;
        case 'stress': return `스트레스 완화를 위해 소음·정체·혼잡 구간이 적은 경로를 우선했습니다.`;
        case 'anxiety': return `불안/공황 상태를 고려해 사람이 붐비는 구간과 잦은 환승을 강하게 회피했습니다.`;
        case 'fatigue': return `피로한 상태를 고려해 소요 시간과 도보 부담이 적은 경로를 우선했습니다.`;
    }
}

/* =====================================================================
 *  렌더링
 * ===================================================================== */
function rescoreAndRender(fitBounds = false) {
    const { mode, candidates } = lastResult;
    lastResult.scored = scoreCandidates(candidates, mode);
    lastResult.selectedIdx = 0;
    drawResult(fitBounds);
}

function selectCandidate(i) {
    lastResult.selectedIdx = i;
    drawResult(false);
}

function drawResult(fitBounds) {
    const { mode, scored, selectedIdx } = lastResult;
    const best = scored[selectedIdx];
    clearMapRoutes(false);

    // 다른 후보 (회색, 아래쪽)
    scored.forEach((c, i) => {
        if (i === selectedIdx) return;
        const line = new kakao.maps.Polyline({
            map, path: c.segments.flatMap(s => s.path),
            strokeWeight: 5, strokeColor: '#9e9e9e', strokeOpacity: 0.55, zIndex: 1
        });
        kakao.maps.event.addListener(line, 'click', () => selectCandidate(i));
        routeOverlays.push(line);
    });

    // 선택 경로
    best.segments.forEach(seg => {
        routeOverlays.push(new kakao.maps.Polyline({
            map, path: seg.path, zIndex: 3,
            strokeWeight: seg.dashed ? 4 : 7,
            strokeColor: seg.color || '#4a7c59',
            strokeOpacity: 0.92,
            strokeStyle: seg.dashed ? 'shortdash' : 'solid'
        }));
    });

    // 환경 표시: 녹지(초록) / 혼잡(빨강)
    const drawn = new Set();
    (best.envSpots || []).forEach(s => {
        const park = s.park.items[0];
        if (park && !drawn.has(park.id)) {
            drawn.add(park.id);
            envOverlays.push(new kakao.maps.Circle({
                map, center: new kakao.maps.LatLng(park.y, park.x), radius: 120,
                strokeWeight: 1, strokeColor: '#43a047', strokeOpacity: 0.9, fillColor: '#43a047', fillOpacity: 0.3, zIndex: 2
            }));
        }
        if (s.busy >= 35) {
            envOverlays.push(new kakao.maps.Circle({
                map, center: s.pt, radius: 150,
                strokeWeight: 1, strokeColor: '#e53935', strokeOpacity: 0.9, fillColor: '#e53935', fillOpacity: 0.25, zIndex: 2
            }));
        }
    });

    // 리포트
    document.getElementById('result-section').style.display = 'block';
    document.getElementById('route-recommend-title').innerText =
        `${selectedIdx === 0 ? '추천' : '선택'} · ${best.name} — 심리 적합도 ${best.finalScore.toFixed(1)}점`;
    document.getElementById('score-fill').style.width = best.finalScore + '%';
    document.getElementById('stat-distance').innerText = (best.distance / 1000).toFixed(2) + ' km';
    document.getElementById('stat-duration').innerText = formatDuration(best.duration);

    let extra = '-', extraLbl = '기타';
    if (mode === 'transit') { extra = `${best.transferCount}회 · ${best.fare.toLocaleString()}원`; extraLbl = '환승 · 요금'; }
    else if (mode === 'car') { extra = best.congestion > 0.3 ? '정체 있음' : '원활'; extraLbl = best.toll ? `통행료 ${best.toll.toLocaleString()}원` : '교통 상황'; }
    else { extra = Math.round(best.greenScore * 100); extraLbl = '녹지 지수'; }
    document.getElementById('stat-extra').innerText = extra;
    document.getElementById('stat-extra-lbl').innerText = extraLbl;

    const reasonEl = document.getElementById('recommend-reason');
    reasonEl.innerHTML = '';
    [`[${MODE_LABEL[mode]} · ${EMOTION_LABEL[selectedEmotion]}] ${emotionSummary(mode)}`, ...best.reasons].forEach(t => {
        const li = document.createElement('li'); li.textContent = t; reasonEl.appendChild(li);
    });

    const list = document.getElementById('cand-list');
    list.innerHTML = scored.length > 1 ? '<div style="font-size:0.74rem;color:#64748b">후보 경로 비교 (클릭해서 보기)</div>' : '';
    if (scored.length > 1) scored.forEach((c, i) => {
        const d = document.createElement('div');
        d.className = 'cand' + (i === selectedIdx ? ' active' : '');
        d.innerHTML = `<span>${i === 0 ? '⭐ ' : ''}${c.name} · ${formatDuration(c.duration)}</span><span class="sc">${c.finalScore.toFixed(1)}점</span>`;
        d.onclick = () => selectCandidate(i);
        list.appendChild(d);
    });

    if (fitBounds) {
        const bounds = new kakao.maps.LatLngBounds();
        scored.forEach(c => c.segments.forEach(s => s.path.forEach(p => bounds.extend(p))));
        bounds.extend(startPoint); bounds.extend(endPoint);
        map.setBounds(bounds, 40, 40, 40, 40);
    }
}

function clearMapRoutes(resetResult = true) {
    routeOverlays.forEach(o => o.setMap(null)); routeOverlays = [];
    envOverlays.forEach(o => o.setMap(null)); envOverlays = [];
    if (resetResult) {
        lastResult = null;
        document.getElementById('result-section').style.display = 'none';
    }
}

/* ---------- 유틸 ---------- */
function formatDuration(sec) {
    const m = Math.ceil(sec / 60);
    return m >= 60 ? `${Math.floor(m / 60)}시간 ${m % 60}분` : `${m}분`;
}
function haversine(lat1, lng1, lat2, lng2) {
    const R = 6371000, toR = d => d * Math.PI / 180;
    const a = Math.sin(toR(lat2 - lat1) / 2) ** 2 + Math.cos(toR(lat1)) * Math.cos(toR(lat2)) * Math.sin(toR(lng2 - lng1) / 2) ** 2;
    return 2 * R * Math.asin(Math.sqrt(a));
}
</script>
</body>
</html>
