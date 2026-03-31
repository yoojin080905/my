<!DOCTYPE html>
<html lang="ko">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>THE CONNECTOR | Artist Archive</title>
    <style>
        /* [CSS] 기존 디자인 유지 */
        * { margin: 0; padding: 0; box-sizing: border-box; font-family: "Apple SD Gothic Neo", "Pretendard", sans-serif; }
        body { background-color: #ffffff; color: #000000; line-height: 1.8; overflow-x: hidden; }
        .minimal-nav { display: flex; justify-content: space-between; align-items: center; padding: 30px 50px; font-size: 0.7rem; letter-spacing: 3px; color: #999; position: relative; z-index: 100; }
        .menu-btn { cursor: pointer; display: flex; flex-direction: column; gap: 6px; padding: 10px; }
        .menu-btn span { display: block; width: 22px; height: 1px; background-color: #000; transition: 0.3s; }
        .sidebar { position: fixed; top: 0; right: -450px; width: 450px; height: 100%; background: #fff; box-shadow: -10px 0 30px rgba(0,0,0,0.03); z-index: 1000; transition: transform 0.5s cubic-bezier(0.77,0.2,0.05,1.0); padding: 80px 50px; overflow-y: auto; }
        .sidebar.active { transform: translateX(-450px); }
        .close-btn { position: absolute; top: 35px; right: 50px; font-size: 1.8rem; cursor: pointer; font-weight: 200; }
        .sidebar-title { font-size: 1.6rem; font-weight: 800; margin-bottom: 20px; letter-spacing: -1px; }
        .sort-container { margin-bottom: 40px; display: flex; align-items: center; gap: 10px; }
        #sortSelect { border: none; border-bottom: 1px solid #eee; font-size: 0.8rem; padding: 5px; outline: none; background: transparent; }
        .category-group { margin-bottom: 45px; }
        .category-name { font-size: 0.8rem; font-weight: 800; color: #000; border-bottom: 2px solid #000; padding-bottom: 8px; margin-bottom: 20px; text-transform: uppercase; letter-spacing: 1px; }
        .sub-category-title { font-size: 0.7rem; color: #aaa; margin-top: 15px; margin-bottom: 10px; font-weight: 600; }
        .artist-list { display: flex; flex-wrap: wrap; gap: 10px 18px; margin-bottom: 20px; }
        .artist-link { font-size: 0.85rem; color: #777; text-decoration: none; cursor: pointer; transition: 0.2s; }
        .artist-link:hover { color: #000; text-decoration: underline; }
        .overlay { position: fixed; top: 0; left: 0; width: 100%; height: 100%; background: rgba(255,255,255,0.85); backdrop-filter: blur(4px); display: none; z-index: 999; }
        .overlay.active { display: block; }
        .search-container { max-width: 700px; margin: 80px auto; padding: 0 20px; }
        .logo { font-size: 2.2rem; font-weight: 800; letter-spacing: -1px; margin-bottom: 60px; text-align: center; }
        input[type="text"] { width: 100%; padding: 15px 0; font-size: 1.2rem; border: none; border-bottom: 1px solid #000; outline: none; background: transparent; }
        .result-item { margin-bottom: 50px; animation: fadeIn 0.6s ease forwards; }
        .result-item a { color: #000; text-decoration: none; font-size: 1.5rem; font-weight: 700; display: block; }
        .request-container { margin-top: 150px; padding-bottom: 100px; text-align: center; }
        .request-btn { display: inline-block; padding: 14px 40px; border: 1px solid #000; color: #000; text-decoration: none; font-size: 0.8rem; margin-top: 25px; }
        @keyframes fadeIn { from { opacity: 0; transform: translateY(10px); } to { opacity: 1; transform: translateY(0); } }
        @media (max-width: 600px) { .sidebar { width: 100%; right: -100%; } .sidebar.active { transform: translateX(-100%); } }
    </style>
</head>
<body>

    <nav class="minimal-nav">
        <div>THE CONNECTOR</div>
        <div class="menu-btn" onclick="toggleSidebar()">
            <span></span><span></span><span></span>
        </div>
    </nav>

    <div class="overlay" id="overlay" onclick="toggleSidebar()"></div>
    
    <div class="sidebar" id="sidebar">
        <div class="close-btn" onclick="toggleSidebar()">×</div>
        <h2 class="sidebar-title">Index</h2>
        <div class="sort-container">
            <select id="sortSelect" onchange="renderCategories()">
                <option value="asc">이름순 (가나다/A-Z)</option>
                <option value="desc">이름 역순 (하타파/Z-A)</option>
            </select>
        </div>
        <div id="categoryContainer"></div>
    </div>

    <main class="search-container">
        <h1 class="logo">PHOTOGRAPHER</h1>
        <div class="search-box">
            <input type="text" id="searchInput" placeholder="작가 이름을 입력하세요" autocomplete="off">
        </div>
        <section id="resultsSection"></section>
        <div class="request-container">
            <p>찾으시는 작가가 결과에 없나요?</p>
            <a href="https://forms.gle/BLrGqXk5kdVHaQhf7" target="_blank" class="request-btn">ADD NEW ARTIST</a>
        </div>
    </main>

    <script>
        // [Data] 70명 이상의 전체 통합 데이터베이스
        const photographers = [
            // 한국
            { name: "김아타", engName: "Atta Kim", links: ["https://k-artist.com/Artist_page.php?tab_num=tab1&artist_num=97"], group: ["한국", "정물/예술"], desc: "해체와 소멸, '온-에어' 프로젝트" },
            { name: "이갑철", engName: "Lee Gap-Chul", links: ["http://www.leegapchul.com/"], group: ["한국", "다큐멘터리"], desc: "한국인의 무의식과 거친 에너지" },
            { name: "최민식", engName: "Choi Min-shik", links: ["https://archives.busan.go.kr/human/index"], group: ["한국", "다큐멘터리"], desc: "인간(Human) 시리즈, 한국 다큐멘터리의 거장" },
            { name: "구본창", engName: "Koo Bohnchang", links: ["http://www.koobohnchang.com/"], group: ["한국", "정물/예술"], desc: "현대사진의 정립, 달항아리 시리즈" },
            { name: "배병우", engName: "Bae Bien-U", links: ["http://www.bxb.co.kr/"], group: ["한국", "풍경"], desc: "소나무의 화가" },
            { name: "성두경", engName: "Sung Du-kyung", links: ["https://www.mmca.go.kr/"], group: ["한국", "다큐멘터리"], desc: "전후 서울의 기록과 리얼리즘" },
            { name: "김중만", engName: "Kim Jungman", links: ["http://www.kimjungman.com/"], group: ["한국", "패션", "인물"], desc: "한국 상업 및 예술 사진의 가교" },
            { name: "노순택", engName: "Noh Suntag", links: ["https://www.moma.org/artists/38018"], group: ["한국", "다큐멘터리"], desc: "분단 현실의 기록" },
            { name: "이명호", engName: "Lee Myoung-Ho", links: ["https://www.yossimilo.com/artists/myoung-ho-lee"], group: ["한국", "정물/예술"], desc: "나무 시리즈, 캔버스 설치" },
            { name: "정연두", engName: "Yeondoo Jung", links: ["https://www.kukjegallery.com/artists/view?user_no=63"], group: ["한국", "정물/예술"], desc: "꿈과 현실의 재구성" },
            { name: "주명덕", engName: "Joo Myung-Duck", links: ["https://www.moma.org/artists/38011"], group: ["한국", "다큐멘터리"], desc: "한국 다큐멘터리 사진의 대부" },
            { name: "임응식", engName: "Limb Eung-Sik", links: ["https://www.mmca.go.kr/"], group: ["한국", "다큐멘터리"], desc: "생활주의 리얼리즘" },
            { name: "황규태", engName: "Hwang Kyu-Tae", links: ["http://www.artspace-j.com/"], group: ["한국", "정물/예술"], desc: "디지털 이미지의 선구자" },
            { name: "성남훈", engName: "Seong Nam-hun", links: ["http://www.seongnamhun.com/"], group: ["한국", "다큐멘터리"], desc: "소외된 유민의 삶" },
            { name: "구성수", engName: "Koo Sung-soo", links: ["http://www.koosungsoo.com/"], group: ["한국", "정물/예술"], desc: "포토제닉 드로잉" },
            { name: "박건희", engName: "Park Geonhi", links: ["https://geonhi.com/"], group: ["한국", "정물/예술"], desc: "박건희 문화재단 설립자" },

            // 미국
            { name: "도로시아 랭", engName: "Dorothea Lange", links: ["https://www.moma.org/artists/3373"], group: ["미국", "다큐멘터리"], desc: "대공황기의 기록" },
            { name: "워크 에번스", engName: "Walker Evans", links: ["https://www.metmuseum.org/toah/hd/evan/hd_evan.htm"], group: ["미국", "다큐멘터리"], desc: "미국적 기록 사진의 정수" },
            { name: "안셀 애덤스", engName: "Ansel Adams", links: ["https://www.anseladams.com/"], group: ["미국", "풍경"], desc: "존 시스템의 창시자" },
            { name: "에드워드 웨스턴", engName: "Edward Weston", links: ["https://www.edward-weston.com/"], group: ["미국", "정물/예술"], desc: "직접 사진의 거장" },
            { name: "신디 셔먼", engName: "Cindy Sherman", links: ["https://www.cindysherman.com/"], group: ["미국", "인물", "정물/예술"], desc: "정체성 탐구" },
            { name: "사울 레이터", engName: "Saul Leiter", links: ["https://www.saulleiterfoundation.org/"], group: ["미국", "정물/예술"], desc: "뉴욕의 색채 시인" },
            { name: "리차드 아베돈", engName: "Richard Avedon", links: ["https://www.avedonfoundation.org/"], group: ["미국", "인물", "패션"], desc: "움직이는 패션 초상" },
            { name: "비비안 마이어", engName: "Vivian Maier", links: ["http://www.vivianmaier.com/"], group: ["미국", "다큐멘터리"], desc: "거리의 기록자" },
            { name: "스티븐 쇼어", engName: "Stephen Shore", links: ["http://stephenshore.net/"], group: ["미국", "풍경"], desc: "미국적 일상의 재발견" },
            { name: "윌리엄 이글스턴", engName: "William Eggleston", links: ["https://egglestonartfoundation.org/"], group: ["미국", "정물/예술"], desc: "컬러 사진의 예술적 승화" },
            { name: "애니 레보비츠", engName: "Annie Leibovitz", links: ["https://www.houkhenry.com/artists/annie-leibovitz"], group: ["미국", "인물", "패션"], desc: "유명인 초상의 대가" },
            { name: "로버트 프랭크", engName: "Robert Frank", links: ["https://www.nga.gov/features/robert-frank.html"], group: ["미국", "다큐멘터리"], desc: "현대 사진의 전환점 'The Americans'" },
            { name: "윌리엄 유진 스미스", engName: "W. Eugene Smith", links: ["https://www.magnumphotos.com/photographer/w-eugene-smith/"], group: ["미국", "다큐멘터리"], desc: "인도주의적 사진가" },
            { name: "어빙 펜", engName: "Irving Penn", links: ["https://irvingpenn.org/"], group: ["미국", "인물", "패션"], desc: "정제된 미학의 극치" },
            { name: "토드 히도", engName: "Todd Hido", links: ["http://www.toddhido.com/"], group: ["미국", "풍경", "정물/예술"], desc: "교외의 고독과 밤" },
            { name: "그레고리 크루드슨", engName: "Gregory Crewdson", links: ["https://gagosian.com/artists/gregory-crewdson/"], group: ["미국", "정물/예술"], desc: "영화 같은 연출" },
            { name: "가리 위노그랜드", engName: "Garry Winogrand", links: ["https://www.sfmoma.org/artist/Garry_Winogrand/"], group: ["미국", "다큐멘터리"], desc: "즉흥적 거리 사진" },
            { name: "허브 리츠", engName: "Herb Ritts", links: ["https://www.herbritts.com/"], group: ["미국", "패션"], desc: "조형적 인물" },
            { name: "만 레이", engName: "Man Ray", links: ["https://www.moma.org/artists/3718"], group: ["미국", "정물/예술"], desc: "초현실주의 사진" },

            // 유럽
            { name: "앙리 카르티에 브레송", engName: "Henri Cartier-Bresson", links: ["https://www.henricartierbresson.org/"], group: ["유럽", "다큐멘터리"], desc: "결정적 순간" },
            { name: "로버트 카파", engName: "Robert Capa", links: ["https://www.magnumphotos.com/photographer/robert-capa/"], group: ["유럽", "다큐멘터리"], desc: "전쟁 사진의 전설" },
            { name: "안드레아스 구르스키", engName: "Andreas Gursky", links: ["https://www.andreasgursky.com/"], group: ["유럽", "풍경", "정물/예술"], desc: "현대적 스펙터클" },
            { name: "아우구스트 잔더", engName: "August Sander", links: ["https://www.moma.org/artists/5145"], group: ["유럽", "인물"], desc: "20세기 독일인의 초상" },
            { name: "브라사이", engName: "Brassai", links: ["https://www.houkhenry.com/artists/brassai"], group: ["유럽", "다큐멘터리"], desc: "밤의 파리" },
            { name: "유진 앗제", engName: "Eugene Atget", links: ["https://www.moma.org/artists/229"], group: ["유럽", "풍경"], desc: "파리의 기록자" },
            { name: "베허 부부", engName: "Bernd & Hilla Becher", links: ["https://www.tate.org.uk/art/artists/bernd-becher-and-hilla-becher-713"], group: ["유럽", "정물/예술"], desc: "유형학적 사진" },
            { name: "헬무트 뉴턴", engName: "Helmut Newton", links: ["https://www.helmut-newton-foundation.org/"], group: ["유럽", "패션"], desc: "도발적인 여성 이미지" },
            { name: "세바스치앙 살가두", engName: "Sebastião Salgado", links: ["https://www.amazonasimages.com/"], group: ["유럽", "다큐멘터리"], desc: "지구와 인류의 기록" },
            { name: "해리 그루야르", engName: "Harry Gruyaert", links: ["https://www.magnumphotos.com/photographer/harry-gruyaert/"], group: ["유럽", "정물/예술"], desc: "강렬한 색채의 미학" },

            // 일본 및 기타
            { name: "린코 가와우치", engName: "Rinko Kawauchi", links: ["http://rinkokawauchi.com/"], group: ["일본", "정물/예술"], desc: "일상의 찰나와 경이로움" },
            { name: "히로시 스기모토", engName: "Hiroshi Sugimoto", links: ["https://www.sugimotohiroshi.com/"], group: ["일본", "정물/예술"], desc: "시간과 빛의 철학" },
            { name: "다이도 모리야마", engName: "Daido Moriyama", links: ["https://www.moriyamadaido.com/"], group: ["일본", "다큐멘터리"], desc: "거칠고 흔들리는 거리" },
            { name: "아라키 노부요시", engName: "Nobuyoshi Araki", links: ["https://www.arakinobuyoshi.com/"], group: ["일본", "인물", "정물/예술"], desc: "생과 사, 에로스" },
            { name: "라구 라이", engName: "Raghu Rai", links: ["https://raghurai.com/"], group: ["기타", "다큐멘터리"], desc: "인도 사진의 거장" }
        ];

        function toggleSidebar() {
            document.getElementById('sidebar').classList.toggle('active');
            document.getElementById('overlay').classList.toggle('active');
        }

        function renderCategories() {
            const container = document.getElementById('categoryContainer');
            const sortOrder = document.getElementById('sortSelect').value;
            container.innerHTML = '';

            const mainCategories = {
                "Region (국가/지역)": ["한국", "미국", "유럽", "일본", "기타"],
                "Style (스타일/분야)": ["인물", "정물/예술", "다큐멘터리", "풍경", "패션"]
            };

            for (const [mainTitle, subTags] of Object.entries(mainCategories)) {
                const groupDiv = document.createElement('div');
                groupDiv.className = 'category-group';
                groupDiv.innerHTML = `<div class="category-name">${mainTitle}</div>`;
                
                subTags.forEach(tag => {
                    const filtered = photographers.filter(p => p.group.includes(tag));
                    if (filtered.length === 0) return;

                    const subTitle = document.createElement('div');
                    subTitle.className = 'sub-category-title';
                    subTitle.innerText = `• ${tag}`;
                    groupDiv.appendChild(subTitle);

                    const listDiv = document.createElement('div');
                    listDiv.className = 'artist-list';
                    
                    filtered.sort((a, b) => {
                        const res = a.name.localeCompare(b.name, 'ko');
                        return sortOrder === 'asc' ? res : -res;
                    });

                    filtered.forEach(artist => {
                        const span = document.createElement('span');
                        span.className = 'artist-link';
                        span.innerText = artist.name;
                        span.onclick = () => {
                            document.getElementById('searchInput').value = artist.name;
                            search(artist.name);
                            toggleSidebar();
                            window.scrollTo({top: 0, behavior: 'smooth'});
                        };
                        listDiv.appendChild(span);
                    });
                    groupDiv.appendChild(listDiv);
                });
                container.appendChild(groupDiv);
            }
        }

        function search(val) {
            const query = val.toLowerCase().replace(/\s/g, ''); 
            const resultsSection = document.getElementById('resultsSection');
            resultsSection.innerHTML = '';
            if (!query) return;
            const matched = photographers.filter(p => 
                p.name.replace(/\s/g, '').includes(query) || 
                p.engName.toLowerCase().replace(/\s/g, '').includes(query)
            );
            if (matched.length > 0) {
                matched.forEach(p => {
                    const div = document.createElement('div');
                    div.className = 'result-item';
                    div.innerHTML = `
                        <a href="${p.links[0]}" target="_blank">${p.name}</a>
                        <p>${p.engName} — ${p.desc}</p>
                        <small>Archive: ${p.links[0]}</small>
                    `;
                    resultsSection.appendChild(div);
                });
            } else {
                resultsSection.innerHTML = '<p style="color:#ddd; text-align:center;">결과가 없습니다.</p>';
            }
        }

        document.getElementById('searchInput').addEventListener('input', (e) => search(e.target.value));
        window.onload = renderCategories;
    </script>
</body>
</html>
