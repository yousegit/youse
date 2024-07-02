<script>
    import Counter from './Counter.svelte';
    import welcome from '$lib/images/svelte-welcome.webp';
    import welcome_fallback from '$lib/images/svelte-welcome.png';
</script>

<section id="about-me">
    <div class="about-container">
        <div class="left-section">
            <div class="image-container">
                <img src="/betterpic.JPG" alt="Yousef" class="profile-image" loading="lazy" />
            </div>
            <h1>Hi, I'm Yousef</h1>
            <h2>Highschool Student</h2>
        </div>
        <div class="about-content">
            <p>
                Hello! My name is Yousef, and I have always been deeply interested in technology. Over the years, I have completed several internships and taken advanced classes such as AP Computer Science Principles and AP Computer Science A. These experiences have not only deepened my passion for technology but also equipped me with valuable skills. As a high school senior living in Zurich, Switzerland, I look towards the future with plans to study computer science at university to further my knowledge and contribute to this exciting field.


            </p>
            
            <div class="contact-me">
                <h2>Contact Me</h2>
                <a href="https://www.linkedin.com/in/yousef-al-saleh-998564272/" target="_blank">
                    <img src="/linkedin.png" alt="LinkedIn" class="linkedin-logo" loading="lazy" />
                </a>
                <a href="mailto:yousef@yousefully.com" target="_blank">
                    <img src="/email.png" alt="Email" class="email-logo" loading="lazy" />
                </a>
            </div>
        </div>
    </div>
</section>

<section id="skills">
    <div class="skills-container">
        <h2>Skills</h2>
        <ul>
            <li>JavaScript</li>
            <li>Python</li>
            <li>Java</li>
            <li>HTML & CSS</li>
            <li>Adobe Premiere Pro</li>
            <li>Critical thinking</li>
            <li>Teamwork</li>
            <li>Problem-solving</li>
        </ul>
    </div>
</section>

<section id="interests">
    <div class="interests-container">
        <h2>Interests</h2>
        <p>I'm a member of the varsity swim and cross-country teams at school, and I enjoy skiing, playing sports, and hanging out with friends. I love picking up new hobbies, and in my free time, I explore new tech, code personal projects, and keep up with streetwear trends. Living in Zurich is amazing, and I make the most of the beautiful outdoor spots around Switzerland.</p>
    </div>
</section>

<section id="timeline">
    <div class="timeline-container">
        <h2>My Journey</h2>
        <div class="timeline-line"></div> <!-- Added line here -->
        <ul>
            <li>
                <span>2022</span>
                <div class="content">
                    <p>Took first computer science class (AP Computer Science Principles)</p>
                </div>
            </li>
            <li>
                <span>2023</span>
                <div class="content">
                    <p>Completed AP Computer Science A</p>
                    <p>Completed internship at <a href="https://www.hebbian.ch" target="_blank">Hebbian</a></p>
                </div>
            </li>
            <li>
                <span>2024</span>
                <div class="content">
                    <p>Completed internship at <a href="https://www.thomsonreuters.com" target="_blank">Thomson Reuters</a></p>
                    <p>Started interning at <a href="https://www.liip.ch" target="_blank">Liip AG</a></p>
                </div>
            </li>
            <li>
                <span>2025</span>
                <div class="content">
                    <p>Expected to graduate in the spring</p>
                </div>
            </li>
        </ul>
    </div>
</section>

<style lang="css">
    body {
    font-family: sans-serif;
    margin: 0;
    background-color: #E0DFE0;
    min-height: 100vh;
    scroll-behavior: smooth;
}

header {
    display: flex;
    justify-content: center;
    align-items: center;
    background: url('colores.png') no-repeat center center/cover;
    padding: 0;
    box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
    position: sticky;
    width: 100%;
    top: 0;
    z-index: 1000;
}

nav {
    display: flex;
    justify-content: center;
    align-items: center;
    width: auto;
    background-color: rgba(224, 223, 224, 0.8);
    padding: 1em 0;
    box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
    backdrop-filter: blur(5px);
}

ul {
    display: flex;
    justify-content: center;
    align-items: center;
    list-style: none;
    margin: 0;
    padding: 0;
}

li {
    position: relative;
    margin: 0 2em;
}

