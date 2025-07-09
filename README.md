# My_Tube-youtube-clone-

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>MyTube - Educational Video Platform</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>
    <div id="google-tools-bar" style="width:100%;background:orange;padding:6px 0;display:flex;justify-content:center;align-items:center;gap:18px;box-shadow:0 2px 8px #e3eafc;">
        <!-- Google tools will be rendered by JS -->
    </div>
    <div id="advanced-web-tools-bar" style="width:100%;background:#222;padding:6px 0;display:flex;justify-content:center;align-items:center;gap:18px;box-shadow:0 2px 8px #e3eafc;">
        <!-- Advanced web tools will be rendered by JS -->
    </div>
    <div id="splash-screen">
        <div class="splash-content">
            <img src="https://cdn-icons-png.flaticon.com/512/3135/3135768.png" alt="Student" class="splash-img">
            <h1>MyTube</h1>
        </div>
    </div>
    <header>
        <div class="logo">MyTube</div>
        <input type="text" class="search-bar" placeholder="Search educational videos">
        <button class="search-btn">🔍</button>
        <div class="auth-buttons">
            <button id="login-btn">Login</button>
            <button id="signup-btn">Sign Up</button>
            <span id="user-count"></span>
        </div>
    </header>
    <main>
        <aside class="sidebar">
            <ul>
                <li id="home-tab">Home</li>
                <li id="edu-tab">Education Only</li>
            </ul>
        </aside>
        <section class="videos" id="videos-section">
            <!-- Videos will be rendered by JS -->
        </section>
        <aside id="history-section" class="history-section">
            <!-- History will be rendered here by JS -->
        </aside>
    </main>
    <div id="auth-modal" class="modal" style="display:none;">
        <div class="modal-content">
            <span class="close-modal" id="close-modal">&times;</span>
            <h2 id="modal-title">Sign Up</h2>
            <form id="auth-form">
                <input type="text" id="username" placeholder="Username" required><br>
                <input type="password" id="password" placeholder="Password" required><br>
                <button type="submit" id="submit-auth">Submit</button>
            </form>
        </div>
    </div>
    <script src="script.js"></script>
</body>
</html>


CSS


