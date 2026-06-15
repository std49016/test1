<!DOCTYPE html>
<html lang="th">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>โปรไฟล์แนะนำตัวของฉัน</title>
    
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Sarabun:wght@300;400;500;700&display=swap" rel="stylesheet">

    <style>
        /* --- ตั้งค่าตัวแปรสีและสไตล์พื้นฐาน --- */
        :root {
            --primary: #2196F3;
            --primary-light: #E3F2FD;
            --white: #FFFFFF;
            --text-dark: #333333;
            --text-muted: #666666;
            --bg-gray: #F8F9FA;
        }

        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
        }

        html {
            scroll-behavior: smooth; /* เลื่อนหน้าจอแบบนุ่มนวล */
        }

        body {
            font-family: 'Sarabun', 'Segoe UI', sans-serif;
            color: var(--text-dark);
            line-height: 1.6;
            background-color: var(--white);
        }

        /* --- Navigation Bar (Sticky) --- */
        header {
            position: sticky;
            top: 0;
            background-color: rgba(255, 255, 255, 0.95);
            backdrop-filter: blur(5px);
            box-shadow: 0 2px 10px rgba(0, 0, 0, 0.05);
            z-index: 1000;
        }

        nav {
            max-width: 1000px;
            margin: 0 auto;
            display: flex;
            justify-content: center;
            padding: 15px 20px;
        }

        nav a {
            color: var(--text-dark);
            text-decoration: none;
            font-weight: 500;
            margin: 0 15px;
            padding: 5px 10px;
            transition: color 0.3s ease;
        }

        nav a:hover {
            color: var(--primary);
        }

        /* --- โครงสร้างสไตล์ของแต่ละ Section --- */
        section {
            padding: 80px 20px;
            max-width: 900px;
            margin: 0 auto;
        }

        .section-title {
            text-align: center;
            font-size: 2rem;
            margin-bottom: 40px;
            color: var(--primary);
            position: relative;
        }

        .section-title::after {
            content: '';
            display: block;
            width: 50px;
            height: 3px;
            background-color: var(--primary);
            margin: 10px auto 0;
            border-radius: 2px;
        }

        /* --- ส่วนหัว (Hero Section) --- */
        #hero {
            background: linear-gradient(135deg, var(--primary-light) 0%, var(--white) 100%);
            max-width: 100%;
            text-align: center;
            padding: 100px 20px;
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
        }

        .profile-img {
            width: 200px;
            height: 200px;
            border-radius: 50%;
            border: 5px solid var(--white);
            box-shadow: 0 8px 20px rgba(0, 0, 0, 0.1);
            margin-bottom: 25px;
            object-fit: cover;
        }

        #hero h1 {
            font-size: 2.8rem;
            color: var(--text-dark);
            margin-bottom: 10px;
        }

        #hero p {
            font-size: 1.3rem;
            color: var(--primary);
            font-weight: 500;
        }

        /* --- ส่วนประวัติย่อ (About Me) --- */
        #about {
            background-color: var(--white);
        }

        .about-box {
            background-color: var(--primary-light);
            padding: 35px;
            border-radius: 15px;
            box-shadow: 0 4px 15px rgba(33, 150, 243, 0.05);
            text-align: center;
            font-size: 1.1rem;
            color: #444;
            max-width: 750px;
            margin: 0 auto;
        }

        /* --- ส่วนความสามารถพิเศษ (Skills) --- */
        #skills {
            background-color: var(--bg-gray);
            max-width: 100%;
        }

        .skills-container {
            max-width: 700px;
            margin: 0 auto;
            background: var(--white);
            padding: 40px;
            border-radius: 15px;
            box-shadow: 0 4px 15px rgba(0,0,0,0.02);
        }

        .skill-wrapper {
            margin-bottom: 25px;
        }

        .skill-wrapper:last-child {
            margin-bottom: 0;
        }

        .skill-info {
            display: flex;
            justify-content: space-between;
            margin-bottom: 8px;
            font-weight: 500;
        }

        .progress-bg {
            background-color: #E0E0E0;
            border-radius: 10px;
            height: 15px;
            width: 100%;
            overflow: hidden;
        }

        .progress-bar {
            height: 100%;
            width: 0%; /* เริ่มต้นจาก 0 เพื่อทำแอนิเมชันผ่าน JS */
            background-color: var(--primary);
            border-radius: 10px;
            transition: width 1.5s cubic-bezier(0.1, 0.8, 0.2, 1);
        }

        /* --- ส่วนช่องทางติดต่อ (Contact) --- */
        #contact {
            background-color: var(--white);
        }

        .contact-links {
            display: flex;
            justify-content: center;
            gap: 20px;
            flex-wrap: wrap;
            margin-top: 20px;
        }

        .contact-item {
            display: flex;
            align-items: center;
            gap: 10px;
            text-decoration: none;
            color: var(--text-dark);
            padding: 12px 24px;
            border: 2px solid var(--primary-light);
            border-radius: 30px;
            font-weight: 500;
            transition: all 0.3s ease;
        }

        .contact-item svg {
            width: 20px;
            height: 20px;
            fill: currentColor;
        }

        /* Hover Effect สำหรับช่องทางติดต่อ */
        .contact-item:hover {
            background-color: var(--primary);
            color: var(--white);
            border-color: var(--primary);
            transform: translateY(-3px);
            box-shadow: 0 5px 15px rgba(33, 150, 243, 0.3);
        }

        /* --- Footer --- */
        footer {
            text-align: center;
            padding: 25px;
            background-color: #222222;
            color: #FAFAFA;
            font-size: 0.9rem;
        }

        /* --- Responsive Design (Mobile Breakpoint 768px) --- */
        @media (max-width: 768px) {
            nav {
                flex-direction: column;
                align-items: center;
                gap: 10px;
            }

            #hero h1 {
                font-size: 2.2rem;
            }

            #hero p {
                font-size: 1.1rem;
            }

            .contact-links {
                flex-direction: column;
                align-items: stretch;
                max-width: 300px;
                margin: 20px auto 0;
            }

            .contact-item {
                justify-content: center;
            }
        }
    </style>
