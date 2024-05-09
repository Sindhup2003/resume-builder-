# resume-builder-
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Resume Builder</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 0;
            padding: 0;
        }

        .container {
            max-width: 800px;
            margin: 0 auto;
            padding: 20px;
        }

        fieldset {
            margin-bottom: 20px;
        }

        legend {
            font-weight: bold;
        }

        input[type="text"] {
            width: 100%;
            padding: 8px;
            margin-top: 4px;
            margin-bottom: 12px;
            box-sizing: border-box;
        }

        button {
            padding: 10px 20px;
            background-color: #e2eaf9;
            color: #f697ee;
            border: none;
            cursor: pointer;
        }

        button:hover {
            background-color: #3093fd;
        }
    </style>
</head>
<body>
    <div class="container">
        <h1>Resume Builder</h1>
        
        <!-- Template selection -->
        <div class="template-selection">
            <label for="templateSelect">Select a Template:</label>
            <select id="templateSelect">
                <option value="template1">Template 1</option>
                <option value="template2">Template 2</option>
                <!-- Add more template options as needed -->
            </select>
        </div>

        <!-- Form for user input -->
        <form id="resumeForm">
            <!-- Personal Information -->
            <fieldset>
                <legend>Personal Information</legend>
                <label for="fullName">Full Name:</label>
                <input type="text" id="fullName" name="fullName" required>

                <label for="phone number">phone number:</label>
                <input type="text" id="phone number" name="phone number" required>
 
                <label for="Email">email:</label>
                <input type="text" id="email" name="email" required>

                <!-- Add more fields for personal information as needed -->
            </fieldset>
            
            <!-- Education -->
            <fieldset>
                <legend>Education</legend>
                <label for="education">education:</label>
                <input type="text" id="education" name="education" required>


                <!-- Education input fields -->
            </fieldset>
            
            <!-- Work Experience -->
            <fieldset>
                <legend>Work Experience</legend>
                <label for="experience">experience:</label>
                <input type="text" id="experience" name="experience" required>

                <!-- Work experience input fields -->
            </fieldset>
            
            <!-- Skills -->
            <fieldset>
                <legend>Skills</legend>
                <label for="skills">skills:</label>
                <input type="text" id="skills" name="skills" required>

                <!-- Skills input fields -->
            </fieldset>
            
            <!-- Submit button -->
            <button type="submit">Generate Resume</button>
        </form>

        <!-- Display area for generated resume -->
        <div id="resumePreview">
            <!-- Resume preview will be displayed here -->
        </div>

        <!-- Download buttons -->
        <div id="downloadButtons">
            <button id="downloadPDF">Download PDF</button>
            <button id="downloadWord">Download Word</button>
        </div>
    </div>

    <script>
        document.getElementById('resumeForm').addEventListener('submit', function(event) {
            event.preventDefault();
            
            // Retrieve form data
            const formData = new FormData(event.target);
            
            // Process form data and generate resume HTML
            let resumeHTML = <h2>${formData.get('fullName')}</h2>;
            // Add more HTML for other form fields
            
            // Display generated resume
            document.getElementById('resumePreview').innerHTML = resumeHTML;
        });

        
    document.getElementById('downloadPDF').addEventListener('click', function() {
        const container = document.querySelector('.container');

        // Create HTML content from container
        const htmlContent = container.innerHTML;

        // Create a new Blob object with HTML content
        const blob = new Blob([htmlContent], { type: 'application/pdf' });

        // Create a download link
        const link = document.createElement('a');
        link.href = URL.createObjectURL(blob);
        link.download = 'resume.pdf';

        // Append the link to the document body and trigger the download
        document.body.appendChild(link);
        link.click();
 
        // Clean up
        document.body.removeChild(link);

        });
        // Download Word button click handler
        document.getElementById('downloadWord').addEventListener('click', function() {
            // Implement Word download functionality
            alert('Word download functionality to be implemented.');
        });
    </script>
</body>
</html>

