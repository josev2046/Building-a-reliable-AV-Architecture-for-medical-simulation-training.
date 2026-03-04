### Building a reliable AV Architecture for medical simulation training

[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.18864522.svg)](https://doi.org/10.5281/zenodo.18864522)


Back in 2015, my colleague, friend and mentor Dean Offord completed a case study with Panasonic and Panopto in the UK. It covered the deployment of video hardware across university campuses. The hardware has naturally updated since then, but the core principles of a good AV setup remain exactly the same today. Whether you are capturing standard lectures, recording graduation ceremonies, or building out a complex healthcare simulation suite, the foundation does not change.

Inspired by that project, I have mapped out a universal architecture that handles these demands predictably and reliably in Panopto today. It works by breaking the system down into five distinct layers. Thus:

![image](https://github.com/user-attachments/assets/5010258f-7eed-462c-82c7-926ae59fde19)

Let's break that down:

1.  **The Source Layer** Everything starts in a room. To capture a scenario properly, you need a mix of PTZ (pan-tilt-zoom) and fixed cameras. Audio is equally important, so we use a combination of installed room microphones and wearable lapel mics. In medical simulation environments, we also capture the live telemetry from patient monitors directly via an HDMI feed.

2.  **Ingestion and Control** Once the raw video and audio are captured, they need to be processed locally. We run the microphones through an Audio DSP (Digital Signal Processor) to ensure the sound levels are clean and balanced. The cameras and HDMI feeds route into a hardware encoder, such as an Epiphan Pearl or a PC set up for remote recording. Alongside this, an operator uses a standard PTZ joystick controller to adjust camera angles in real time.

3.  **Immediate Review** In many scenarios, particularly medical or tactical simulation, instructors need to review the footage instantly during a debrief. Relying on a cloud connection for this introduces too much delay. Instead, the encoder outputs a low latency feed straight to a local monitor and local solid-state storage. This guarantees the team can play back the recording the second the simulation finishes.

4.  **Cloud Content Management** For wider distribution and long-term archiving, the encoder feeds into a Panopto Remote Recorder. This handles the scheduling and securely pushes the mixed media up to a cloud storage environment. Once uploaded, the platform processes the video so it is ready for video-on-demand playback.

5.  **Distribution** The final step is getting the video to the end users. Panopto acts as the central hub. From here, the content is distributed to large classroom displays, streamed to remote students, or accessed privately by faculty staff for grading and assessment.

Why does this approach work? The reason this setup works as well today as it did back in the day is because it separates the critical functions. If your external network drops, the local recording and immediate review layer will still function perfectly. The hardware encoder manages the difficult processing locally, meaning the cloud platform only has to handle storage and user distribution.

If you are walking a prospective client through a demo, the message is straightforward. Good AV architecture is simply about predictable routing. You capture the action locally, give instructors immediate access to the raw footage, and let the cloud handle the long-term delivery. It is a proven model that scales to fit almost any educational or clinical use case.

#HopeThisHelps

---

**José Velázquez (MA)** is a software architect with over two decades of experience driving digital innovation, consulting for organisations such as the BBC, IBM, and Google. His work sits at the intersection of academia and industry, with a focus on audiovisual preservation, cultural memory, and open, interoperable systems for managing media at scale. Since 2016, José has been an Associate Lecturer on the interdisciplinary Digital Humanities Master's programme at the University of Pablo de Olavide (Seville, Spain.)
