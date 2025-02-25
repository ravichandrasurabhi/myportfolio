<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Ravi's Portfolio</title>
    <link
      href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;600&display=swap"
      rel="stylesheet"
    />
    <link
      href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css"
      rel="stylesheet"
    />

    <link rel="stylesheet" type="text/css" href="./style.css" />
  </head>
  <body>
    <div class="container">
      <!-- Navbar -->
      <div class="navbar">
        <a
          href="#"
          class="logo"
          style="font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif"
          >Ravi Chandra Surabhi</a
        >
        <ul class="nav-links">
          <!-- <li><a href="#home">Home</a></li> -->
          <li><a href="#experience-section">Experience</a></li>
          <li><a href="#footer">Contact</a></li>
        </ul>
      </div>
      <!-- Bio Section (Card layout) -->
      <div class="bio-card" style="margin-top: 60px">
        <img src="./assets/profile.jpg" alt="Profile Picture" />
        <div class="bio-text">
          <h2>Ravi Chandra Surabhi</h2>
          <p>Senior Quality Engineer | AI Transformation </p>
          <div class="divider"></div>
          <p>
            Hello! I’m Ravi, a passionate software engineer with a passion for delivering high-quality software solutions with around 8 years of professional experience. I have strong skillset in automation testing and a wide array of tools & methodologies. 
          </p>
          <!-- Download Resume Button -->

          <a
            href="./assets/updated_Resume.pdf"
            target="_blank"
            download="Ravi_Resume.pdf"
            class="download-btn"
            style="
              padding: 12px 30px;
              font-size: 16px;
              color: #fff;
              background-color: #4caf50;
              text-decoration: none;
              border-radius: 30px;
              border: 2px solid #36a039;
              transition: all 0.3s ease-in-out;
              box-shadow: 0px 4px 8px rgba(0, 0, 0, 0.1);
              display: inline-block;
              text-align: center;
            "
            onmouseover="this.style.backgroundColor='#fff'; this.style.color='black'; this.style.boxShadow='0px 6px 10px rgba(0, 0, 0, 0.2)';"
            onmouseout="this.style.backgroundColor='#36a039'; this.style.color='#fff'; this.style.boxShadow='0px 4px 8px rgba(0, 0, 0, 0.1)';"
          >
            Download Resume
          </a>

          <!-- Social Media Links -->
        </div>
      </div>

      <!-- Scroll to Experience Icon -->
      <div class="scroll-to-experience" id="scroll-to-exp">
        <i class="fas fa-arrow-down"></i>
        <h3>see experience</h3>
      </div>

      <!-- Experience Section with Stepper -->
      <div class="experience" id="experience-section">
        <h2>Experience</h2>

        <!-- Stepper Container -->
        <div class="stepper-container">
          <div class="step" data-step="1">2017</div>
          <div class="step" data-step="2">2018</div>
          <div class="step" data-step="3">2019</div>
          <div class="step" data-step="4">2020</div>
          <div class="step" data-step="5">2021</div>
          <div class="step" data-step="6">2022</div>
          <div class="step" data-step="7">2023</div>                 
          <div class="step active" data-step="8">2024</div>
          <div class="step" id="mobile-view" data-step="9">2025</div>
        </div>

        <!-- Progress Bar -->
        <div class="stepper-progress">
          <div class="active-bar" style="width: 20%"></div>
        </div>

       

    <!-- Footer -->

    <footer id="footer">
      <h3 style="margin-bottom: 2%">
        Contact Info:
        <hr style="border: 3px solid #4caf50" />
      </h3>

      <!-- Footer grid container -->
      <div class="footer-grid">
        <!-- Social media links with icons and text (in one column) -->
        <div class="socials">
          <div class="social-item">
            <a
              href="https://www.linkedin.com/in/ravichandrasurabhi"
              target="_blank"
              class="fab fa-linkedin"
            ></a>
            <span>LinkedIn</span>
          </div>
          <div class="social-item">
            <a
              href="https://github.com/ravichandrasurabhi"
              target="_blank"
              class="fab fa-github"
            ></a>
            <span>GitHub</span>
          </div>
        </div>

        <!-- Contact details (email and phone) (in another column) -->
        <div class="contact-info">
          <div class="contact-item">
            <i class="fas fa-envelope"></i>
            <a href="mailto:ravichandrasurabhi@gmail.com">ravichandrasurabhi@gmail.com</a>
          </div>
          <div class="contact-item">
            <i class="fas fa-phone-alt"></i>
            <a href="tel:+19">NA</a>
          </div>
        </div>
      </div>
    </footer>

    <!-- JavaScript to handle the scroll functionality -->
    <script>
      document
        .getElementById("scroll-to-exp")
        .addEventListener("click", function () {
          document.getElementById("experience-section").scrollIntoView({
            behavior: "smooth",
          });
        });

      // Handle stepper clicks
      const steps = document.querySelectorAll(".step");
      const experienceDetails = document.querySelectorAll(
        ".experience-details"
      );
      const activeBar = document.querySelector(".active-bar");

      steps.forEach((step) => {
        step.addEventListener("click", () => {
          const stepNumber = step.getAttribute("data-step");

          // Remove active class from all steps and details
          steps.forEach((s) => s.classList.remove("active"));
          experienceDetails.forEach((d) => d.classList.remove("active"));

          // Add active class to clicked step and corresponding experience details
          step.classList.add("active");
          document
            .querySelector(`.experience-details[data-step="${stepNumber}"]`)
            .classList.add("active");

          // Update progress bar
          const width = (stepNumber - 1) * 33.33; // For 4 steps, each step is 33.33%
          activeBar.style.width = `${width}%`;
        });
      });
    </script>
  </body>
</html>
