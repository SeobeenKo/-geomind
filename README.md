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
            padding: 8px 4px; border: 1px solid #cbd5e1;