</head>
<body>

    <header>
        <nav>
            <a href="#hero">หน้าแรก</a>
            <a href="#about">ประวัติย่อ</a>
            <a href="#skills">ความสามารถ</a>
            <a href="#contact">ติดต่อ</a>
        </nav>
    </header>

    <section id="hero">
        <img src="https://placehold.co/200x200/2196F3/ffffff?text=My+Profile" alt="รูปโปรไฟล์ของคุณ" class="profile-img">
        <h1>สมชาย ใจดี</h1>
        <p>Frontend Developer & UX/UI Enthusiast</p>
    </section>

    <section id="about">
        <h2 class="section-title">เกี่ยวกับฉัน</h2>
        <div class="about-box">
            <p>สวัสดีครับ! ผมเป็นนักพัฒนาเว็บไซต์ที่หลงใหลในการสร้างสรรค์ User Experience ที่ดีเยี่ยมและตอบโจทย์ผู้ใช้งาน มีความสนใจในเทคโนโลยีเว็บสมัยใหม่และการออกแบบที่เรียบง่ายสะอาดตา เป้าหมายของผมคือการพัฒนาซอฟต์แวร์ที่ช่วยขับเคลื่อนธุรกิจและยกระดับชีวิตประจำวันของผู้คนให้ง่ายขึ้นผ่านโค้ดที่มีประสิทธิภาพ</p>
        </div>
    </section>

    <section id="skills">
        <h2 class="section-title">ความสามารถพิเศษ</h2>
        <div class="skills-container">
            
            <div class="skill-wrapper">
                <div class="skill-info">
                    <span>HTML / CSS</span>
                    <span>90%</span>
                </div>
                <div class="progress-bg">
                    <div class="progress-bar" data-percent="90"></div>
                </div>
            </div>

            <div class="skill-wrapper">
                <div class="skill-info">
                    <span>JavaScript</span>
                    <span>80%</span>
                </div>
                <div class="progress-bg">
                    <div class="progress-bar" data-percent="80"></div>
                </div>
            </div>

            <div class="skill-wrapper">
                <div class="skill-info">
                    <span>Responsive Design</span>
                    <span>85%</span>
                </div>
                <div class="progress-bg">
                    <div class="progress-bar" data-percent="85"></div>
                </div>
            </div>

            <div class="skill-wrapper">
                <div class="skill-info">
                    <span>React / Vue</span>
                    <span>70%</span>
                </div>
                <div class="progress-bg">
                    <div class="progress-bar" data-percent="70"></div>
                </div>
            </div>

            <div class="skill-wrapper">
                <div class="skill-info">
                    <span>UX/UI Design</span>
                    <span>75%</span>
                </div>
                <div class="progress-bg">
                    <div class="progress-bar" data-percent="75"></div>
                </div>
            </div>

        </div>
    </section>

    <section id="contact">
        <h2 class="section-title">ช่องทางการติดต่อ</h2>
        <div class="contact-links">
            
            <a href="mailto:somchai.dev@email.com" class="contact-item">
                <svg viewBox="0 0 24 24"><path d="M20 4H4c-1.1 0-1.99.9-1.99 2L2 18c0 1.1.9 2 2 2h16c1.1 0 2-.9 2-2V6c0-1.1-.9-2-2-2zm0 4l-8 5-8-5V6l8 5 8-5v2z"/></svg>
                <span>somchai.dev@email.com</span>
            </a>

            <a href="tel:0812345678" class="contact-item">
                <svg viewBox="0 0 24 24"><path d="M6.62 10.79c1.44 2.83 3.76 5.14 6.59 6.59l2.2-2.2c.27-.27.67-.36 1.02-.24 1.12.37 2.33.57 3.57.57.55 0 1 .45 1 1V20c0 .55-.45 1-1 1-9.39 0-17-7.61-17-17 0-.55.45-1 1-1h3.5c.55 0 1 .45 1 1 0 1.25.2 2.45.57 3.57.11.35.03.74-.25 1.02l-2.2 2.2z"/></svg>
                <span>081-234-5678</span>
            </a>

            <a href="https://github.com" target="_blank" class="contact-item">
                <svg viewBox="0 0 24 24"><path d="M12 2C6.48 2 2 6.48 2 12s4.48 10 10 10 10-4.48 10-10S17.52 2 12 2zm-1 17.93c-3.95-.49-7-3.85-7-7.93 0-.62.08-1.21.21-1.79L9 15v1c0 1.1.9 2 2 2v1.93zm6.9-2.53c-.26-.81-1-1.4-1.9-1.4h-1v-3c0-.55-.45-1-1-1h-6v-2h2c.55 0 1-.45 1-1V7h2c1.1 0 2-.9 2-2v-.41c2.93 1.19 5 4.06 5 7.41 0 2.08-.8 3.97-2.1 5.39z"/></svg>
                <span>GitHub Profile</span>
            </a>

        </div>
    </section>

    <footer>
        <p>&copy; 2026 Somchai Jaidee. All Rights Reserved.</p>
    </footer>

    <script>
        document.addEventListener("DOMContentLoaded", function() {
            const progressBars = document.querySelectorAll('.progress-bar');
            
            // ฟังก์ชันสั่งเพิ่มความกว้างเมื่อ Section เลื่อนเข้ามาในจอ
            const animateSkills = (entries, observer) => {
                entries.forEach(entry => {
                    if (entry.isIntersecting) {
                        const bar = entry.target;
                        const percent = bar.getAttribute('data-percent');
                        bar.style.width = percent + '%';
                        observer.unobserve(bar); // สั่งให้ทำงานแค่ครั้งเดียว ไม่ต้องตรวจจับซ้ำ
                    }
                });
            };

            // สร้าง Observer ตรวจจับตำแหน่งหน้าจอ
            const observer = new IntersectionObserver(animateSkills, {
                threshold: 0.1 // ให้เริ่มทำงานเมื่อส่วนประกอบโผล่มา 10% ของจอ
            });

            progressBars.forEach(bar => {
                observer.observe(bar);
            });
        });
    </script>
</body>
</html>
