<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>SRH Student Registration</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            max-width: 800px;
            margin: 0 auto;
            padding: 20px;
            line-height: 1.6;
        }
        .form-group {
            margin-bottom: 15px;
        }
        label {
            display: block;
            margin-bottom: 5px;
            font-weight: bold;
        }
        input[type="text"],
        input[type="email"],
        input[type="number"],
        select,
        textarea {
            width: 100%;
            padding: 8px;
            border: 1px solid #ddd;
            border-radius: 4px;
            margin-bottom: 10px;
        }
        textarea {
            height: 100px;
        }
        .error {
            color: red;
            font-size: 0.9em;
            display: none;
        }
        button {
            background-color: #007bff;
            color: white;
            padding: 10px 20px;
            border: none;
            border-radius: 4px;
            cursor: pointer;
        }
        button:hover {
            background-color: #0056b3;
        }
        .content-section {
            margin-top: 40px;
            padding: 20px;
            background-color: #fff;
            border-radius: 8px;
            box-shadow: 0 2px 4px rgba(0,0,0,0.1);
        }
        .methodology {
            margin: 20px 0;
            padding: 15px;
            background-color: #f8f9fa;
            border-left: 4px solid #007bff;
            border-radius: 4px;
        }
        .methodology h4 {
            color: #2c3e50;
            margin-top: 0;
        }
        .methodology p {
            color: #444;
            line-height: 1.6;
            margin-bottom: 0;
        }
        .content-section h3 {
            color: #2c3e50;
            margin-bottom: 20px;
        }
        .course-topic {
            margin: 20px 0;
            padding: 15px;
            background-color: #f8f9fa;
            border-left: 4px solid #28a745;
            border-radius: 4px;
        }
        .course-topic h4 {
            color: #2c3e50;
            margin-top: 0;
        }
        .course-topic p {
            color: #444;
            line-height: 1.6;
            margin-bottom: 0;
        }
        .technology-point {
            margin: 15px 0;
            padding: 15px;
            background-color: #f8f9fa;
            border-left: 4px solid #17a2b8;
            border-radius: 4px;
        }
        .reasons-list p {
            margin: 10px 0;
            padding-left: 20px;
            position: relative;
        }
        .section-divider {
            margin: 20px 0;
            padding: 10px 0;
        }
        .checkbox-group, .radio-group {
            margin: 10px 0;
        }
        .declaration-section {
            margin-top: 40px;
            padding: 20px;
            background-color: #f8f9fa;
            border-radius: 8px;
            text-align: center;
        }
        .declaration {
            font-weight: bold;
            margin-bottom: 20px;
        }
        .contact-info {
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 10px;
        }
        .contact-info input[type="email"] {
            width: 300px;
            padding: 8px;
            border: 1px solid #ddd;
            border-radius: 4px;
        }
    </style>
