# party-video-metadata
Build an iOS Xcode Swift UI app that retrieves metadata from a streaming service based on either a video ID or a video title.

📺 Streaming Metadata Fetcher (iOS – SwiftUI)
Overview
This project is an iOS SwiftUI application that retrieves video metadata from a streaming service using a non-public internal API.
The API was reverse-engineered by inspecting network requests made by the streaming service’s web player, without using any public APIs or API keys.
The application demonstrates how internal APIs used by real-world streaming platforms can be identified and consumed to fetch metadata such as title, description, duration, author, and image URLs.

Key Requirements (How This Project Meets Them) - 

✅ Non-Public API Usage
No public APIs (e.g. YouTube Data API, TMDB, IMDB) are used.
No API keys are required.
The app replicates the same internal request used by the streaming service’s own web client.

✅ Reverse Engineering
The API endpoint and request payload were identified by inspecting network traffic in browser developer tools.
The app reproduces this request using URLSession.

✅ Metadata Retrieval
The app fetches and displays metadata including:
Video title
Description
Duration
Author / Channel name
Thumbnail image URLs
Playback is not required and intentionally not implemented.

**How It Works**
1. Input
The app accepts a video identifier (hard-coded for demonstration purposes, which is allowed by the assignment).
Hard-coding is used to reliably demonstrate a working request at least once, as permitted.

2. Internal API Request
A POST request is sent to the streaming service’s internal metadata endpoint.
The request body includes a client context matching the web player.
The request is performed using Swift Concurrency (async/await) and URLSession.
3. Response Handling
The JSON response is decoded.
Only relevant metadata fields are extracted.
The metadata is displayed in a simple SwiftUI interface.

**Technical Stack**
Language: Swift
UI Framework: SwiftUI
Concurrency: async / await
Networking: URLSession
Architecture: MVVM (lightweight)
Observation: @Observable (modern SwiftUI state management)

**User Interface**
UI is intentionally minimal, as allowed by the assignment.
Metadata is clearly presented using text and image components.
No video playback functionality is included.
