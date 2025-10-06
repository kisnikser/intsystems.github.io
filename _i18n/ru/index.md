<div style="position: relative; min-height: 60vh; display: flex; align-items: center; justify-content: center; text-align: center; margin: auto auto; width: 100vw; left: 50%; transform: translateX(-50%); overflow: hidden;">
  <div style="position: absolute; top: 0; bottom: 0; left: 0; right: 0; background: url('{{ site.baseurl_root }}/images/main/вц_ран.jpg') center/cover no-repeat; filter: blur(5px); transform: scale(1.1); z-index: 0;"></div>
  <div style="position: absolute; top: 0; bottom: 0; left: 0; right: 0; background-color: #000; z-index: 1; opacity: 0.6"></div>
  <div style="position: relative; z-index: 2; color: #fff; width: 70%; min-width: 500px; max-width: 1000px; padding: 2rem;">
    <h1 class="fade-in-left" style="color: #fff; margin-bottom: 2rem; font-size: 2.5rem; font-weight: 600;">Кафедра интеллектуальных систем</h1>
    <p class="fade-in-right">
        Мы готовим специалистов в области прикладной математики и физики — от бакалавриата до аспирантуры. Наши исследования охватывают теорию машинного обучения, интеллектуальные системы и практические приложения. Основываясь на базе ВЦ РАН, мы объединяем академическое превосходство и сотрудничество с индустрией.
    </p>
    <div class="fade-in-right">
    {% if site.github %}
    <a href="https://github.com/{{site.github}}" target="_blank" style="font-size: 1.5rem; margin: 0 1rem"><i class="fa fa-github"></i></a>
    {% endif %}
    {% if site.mail %}
    <a href="mailto:{{site.mail}}" style="font-size: 1.5rem; margin: 0 1rem"><i class="fa fa-envelope-o"></i></a>
    {% endif %}
    {% if site.telegram %}
    <a href="{{site.telegram}}"  target="_blank" style="font-size: 1.5rem; margin: 0 1rem"><i class="fa fa-telegram"></i></a>
    {% endif %}
    {% if site.youtube %}
    <a href="{{site.youtube}}"  target="_blank" style="font-size: 1.5rem; margin: 0 1rem"><i class="fa fa-youtube-play"></i></a>
    {% endif %}
    </div>
    </div>
</div>