li[aria-current='page']::before {
    --size: 6px;
    content: '';
    width: 0;
    height: 0;
    position: absolute;
    top: 0;
    left: calc(50% - var(--size));
    border: var(--size) solid transparent;
    border-top: var(--size) solid var(--color-theme-1);
}

nav a {
    display: flex;
    align-items: center;
    padding: 0 1rem;
    color: var(--color-text);
    font-weight: 600;
    font-size: 1rem;
    text-transform: uppercase;
    letter-spacing: 0.1em;
    text-decoration: none;
    transition: color 0.3s ease, transform 0.3s ease;
}

nav a:hover {
    color: var(--color-theme-1);
    transform: scale(1.1) translateY(-3px);
    text-shadow: 2px 2px 8px rgba(0, 0, 0, 0.2);
}

#about-me {
    display: flex;
    justify-content: center;
    align-items: center;
    padding: 2em 1em;
    margin-top: 4em;
    background-color: #E0DFE0;
}

.about-container {
    display: flex;
    align-items: flex-start;
    max-width: 1500px;
    width: 100%;
    margin-left: 0em;
    opacity: 0;
    transform: translateY(20px);
    animation: fadeInUp 1s forwards;
}

@keyframes fadeInUp {
    to {
        opacity: 1;
        transform: translateY(0);
    }
}

.left-section {
    display: flex;
    flex-direction: column;
    align-items: center;
    margin-right: 2em;
    transform: translateY(-40px);
}

.image-container {
    width: 500px;
    height: 500px;
    overflow: hidden;
    border-radius: 40px;
    margin-bottom: 0.5em;
    box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
    transition: transform 0.3s ease, box-shadow 0.3s ease;
}

.image-container:hover {
    transform: scale(1.05);
    box-shadow: 0 8px 16px rgba(0, 0, 0, 0.2);
}

.profile-image {
    width: 100%;
    height: 100%;
    object-fit: cover;
}

.left-section h1 {
    font-size: 3em;
    margin: 0.2em 0;
    text-shadow: 2px 2px 8px rgba(0, 0, 0, 0.2);
}

.left-section h2 {
    font-size: 1.5em;
    color: gray;
    margin: 0;
	transform: translateY(-8px);
    text-shadow: 1px 1px 4px rgba(0, 0, 0, 0.2);
}

.about-content {
    flex: 1;
    padding-left: 2em;
}

.about-content p {
    font-size: 1.3em;
    line-height: 1.6;
    margin-top: 3em;
    text-shadow: 1px 1px 4px rgba(0, 0, 0, 0.1);
}

.contact-me {
    margin-top: 6.7em;
    text-align: center;
}

.contact-me h2 {
    font-size: 2em;
    margin-bottom: 0.5em;
}

.linkedin-logo,
.email-logo {
    width: 64px;
    height: 64px;
    transition: transform 0.3s ease, filter 0.3s ease;
    margin: 0 1em;
}

.linkedin-logo:hover,
.email-logo:hover {
    transform: rotate(360deg) scale(1.2);
    filter: brightness(1.2);
}

#skills {
    padding: 2em 1em;
    background-color: #f7f7f7;
    text-align: center;
}

.skills-container {
    max-width: 1000px;
    margin: 0 auto;
}

.skills-container h2 {
    font-size: 2.5em;
    margin-bottom: 1em;
}

.skills-container ul {
    list-style: none;
    padding: 0;
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
}

.skills-container li {
    background-color: #e0e0e0;
    margin: 0.5em;
    padding: 0.5em 1em;
    border-radius: 5px;
    outline: 2px solid #d8d4d4;
    transition: transform 0.3s ease, box-shadow 0.3s ease, outline-color 0.3s ease;
}

.skills-container li:hover {
    transform: scale(1.05);
    box-shadow: 0 8px 16px rgba(0, 0, 0, 0.2);
    outline-color: #007BFF; /* Change to your desired hover color */
}


#interests {
    padding: 2em 1em;
    background-color: #e0e0e0;
    text-align: center;
}

.interests-container {
    max-width: 1000px;
    margin: 0 auto;
}

.interests-container h2 {
    font-size: 2.5em;
    margin-bottom: 1em;
}

#timeline {
    padding: 2em 1em;
    background-color: #f7f7f7;
    text-align: center;
}

