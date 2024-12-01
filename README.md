document.getElementById('submit').addEventListener('click', function() {
    let score = 0;
    let totalQuestions = 6;

    // Define correct answers
    const correctAnswers = {
        q1: 'A',
        q2: 'B',
        q3: 'A',
        q4: 'B',
        q5: 'B',
        q6: 'D'
    };

    // Loop through each question and check the selected answers
    for (let i = 1; i <= totalQuestions; i++) {
        let selectedOption = document.querySelector(`input[name="q${i}"]:checked`);

        // If an answer is selected
        if (selectedOption) {
            if (selectedOption.value === correctAnswers[`q${i}`]) {
                score++;
            }
        }
    }

    // Display the result
    let resultMessage = `You scored ${score} out of ${totalQuestions}.`;
    document.getElementById('results').innerText = resultMessage;
});