body {
    margin: 0;
    font-family: 'Segoe UI', Arial, sans-serif;
    background: #f4f6fa;
}
#splash-screen {
    position: fixed;
    top: 0; left: 0; width: 100vw; height: 100vh;
    background: #1976d2;
    display: flex; align-items: center; justify-content: center;
    z-index: 9999;
    transition: opacity 0.6s;
}
.splash-content {
    display: flex; flex-direction: column; align-items: center;
}
.splash-img {
    width: 90px; height: 90px; border-radius: 50%; background: #fff;
    box-shadow: 0 2px 12px #1976d2; margin-bottom: 18px;
}
#splash-screen h1 {
    color: #fff; font-size: 2.5rem; font-weight: bold; letter-spacing: 2px;
}
#google-tools-bar {
    position: fixed;
    top: 0;
    left: 0;
    width: 100vw;
    z-index: 102;
    background: orange;
    padding: 6px 0;
    display: flex;
    justify-content: center;
    align-items: center;
    gap: 18px;
    box-shadow: 0 2px 8px #e3eafc;
}
#advanced-web-tools-bar {
    position: fixed;
    top: 44px;
    left: 0;
    width: 100vw;
    z-index: 101;
    background: #222;
    padding: 6px 0;
    display: flex;
    justify-content: center;
    align-items: center;
    gap: 18px;
    box-shadow: 0 2px 8px #e3eafc;
}
header {
    display: flex; align-items: center; padding: 18px 32px; background: #fff;
    box-shadow: 0 2px 8px #e3eafc; 
    position: fixed;
    top: 88px; /* below both bars (44px each) */
    left: 0;
    width: 100vw;
    z-index: 100;
}
.logo {
    font-size: 2rem; font-weight: bold; color: #1976d2; letter-spacing: 2px;
    margin-right: 32px;
}
.search-bar {
    flex: 1; padding: 8px 16px; border-radius: 6px; border: 1px solid #b3c6f7;
    font-size: 1rem; margin-right: 8px;
}
.search-btn {
    background: #1976d2; color: #fff; border: none; border-radius: 6px;
    padding: 8px 18px; font-size: 1rem; cursor: pointer; margin-right: 24px;
    transition: background 0.2s;
}
.search-btn:hover { background: #1251a3; }
.auth-buttons button {
    background: #fff; color: #1976d2; border: 1px solid #1976d2;
    border-radius: 6px; padding: 6px 16px; font-size: 1rem; cursor: pointer;
    margin-left: 8px; transition: background 0.2s, color 0.2s;
}
.auth-buttons button:hover {
    background: #1976d2; color: #fff;
}
main {
    display: flex;
    margin-top: 178px; /* 44+44+90px header height */
}
.sidebar {
    width: 180px; background: #fff; box-shadow: 0 2px 8px #e3eafc;
    border-radius: 12px; margin-left: 32px; padding: 18px 0;
    height: fit-content;
}
.sidebar ul { list-style: none; padding: 0; margin: 0; }
.sidebar li {
    padding: 12px 24px; font-size: 1.1rem; color: #1976d2; cursor: pointer;
    border-radius: 6px; margin-bottom: 8px; transition: background 0.2s;
}
.sidebar li:hover { background: #e3eafc; }
.videos {
    flex: 1; display: flex; flex-wrap: wrap; gap: 24px;
    padding: 0 32px;
}
.video-card {
    background: #fff; border-radius: 14px; box-shadow: 0 2px 12px #e3eafc;
    margin: 18px 0; padding: 18px 18px 12px 18px;
    display: flex; flex-direction: column; align-items: flex-start;
    transition: box-shadow 0.2s; position: relative; width: 320px;
}
.video-card:hover { box-shadow: 0 4px 24px #b3c6f7; }
.video-thumb {
    width: 100%; max-width: 340px; border-radius: 10px; margin-bottom: 12px;
    object-fit: cover; background: #e3eafc;
}
.video-title {
    font-size: 1.2rem; font-weight: bold; color: #1976d2; margin-bottom: 6px;
}
.video-desc {
    font-size: 1rem; color: #444; margin-bottom: 10px;
}
.download-btn {
    background: #1976d2; color: #fff; border: none; border-radius: 6px;
    padding: 6px 16px; font-size: 1rem; cursor: pointer; margin-top: 6px;
    transition: background 0.2s;
}
.download-btn:hover { background: #1251a3; }
.history-section {
    width: 260px; background: #fff; box-shadow: 0 2px 8px #e3eafc;
    border-radius: 12px; margin-right: 32px; padding: 18px 18px 12px 18px;
    height: fit-content;
}
.modal {
    position: fixed; top: 0; left: 0; width: 100vw; height: 100vh;
    background: rgba(0,0,0,0.3); display: flex; align-items: center; justify-content: center;
    z-index: 10000;
}
.modal-content {
    background: #fff; border-radius: 12px; padding: 32px 40px; box-shadow: 0 2px 12px #b3c6f7;
    position: relative;
}
.close-modal {
    position: absolute; top: 12px; right: 18px; font-size: 2rem; color: #1976d2; cursor: pointer;
}
@media (max-width: 900px) {
    main { flex-direction: column; }
    .sidebar, .history-section { width: 100%; margin: 0 0 18px 0; }
    .videos { padding: 0 8px; }
}



JS


// Splash screen logic
window.addEventListener('DOMContentLoaded', function() {
    const splash = document.getElementById('splash-screen');
    setTimeout(() => {
        splash.style.opacity = 0;
        setTimeout(() => splash.remove(), 600);
    }, 1800);
});

// Educational video data
const videoData = [
    {
        title: "HTML5 Full Course - Build a Website Tutorial",
        desc: "Learn HTML5 from scratch and build a complete website.",
        thumb: "https://img.youtube.com/vi/mU6anWqZJcc/hqdefault.jpg",
        url: "https://www.youtube.com/watch?v=mU6anWqZJcc"
    },
    {
        title: "CSS Tutorial - Zero to Hero (Complete Course)",
        desc: "Master CSS and responsive design in this full course.",
        thumb: "https://img.youtube.com/vi/1Rs2ND1ryYc/hqdefault.jpg",
        url: "https://www.youtube.com/watch?v=1Rs2ND1ryYc"
    },
    {
        title: "JavaScript Tutorial for Beginners",
        desc: "A complete introduction to JavaScript programming.",
        thumb: "https://img.youtube.com/vi/W6NZfCO5SIk/hqdefault.jpg",
        url: "https://www.youtube.com/watch?v=W6NZfCO5SIk"
    },
    {
        title: "Python Programming for Beginners",
        desc: "Start learning Python from scratch with this beginner-friendly tutorial.",
        thumb: "https://img.youtube.com/vi/_uQrJ0TkZlc/hqdefault.jpg",
        url: "https://www.youtube.com/watch?v=_uQrJ0TkZlc"
    },
    {
        title: "Full Stack Web Development Bootcamp",
        desc: "Become a full stack web developer with this comprehensive course.",
        thumb: "https://img.youtube.com/vi/nu_pCVPKzTk/hqdefault.jpg",
        url: "https://www.youtube.com/watch?v=nu_pCVPKzTk"
    },
    {
        title: "Kali Linux Tutorial for Beginners",
        desc: "Learn the basics of Kali Linux, a popular OS for cybersecurity.",
        thumb: "https://img.youtube.com/vi/2eJzSRgB8xE/hqdefault.jpg",
        url: "https://www.youtube.com/watch?v=2eJzSRgB8xE"
    },
    {
        title: "Ubuntu Linux Full Course",
        desc: "Complete Ubuntu Linux course for beginners.",
        thumb: "https://img.youtube.com/vi/8lR8RkW3Yl0/hqdefault.jpg",
        url: "https://www.youtube.com/watch?v=8lR8RkW3Yl0"
    },
    {
        title: "HTML & CSS Crash Course",
        desc: "Master the basics of HTML and CSS for web design.",
        thumb: "https://img.youtube.com/vi/UB1O30fR-EE/hqdefault.jpg",
        url: "https://www.youtube.com/watch?v=UB1O30fR-EE"
    },
    {
        title: "JavaScript DOM Tutorial",
        desc: "Learn how to manipulate the DOM with JavaScript.",
        thumb: "https://img.youtube.com/vi/0ik6X4DJKCc/hqdefault.jpg",
        url: "https://www.youtube.com/watch?v=0ik6X4DJKCc"
    },
    {
        title: "React JS Crash Course",
        desc: "A fast-paced introduction to building web apps with React JS.",
        thumb: "https://img.youtube.com/vi/w7ejDZ8SWv8/hqdefault.jpg",
        url: "https://www.youtube.com/watch?v=w7ejDZ8SWv8"
    },
    {
        title: "SQL Tutorial - Full Database Course for Beginners",
        desc: "Learn SQL and database fundamentals in this full course.",
        thumb: "https://img.youtube.com/vi/HXV3zeQKqGY/hqdefault.jpg",
        url: "https://www.youtube.com/watch?v=HXV3zeQKqGY"
    },
    {
        title: "Machine Learning Crash Course",
        desc: "A beginner's guide to machine learning concepts and applications.",
        thumb: "https://img.youtube.com/vi/GwIo3gDZCVQ/hqdefault.jpg",
        url: "https://www.youtube.com/watch?v=GwIo3gDZCVQ"
    },
    {
        title: "Git & GitHub Crash Course",
        desc: "Learn version control with Git and GitHub for collaboration.",
        thumb: "https://img.youtube.com/vi/RGOj5yH7evk/hqdefault.jpg",
        url: "https://www.youtube.com/watch?v=RGOj5yH7evk"
    },
    {
        title: "Data Structures & Algorithms in Python",
        desc: "Learn essential data structures and algorithms using Python.",
        thumb: "https://img.youtube.com/vi/8hly31xKli0/hqdefault.jpg",
        url: "https://www.youtube.com/watch?v=8hly31xKli0"
    },
    {
        title: "Physics - Motion, Force, Energy",
        desc: "Understand the basics of physics: motion, force, and energy.",
        thumb: "https://img.youtube.com/vi/1TtGQnyPZ6g/hqdefault.jpg",
        url: "https://www.youtube.com/watch?v=1TtGQnyPZ6g"
    },
    {
        title: "Chemistry - Atomic Structure",
        desc: "Explore the fundamentals of atomic structure in chemistry.",
        thumb: "https://img.youtube.com/vi/FSyAehMdpyI/hqdefault.jpg",
        url: "https://www.youtube.com/watch?v=FSyAehMdpyI"
    },
    {
        title: "Biology - Cell Structure & Function",
        desc: "Learn about the structure and function of cells in biology.",
        thumb: "https://img.youtube.com/vi/URUJD5NEXC8/hqdefault.jpg",
        url: "https://www.youtube.com/watch?v=URUJD5NEXC8"
    },
    {
        title: "Mathematics - Algebra Basics",
        desc: "Master the basics of algebra in mathematics.",
        thumb: "https://img.youtube.com/vi/5ANcspdYh_U/hqdefault.jpg",
        url: "https://www.youtube.com/watch?v=5ANcspdYh_U"
    },
    {
        title: "Learn Bootstrap 5 in 1 Hour",
        desc: "A quick introduction to Bootstrap 5 for responsive web design.",
        thumb: "https://img.youtube.com/vi/4sosXZsdy-s/hqdefault.jpg",
        url: "https://www.youtube.com/watch?v=4sosXZsdy-s"
    },
    {
        title: "Node.js Crash Course",
        desc: "Get started with Node.js and build your first server-side app.",
        thumb: "https://img.youtube.com/vi/fBNz5xF-Kx4/hqdefault.jpg",
        url: "https://www.youtube.com/watch?v=fBNz5xF-Kx4"
    },
    {
        title: "Learn TypeScript - Full Course",
        desc: "A complete guide to TypeScript for JavaScript developers.",
        thumb: "https://img.youtube.com/vi/BwuLxPH8IDs/hqdefault.jpg",
        url: "https://www.youtube.com/watch?v=BwuLxPH8IDs"
    },
    {
        title: "Linux Command Line Full Course",
        desc: "Master the Linux command line for productivity and scripting.",
        thumb: "https://img.youtube.com/vi/ROjZy1WbCIA/hqdefault.jpg",
        url: "https://www.youtube.com/watch?v=ROjZy1WbCIA"
    },
    {
        title: "Excel Full Course - Beginner to Advanced",
        desc: "Learn Microsoft Excel from beginner to advanced level.",
        thumb: "https://img.youtube.com/vi/8P0j5EUw3ac/hqdefault.jpg",
        url: "https://www.youtube.com/watch?v=8P0j5EUw3ac"
    },
    {
        title: "Introduction to Artificial Intelligence",
        desc: "A beginner's guide to AI concepts and applications.",
        thumb: "https://img.youtube.com/vi/JMUxmLyrhSk/hqdefault.jpg",
        url: "https://www.youtube.com/watch?v=JMUxmLyrhSk"
    },
    {
        title: "Learn Docker in 1 Hour",
        desc: "A fast-paced introduction to Docker and containerization.",
        thumb: "https://img.youtube.com/vi/3c-iBn73dDE/hqdefault.jpg",
        url: "https://www.youtube.com/watch?v=3c-iBn73dDE"
    },
    {
        title: "AWS for Beginners - Full Course",
        desc: "Learn Amazon Web Services (AWS) cloud basics.",
        thumb: "https://img.youtube.com/vi/ulprqHHWlng/hqdefault.jpg",
        url: "https://www.youtube.com/watch?v=ulprqHHWlng"
    },
    {
        title: "Learn Ethical Hacking in 10 Hours",
        desc: "A comprehensive course on ethical hacking and penetration testing.",
        thumb: "https://img.youtube.com/vi/3Kq1MIfTWCE/hqdefault.jpg",
        url: "https://www.youtube.com/watch?v=3Kq1MIfTWCE"
    },
    {
        title: "Learn Data Science in 3 Hours",
        desc: "A crash course on data science concepts and tools.",
        thumb: "https://img.youtube.com/vi/ua-CiDNNj30/hqdefault.jpg",
        url: "https://www.youtube.com/watch?v=ua-CiDNNj30"
    },
    { // New videos start here
        title: "Learn Java in One Video",
        desc: "Java programming full course for beginners.",
        thumb: "https://img.youtube.com/vi/grEKMHGYyns/hqdefault.jpg",
        url: "https://www.youtube.com/watch?v=grEKMHGYyns"
    },
    {
        title: "C Programming Tutorial for Beginners",
        desc: "Comprehensive C programming course.",
        thumb: "https://img.youtube.com/vi/KJgsSFOSQv0/hqdefault.jpg",
        url: "https://www.youtube.com/watch?v=KJgsSFOSQv0"
    },
    {
        title: "Learn C++ in One Video",
        desc: "C++ programming full course for beginners.",
        thumb: "https://img.youtube.com/vi/vLnPwxZdW4Y/hqdefault.jpg",
        url: "https://www.youtube.com/watch?v=vLnPwxZdW4Y"
    },
    {
        title: "JavaScript ES6 Tutorial",
        desc: "Modern JavaScript ES6 features explained.",
        thumb: "https://img.youtube.com/vi/NCwa_xi0Uuc/hqdefault.jpg",
        url: "https://www.youtube.com/watch?v=NCwa_xi0Uuc"
    },
    {
        title: "Python Data Science Crash Course",
        desc: "Data Science with Python for beginners.",
        thumb: "https://img.youtube.com/vi/X3paOmcrTjQ/hqdefault.jpg",
        url: "https://www.youtube.com/watch?v=X3paOmcrTjQ"
    },
    {
        title: "Deep Learning with TensorFlow",
        desc: "Deep learning basics using TensorFlow.",
        thumb: "https://img.youtube.com/vi/tPYj3fFJGjk/hqdefault.jpg",
        url: "https://www.youtube.com/watch?v=tPYj3fFJGjk"
    },
    {
        title: "Learn Cybersecurity in 8 Hours",
        desc: "Cybersecurity essentials for beginners.",
        thumb: "https://img.youtube.com/vi/3Kq1MIfTWCE/hqdefault.jpg",
        url: "https://www.youtube.com/watch?v=3Kq1MIfTWCE"
    },
    {
        title: "AP Calculus AB - Full Course",
        desc: "Complete AP Calculus AB course.",
        thumb: "https://img.youtube.com/vi/3Jxeh-yAXek/hqdefault.jpg",
        url: "https://www.youtube.com/watch?v=3Jxeh-yAXek"
    },
    {
        title: "Organic Chemistry Basics",
        desc: "Introduction to organic chemistry.",
        thumb: "https://img.youtube.com/vi/IVzNpR-jd-Y/hqdefault.jpg",
        url: "https://www.youtube.com/watch?v=IVzNpR-jd-Y"
    },
    {
        title: "World History Crash Course",
        desc: "Crash Course World History full playlist.",
        thumb: "https://img.youtube.com/vi/yvTKK8a6G2w/hqdefault.jpg",
        url: "https://www.youtube.com/watch?v=yvTKK8a6G2w"
    },
    {
        title: "Learn Statistics in 1 Hour",
        desc: "Statistics basics for students.",
        thumb: "https://img.youtube.com/vi/xxpc-HPKN28/hqdefault.jpg",
        url: "https://www.youtube.com/watch?v=xxpc-HPKN28"
    },
    {
        title: "Economics Explained - Full Course",
        desc: "Economics for beginners explained.",
        thumb: "https://img.youtube.com/vi/3ez10ADR_gM/hqdefault.jpg",
        url: "https://www.youtube.com/watch?v=3ez10ADR_gM"
    },
    {
        title: "Learn English Grammar - Full Course",
        desc: "English grammar for all levels.",
        thumb: "https://img.youtube.com/vi/2XgHM6bQ7Ck/hqdefault.jpg",
        url: "https://www.youtube.com/watch?v=2XgHM6bQ7Ck"
    },
    {
        title: "SAT Math Full Prep",
        desc: "SAT Math preparation and strategies.",
        thumb: "https://img.youtube.com/vi/1gkHwqB3b8A/hqdefault.jpg",
        url: "https://www.youtube.com/watch?v=1gkHwqB3b8A"
    },
    {
        title: "IELTS Listening Practice Test",
        desc: "IELTS listening test with answers.",
        thumb: "https://img.youtube.com/vi/7Hj6qQb2u2k/hqdefault.jpg",
        url: "https://www.youtube.com/watch?v=7Hj6qQb2u2k"
    },
    {
        title: "Learn Spanish for Beginners",
        desc: "Spanish language basics for beginners.",
        thumb: "https://img.youtube.com/vi/8lQ_OaQ0p6o/hqdefault.jpg",
        url: "https://www.youtube.com/watch?v=8lQ_OaQ0p6o"
    },
    {
        title: "Geography Now! - All Countries",
        desc: "Learn about every country in the world.",
        thumb: "https://img.youtube.com/vi/6v2L2UGZJAM/hqdefault.jpg",
        url: "https://www.youtube.com/watch?v=6v2L2UGZJAM"
    },
    {
        title: "Learn Blockchain in 1 Hour",
        desc: "Blockchain technology explained simply.",
        thumb: "https://img.youtube.com/vi/SSo_EIwHSd4/hqdefault.jpg",
        url: "https://www.youtube.com/watch?v=SSo_EIwHSd4"
    },
    {
        title: "Quantum Physics for Beginners",
        desc: "Introduction to quantum physics.",
        thumb: "https://img.youtube.com/vi/p7bzE1E5PMY/hqdefault.jpg",
        url: "https://www.youtube.com/watch?v=p7bzE1E5PMY"
    },
    {
        title: "Philosophy - The Basics",
        desc: "Crash course in philosophy.",
        thumb: "https://img.youtube.com/vi/1A_CAkYt3GY/hqdefault.jpg",
        url: "https://www.youtube.com/watch?v=1A_CAkYt3GY"
    }
];

function renderVideos(videos) {
    const section = document.getElementById('videos-section');
    section.innerHTML = '';
    videos.forEach(video => {
        const card = document.createElement('div');
        card.className = 'video-card';
        card.innerHTML = `
            <img class="video-thumb" src="${video.thumb}" alt="${video.title}">
            <div class="video-title">${video.title}</div>
            <div class="video-desc">${video.desc}</div>
            <button class="download-btn">Download</button>
            <a href="${video.url}" target="_blank" class="watch-btn" style="margin-left:12px;color:#1976d2;text-decoration:underline;">Watch</a>
        `;
        card.querySelector('.download-btn').onclick = (e) => {
            e.stopPropagation();
            alert('Download preview only.');
        };
        section.appendChild(card);
    });
}

// Initial render
renderVideos(videoData);

// Search functionality
const searchBar = document.querySelector('.search-bar');
const searchBtn = document.querySelector('.search-btn');
searchBtn.addEventListener('click', () => {
    const query = searchBar.value.toLowerCase();
    const filtered = videoData.filter(v => v.title.toLowerCase().includes(query) || v.desc.toLowerCase().includes(query));
    renderVideos(filtered);
    if (filtered.length === 0 && query) {
        // If no results, open Google search in a new tab
        window.open(`https://www.google.com/search?q=${encodeURIComponent(query)}`, '_blank');
    }
});
searchBar.addEventListener('keydown', (e) => {
    if (e.key === 'Enter') {
        const query = searchBar.value.toLowerCase();
        const filtered = videoData.filter(v => v.title.toLowerCase().includes(query) || v.desc.toLowerCase().includes(query));
        renderVideos(filtered);
        if (filtered.length === 0 && query) {
            window.open(`https://www.google.com/search?q=${encodeURIComponent(query)}`, '_blank');
        }
    }
});

// Sidebar filtering
const eduTab = document.getElementById('edu-tab');
const homeTab = document.getElementById('home-tab');
eduTab.addEventListener('click', () => {
    renderVideos(videoData);
});
homeTab.addEventListener('click', () => {
    renderVideos(videoData);
});

// Simple auth logic (demo only)
const loginBtn = document.getElementById('login-btn');
const signupBtn = document.getElementById('signup-btn');
const authModal = document.getElementById('auth-modal');
const closeModal = document.getElementById('close-modal');
const authForm = document.getElementById('auth-form');
const modalTitle = document.getElementById('modal-title');
const submitAuth = document.getElementById('submit-auth');
const userCount = document.getElementById('user-count');
let authMode = 'signup';
function getUsers() {
    return JSON.parse(localStorage.getItem('mytube_users') || '[]');
}
function setUsers(users) {
    localStorage.setItem('mytube_users', JSON.stringify(users));
}
function updateUserCount() {
    const users = getUsers();
    userCount.textContent = `Users: ${users.length}`;
}
function showModal(mode) {
    authMode = mode;
    modalTitle.textContent = mode === 'signup' ? 'Sign Up' : 'Login';
    authModal.style.display = 'flex';
}
function hideModal() {
    authModal.style.display = 'none';
    authForm.reset();
}
loginBtn.onclick = () => showModal('login');
signupBtn.onclick = () => showModal('signup');
closeModal.onclick = hideModal;
authModal.onclick = (e) => { if (e.target === authModal) hideModal(); };
authForm.onsubmit = (e) => {
    e.preventDefault();
    const username = document.getElementById('username').value.trim();
    const password = document.getElementById('password').value;
    let users = getUsers();
    if (authMode === 'signup') {
        if (users.find(u => u.username === username)) {
            alert('Username already exists!');
            return;
        }
        users.push({ username, password });
        setUsers(users);
        alert('Sign up successful!');
        updateUserCount();
        hideModal();
    } else {
        if (users.find(u => u.username === username && u.password === password)) {
            alert('Login successful!');
            hideModal();
        } else {
            alert('Invalid credentials!');
        }
    }
};
document.addEventListener('DOMContentLoaded', updateUserCount);

// Simple history (demo only)
const historyKey = 'mytube_history';
function addToHistory(title, url) {
    let history = JSON.parse(localStorage.getItem(historyKey) || '[]');
    history.unshift({ title, url, time: new Date().toLocaleString() });
    if (history.length > 30) history = history.slice(0, 30);
    localStorage.setItem(historyKey, JSON.stringify(history));
    renderHistory();
}
function renderHistory() {
    let history = JSON.parse(localStorage.getItem(historyKey) || '[]');
    const historySection = document.getElementById('history-section');
    if (!historySection) return;
    historySection.innerHTML = '<h3>History</h3>' +
        (history.length === 0 ? '<p>No history yet.</p>' :
        '<ul>' + history.map(item => `<li><a href="${item.url}" target="_blank">${item.title}</a> <span style="color:#888;font-size:0.9em;">(${item.time})</span></li>`).join('') + '</ul>');
}
document.addEventListener('DOMContentLoaded', renderHistory);

// Google tools/apps bar rendering
const googleApps = [
    { title: 'Google Search', url: 'https://www.google.com', img: 'https://www.google.com/images/branding/googlelogo/2x/googlelogo_light_color_92x30dp.png' },
    { title: 'Google Maps', url: 'https://maps.google.com', img: 'https://upload.wikimedia.org/wikipedia/commons/9/99/Google_Maps_Logo_2020.png' },
    { title: 'Google Docs', url: 'https://docs.google.com', img: 'https://ssl.gstatic.com/docs/doclist/images/drive_2022q3_32dp.png' },
    { title: 'Google Drive', url: 'https://drive.google.com', img: 'https://ssl.gstatic.com/images/branding/product/1x/drive_2020q4_32dp.png' },
    { title: 'Google Calendar', url: 'https://calendar.google.com', img: 'https://ssl.gstatic.com/calendar/images/dynamiclogo_2020q4/calendar_32_2x.png' },
    { title: 'Google Translate', url: 'https://translate.google.com', img: 'https://ssl.gstatic.com/translate/favicon.ico' },
    { title: 'Google News', url: 'https://news.google.com', img: 'https://ssl.gstatic.com/news-static/img/favicon.ico' },
    { title: 'Gmail', url: 'https://mail.google.com', img: 'https://ssl.gstatic.com/ui/v1/icons/mail/rfr/gmail.ico' },
    { title: 'Google Photos', url: 'https://photos.google.com', img: 'https://ssl.gstatic.com/images/branding/product/1x/photos_2022_48dp.png' },
    { title: 'YouTube', url: 'https://www.youtube.com', img: 'https://www.youtube.com/s/desktop/6e8e2e5d/img/favicon_32x32.png' },
    { title: 'Google Keep', url: 'https://keep.google.com', img: 'https://ssl.gstatic.com/keep/icon_2020v2_32.png' },
    { title: 'Google Classroom', url: 'https://classroom.google.com', img: 'https://ssl.gstatic.com/classroom/ic_product_classroom_32.png' },
    { title: 'Google Forms', url: 'https://forms.google.com', img: 'https://ssl.gstatic.com/docs/spreadsheets/forms/forms_2022_32dp.png' },
    { title: 'Google Sheets', url: 'https://sheets.google.com', img: 'https://ssl.gstatic.com/docs/spreadsheets/forms/sheets_2022_32dp.png' },
    { title: 'Google Slides', url: 'https://slides.google.com', img: 'https://ssl.gstatic.com/docs/presentations/images/favicon5.ico' },
    { title: 'Google Greek', url: 'https://www.google.gr', img: 'https://www.google.com/images/branding/googlelogo/2x/googlelogo_light_color_92x30dp.png' },
    { title: 'Wikipedia', url: 'https://www.wikipedia.org', img: 'https://upload.wikimedia.org/wikipedia/commons/6/63/Wikipedia-logo.png' }
];

function renderGoogleToolsBar() {
    const bar = document.getElementById('google-tools-bar');
    if (!bar) return;
    bar.innerHTML = googleApps.map(app =>
        `<a href="${app.url}" target="_blank" title="${app.title}" style="display:inline-block;"><img src="${app.img}" alt="${app.title}" style="height:28px;vertical-align:middle;margin:0 4px;"></a>`
    ).join('');
}
document.addEventListener('DOMContentLoaded', renderGoogleToolsBar);

// Advanced web development tools
const advancedWebTools = [
    { title: 'W3Schools', url: 'https://www.w3schools.com', img: 'https://www.w3schools.com/favicon.ico' },
    { title: 'MDN Web Docs', url: 'https://developer.mozilla.org', img: 'https://developer.mozilla.org/favicon-48x48.cbbd161b.png' },
    { title: 'CodePen', url: 'https://codepen.io', img: 'https://blog.codepen.io/wp-content/uploads/2012/06/Button-Fill-Black-Large.png' },
    { title: 'JSFiddle', url: 'https://jsfiddle.net', img: 'https://jsfiddle.net/img/favicon.png' },
    { title: 'Stack Overflow', url: 'https://stackoverflow.com', img: 'https://cdn.sstatic.net/Sites/stackoverflow/Img/favicon.ico' },
    { title: 'Can I use', url: 'https://caniuse.com', img: 'https://caniuse.com/img/favicon-128.png' },
    { title: 'CSS Tricks', url: 'https://css-tricks.com', img: 'https://css-tricks.com/favicon.ico' },
    { title: 'Google Fonts', url: 'https://fonts.google.com', img: 'https://fonts.gstatic.com/s/i/productlogos/google_fonts/v6/192px.svg' },
    { title: 'Font Awesome', url: 'https://fontawesome.com', img: 'https://fontawesome.com/images/favicon.ico' },
    { title: 'GitHub', url: 'https://github.com', img: 'https://github.githubassets.com/favicons/favicon.svg' }
];

function renderAdvancedWebToolsBar() {
    let bar = document.getElementById('advanced-web-tools-bar');
    if (!bar) return;
    bar.innerHTML = advancedWebTools.map(tool =>
        `<a href="${tool.url}" target="_blank" title="${tool.title}" style="display:inline-block;"><img src="${tool.img}" alt="${tool.title}" style="height:28px;vertical-align:middle;margin:0 4px;"></a>`
    ).join('');
}
document.addEventListener('DOMContentLoaded', renderAdvancedWebToolsBar);

// Dynamic background color changer for the body
const bgColors = [
    '#ff1744', // Red
    '#ffd600', // Yellow
    '#212121', // Black
    '#1976d2', // Blue
    '#00e676', // Green
    '#ff9100', // Orange
    '#d500f9', // Purple
    '#00bcd4', // Cyan
    '#ff80ab', // Pink
    '#aeea00', // Lime
    '#ff3d00', // Deep Orange
    '#8d6e63', // Brown
    '#c51162', // Magenta
    '#00c853', // Emerald
    '#fbc02d', // Gold
    '#3949ab', // Indigo
    '#b2ff59', // Light Green
    '#e040fb', // Violet
    '#ffeb3b', // Bright Yellow
    '#607d8b'  // Blue Grey
];
let bgIndex = 0;
function changeBgColor() {
    document.body.style.background = bgColors[bgIndex];
    bgIndex = (bgIndex + 1) % bgColors.length;
}
setInterval(changeBgColor, 10000);
window.addEventListener('DOMContentLoaded', changeBgColor);

// Animated gradient background with slow transitions and different directions
const gradients = [
    'linear-gradient(120deg,rgb(251, 8, 8),rgb(255, 208, 0),)',
    'linear-gradient(240deg, #1976d2, #00e676)',
    'linear-gradient(60deg, #ff9100, #d500f9)',
    'linear-gradient(180deg, #00bcd4, #ff80ab)',
    'linear-gradient(300deg, #aeea00, #ff3d00)',
    'linear-gradient(90deg, #8d6e63, #c51162)',
    'linear-gradient(45deg, #00c853, #fbc02d)',
    'linear-gradient(135deg, #3949ab, #b2ff59)',
    'linear-gradient(210deg, #e040fb, #ffeb3b)',
    'linear-gradient(270deg, #607d8b, #ff1744)'
];
let gradIndex = 0;
function changeGradientBg() {
    document.body.style.transition = 'background 3s cubic-bezier(0.4,0,0.2,1)';
    document.body.style.background = gradients[gradIndex];
    gradIndex = (gradIndex + 1) % gradients.length;
}
setInterval(changeGradientBg, 10000);
window.addEventListener('DOMContentLoaded', changeGradientBg);




![image](https://github.com/user-attachments/assets/2eb3694e-a460-4a8d-b0df-4cfe701b11d7)

