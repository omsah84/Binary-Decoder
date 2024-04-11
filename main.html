<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Binary Decoder</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            padding: 20px;
        }
        label {
            font-weight: bold;
        }
        input {
            margin-bottom: 10px;
            padding: 8px;
            width: 100%;
            box-sizing: border-box;
        }
        button {
            padding: 10px 20px;
            background-color: #007bff;
            color: #fff;
            border: none;
            cursor: pointer;
        }
        button:hover {
            background-color: #0056b3;
        }
        #decoded-message {
            margin-top: 20px;
            font-weight: bold;
        }
        #letter-map-container {
            margin-top: 40px;
            border-top: 1px solid #ccc;
            padding-top: 20px;
        }
        #letter-map-container h2 {
            font-size: 18px;
            font-weight: bold;
            margin-bottom: 10px;
        }
        #letter-map-table {
            width: 100%;
            border-collapse: collapse;
        }
        #letter-map-table td {
            border: 1px solid #ccc;
            padding: 4px;
            text-align: left;
            font-size: 14px;
        }
    </style>
</head>
<body>
    <h1>Binary Decoder</h1>
    <div>
        <label for="binary-input">Encoded Message:</label>
        <input type="text" id="binary-input" placeholder="Enter encoded binary message...">
        <button onclick="decodeBinary()">Decode</button>
    </div>
    <div id="decoded-message"></div>

    <div id="letter-map-container">
        <h2>Letter Map</h2>
        <table id="letter-map-table"></table>
    </div>

    <script>
        // Define the letter map
        const letterMap = {
            ".0": 'A', ".1": 'B', ".2": 'C', ".3": 'D', ".4": 'E', ".5": 'F', ".6": 'G', ".7": 'H', ".8": 'I', ".9": 'J',
            ".00": 'K', ".01": 'L', ".02": 'M', ".03": 'N', ".04": 'O', ".05": 'P', ".06": 'Q', ".07": 'R', ".08": 'S', ".09": 'T',
            ".000": 'U', ".001": 'V', ".002": 'W', ".003": 'X', ".004": 'Y', ".005": 'Z'
        };

        // Function to display letter map in table format
        function displayLetterMap() {
            const letterMapTable = document.getElementById('letter-map-table');
            let rowCount = 0;
            let currentRow = null;

            // Iterate over the letterMap object
            for (const binaryCode in letterMap) {
                if (letterMap.hasOwnProperty(binaryCode)) {
                    const letter = letterMap[binaryCode];

                    // Create a new row every 5 entries for compact display
                    if (rowCount % 5 === 0) {
                        currentRow = letterMapTable.insertRow();
                    }

                    // Create a cell for the binary code and letter pair
                    const codeCell = currentRow.insertCell();
                    codeCell.textContent = binaryCode + ': ' + letter;

                    rowCount++;
                }
            }
        }

        // Call the function to display letter map on page load
        displayLetterMap();

        // Function to decode the binary representation string
        function decodeBinaryString(binaryString) {
            let decodedMessage = "";

            // Split the binaryString into segments using '.'
            const segments = binaryString.split('.');

            // Process each segment
            segments.forEach(segment => {
                if (segment) {
                    // Check if the segment contains a step-back indicator
                    const pos = segment.indexOf('-');
                    if (pos !== -1) {
                        // Extract binary code and step-back value
                        const binaryCode = segment.substring(0, pos);
                        const stepBack = parseInt(segment.substring(pos + 1));

                        // Find the corresponding letter for the binary code
                        const letter = letterMap["." + binaryCode];
                        if (letter) {
                            // Calculate the new position after applying step-back
                            let position = letter.charCodeAt(0) - 'A'.charCodeAt(0) - stepBack;
                            if (position < 0) {
                                position += 26; // Wrap around if position is negative
                            }
                            // Convert position back to a character and append to decoded message
                            decodedMessage += String.fromCharCode('A'.charCodeAt(0) + position);
                        }
                    } else {
                        // No step-back indicator, directly decode the binary segment
                        const letter = letterMap["." + segment];
                        if (letter) {
                            decodedMessage += letter;
                        }
                    }
                }
            });

            return decodedMessage;
        }

        // Function to handle decoding when the button is clicked
        function decodeBinary() {
            const binaryInput = document.getElementById('binary-input').value;
            const decodedMessage = decodeBinaryString(binaryInput);

            // Display the decoded message
            const decodedMessageDiv = document.getElementById('decoded-message');
            decodedMessageDiv.textContent = "Decoded message: " + decodedMessage;
        }
    </script>
</body>
