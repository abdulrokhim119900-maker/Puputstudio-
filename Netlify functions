// netlify/functions/api.js

const fetch = require('node-fetch');

exports.handler = async function(event, context) {
    const apiKey = process.env.OPENAI_API_KEY; // Mengakses API Key dari Environment Variables

    const response = await fetch('https://api.openai.com/v1/completions', {
        method: 'POST',
        headers: {
            'Authorization': `Bearer ${apiKey}`,
            'Content-Type': 'application/json'
        },
        body: JSON.stringify({
            prompt: 'Hello, world!',
            max_tokens: 50
        })
    });

    const data = await response.json();

    return {
        statusCode: 200,
        body: JSON.stringify({ message: data.choices[0].text })
    };
};