<!-- Conferences Deadlines Section -->
<section class="fade-in-section" style="margin: 3rem 0;">
    <h2>Дедлайны конференций</h2>
    <p style="margin-top: 1rem;">Ближайшие дедлайны подачи работ на топовые конференции по машинному обучению. Будьте в курсе самых важных событий в области!</p>
    <div style="display: grid; grid-template-columns: repeat(auto-fit, minmax(320px, 1fr)); gap: 1.5rem; margin-top: 2rem;">
    {% assign today = site.time | date: '%s' %}
    {% assign sorted_conferences = site.data.conferences.conferences | where: "active", true | sort: "abstract_deadline" %}
    {% assign upcoming_count = 0 %}
    {% for conf in sorted_conferences %}
        {% comment %} Определяем, какой дедлайн использовать и проверяем {% endcomment %}
        {% assign abstract_timestamp = conf.abstract_deadline | date: '%s' %}
        {% assign submission_timestamp = conf.submission_deadline | date: '%s' %}
        
        {% comment %} Определяем основной дедлайн (abstract если есть и не прошел, иначе submission) {% endcomment %}
        {% if conf.abstract_deadline and abstract_timestamp >= today %}
            {% assign primary_deadline = conf.abstract_deadline %}
            {% assign primary_deadline_timestamp = abstract_timestamp %}
            {% assign deadline_type = "Abstract" %}
        {% else %}
            {% assign primary_deadline = conf.submission_deadline %}
            {% assign primary_deadline_timestamp = submission_timestamp %}
            {% assign deadline_type = "Submission" %}
        {% endif %}
        
        {% comment %} Показываем только конференции с будущими дедлайнами, максимум 6 {% endcomment %}
        {% if primary_deadline_timestamp >= today and upcoming_count < 6 %}
            {% assign upcoming_count = upcoming_count | plus: 1 %}
            {% assign days_until = primary_deadline_timestamp | minus: today | divided_by: 86400 %}
            <a href="{{ conf.website }}" target="_blank" class="conference-card">
                <div class="conference-name">
                    <h3>{{ conf.name }}</h3>
                    <span class="conference-rank">{{ conf.rank }}</span>
                </div>
                <p class="conference-full-name">{{ conf.full_name }}</p>
                <div class="conference-deadline-box">
                    {% comment %} Показываем abstract deadline если есть и не прошел {% endcomment %}
                    {% if conf.abstract_deadline and abstract_timestamp >= today %}
                    <div style="display: flex; justify-content: space-between; align-items: center; margin-bottom: 0.5rem;">
                        <span class="deadline-label">Дедлайн абстракта</span>
                        <span class="deadline-date">{{ conf.abstract_deadline | date: "%d.%m.%Y" }}</span>
                    </div>
                    {% endif %}
                    {% comment %} Показываем submission deadline если отличается от abstract или если abstract прошел {% endcomment %}
                    {% if conf.submission_deadline != conf.abstract_deadline or abstract_timestamp < today %}
                    <div style="display: flex; justify-content: space-between; align-items: center;">
                        <span class="deadline-label">Дедлайн подачи</span>
                        <span class="deadline-date">{{ conf.submission_deadline | date: "%d.%m.%Y" }}</span>
                    </div>
                    {% endif %}
                    {% if days_until <= 30 %}
                    <div class="deadline-warning">
                        {% if deadline_type == "Abstract" %}
                        ⚠️ Осталось всего {{ days_until }} дней до дедлайна абстракта!
                        {% else %}
                        ⚠️ Осталось всего {{ days_until }} дней до дедлайна подачи!
                        {% endif %}
                    </div>
                    {% endif %}
                </div>
                <div class="conference-info">
                    📅 Конференция: {{ conf.conference_date | date: "%d.%m.%Y" }}
                </div>
                <div class="conference-info">
                    📍 {{ conf.location }}
                </div>
            </a>
        {% endif %}
    {% endfor %}
    </div>
</section>

<!-- News Section -->
<section class="fade-in-section" style="margin: 3rem 0;">
    <h2>Новости</h2>
    <div style="display: flex; align-items: center; position: relative;">
        <div class="news-scroll-container" style="overflow-x: auto; flex: 1; padding: 0.5rem 0;">
            <div style="display: flex; gap: 1.5rem; min-width: 0; padding: 0 0.5rem;">
            {% if site.posts and site.posts.size > 0 %}
                {% assign news_sorted = site.posts | where: "lang", "ru" | sort: 'date' | reverse %}
                {% for post in news_sorted limit:10 %}
                    <a class="news-block" href="{{ site.baseurl }}{{ post.url }}">
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
    </div>
</section>

<!-- About Section -->
<section class="fade-in-section">
    <h2>О кафедре</h2>
    <div style="margin-top: 1rem;">
    <p>Кафедра интеллектуальных систем в Физтехе (МФТИ) является ведущим центром образования и исследований в области прикладной математики, науки о данных и искусственного интеллекта. Кафедра предлагает программы бакалавриата и магистратуры по направлению «Прикладная математика и физика» со специализациями в области науки о данных, проектирования интеллектуальных систем и машинного обучения.</p>
    <p>Кафедра была основана академиком Константином Владимировичем Рудаковым и развивалась в рамках научной школы академика Юрия Ивановича Журавлева. Она базируется в Вычислительном центре Российской академии наук. В нашем составе — известные профессора, молодые ученые и эксперты из индустрии, средний возраст которых составляет 35 лет.</p>
    <p>Исследования кафедры охватывают машинное обучение, многомерную статистику, глубокое обучение, выбор моделей, генеративные нейронные сети и анализ сложных данных. Прикладные проекты включают анализ текста и изображений, обработку биомедицинских сигналов и интерфейсы «мозг-компьютер». Кафедра активно сотрудничает с международными университетами, научными центрами и высокотехнологичными компаниями, предлагая студентам уникальные возможности для стажировок, двойных дипломов и совместных исследований.</p>
    <p>Мы ценим открытость, инновации и постоянное совершенствование, поддерживая студентов стипендиями и личным наставничеством. Присоединяйтесь к нам, чтобы учиться, исследовать и внедрять инновации в области интеллектуальных систем!</p>
    </div>
