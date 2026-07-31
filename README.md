# EgoMem : Egocentric-Visual-Memory-Retrieval-System


> A proof-of-concept AI system for natural language search across multiple egocentric (first-person) videos using OpenCLIP and FAISS.

---
![Uploading EgoGen - Egocentric Visual Memory Retrieval System.png…]()

---
## Overview

The Egocentric Visual Memory Retrieval System enables semantic search over multiple first-person videos. Instead of manually watching long videos, users can enter a natural language query such as:

- "person cooking"
- "making breakfast"
- "working on laptop"
- "walking outdoors"

The system retrieves the most semantically relevant frame along with its source video and timestamp.

This project explores the core concepts behind visual memory systems by combining vision-language embeddings with efficient vector search.

---

## Features

- Multi-video indexing
- Egocentric (first-person) video support
- Natural language semantic search
- OpenCLIP vision-language embeddings
- FAISS vector similarity search
- Automatic frame extraction
- Timestamp retrieval
- Metadata management for each frame
- Fast nearest-neighbor retrieval

---

## System Pipeline

```
Multiple MP4 Videos
        │
        ▼
Frame Extraction (OpenCV)
        │
        ▼
Frame Metadata Generation
(Video • Frame Number • Timestamp)
        │
        ▼
OpenCLIP Image Embeddings
(512-dimensional vectors)
        │
        ▼
FAISS Vector Index
        │
        ▼
Natural Language Query
        │
        ▼
OpenCLIP Text Embedding
        │
        ▼
Similarity Search
        │
        ▼
Top Matching Frame
+
Source Video
+
Timestamp
```

---

## Tech Stack

- Python
- Google Colab
- OpenCV
- OpenCLIP (ViT-B/32, LAION-2B)
- FAISS
- NumPy
- Pillow
- Matplotlib

---

## Dataset

The project uses multiple short egocentric (first-person) videos representing everyday activities, including:

- Preparing breakfast
- Cooking tomato garlic rice
- Making a natural pink beverage
- Working on a laptop
- Walking and hiking

---

## How It Works

### Step 1
Upload multiple MP4 videos.

### Step 2
Extract frames from each video at fixed intervals using OpenCV.

### Step 3
Store metadata for every extracted frame, including:
- Frame filename
- Source video
- Frame number
- Timestamp

### Step 4
Generate image embeddings using OpenCLIP.

### Step 5
Store all embeddings inside a FAISS vector index.

### Step 6
Convert a user's natural language query into a text embedding.

### Step 7
Perform semantic similarity search using FAISS.

### Step 8
Return:
- Top matching frame
- Source video
- Timestamp

---

## Example Queries

- person cooking
- making breakfast
- tomato garlic rice
- working on laptop
- walking outdoors
- hiking
- beverage preparation

---

## Challenges Faced

- Selecting an appropriate frame sampling interval for efficient retrieval.
- Managing metadata across multiple videos.
- Handling dependency installation and runtime resets in Google Colab.
- Organising embeddings and timestamps for accurate retrieval.

---

## Limitations

- Frame-level retrieval rather than full temporal reasoning.
- Retrieval quality depends on the diversity of the indexed videos.
- OpenCLIP performs semantic similarity search and may return the closest available match when an exact concept is not present.

---

## Future Improvements

- Clip-level temporal retrieval
- Visual Question Answering (VQA)
- Persistent visual memory across long videos
- Event-level retrieval instead of individual frames
- Integration with multimodal memory architectures

---

## Project Outcome

This project demonstrates an end-to-end visual retrieval pipeline capable of indexing multiple egocentric videos and retrieving semantically relevant frames using natural language. It combines computer vision, vision-language models, and vector search into a scalable proof-of-concept for visual memory retrieval.

---

## Author

**Designed, Developed, and Documented by**

**Syeda Alia Samia**
