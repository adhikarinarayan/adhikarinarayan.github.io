---
# the default layout is 'page'
icon: fas fa-info-circle
order: 3
---

<head>
    <style>
        body {
            font-family: sans-serif;
            line-height: 1.6;
            margin: 20px;
            background-color: #f8f8f8;
             color: #333;
              max-width: 800px; /* Added max-width for better readability */
            margin-left: auto;
             margin-right: auto; /* Centers horizontally */
             padding: 30px; /* Added padding to provide spacing for content */
               background-color: #fff;
               border-radius: 8px;
              box-shadow: 0 2px 5px rgba(0,0,0,0.1);

        }
        .content {
            padding: 10px;
        }

        blockquote {
             font-style: italic;
             border-left: 4px solid #4CAF50;
            margin: 20px 0;
             padding: 15px;
             background-color: #f9f9f9;

        }

       blockquote p{
          margin: 0;
          color: red;
        }


        p {
            margin-bottom: 15px;
        }

        a {
            color: #007bff;
           text-decoration: none;
        }

      a:hover {
          text-decoration: underline;
      }
         /* icon section */
      .icon-container {
          display: flex;
           align-items: center;
           justify-content: flex-start;
             margin-bottom: 10px;
        }

      .icon-container i {
          font-size: 1.2em;
           margin-right: 5px;
            color:#333;
      }

    </style>
</head>
<body>
     <div class="icon-container">
         <i class="fas fa-info-circle"></i> <!-- Icon -->
      </div>
    <div class="content">
        <blockquote>
            <p>"When something is important enough, you do it even if the odds are not in your favor."</p>
        </blockquote>
        <p>
            I am an AI Engineer with a passion for leveraging Natural Language Processing (NLP) and Large Language Models (LLMs) to create impactful solutions, particularly in areas such as Retrieval-Augmented Generation (RAG) and AI agents. I hold a Master’s degree in Physics from IIT Ropar and a Bachelor’s degree in Physics, Chemistry, and Mathematics from Kumaun University. Currently, I am contributing to innovative NLP projects at a stealth startup, focusing on document analysis and processing, as well as building intelligent AI agents.
        </p>
        <p>
            Additionally, I lead the Omdena Dehradun chapter, where I collaborate with others to develop AI solutions for social impact, bringing people together to create innovative solutions for the greater good using AI.
        </p>
        <p>
            Beyond my professional work, I enjoy exploring the philosophical implications of AI, discussing books and music, and engaging in sports like cricket and volleyball. I also share my work and insights through presentations (slides available <a href="https://github.com/adhikarinarayan/talks">here</a>). I'm always open to connecting with fellow AI enthusiasts and researchers to discuss new ideas and potential collaborations. Feel free to reach out!
        </p>
    </div>

   <script>
          // Fallback for Font Awesome if it doesn't load
         document.addEventListener('DOMContentLoaded', function () {
           const iconElement = document.querySelector('.icon-container i');
               if (iconElement && iconElement.classList.contains('fas')) {
               const span = document.createElement('span');
               span.textContent = '\u24D8'; // Unicode for info circle 'ℹ️'
               span.style.display = 'inline-block'
              iconElement.parentNode.replaceChild(span, iconElement);
          }
         });
  </script>
</body>
