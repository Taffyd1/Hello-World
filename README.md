<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Travel Planner</title>
    <style>
        /* Basic CSS for layout - we can expand on this later */
        body {
            font-family: sans-serif;
            margin: 20px;
        }
        .input-section, .itinerary-section, .share-section {
            margin-bottom: 20px;
            padding: 15px;
            border: 1px solid #ccc;
            border-radius: 5px;
        }
    </style>
</head>
<body>
    <div class="input-section">
        <h2>Add New Location</h2>
        <label for="location">Location:</label>
        <input type="text" id="location" name="location"><br><br>
        <label for="start-time">Estimated Start:</label>
        <input type="text" id="start-time" name="start-time" placeholder="e.g., YYYY-MM-DD HH:MM"><br><br>
        <label for="end-time">Estimated End:</label>
        <input type="text" id="end-time" name="end-time" placeholder="e.g., YYYY-MM-DD HH:MM"><br><br>
        <button onclick="addLocation()">Add to Itinerary</button>
    </div>

    <div class="itinerary-section">
        <h2>My Travel Itinerary</h2>
        <ul id="itinerary-list">
            </ul>
    </div>

    <div class="share-section">
        <h2>Share Your Plans</h2>
        <p>Here you will be able to generate a link to share your itinerary.</p>
        </div>

    <script>
        // JavaScript will go here to handle adding locations and displaying the itinerary
        function addLocation() {
            const locationInput = document.getElementById('location');
            const startTimeInput = document.getElementById('start-time');
            const endTimeInput = document.getElementById('end-time');
            const itineraryList = document.getElementById('itinerary-list');

            const location = locationInput.value.trim();
            const startTime = startTimeInput.value.trim();
            const endTime = endTimeInput.value.trim();

            if (location) {
                const listItem = document.createElement('li');
                listItem.textContent = `${location} (${startTime} - ${endTime})`;
                itineraryList.appendChild(listItem);

                // Clear input fields after adding
                locationInput.value = '';
                startTimeInput.value = '';
                endTimeInput.value = '';
            } else {
                alert('Please enter a location.');
            }
        }
    </script>
</body>
</html>