.timeline-container {
    max-width: 1000px;
    margin: 0 auto;
    position: relative;
}


.timeline-container h2 {
    font-size: 2.5em;
    margin-bottom: 1em;
	
}

.timeline-container ul {
    list-style: none;
    padding: 0;
    display: flex;
    flex-direction: row;
    justify-content: center;
	
}

.timeline-container li {
    background-color: #e0e0e0;
    margin: 1em;
    padding: 1.5em; /* Adjust padding as needed */
    border-radius: 5px;
    flex: 1;
    max-width: 250px;
    height: 190px; /* Fixed height */
    display: flex;
    flex-direction: column;
    justify-content: flex-start; /* Align items to the top */
    align-items: center;
    text-align: center; /* Center text inside the box */
    outline: 2px solid #5A5A5A; /* Example: 4px width, red color */
    transition: transform 0.3s ease, box-shadow 0.3s ease, outline-color 0.3s ease;
}

.timeline-container li:hover {
    transform: scale(1.05);
    box-shadow: 0 8px 16px rgba(0, 0, 0, 0.2);
    outline-color: #007BFF; /* Change to your desired hover color */
}



.timeline-container li p {
    margin-top: 0.5em; /* Adjust margin as needed */
    text-align: center; /* Center text inside paragraphs */
}

.timeline-container span {
    font-weight: bold;
    display: block;
    margin-bottom: 1em; /* Adjust margin as needed */
    text-align: center; /* Center text inside span */
}

/* New styles for hyperlinks */
a {
    color: #007BFF; /* Change this to your desired color */
    text-decoration: none; /* Optional: remove underline */
}

a:hover {
    color: #cc00ff; /* Change this to your desired hover color */
    text-decoration: underline; /* Optional: add underline on hover */
}

a:active {
    color: #0056b3; /* Change this to your desired active color */
}

a:visited {
    color: #0056b3; /* Change this to your desired visited color */
}

#projects {
    display: flex;
    justify-content: center;
    align-items: center;
    padding: 2em 1em;
    background-color: #E0DFE0;
    min-height: 50vh;
}

.projects-container {
    text-align: center;
}

.projects-container h1 {
    font-size: 2.5em;
    color: gray;
    text-shadow: 1px 1px 4px rgba(0, 0, 0, 0.1);
}

.divider {
    width: 100%;
    height: 100px;
    background: url('divider.svg') no-repeat center center/contain;
    animation: slideIn 1s ease-out;
}

@keyframes slideIn {
    from {
        transform: translateX(-100%);
        opacity: 0;
    }
    to {
        transform: translateX(0);
        opacity: 1;
    }
}

@media (max-width: 1030px) {
    .about-container {
        flex-direction: column;
        align-items: center;
    }

    .left-section {
        margin-right: 0;
        transform: translateY(0);
    }

    .image-container {
        width: 80%;
        height: auto;
    }

    .left-section h1 {
        font-size: 2em;
    }

    .left-section h2 {
        font-size: 1.2em;
    }

    .about-content {
        padding-left: 0;
        padding-top: 1em;
        text-align: center;
    }

    .about-content p {
        font-size: 1em;
    }

    .contact-me {
        margin-top: 2em;
    }

    .contact-me h2 {
        font-size: 1.5em;
    }

    .linkedin-logo,
    .email-logo {
        width: 40px;
        height: 40px;
    }

    .skills-container h2,
    .interests-container h2,
    .timeline-container h2 {
        font-size: 2em;
    }

    .skills-container ul,
    .timeline-container ul {
        flex-direction: column;
    }

    .skills-container li,
    .timeline-container li {
        width: 80%;
        max-width: none;
    }
}

/* Line CSS */
.timeline-line {
    position: absolute;
    top: 60%;
    left: -4%;
    right: -4%;
    height: 2px;
    background-color: #5A5A5A;
    z-index: 0; /* Ensure the line is behind the boxes */
    transform: translateY(-50%);
    border-radius: 2px; /* Makes the edges rounded */
    box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1); /* Adds a subtle shadow */
}

/* Media query to hide the timeline line on smaller screens */
@media (max-width: 1090px) {
    .timeline-line {
        display: none;
    }
}

</style>
