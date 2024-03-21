<p align="center">
  <img width="50%" align="center" alt="Ubos - End-to-End Software Development Platform" src="https://ubos.tech/wp-content/uploads/2023/03/cropped-Group-21015-1.png">
</p>

<h3 align="center">
  <b><a href="https://documentation.ubos.tech/docs/intro">Get Started</a></b>
  •
  <a href="https://community.ubos.tech/">Community</a>
  •
  <a href="https://www.youtube.com/@ubos_tech">Youtube</a>
  •
  <a href="https://discord.com/invite/dt59QaptH2">Discord</a>
  •
  <a href="https://github.com/UBOS-tech">GitHub</a>
  </h3>

<div align="center">
  
  [![Use template](https://ubos.tech/wp-content/uploads/2023/06/download-logo.png)](https://platform.ubos.tech/?templateId=65fb0a9cedcd1b001134d4fd)
  
</div>
    <h1>Speech To Text</h1>

  <p>The Speech to Text template is a powerful tool that leverages advanced speech recognition and natural language processing capabilities to generate accurate textual transcriptions from uploaded audio or video files. This template provides a seamless experience for users, enabling them to effortlessly extract meaningful information from audio-visual content.</p>

  <h2>Node-RED Flow for Image Description using Claude AI</h2>

  <p>
    <img width="860" alt="Знімок екрана 2024-03-20 о 15 50 59" src="https://github.com/UBOS-tech/UBOS-template-Speech-To-Text/assets/76822866/efd24a9a-792c-4a9e-a5ff-b41081a5f949">
  </p>

  <p>This is a Node-RED flow that allows users to send an image and receive a textual description of the image's contents using the Claude AI model from Anthropic. Here's a breakdown of the flow's components:</p>
  
  <ul>
    <li><strong>HTTP Input Node (`/convertSpeech`):</strong> This node listens for incoming HTTP POST requests at the `/convertSpeech` endpoint. It expects the request to include an audio file or a YouTube video URL, along with an OpenAI API key.</li>
    <li><strong>Function Node (`check type`):</strong> This function node determines whether the user has provided an audio file or a YouTube video URL. If a URL is provided, it sets up the necessary parameters for downloading the audio from the video. If a file is provided, it prepares the payload for the OpenAI API request.</li>
    <li><strong>YouTube-YTDL Node:</strong> If a YouTube video URL is provided, this node downloads the audio from the video.</li>
    <li><strong>HTTP Request Node (to OpenAI):</strong> If an audio file is provided, this node sends a POST request to the OpenAI API (`https://api.openai.com/v1/audio/transcriptions`) with the audio file and the necessary headers, including the API key.</li>
    <li><strong>Function Node (`response`):</strong> This function node processes the response from the OpenAI API. If the response status code is 200 (successful), it extracts the transcribed text from the response payload and assigns it to `msg.payload`. If there's an error, it constructs an error message and assigns it to `msg.payload`.</li>
    <li><strong>HTTP Response Node:</strong> This node sends the final response back to the client, containing either the transcribed text or an error message.</li>
  </ul>

  <h2>Key Features</h2>

  ### Audio/Video Upload

The template features a user-friendly interface that allows users to upload audio files in popular formats such as WAV, MP3, FLAC, or provide YouTube video URLs. The uploading process is straightforward and intuitive, ensuring a smooth user experience.

### Text Transcription with Whisper

At the heart of this template lies the powerful Whisper AI model from OpenAI, specifically designed for speech recognition and transcription tasks. Whisper employs advanced machine learning techniques to accurately transcribe audio content into textual form, capturing the spoken words with high fidelity.

### Multiple Language Support

To cater to diverse linguistic needs, the template offers support for multiple languages, allowing users to transcribe audio in various languages and dialects. The available language options are regularly updated to ensure wide coverage and accuracy.

### API Integration

To leverage the Whisper AI model, users need to obtain an OpenAI API key. The template provides clear instructions and guidance on how to acquire and utilize the API key effectively, ensuring secure and seamless integration with the transcription service.

### Fast Processing

Thanks to Whisper's efficient processing capabilities, users can expect quick turnaround times for transcribing audio files or videos. This feature ensures a smooth and responsive user experience, minimizing wait times and enabling users to access textual insights from audio-visual content promptly.

### Accuracy and Reliability

Whisper is trained on vast datasets and continuously updated to maintain high accuracy and reliability in transcribing speech across various domains, accents, and noise conditions. Users can trust the quality of the outputted text, ensuring that the transcriptions faithfully capture the spoken content.

### Customization Options

The template offers various customization options, allowing users to fine-tune the output according to their specific requirements. This includes adjusting parameters such as language settings, formatting options, and specific areas of focus, ensuring that the transcriptions align with the user's needs.

### Benefits

The Speech-to-Text template empowers users with a robust and efficient solution for extracting valuable textual information from audio-visual content. Whether for accessibility purposes, content analysis, data mining, or simply capturing spoken words in written form, this template offers a comprehensive and user-friendly experience. By leveraging the advanced capabilities of the Whisper AI model, users can unlock the hidden potential of their audio-visual data and transform it into actionable and meaningful textual information.
  
![FireShot Capture 017 - Speech To Text - speech2text-ui-65a79fff4632651100000001 ubos tech](https://github.com/UBOS-tech/UBOS-template-Speech-To-Text/assets/76822866/d47fe090-05d1-4640-ac80-c1c737b752ad)


