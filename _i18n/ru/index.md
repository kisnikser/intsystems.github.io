
<div class="hero-viewport" style="position: relative; min-height: 95vh; height: auto; display: flex; align-items: flex-start; justify-content: center; text-align: center; width: 100vw; left: 50%; right: 50%; margin-left: -50vw; margin-right: -50vw; overflow: hidden;">
  <div style="position: absolute; inset: 0; background: url('{{ site.baseurl_root }}/images/main/вц_ран.jpg') center/cover no-repeat; filter: blur(5px); transform: scale(1.1); z-index: 0;"></div>
  <div style="position: absolute; inset: 0; background-color: #000; z-index: 1; opacity: 0.6;"></div>
    <div class="hero-content" style="position: relative; z-index: 2; color: #fff; width: 90%; max-width: 1200px; padding: clamp(4rem, 8vh, 8rem) 1.5rem 1.5rem; margin-bottom: 6vh;">
    <style>
        .department-title {
            font-size: clamp(1rem, 3.5vw, 1.4rem);
            margin-bottom: 0.2rem;
            opacity: 0.9;
        }
        .department-name {
            font-size: clamp(1.4rem, 5.5vw, 2.2rem);
            font-weight: 600;
            letter-spacing: -0.02em;
        }
        @media (max-width: 480px) {
            .department-title { font-size: 1rem; }
            .department-name { font-size: 1.4rem; }
        }
    </style>
    <h1 class="fade-in-left" style="color: #fff; margin-bottom: 1.5rem; line-height: 1.1;">
        <span class="department-title" style="display: block;">Кафедра</span>
        <span class="department-name" style="display: block;">Интеллектуальных систем</span>
    </h1>
    <p class="fade-in-right">
        Мы готовим специалистов в области прикладной математики и физики — от бакалавриата до аспирантуры. Наши исследования охватывают теорию машинного обучения, интеллектуальные системы и практические приложения. Основываясь на базе ВЦ РАН, мы объединяем академическое превосходство и сотрудничество с индустрией.
    </p>
    <style>
        .social-icon {
            font-size: clamp(1.2rem, 5vw, 1.5rem);
            padding: 0.5rem;
            min-width: 44px;
            min-height: 44px;
            display: inline-flex;
            align-items: center;
            justify-content: center;
            text-decoration: none;
            color: white;
            transition: color 0.3s ease;
            border-radius: 50%;
            background: transparent;
            border: 2px solid transparent;
        }
        .social-icon:hover {
            border-color: currentColor;
        }
        .social-icon.github:hover {
            color: #ffffff;
            border-color: #ffffff;
        }
        .social-icon.mail:hover {
            color: #0066cc;
        }
        .social-icon.telegram:hover {
            color: #2AABEE;
        }
        .social-icon.youtube:hover {
            color: #FF0000;
        }
    </style>
    <div class="fade-in-right" style="display: flex; justify-content: center; align-items: center; gap: clamp(0.8rem, 4vw, 1.5rem); flex-wrap: wrap;">
    {% if site.github %}
    <a href="https://github.com/{{site.github}}" target="_blank" class="social-icon github"><i class="fa fa-github"></i></a>
    {% endif %}
    {% if site.mail %}
    <a href="#" onclick="copyEmailToClipboard(event, '{{site.mail}}')" class="social-icon mail"><i class="fa fa-envelope-o"></i></a>
    {% endif %}
    {% if site.telegram %}
    <a href="{{site.telegram}}" target="_blank" class="social-icon telegram"><i class="fa fa-telegram"></i></a>
    {% endif %}
    {% if site.youtube %}
    <a href="{{site.youtube}}" target="_blank" class="social-icon youtube"><i class="fa fa-youtube-play"></i></a>
    {% endif %}
    </div>
    <div class="cta-buttons" style="margin-top: 2rem;">
        <a href="{{ site.baseurl }}/admission" class="main-cta" style="background: #ff4d4d; color: white; padding: 1rem 2rem; border-radius: 5px; text-decoration: none; font-weight: bold; display: inline-block; margin: 0.5rem;">Поступить на кафедру</a>
        <a href="{{ site.baseurl }}/materials/nir" class="secondary-cta" style="background: transparent; border: 2px solid white; color: white; padding: 1rem 2rem; border-radius: 5px; text-decoration: none; font-weight: bold; display: inline-block; margin: 0.5rem;">Научные проекты</a>
    </div>
    </div>