</head>
<body>
    <h1>SRH Student Registration</h1>
    
    <form id="studentForm" onsubmit="return validateForm(event)">
        <div class="form-group">
            <label for="firstName">First Name:</label>
            <input type="text" id="firstName" name="firstName" required>
            <div class="error" id="firstNameError">Only alphabetic characters allowed</div>
        </div>

        <div class="form-group">
            <label for="middleInitial">Middle Initial:</label>
            <input type="text" id="middleInitial" name="middleInitial" maxlength="1">
            <div class="error" id="middleInitialError">Only alphabetic character allowed</div>
        </div>

        <div class="form-group">
            <label for="lastName">Last Name:</label>
            <input type="text" id="lastName" name="lastName" required>
            <div class="error" id="lastNameError">Only alphabetic characters allowed</div>
        </div>

        <div class="form-group">
            <label for="matriculation">Matriculation Number:</label>
            <input type="text" id="matriculation" name="matriculation" required>
            <div class="error" id="matriculationError">Only numbers allowed</div>
        </div>

        <div class="form-group">
            <label for="email">Email:</label>
            <input type="email" id="email" name="email" required>
            <div class="error" id="emailError">Please enter a valid email address</div>
        </div>

        <div class="form-group">
            <label for="country">Country:</label>
            <select id="country" name="country" required>
                <option value="">Select a country</option>
                <option value="DE">Germany</option>
                <option value="FR">France</option>
                <option value="UK">United Kingdom</option>
                <option value="US">United States</option>
            </select>
        </div>

        <div class="form-group">
            <label for="startDate">Program Start Date:</label>
            <input type="date" id="startDate" name="startDate" required>
        </div>

        <div class="form-group">
            <label for="program">Graduate Program:</label>
            <select id="program" name="program" required>
                <option value="">Select a program</option>
                <option value="cs">Computer Science</option>
                <option value="ba">Business Administration</option>
                <option value="ds">Data Science</option>
            </select>
        </div>

        <div class="section-divider">
            <label>I've heard this graduate program from:</label>
            <div class="checkbox-group">
                <input type="checkbox" id="media" name="heard_from" value="media">
                <label for="media">Media</label>
            </div>
            <div class="checkbox-group">
                <input type="checkbox" id="ad" name="heard_from" value="ad">
                <label for="ad">Ad</label>
            </div>
            <div class="checkbox-group">
                <input type="checkbox" id="agency" name="heard_from" value="agency">
                <label for="agency">Agency</label>
            </div>
            <div class="checkbox-group">
                <input type="checkbox" id="other" name="heard_from" value="other">
                <label for="other">Other</label>
            </div>
        </div>

        <div class="section-divider">
            <label>When I finish my study, I will:</label>
            <div class="radio-group">
                <input type="radio" id="return" name="future_plan" value="return">
                <label for="return">Return to my country</label>
            </div>
            <div class="radio-group">
                <input type="radio" id="europe_job" name="future_plan" value="europe_job">
                <label for="europe_job">Find a job in Europe</label>
            </div>
            <div class="radio-group">
                <input type="radio" id="practical" name="future_plan" value="practical">
                <label for="practical">Do the practical training and then decide</label>
            </div>
        </div>

        <div class="section-divider">
            <label for="feedback">Feedback for the course:</label>
            <textarea id="feedback" name="feedback" required></textarea>
        </div>

        <button type="submit">Submit</button>
    </form>

    <div class="content-section">
        <h2>SDLC Methodologies Analysis</h2>
        <h3>Among so many SDLC Methodologies the ones that are in the AGILE classification are better. Among AGILE SDLC Methods, I have few suggestions:</h3>
        <div class="methodology">
            <h4>a) Scrum</h4>
            <p>Scrum is one of the most popular Agile methodologies because of its structured yet flexible approach. It divides work into fixed-length iterations called sprints (typically 2-4 weeks), with daily stand-up meetings to track progress. The framework includes specific roles (Scrum Master, Product Owner, Development Team), ceremonies (Sprint Planning, Daily Scrum, Sprint Review, Sprint Retrospective), and artifacts (Product Backlog, Sprint Backlog, Increment). Scrum's emphasis on transparency, inspection, and adaptation makes it particularly effective for complex projects where requirements may evolve.</p>
        </div>

        <div class="methodology">
            <h4>b) Kanban</h4>
            <p>Kanban is a visual approach to Agile development that focuses on continuous delivery while preventing team overload. It uses a board with columns representing different stages of work (To Do, In Progress, Done) to visualize workflow and identify bottlenecks. Kanban's key principles include visualizing work, limiting work in progress (WIP), managing flow, making process policies explicit, and implementing feedback loops. This method is especially useful for teams with a continuous flow of incoming requests and where priorities can change frequently.</p>
        </div>

        <div class="methodology">
            <h4>c) Extreme Programming (XP)</h4>
            <p>Extreme Programming emphasizes technical excellence and customer satisfaction through practices like pair programming, test-driven development (TDD), and continuous integration. XP is particularly valuable for projects requiring high code quality and frequent releases. It includes practices such as simple design, continuous feedback, embracing change, and maintaining a sustainable pace. XP's focus on engineering practices makes it excellent for projects where software quality is critical and requirements change frequently.</p>
        </div>
    </div>

    <div class="content-section">
        <h2>SRH Course Content</h2>
        <h3>In this Software Development and Application course of SRH we learn the following:</h3>
        <div class="course-topic">
            <h4>a) Web Development Fundamentals</h4>
            <p>The course provides comprehensive coverage of essential web technologies including HTML5 for structure, CSS3 for styling, and JavaScript for interactivity. We learn how to create responsive, user-friendly web applications using modern development practices. This includes understanding DOM manipulation, event handling, and creating interactive forms with proper validation.</p>
        </div>

        <div class="course-topic">
            <h4>b) Software Development Life Cycle</h4>
            <p>We explore various SDLC methodologies, with particular emphasis on Agile approaches. This includes understanding project management frameworks, requirements gathering, system design, implementation strategies, testing methodologies, and deployment practices. We learn how to choose and apply the appropriate methodology based on project requirements and constraints.</p>
        </div>

        <div class="course-topic">
            <h4>c) Version Control and Collaboration</h4>
            <p>The course covers modern development workflows using Git for version control, including branching strategies, merge conflict resolution, and collaborative development practices. We learn how to work effectively in teams, manage code repositories, and implement continuous integration/continuous deployment (CI/CD) pipelines.</p>
        </div>

        <div class="course-topic">
            <h4>d) Software Testing and Quality Assurance</h4>
            <p>We learn various testing methodologies including unit testing, integration testing, and end-to-end testing. The course covers test automation, quality assurance practices, debugging techniques, and the importance of code review processes. We also explore tools and frameworks commonly used in modern testing environments.</p>
        </div>
    </div>

    <div class="content-section">
        <h2>CSS Implementation</h2>
        <h3>I have used CSS in this webpage and there are 3 ways to include CSS in a webpage as follows:</h3>
        <div class="technology-point">
            <h4>a) Inline CSS</h4>
            <p>CSS can be applied directly to individual HTML elements using the style attribute. This method is useful for applying unique styles to single elements, though it's generally not recommended for maintaining clean and maintainable code.</p>
        </div>

        <div class="technology-point">
            <h4>b) Internal CSS</h4>
            <p>CSS can be included within the HTML document itself using the style tag in the head section. This method is useful for single-page websites where styles don't need to be shared across multiple pages.</p>
        </div>

        <div class="technology-point">
            <h4>c) External CSS</h4>
            <p>CSS can be placed in a separate file and linked to the HTML document using the link tag. This is the most recommended method as it promotes better organization, maintenance, and reusability of styles across multiple pages.</p>
        </div>

        <h3>The reasons CSS used in a webpage are:</h3>
        <div class="reasons-list">
            <p>1. Enhanced Visual Presentation: CSS allows for complete control over the layout, colors, typography, and overall aesthetic appeal of a webpage.</p>
            <p>2. Improved Maintainability: Separating style from content makes it easier to update and maintain websites, as changes can be made in one place affecting multiple elements.</p>
            <p>3. Better User Experience: CSS enables responsive design, ensuring websites look good and function well across different devices and screen sizes.</p>
        </div>
    </div>

    <div class="content-section">
        <h2>JavaScript Implementation</h2>
        <h3>We also use JavaScript in webpage development. The main reasons are as follows:</h3>
        <div class="technology-point">
            <h4>a) Dynamic Content Updates</h4>
            <p>JavaScript allows for real-time content updates without requiring page reloads, enabling interactive and dynamic user experiences.</p>
        </div>

        <div class="technology-point">
            <h4>b) Form Validation</h4>
            <p>It enables client-side form validation, providing immediate feedback to users and reducing server load.</p>
        </div>

        <div class="technology-point">
            <h4>c) Event Handling</h4>
            <p>JavaScript handles user interactions like clicks, keyboard input, and form submissions, making websites interactive.</p>
        </div>

        <div class="technology-point">
            <h4>d) DOM Manipulation</h4>
            <p>It allows dynamic modification of webpage content and structure through DOM manipulation.</p>
        </div>

        <div class="technology-point">
            <h4>e) AJAX Communications</h4>
            <p>JavaScript enables asynchronous communication with servers, allowing for smooth data updates without page refreshes.</p>
        </div>
    </div>

    <div class="declaration-section">
        <p class="declaration">I've done this project myself and accept the consequences if found other ways.</p>
        <div class="contact-info">
            <label for="contact-email">You can reach me at:Gsanchit2299@gmail.com </label>