</section>

<!-- Department Statistics -->
<div style="margin: 3rem auto 2.5rem auto; max-width: 1200px; width: 95%;">
    <div style="display: grid; grid-template-columns: repeat(auto-fit, minmax(320px, 1fr)); gap: 3rem 4rem; text-align: center; padding: 1.5rem 0;">
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
            <p style="max-width: 220px; font-size: 1rem;">студенты представляют <a href="/materials/nir">научные отчеты</a>: paper-code-presentation</p>
        </div>
        <div class="fade-in-right" style="display: flex; flex-direction: column; align-items: center;">
            <p style="font-size: 2.2rem; font-weight: 600; line-height: 1.1; margin-bottom: 0.5rem;">NeurIPS,<br>ICML, ICLR<br>AISTATS</p>
            <p style="max-width: 220px; font-size: 1rem;">top-tier конференции публикуют наши исследования</p>
        </div>
    </div>
</div>

<!-- Personalities Section -->
<section id="personalities" class="fade-in-section" style="margin: 2rem 0;">
  <h2>Личности</h2>
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
                    <a class="name" href="{{ site.baseurl }}{{ profile.url }}">{% t peoples.name.{{ profile_id }} %}</a>
                    </p>
                </div>
            {% endif %}
        {% endfor %}
    {% endfor %}
    </div>
</section>

<!-- Courses Section -->
<section class="fade-in-section">
    <h2>Курсы</h2>
    <p>
        Мы предлагаем широкий спектр курсов по прикладной математике, анализу данных и машинному обучению как для студентов бакалавриата, так и для магистрантов. Наша учебная программа разработана для обеспечения прочной теоретической базы наряду с практическими навыками, необходимыми в индустрии.
    </p>
    {% for type in site.global.course.types %}
        {% if type != 'deprecated' %}
            <div class="list-header">
                <h3 id="{% t site.global.course.types.{{ type }} %}">{% t site.global.course.types.{{ type }} %}</h3>
            </div>
            <div class="list-course">
                {% for course in site.course %}
                    {% if course.type contains type %}
                    <a class="course-name" href="{{ site.baseurl }}{{ course.url }}">
                    <div class="list-item-course">
                        <p class="list-item-course-title">
                        {% t courses.name.{{ course.id | split: "/" | last }} %}
                        </p>
                    </div>
                    </a>
                    {% endif %}
                {% endfor %}
            </div>
        {% endif %}
    {% endfor %}
</section>

<!-- Full-width Image Before Research Section -->
<div style="width: 100vw; position: relative; left: 50%; transform: translateX(-50%); margin: 3.5rem 0;">
<img src="{{ site.baseurl_root }}/images/main/zhuravlev_rudakov_merged.jpg" loading="lazy" style="width: 100vw; max-width: 100%; height: auto; object-fit: cover;  border-radius: 0px">
</div>

