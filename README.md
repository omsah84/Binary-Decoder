<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<title>Binary Decoder</title>
<style>
    body {
        font-family: 'Arial', sans-serif;
        background-color: #f7f7f7;
        margin: 0;
        padding: 0;
        display: flex;
        justify-content: center;
        /* align-items: center; */
        height: 100vh;
    }

    .container {
        background-color: #fff;
        margin-top: 20px;
        padding: 20px;
        border-radius: 5px;
        box-shadow: 0 2px 5px rgba(0,0,0,0.2);
        width: 40%;
        height: 50vh;
    }

    h1 {
        color: #333;
        text-align: center;
    }

    form {
        display: flex;
        flex-direction: column;
        gap: 10px;
    }

    label {
        font-size: 16px;
        color: #666;
    }

    input[type="text"] {
        padding: 10px;
        border: 1px solid #ddd;
        border-radius: 5px;
        font-size: 16px;
    }

    button {
        padding: 10px 15px;
        background-color: #5cb85c;
        color: white;
        border: none;
        border-radius: 5px;
        cursor: pointer;
        font-size: 16px;
    }

    button:hover {
        background-color: #4cae4c;
    }

    p {
        color: #333;
        font-size: 16px;
        text-align: center;
        margin-top: 20px;
    }
</style>
<script>
// JavaScript version of the decodeBinaryString function
function decodeBinaryString(binaryString) {
    // Define the binary to letter mappings
    const letterMap = {
        ".0": 'A', ".1": 'B', ".2": 'C', ".3": 'D', ".4": 'E', ".5": 'F', ".6": 'G', ".7": 'H', ".8": 'I', ".9": 'J', ".00": 'K', ".01": 'L', ".02": 'M', ".03": 'N', ".04": 'O', ".05": 'P', ".06": 'Q', ".07": 'R', ".08": 'S', ".09": 'T', ".000": 'U', ".001": 'V', ".002": 'W', ".003": 'X', ".004": 'Y', ".005": 'Z'
    };

    const segments = binaryString.split('.');
    let decodedMessage = '';
    const stepBackValues = [];

    // Process each segment
    segments.forEach(segment => {
        if (segment) {
            // Check if the segment contains a step-back indicator
            const pos = segment.indexOf('-');
            if (pos !== -1) {
                // Extract binary code and step-back value
                const binaryCode = segment.substring(0, pos);
                const stepBack = parseInt(segment.substring(pos + 1), 10);
                stepBackValues.push(stepBack); // Store the step-back value

                // Find the corresponding letter for the binary code
                if (letterMap["." + binaryCode]) {
                    decodedMessage += letterMap["." + binaryCode];
                }
            } else {
                // No step-back indicator, simply decode the binary segment
                if (letterMap["." + segment]) {
                    decodedMessage += letterMap["." + segment];
                }
            }
        }
    });

    // Apply the step-back values to the entire decoded message
    decodedMessage = decodedMessage.split('').map((char, i) => {
        let charCode = char.charCodeAt(0) - 'A'.charCodeAt(0);
        stepBackValues.forEach(stepBack => {
            charCode = (charCode - stepBack + 26) % 26;
        });
        return String.fromCharCode('A'.charCodeAt(0) + charCode);
    }).join('');

    return decodedMessage;
}

// Function to handle the form submission
function handleFormSubmit(event) {
    event.preventDefault();
    const binaryString = document.getElementById('binaryString').value;
    const decodedMessage = decodeBinaryString(binaryString);
    document.getElementById('decodedMessage').textContent = `Decoded message: ${decodedMessage}`;
}
</script>
</head>
<body>
<div class="container">
    <h1>Binary Decoder</h1>
    <form onsubmit="handleFormSubmit(event)">
        <label for="binaryString">Encoded message:</label>
        <input type="text" id="binaryString" name="binaryString">
        <button type="submit">Decode</button>
    </form>
    <p id="decodedMessage"></p>
</div>
</body>
</html>
