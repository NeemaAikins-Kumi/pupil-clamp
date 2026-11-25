# pupil-clamp
Pupil Clamp 👁️

A low-cost, 3D-printed headset that measures mental effort by holding your pupil at a fixed size with PID-controlled light.

🚧 Status: early design phase. This project is just getting started. See the progress log below.

The problem

Your pupils get slightly bigger when your brain works harder. This "effort" response is driven by the locus coeruleus, a small brain region that is one of the first places affected in Alzheimer's disease.

Research has found that people with mild cognitive impairment (MCI) show greater pupil dilation than cognitively normal people while doing the same memory task, even when they get the same score. Their brains are working harder to keep up, and the pupil shows it before test scores drop.

The catch: measuring this usually requires lab equipment that costs thousands of dollars, plus tightly controlled lighting. Light changes pupil size far more than thinking does, so any change in room light can hide the effort signal.

The idea

Instead of just watching the pupil, this project controls it.

An infrared camera watches the eye inside a light-tight, 3D-printed viewer. Infrared is invisible, so it doesn't change pupil size.
Code on a Raspberry Pi measures pupil diameter in real time.
A PID controller adjusts the brightness of a visible LED to hold the pupil at a fixed target size.
When the user does a hard mental task, the brain tries to widen the pupil, so the controller has to add light to resist it.
That extra light is the effort score.

It works like a thermostat: instead of measuring how cold it is outside, you measure how hard the heater is working.

IR camera → Pupil tracker → PID controller → LED brightness
    ↑                                              ↓
    └──────────────────── Eye ←───────────────────┘
                           ↑
                     Mental task
              (tries to widen the pupil)
Research question

Does the controller's light output rise with mental task difficulty in healthy volunteers, and does this effort signal differ between men and women?

Planned build stages

Version/Goals
v0	Simple black test box with an eyehole	Get the camera, pupil tracking, and LED control working
v1	3D-printed one-eye viewer with proper mounts	Stable camera angle and even lighting
v2	Wearable version with a strap	Comfortable, repeatable sessions

Hardware

Parts list coming soon. Planned components include a Raspberry Pi, a small infrared camera, infrared and visible LEDs, and 3D-printed parts in black filament.

Safety
Infrared and visible light levels will be kept well within eye-safety limits.
No fast flashing light (flicker can trigger seizures in some people).
Testing will be done only with healthy volunteers who give informed consent.
No personal data, names, or eye recordings are stored in this repository. Only 
anonymized numbers will ever be shared.

Prior work and acknowledgments

Closed-loop pupil control (the "pupil clamp") was studied by Lawrence Stark in the 1960s. This project applies the idea to measuring cognitive effort with low-cost hardware.
Research linking task-evoked pupil dilation to MCI and Alzheimer's risk:
Granholm et al. (2017), Pupillary Responses as a Biomarker of Early Risk for Alzheimer's Disease, Journal of Alzheimer's Disease
Kremen et al. (2019), pupillary responses and Alzheimer's polygenic risk

Progress log

Date	Update

Nov 2026	Project idea finalized; repository created

License

This project is released under the MIT License.