<!-- Research Section -->
<section class="fade-in-section">
    <h2>Научная работа</h2>
    <div style="margin: 0 0 3rem 0; max-width: 1200px;">
        <p>
            Мы открыто публикуем результаты исследований и приглашаем к сотрудничеству студентов, исследователей и промышленные компании.
        </p>
        <div style="display: grid; grid-template-columns: repeat(auto-fit, minmax(350px, 1fr)); gap: 2.5rem; margin: 2.5rem 0;">
            <div class="fade-in-left research-block" >
                <a class="research-block-title" href="/materials/nir">Научные исследования</a>
                <p style="margin: 1rem 0;">
                    Наша кафедра проводит фундаментальные и прикладные исследования в области машинного обучения, анализа данных, искусственного интеллекта и смежных областей.
                    Результаты публикуются в открытом доступе и представляются на международных конференциях. Мы приветствуем совместные проекты и новые идеи!
                </p>
                <p style="padding-top: 1rem; border-top: 1px solid #eee; text-align: left;">
                    <strong>Научные направления:</strong> распознавание образов, обработка естественного языка, биомедицинские сигналы, генеративные модели, теория машинного обучения
                </p>
            </div>
            <div class="fade-in-right research-block" >
                <a class="research-block-title" href="/materials/thesis">Дипломные работы</a>
                <p style="margin: 1rem 0;">
                    Студенты участвуют в реальных исследованиях, готовят дипломные работы и публикуют свои результаты.
                    Мы поддерживаем открытое опубликование кода и статей и приглашаем всех к сотрудничеству по темам дипломных работ и исследовательским проектам.
                </p>
                <p style="padding-top: 1rem; border-top: 1px solid #eee; text-align: left;">
                    <strong>Работа студентов:</strong> публикации, дипломные работы бакалавров и магистров, кандидатские диссертации
                </p>
            </div>
        </div>
        <div style="display: grid; grid-template-columns: repeat(auto-fit, minmax(350px, 1fr)); gap: 2.5rem;">
            <div class="fade-in-left research-block" >
                <a class="research-block-title" href="/materials/scholarship">Стипендии</a>
                <p style="margin: 1rem 0;">
                    Мы поддерживаем исследования наших студентов, присуждая несколько стипендий каждый семестр.
                    <a href="/materials/scholarship/" style="font-weight: 400;">Научная стипендия имени К.В. Рудакова</a> присуждается студентам бакалавриата и магистратуры за академические и исследовательские достижения.
                    <span style="font-weight: 400;">Спонсор: Forexis Group.</span>
                </p>
            </div>
            <div class="fade-in-right research-block" >
                <div class="research-block-title">Стажировки</div>
                <p style="margin: 1rem 0;">
                    С самого начала кафедра активно сотрудничает с базовыми организациями группы компаний Forexis и участвует в совместных проектах с ведущими технологическими компаниями.
                </p>
                <div style="display: flex; flex-wrap: wrap; gap: 0.5rem;">
                    <p style="background: #f0f0f0; padding: 0.3rem 0.8rem; border-radius: 1rem;">Форексис</p>
                    <p style="background: #f0f0f0; padding: 0.3rem 0.8rem; border-radius: 1rem;">Антиплагиат</p>
                    <p style="background: #f0f0f0; padding: 0.3rem 0.8rem; border-radius: 1rem;">Яндекс</p>
                    <p style="background: #f0f0f0; padding: 0.3rem 0.8rem; border-radius: 1rem;">СБЕР</p>
                </div>
            </div>
        </div>
    </div>
</section>

<!-- Image carousel -->
<section class="fade-in-section">
    <h2>Наша жизнь</h2>
    <p>
        Здесь мы делимся некоторыми моментами из жизни нашей кафедры: учебные мероприятия, защиты дипломов, встречи выпускников.
    </p>
    <div id="carousel-section">
        <link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/bulma-carousel@4.0.3/dist/css/bulma-carousel.min.css">
        <div id="carousel-demo" class="carousel">
            <div class="carousel-item">
                <img src="{{ site.baseurl_root }}/images/life/bachelors-2025.jpeg" loading="lazy" alt="Бакалавриат 2025">
                <p>Бакалавриат, выпуск 2025</p>
            </div>
            <div class="carousel-item">
                <img src="{{ site.baseurl_root }}/images/life/masters-2025.jpeg" loading="lazy" alt="Магистратура 2025">
                <p>Магистратура, выпуск 2025</p>
            </div>
            <div class="carousel-item">
                <img src="{{ site.baseurl_root }}/images/life/bachelors-2024.jpeg" loading="lazy" alt="Бакалавриат 2024">
                <p>Бакалавриат, выпуск 2024</p>
            </div>
            <div class="carousel-item">
                <img src="{{ site.baseurl_root }}/images/life/masters-2024.jpeg" loading="lazy" alt="Магистратура 2024">
                <p>Магистратура, выпуск 2024</p>
            </div>
        </div>
    </div>
</section>