</div>

<!-- Quick links: быстрый доступ к важному -->
<style>
    /* quick-links positioning tweaks: raise card to overlap hero more on wide screens */
    .quick-links-wrap { max-width: 1200px; margin: -20vh auto 1.25rem; padding: 0 1rem; position: relative; z-index: 10; }
    /* keep additional bottom spacing so following sections don't slide under the card */
    .quick-links-wrap { margin-bottom: 3rem; }
    .quick-links-card { display:grid; grid-template-columns:repeat(auto-fit,minmax(160px,1fr)); gap:0.75rem; background:white; border-radius:12px; padding:1.5rem; box-shadow:0 4px 12px rgba(0,0,0,0.1); }
    /* make sure section navigation (mobile links) stays on top of quick-links card */
    .section-nav { 
        position: relative; 
        z-index: 999; 
        display: flex; 
        gap: .75rem; 
        flex-wrap: wrap; 
        justify-content: center; 
        margin-top: -1rem; 
        margin-bottom: 1rem;
        background: rgba(255,255,255,0.98); 
        padding: 0.35rem 0.6rem; 
        border-radius: 8px; 
        box-shadow: 0 6px 18px rgba(0,0,0,0.06);
        width: fit-content;
        margin-left: auto;
        margin-right: auto;
    }
    .section-nav a { display: inline-block; color: #222; }
    /* make the first content section clearly separated (white surface) from the hero */
    .section-alternate:first-of-type { 
        position: relative; 
        z-index: 2; 
        padding-top: 1.5rem; 
        margin-top: 0; 
        background: #ffffff; 
        box-shadow: 0 -8px 24px rgba(0,0,0,0.06); 
        border-top-left-radius: 8px; 
        border-top-right-radius: 8px; 
    }
    .section-alternate:first-of-type .section-container { padding-top: 0.5rem; }
    /* reduce the contrasting gray by ensuring a white band under quick-links */
    .quick-links-wrap::after { content: ""; display: block; height: 1rem; width: 100%; background: transparent; }

    @media (max-width: 1024px) {
        /* On tablets and smaller: stop overlapping the hero (place card below CTAs)
           and add extra bottom space for hero content so CTAs remain visible. */
        .quick-links-wrap { margin: -12vh auto 1rem; padding: 0 0.75rem; }
        .quick-links-card { padding: 1rem; gap: 0.5rem; }
        .quick-links-card { grid-template-columns: repeat(auto-fit,minmax(140px,1fr)); }
        /* force more space below hero content to keep CTAs above the card */
        .hero-content { margin-bottom: 14vh !important; }
    }
    @media (max-width: 480px) {
        /* On small phones make the quick-links single-column and keep it below hero */
        .quick-links-wrap { margin: 1rem auto 0.75rem; }
        .quick-links-card { grid-template-columns: 1fr; padding: 0.9rem; gap: 0.5rem; }
        .hero-content { margin-bottom: 24vh !important; }
    }
    /* Добавляем специальные правила для экранов с маленькой высотой */
    @media (max-height: 700px) {
        .hero-viewport { height: auto; min-height: 100vh; }
        .hero-content { margin-bottom: 26vh !important; padding-top: 4rem; }
        .quick-links-wrap { position: relative; margin: 2rem auto 1rem; }
        .cta-buttons { margin-bottom: 2rem; }
    }
        /* also cancel the hero negative overlap on small devices to avoid covering CTAs */
        @media (max-width: 1024px) {
            .hero-viewport { margin-bottom: 0 !important; left: auto; right: auto; margin-left: 0; margin-right: 0; width: auto; }
            .hero-viewport > div[style*="background:"] { left: 0; right: 0; width: 100%; }
            /* on smaller screens ensure nav is above quick-links and quick-links sits below CTAs */
            .section-nav { z-index: 8; }
            .quick-links-wrap { margin-top: 0.5rem; margin-bottom: 3rem; }
        }
</style>
<section class="quick-links-wrap">
    <div class="quick-links-card">
    <a class="ql-card" href="{{ site.baseurl }}/admission" style="display:block;padding:0.9rem;border-radius:8px;background:#fff;color:#222;text-decoration:none;box-shadow:0 1px 4px rgba(0,0,0,.04);font-weight:600;">
      <div style="font-size:0.95rem;">Поступление</div>
      <div style="font-size:0.85rem;color:#666;margin-top:0.25rem;">Сроки, требования, документы</div>
    </a>
    <a class="ql-card" href="{{ site.baseurl }}/materials/scholarship" style="display:block;padding:0.9rem;border-radius:8px;background:#fff;color:#222;text-decoration:none;box-shadow:0 1px 4px rgba(0,0,0,.04);font-weight:600;">
      <div style="font-size:0.95rem;">Стипендии</div>
      <div style="font-size:0.85rem;color:#666;margin-top:0.25rem;">Кто и на каких условиях получает</div>
    </a>
    <a class="ql-card" href="{{ site.baseurl }}/education/" style="display:block;padding:0.9rem;border-radius:8px;background:#fff;color:#222;text-decoration:none;box-shadow:0 1px 4px rgba(0,0,0,.04);font-weight:600;">
      <div style="font-size:0.95rem;">Календарь</div>
      <div style="font-size:0.85rem;color:#666;margin-top:0.25rem;">Ближайшие семинары и дедлайны</div>
    </a>
    <a class="ql-card" href="{{ site.baseurl }}/contacts" style="display:block;padding:0.9rem;border-radius:8px;background:#fff;color:#222;text-decoration:none;box-shadow:0 1px 4px rgba(0,0,0,.04);font-weight:600;">
      <div style="font-size:0.95rem;">Контакты</div>
      <div style="font-size:0.85rem;color:#666;margin-top:0.25rem;">Кафедра, приёмная комиссия, соцсети</div>
    </a>
  </div>
</section>
<!-- Navigation Menu -->
<nav class="section-nav">
    <a href="#about">О кафедре</a>
    <a href="#courses">Курсы</a>
    <a href="#news">Новости</a>
    <a href="#personalities">Личности</a>
    <a href="#research">Научная работа</a>
    <a href="#life">Наша жизнь</a>
</nav>
<!-- About Section -->
<section id="about" class="section-alternate hero-separated">
    <div class="section-container fade-in-section">
            <h2 class="section-title"><i class="fa fa-university"></i> О кафедре</h2>
            <div style="margin-top: 1rem;">
            <p>Кафедра интеллектуальных систем в Физтехе (МФТИ) является ведущим центром образования и исследований в области прикладной математики, науки о данных и искусственного интеллекта. Кафедра предлагает программы бакалавриата и магистратуры по направлению «Информатика и вычислительная техника» со специализациями в области науки о данных, проектирования интеллектуальных систем и машинного обучения.</p>
        <p>Кафедра была основана академиком Константином Владимировичем Рудаковым и развивалась в рамках научной школы академика Юрия Ивановича Журавлева. Она базируется в Вычислительном центре Российской академии наук. В нашем составе — известные профессора, молодые ученые и эксперты из индустрии, средний возраст которых составляет 35 лет.</p>
        <p>Исследования кафедры охватывают машинное обучение, многомерную статистику, глубокое обучение, выбор моделей, генеративные нейронные сети и анализ сложных данных. Прикладные проекты включают анализ текста и изображений, обработку биомедицинских сигналов и интерфейсы «мозг-компьютер». Кафедра активно сотрудничает с международными университетами, научными центрами и высокотехнологичными компаниями, предлагая студентам уникальные возможности для стажировок, двойных дипломов и совместных исследований.</p>
        <p>Выпускники кафедры занимаются и руководят индустриальными и академическими исследованиями в области ИИ, машинного обучения. Практичеки все имеют ученые степени.</p>
        <p>Мы ценим открытость, инновации и постоянное совершенствование, поддерживая студентов стипендиями и личным наставничеством. Присоединяйтесь к нам, чтобы учиться, исследовать и внедрять инновации в области интеллектуальных систем!</p>
        </div>
    </div>
<!-- Department Statistics -->
    <div class="section-alternate">
        <div class="section-container">
            <h2 class="section-title"><i class="fa fa-chart-bar"></i> Кафедра в цифрах</h2>
                <div style="margin: 3rem auto 2.5rem auto; max-width: 1200px; width: 95%;">
                    <div style="display: grid; grid-template-columns: repeat(auto-fit, minmax(min(240px, 100%), 1fr)); gap: clamp(1.5rem, 3vw, 2rem) clamp(2rem, 4vw, 4rem); text-align: center; padding: 1.5rem 0;">
                        <div class="fade-in-left" style="display: flex; flex-direction: column; align-items: center;">
                            <p style="font-size: 4rem; font-weight: 600; line-height: 0.9; margin-bottom: 0.5rem;">2003</p>
                            <p style="max-width: 220px;font-size: 1rem;">год основания кафедры</p>
                        </div>
                        <div class="fade-in-right" style="display: flex; flex-direction: column; align-items: center;">
                            <p style="font-size: 4rem; font-weight: 600; line-height: 0.9; margin-bottom: 0.5rem;">>50%</p>
                            <p style="max-width: 220px;font-size: 1rem;">выпускников защитили кандидатские диссертации</p>
                        </div>
                        <div class="fade-in-left" style="display: flex; flex-direction: column; align-items: center;">
                            <p style="font-size: 4rem; font-weight: 600; line-height: 0.9; margin-bottom: 0.5rem;"><35</p>
                            <p style="max-width: 220px; font-size: 1rem;">средний возраст преподавателей курсов</p>
                        </div>
                        <div class="fade-in-right" style="display: flex; flex-direction: column; align-items: center;">
                            <p style="font-size: 4rem; font-weight: 600; line-height: 0.9; margin-bottom: 0.5rem;">170+</p>
                            <p style="max-width: 220px; font-size: 1rem;">open source проектов на <a href="https://github.com/{{site.github}}" >GitHub</a></p>
                        </div>
                    </div>
                </div>
        </div>
    </div>
</section>
<!-- News Section -->
<section id="news" class="section-alternate">
    <div class="section-container fade-in-section">
        <h2 class="section-title"><i class="fa fa-newspaper"></i> Новости</h2>
    <style>
      .news-scroll-container { overflow-x: auto; flex: 1; -webkit-overflow-scrolling: touch; }
      .news-list { display: flex; gap: 1.5rem; min-width: 0; padding: 1rem 0.5rem; }
      .news-block { display: block; min-width: 280px; max-width: 420px; padding: 1rem; background: #fff; border-radius: 6px; box-shadow: 0 1px 3px rgba(0,0,0,.06); text-decoration: none; color: inherit; }
      .news-important-badge { background: #ff4d4d; color: #fff; padding:0.2rem .5rem; border-radius:3px; font-size:0.75rem; }
      .news-title { font-weight:600; margin: 0.5rem 0; }
      .news-excerpt { color: #555; margin: 0.25rem 0 0; font-size: .95rem; }
            /* Desktop/large screens: horizontal scroll (default) */
            .news-scroll-container { overflow-x: auto; -webkit-overflow-scrolling: touch; position: relative; }
            .news-list { display: flex; gap: 1.5rem; min-width: 0; padding: 1rem 0.5rem; }
            .news-list { flex-direction: row; flex-wrap: nowrap; -webkit-overflow-scrolling: touch; }
            .news-scroll-container { scroll-snap-type: x mandatory; scroll-behavior: smooth; }
            .news-block { display: block; min-width: 280px; max-width: 420px; padding: 1rem; background: #fff; border-radius: 6px; box-shadow: 0 1px 3px rgba(0,0,0,.06); text-decoration: none; color: inherit; scroll-snap-align: start; scroll-snap-stop: always; }
            /* Desktop arrows */
            .news-nav { display: none; position: absolute; top: 50%; transform: translateY(-50%); width: 2.6rem; height: 2.6rem; border-radius: 50%; background: #fff; box-shadow: 0 2px 6px rgba(0,0,0,0.12); align-items: center; justify-content: center; cursor: pointer; }
            .news-prev { left: 0.4rem; }
            .news-next { right: 0.4rem; }
            .news-nav svg { width: 1rem; height: 1rem; fill: #333; }
            /* Small screens (phones and small browser windows): vertical flow with full-width cards */
            @media (max-width: 768px) {
                .news-scroll-container { overflow-x: visible; }
                .news-list { flex-direction: column; gap: 1rem; padding: 0; }
                .news-block { min-width: auto; max-width: none; width: 100%; box-sizing: border-box; }
                section > h2 { margin-bottom: 0.75rem; }
            }
                    /* show arrows only on wide screens */
                    @media (min-width: 769px) {
                        .news-nav { display: flex; }
                    }
    </style>
    <div style="display: flex; align-items: center; position: relative;">
        <button type="button" class="news-nav news-prev" aria-label="Предыдущие новости" data-action="prev">
                <svg viewBox="0 0 24 24" aria-hidden="true"><path d="M15.41 7.41L14 6l-6 6 6 6 1.41-1.41L10.83 12z"/></svg>
            </button>
            <div class="news-scroll-container" style="flex: 1;" role="region" aria-label="Новости кафедры">
                    <div class="news-list" style="display: flex; gap: 1.5rem; min-width: 0; padding: 1rem 0.5rem;">
            {% if site.posts and site.posts.size > 0 %}
                {% assign news_sorted = site.posts | where: "lang", "ru" | sort: 'date' | reverse %}
                {% for post in news_sorted limit:10 %}
                    <a class="news-block" href="{{ site.baseurl }}{{ post.url }}">
                        <div style="display: flex; justify-content: flex-end; align-items: flex-start;">
                            {% if post.important %}
                                <span class="news-important-badge">ВАЖНОЕ</span>
                            {% endif %}
                        </div>
                        <p class="news-title">{{ post.title }}</p>
                        <p class="news-date">{{ post.date | date: "%d.%m.%Y" }}</p>
                        <p class="news-excerpt">{{ post.excerpt }}</p>
                    </a>
                {% endfor %}
            {% else %}
                Нет новостей
            {% endif %}
            </div>
        </div>
            <button type="button" class="news-nav news-next" aria-label="Следующие новости" data-action="next">
                    <svg viewBox="0 0 24 24" aria-hidden="true"><path d="M8.59 16.59L13.17 12 8.59 7.41 10 6l6 6-6 6z"/></svg>
                </button>
    </div>
        <script>
        document.addEventListener('DOMContentLoaded', function(){
            const container = document.querySelector('.news-scroll-container');
            const list = document.querySelector('.news-list');
            const prev = document.querySelector('[data-action="prev"]');
            const next = document.querySelector('[data-action="next"]');
            if(!container || !list) return;
            function getVisibleIndex(){
                const cards = Array.from(list.querySelectorAll('.news-block'));
                const containerRect = container.getBoundingClientRect();
                let bestIndex = 0;
                let bestDist = Infinity;
                cards.forEach((c, i) => {
                    const r = c.getBoundingClientRect();
                    const dist = Math.abs(r.left - containerRect.left);
                    if(dist < bestDist){ bestDist = dist; bestIndex = i; }
                });
                return bestIndex;
            }
            function scrollToIndex(index, button){
                const cards = Array.from(list.querySelectorAll('.news-block'));
                if(index < 0) index = 0;
                if(index >= cards.length) index = cards.length - 1;
                const target = cards[index];
                if(!target) return;
                const left = target.offsetLeft - list.offsetLeft;
                container.scrollTo({ left: left, behavior: 'smooth' });
                if(button && typeof button.blur === 'function') button.blur();
                setTimeout(updateArrows, 350);
            }
            if(prev){
                prev.addEventListener('pointerdown', function(e){ e.preventDefault(); e.stopPropagation(); this.blur(); }, { passive: false });
                prev.addEventListener('click', (e)=> { e.preventDefault(); e.stopPropagation(); const idx = getVisibleIndex(); scrollToIndex(idx - 1, prev); });
            }
            if(next){
                next.addEventListener('pointerdown', function(e){ e.preventDefault(); e.stopPropagation(); this.blur(); }, { passive: false });
                next.addEventListener('click', (e)=> { e.preventDefault(); e.stopPropagation(); const idx = getVisibleIndex(); scrollToIndex(idx + 1, next); });
            }
            function updateArrows(){
                if(!prev || !next) return;
                prev.disabled = container.scrollLeft <= 1;
                next.disabled = container.scrollLeft + container.clientWidth >= list.scrollWidth - 1;
                prev.style.opacity = prev.disabled ? '0.5' : '1';
                next.style.opacity = next.disabled ? '0.5' : '1';
            }
            container.addEventListener('scroll', updateArrows);
            window.addEventListener('resize', updateArrows);
            updateArrows();
        });
        </script>
    </div>
 </section>
<!-- Department Statistics -->
<div class="statistics" style="background: #f8f9fa; padding: 3rem 0; margin: 3rem 0;">
    <div style="max-width: 1200px; margin: 0 auto;">
        <h2 style="text-align: center; margin-bottom: 2rem;">Кафедра в цифрах</h2>
            <div style="margin: 3rem auto 2.5rem auto; max-width: 1200px; width: 95%;">
                <div style="display: grid; grid-template-columns: repeat(auto-fit, minmax(min(240px, 100%), 1fr)); gap: clamp(1.5rem, 3vw, 2rem) clamp(2rem, 4vw, 4rem); text-align: center; padding: 1.5rem 0;">
                    <div class="fade-in-left" style="display: flex; flex-direction: column; align-items: center;">
                        <p style="font-size: 4rem; font-weight: 600; line-height: 0.9; margin-bottom: 0.5rem;">2003</p>
                        <p style="max-width: 220px;font-size: 1rem;">год основания кафедры</p>
                    </div>
                    <div class="fade-in-right" style="display: flex; flex-direction: column; align-items: center;">
                        <p style="font-size: 4rem; font-weight: 600; line-height: 0.9; margin-bottom: 0.5rem;">>50%</p>
                        <p style="max-width: 220px;font-size: 1rem;">выпускников защитили кандидатские диссертации</p>
                    </div>
                    <div class="fade-in-left" style="display: flex; flex-direction: column; align-items: center;">
                        <p style="font-size: 4rem; font-weight: 600; line-height: 0.9; margin-bottom: 0.5rem;"><35</p>
                        <p style="max-width: 220px; font-size: 1rem;">средний возраст преподавателей курсов</p>
                    </div>
                    <div class="fade-in-right" style="display: flex; flex-direction: column; align-items: center;">
                        <p style="font-size: 4rem; font-weight: 600; line-height: 0.9; margin-bottom: 0.5rem;">170+</p>
                        <p style="max-width: 220px; font-size: 1rem;">open source проектов на <a href="https://github.com/{{site.github}}" >GitHub</a></p>
                    </div>
                    <div class="fade-in-left" style="display: flex; flex-direction: column; align-items: center;">
                        <p style="font-size: 2.8rem; font-weight: 600; line-height: 0.9; margin-bottom: 0.5rem;">каждый<br>семестр</p>
                        <p style="max-width: 220px; font-size: 1rem;">студенты представляют <a href="{{ site.baseurl }}/materials/nir">научные отчеты</a>: paper-code-presentation</p>
                    </div>
                    <div class="fade-in-right" style="display: flex; flex-direction: column; align-items: center;">
                        <p style="font-size: 2.2rem; font-weight: 600; line-height: 1.1; margin-bottom: 0.5rem;">NeurIPS,<br>ICML, ICLR<br>AISTATS</p>
                        <p style="max-width: 220px; font-size: 1rem;">top-tier конференции публикуют наши исследования</p>
                    </div>
                </div>
            </div>
    </div>
</div>

<!-- Courses Section -->
<section id="courses" class="section-container fade-in-section">
    <h2 class="section-title"><i class="fa fa-graduation-cap"></i> Курсы</h2>
    <p>
        Мы предлагаем широкий спектр курсов по прикладной математике, анализу данных и машинному обучению как для студентов бакалавриата, так и для магистрантов. Наша учебная программа разработана для обеспечения прочной теоретической базы наряду с практическими навыками, необходимыми в индустрии.
    </p>
    {% for type in site.global.course.types %}
        {% if type == 'bachelor' or type == 'master' %}
            <div class="list-header">
                <h3 id="{% t site.global.course.types.{{ type }} %}">{% t site.global.course.types.{{ type }} %}</h3>
            </div>
            <div class="list-course">
                {% for course in site.course %}
                    {% if course.type contains type %}
                    <a class="course-name" href="{{ site.baseurl }}{{ course.url }}">
                    <div class="list-item-course">
                        <p class="list-item-course-title">
                        {% t courses.{{ course.id | split: "/" | last }} %}
                        </p>
                    </div>
                    </a>
                    {% endif %}
                {% endfor %}
            </div>
        {% endif %}
    {% endfor %}
    <div style="text-align: center; margin-top: 1.5rem;">
        <a href="{{ site.baseurl }}/course" class="button-primary">Все курсы кафедры</a>
    </div>
</section>


<!-- Personalities Section -->
<section id="personalities" class="section-alternate">
    <div class="section-container fade-in-section">
        <h2 class="section-title"><i class="fa fa-users"></i> Личности</h2>
        <p style="margin-top: 1rem;">
            Мы гордимся нашими основателями и преподавателями, которые внесли значительный вклад в область машинного обучения. Их работа проложила путь к современным достижениям в области искусственного интеллекта.
        </p>
        {% assign featured_people = "zhuravlyov_yv,rudakov_kv,vorontsov_kv,strijov_vv" | split: "," %}
        <div class="list people">
        {% for person_id in featured_people %}
            {% for profile in site.people %}
                {% assign profile_id = profile.id | split: "/" | last %}
                {% if profile_id == person_id %}
                    <div class="list-item-people">
                        <p class="list-post-title">
                        {% if profile.avatar %}
                            <a href="{{ site.baseurl }}{{ profile.url }}"><img class="profile-thumbnail" src="{{ site.baseurl_root }}/images/people/{{profile.avatar}}"></a>
                        {% else %}
                            <a href="{{ site.baseurl }}{{ profile.url }}"><img class="profile-thumbnail" src="{{ site.baseurl_root }}/images/people/default.jpg"></a>
                        {% endif %}
                        <a class="name" href="{{ site.baseurl }}{{ profile.url }}">{% t people.{{ profile_id }} %}</a>
                        </p>
                    </div>
                {% endif %}
            {% endfor %}
        {% endfor %}
        </div>
    </div>
</section>

<!-- Full-width Image Before Research Section -->
<div style="width: 100vw; position: relative; left: 50%; transform: translateX(-50%); margin: 3.5rem 0;">
<img src="{{ site.baseurl_root }}/images/main/zhuravlev_rudakov_merged.jpg" style="width: 100vw; max-width: 100%; height: auto; object-fit: cover;  border-radius: 0px">
</div>

<!-- Research Section -->
<section id="research" class="section-alternate">
    <div class="section-container fade-in-section">
        <h2 class="section-title"><i class="fa fa-flask"></i> Научная работа</h2>
        <div style="margin: 0 0 3rem 0; max-width: 1200px;">
            <p>
                Мы открыто публикуем результаты исследований и приглашаем к сотрудничеству студентов, исследователей и промышленные компании.
            </p>
            <div style="display: grid; grid-template-columns: repeat(auto-fit, minmax(min(360px, 100%), 1fr)); gap: 2.5rem; margin: 2.5rem 0;">
                <div class="fade-in-left research-block" >
                    <a class="research-block-title" href="{{ site.baseurl }}/materials/nir">Научные исследования</a>
                    <p style="margin: 1rem 0;">
                        Наша кафедра проводит фундаментальные и прикладные исследования в области машинного обучения, анализа данных, искусственного интеллекта и смежных областей.
                        Результаты публикуются в открытом доступе и представляются на международных конференциях. Мы приветствуем совместные проекты и новые идеи!
                    </p>
                    <p style="padding-top: 1rem; border-top: 1px solid #eee; text-align: left;">
                        <strong>Научные направления:</strong> распознавание образов, обработка естественного языка, биомедицинские сигналы, генеративные модели, теория машинного обучения
                    </p>
                </div>
                <div class="fade-in-right research-block" >
                    <a class="research-block-title" href="{{ site.baseurl }}/materials/thesis">Дипломные работы</a>
                    <p style="margin: 1rem 0;">
                        Студенты участвуют в реальных исследованиях, готовят дипломные работы и публикуют свои результаты.
                        Мы поддерживаем открытое опубликование кода и статей и приглашаем всех к сотрудничеству по темам дипломных работ и исследовательским проектам.
                    </p>
                    <p style="padding-top: 1rem; border-top: 1px solid #eee; text-align: left;">
                        <strong>Работа студентов:</strong> публикации, дипломные работы бакалавров и магистров, кандидатские диссертации
                    </p>
                </div>
            </div>
        </div>
    </div>
</section>

<!-- Life Section -->
<section id="life" class="section-alternate">
    <div class="section-container fade-in-section">
        <h2 class="section-title"><i class="fa fa-camera"></i> Наша жизнь</h2>
        <p>
            Здесь мы делимся некоторыми моментами из жизни нашей кафедры: учебные мероприятия, защиты дипломов, встречи выпускников.
        </p>
        <div id="carousel-section">
            <link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/bulma-carousel@4.0.3/dist/css/bulma-carousel.min.css">
            <div id="carousel-demo" class="carousel">
                <div class="carousel-item">
                    <img src="{{ site.baseurl_root }}/images/life/bachelors-2025.jpeg" alt="Бакалавриат 2025">
                    <p>Бакалавриат, выпуск 2025</p>
                </div>
                <div class="carousel-item">
                    <img src="{{ site.baseurl_root }}/images/life/masters-2025.jpeg" alt="Магистратура 2025">
                    <p>Магистратура, выпуск 2025</p>
                </div>
                <div class="carousel-item">
                    <img src="{{ site.baseurl_root }}/images/life/bachelors-2024.jpeg" alt="Бакалавриат 2024">
                    <p>Бакалавриат, выпуск 2024</p>
                </div>
                <div class="carousel-item">
                    <img src="{{ site.baseurl_root }}/images/life/masters-2024.jpeg" alt="Магистратура 2024">
                    <p>Магистратура, выпуск 2024</p>
                </div>
            </div>
        </div>
    </div>
</section>

<section class="section-container faq-section" style="margin: 3rem auto; max-width: 800px;">
    <h2 class="section-title"><i class="fa fa-question-circle"></i> Частые вопросы</h2>
    <div class="faq-item" style="margin: 1.5rem 0; border-bottom: 1px solid #eee; padding-bottom: 1rem;">
        <h3>Как поступить на кафедру?</h3>
        <p>Подробная информация о поступлении на программы бакалавриата и магистратуры доступна в разделе <a href="{{ site.baseurl }}/admission">Поступление</a>.</p>
    </div>
    <div class="faq-item" style="margin: 1.5rem 0; border-bottom: 1px solid #eee; padding-bottom: 1rem;">
        <h3>Какие перспективы трудоустройства?</h3>
        <p>С самого начала кафедра активно сотрудничает с базовыми организациями группы компаний Forecsys и участвует в совместных проектах с ведущими технологическими компаниями.Успешные студенты могут получать <a href="{{ site.baseurl }}/materials/scholarship">стипендии</a>.</p>
    </div>
    <div class="faq-item" style="margin: 1.5rem 0; border-bottom: 1px solid #eee; padding-bottom: 1rem;">
        <h3>Я уже обучаюсь на кафедре. Где можно посмотреть расписание кафедры?</h3>
        <p>Вся полезная информация для студентов и аспирантов находится в разделе <a href="{{ site.baseurl }}/education/">"Обучение"</a>.</p>
    </div>
</section>

