<div align="center">

![KURA Humanoid Robotics header](https://capsule-render.vercel.app/api?type=waving&height=250&color=0:071A2B,55:0B3B53,100:0096A6&text=KURA%20Humanoid%20Robotics&fontColor=EAFBFF&fontSize=42&fontAlignY=38&desc=Humanoid%20football%20%7C%20ROS-based%20development%20%7C%20RoboCup&descAlignY=58&animation=fadeIn)

[![Typing SVG](https://readme-typing-svg.demolab.com?font=JetBrains+Mono&weight=600&size=20&duration=3200&pause=900&color=36D1DC&center=true&vCenter=true&width=900&lines=Humanoid+football+and+robot+behaviour;ROS-based+development+and+field+testing;International+RoboCup+competition+experience)](https://git.io/typing-svg)

![ROS](https://img.shields.io/badge/ROS-071A2B?style=for-the-badge&logo=ros&logoColor=36D1DC)
![C++](https://img.shields.io/badge/C%2B%2B-0B3B53?style=for-the-badge&logo=cplusplus&logoColor=white)
![Python](https://img.shields.io/badge/Python-007C91?style=for-the-badge&logo=python&logoColor=white)
![Linux](https://img.shields.io/badge/Linux-075E54?style=for-the-badge&logo=linux&logoColor=white)
![Humanoid Robotics](https://img.shields.io/badge/Humanoid_Robotics-0096A6?style=for-the-badge&logo=probot&logoColor=white)

**Humanoid football, robot behaviour, ROS-based development, and international RoboCup competition experience.**

</div>

<p align="center">
  <img src="assets/banner/robocup-2026-field-debugging.jpg" width="100%" alt="KURA team members debugging humanoid football robots on the RoboCup 2026 field in South Korea">
</p>

<p align="center"><em>Field debugging and robot preparation at RoboCup 2026 in South Korea.</em></p>

> [!IMPORTANT]
> This is a personal technical portfolio documenting my experience as a KURA team member. It is not the official KURA repository and does not represent the team as a whole.

## About KURA

KURA is the Khalifa University Robotics Team. This repository documents my robotics journey as part of the team, with a focus on humanoid football robots and the engineering work required to prepare them for real competition environments.

My experience included developing, testing, debugging, and deploying software within a ROS-based robotics architecture. This portfolio highlights that work, the technical lessons behind it, and international RoboCup competition experience without publishing the complete team codebase.

<p align="center">
  <img src="assets/team/kura-team-rcap-2025.png" width="100%" alt="KURA team featured after RoboCup Asia-Pacific 2025 in Abu Dhabi">
</p>

<p align="center"><em>KURA at RoboCup Asia-Pacific 2025 in Abu Dhabi.</em></p>

## My role

I contributed to robot behaviour and match readiness: translating high-level football objectives into testable robot actions, evaluating behaviour on the field, diagnosing issues under competition constraints, and supporting integrated deployment.

My confirmed contributions include:

- Robot adjust behaviour
- Robot chase behaviour
- Robot positioning
- Ball tracking and movement behaviour
- Robot decision-making during matches
- Competition debugging and field support
- Robot testing, system integration, and competition deployment

## What I worked on

<table>
  <tr>
    <td width="33%" valign="top"><strong>Behaviour development</strong><br><br>Worked on adjust and chase behaviours that connect ball-related information to purposeful movement decisions.</td>
    <td width="33%" valign="top"><strong>Positioning and tracking</strong><br><br>Contributed to ball tracking, robot positioning, and movement behaviour needed during dynamic match situations.</td>
    <td width="33%" valign="top"><strong>Match decisions</strong><br><br>Supported robot decision-making during matches while respecting the wider integrated system.</td>
  </tr>
  <tr>
    <td width="33%" valign="top"><strong>Testing and integration</strong><br><br>Tested robot behaviour as part of the complete system and helped identify integration issues.</td>
    <td width="33%" valign="top"><strong>Competition debugging</strong><br><br>Investigated field issues under time pressure and used observations to guide practical fixes.</td>
    <td width="33%" valign="top"><strong>Deployment support</strong><br><br>Assisted with competition deployment, field preparation, and hands-on match support.</td>
  </tr>
</table>

## Competition journey

| Year | Competition | Location | Status / result |
|:---:|---|---|---|
| **2025** | **RoboCup Asia-Pacific 2025** | ADNEC, Abu Dhabi, United Arab Emirates | KURA reached the finals and achieved **second place** in both the AdultSize and KidSize Humanoid leagues. |
| **2026** | **RoboCup Asia-Pacific 2026** | Tianjin, China | Result awaiting confirmed information. |
| **2026** | **RoboCup 2026** | South Korea | Result awaiting confirmed information. |

```text
Abu Dhabi, UAE                     Tianjin, China                    South Korea
RCAP 2025                          RCAP 2026                         RoboCup 2026
Finalist · 2nd place               Result pending confirmation      Result pending confirmation
AdultSize + KidSize
      ●──────────────────────────────────●─────────────────────────────────●
     2025                               2026                              2026
```

## Robot behaviour overview

The following flow is a **conceptual portfolio overview**, not KURA's complete architecture, behaviour tree, or private implementation:

```mermaid
flowchart LR
    A[Perception input] --> B[Ball location estimate]
    B --> C[Robot position and orientation]
    C --> D{Behaviour decision}
    D --> E[Adjust action]
    D --> F[Chase action]
    E --> G[Motion command]
    F --> G
    G --> H[Field testing feedback]
    H -. refinement .-> D
```

In practice, reliable behaviour depends on the quality of the input, appropriate decisions for the current situation, safe movement commands, and repeated observation on the field.

## Adjust behaviour

The adjust behaviour helps the robot refine its position and orientation relative to the ball before continuing its action. At a high level, it uses the robot's current relationship to the ball to decide whether a positional or rotational correction is needed, then requests a suitable movement.

The engineering challenge is to make those corrections useful without creating unnecessary oscillation, delay, or loss of alignment. Field testing helps reveal where thresholds, timing, and transitions need further refinement.

## Chase behaviour

The chase behaviour helps the robot approach and follow the ball using suitable movement and positioning decisions. It turns changing ball information into a practical approach action while accounting for where the robot is and how it is oriented.

This behaviour must remain responsive as the ball estimate changes. Testing therefore includes observing approach direction, transition quality, recovery from imperfect positions, and interaction with the wider decision logic.

## ROS-based system overview

My work took place within a ROS-based robotics architecture, where specialised components exchange information and actions. The simplified relationship below describes the context of my contribution without claiming ownership of the complete perception, control, or communication system.

| System context | Portfolio-level description |
|---|---|
| Perception input | Supplies observations such as an estimated ball location. |
| State and positioning | Provides relevant robot position and orientation information. |
| Behaviour logic | Selects an appropriate response, including adjust or chase decisions. |
| Robot control | Converts requested actions into executable robot motion. |
| Feedback and debugging | Uses logs, observations, and field results to evaluate behaviour. |

## Competition debugging and field testing

Competition work turns software into a complete engineering system. A behaviour that looks correct in isolation still needs to operate with real sensing, motion, timing, robot state, field conditions, and match pressure.

My work included:

- Reproducing behaviour issues through robot and field tests
- Observing ball response, positioning, movement, and decision transitions
- Distinguishing behaviour-level problems from wider integration effects
- Supporting fixes, retesting, and deployment under limited competition time
- Providing field support before and during matches

No private logs, credentials, robot configuration, or restricted implementation details are published here.

<table>
  <tr>
    <td width="50%" align="center"><img src="assets/technical/rcap-2025-robot-debugging.jpg" width="100%" alt="Robot debugging at RCAP 2025"><br><sub>Robot debugging · RCAP 2025</sub></td>
    <td width="50%" align="center"><img src="assets/technical/rcap-2025-field-integration.jpg" width="100%" alt="Field integration work at RCAP 2025"><br><sub>Field integration · RCAP 2025</sub></td>
  </tr>
  <tr>
    <td width="50%" align="center"><img src="assets/technical/robocup-2026-field-testing.jpg" width="100%" alt="Field testing at RoboCup 2026"><br><sub>Field testing · RoboCup 2026</sub></td>
    <td width="50%" align="center"><img src="assets/technical/robocup-2026-system-debugging.jpg" width="100%" alt="System debugging beside a KURA robot at RoboCup 2026"><br><sub>System debugging · RoboCup 2026</sub></td>
  </tr>
</table>

## Technical toolbox

| Robotics and autonomy | Software and platforms | Engineering practice |
|---|---|---|
| Humanoid Robotics | ROS | Behaviour Logic |
| Computer Vision | C++ | Competition Debugging |
| Ball Tracking | Python | Field Testing |
| Robot Positioning | Linux | System Integration |
| Robot Control | Git | Competition Deployment |
| Multi-robot Systems | ROS-based communication | Iterative Testing |

## Image gallery

### KURA humanoid robots

<table>
  <tr>
    <td width="50%" align="center"><img src="assets/robots/kura-robots-robocup-2026.jpg" width="100%" alt="Three KURA humanoid football robots at RoboCup 2026"><br><sub>KURA robots on the competition field</sub></td>
    <td width="50%" align="center"><img src="assets/robots/kura-robot-lineup-robocup-2026.jpg" width="100%" alt="KURA humanoid robot lineup at RoboCup 2026"><br><sub>Competition robot lineup · South Korea</sub></td>
  </tr>
</table>

### RoboCup Asia-Pacific 2025 · Abu Dhabi

<table>
  <tr>
    <td width="50%" align="center"><img src="assets/competitions/rcap-2025-abu-dhabi/humanoid-match.jpg" width="100%" alt="Humanoid robots playing football at RCAP 2025"><br><sub>Humanoid football match</sub></td>
    <td width="50%" align="center"><img src="assets/competitions/rcap-2025-abu-dhabi/omar-field-support.jpg" width="100%" alt="Omar Yousef supporting field operations at RCAP 2025"><br><sub>Field support during competition</sub></td>
  </tr>
  <tr>
    <td width="50%" align="center"><img src="assets/competitions/rcap-2025-abu-dhabi/omar-accreditation.jpg" width="100%" alt="Omar Yousef RCAP 2025 participant accreditation"><br><sub>RCAP 2025 accreditation</sub></td>
    <td width="50%" align="center"><img src="assets/competitions/rcap-2025-abu-dhabi/omar-al-emarat-tv-interview.jpg" width="100%" alt="Omar Yousef interviewed by Al Emarat TV at RCAP 2025"><br><sub>Interview with Al Emarat TV</sub></td>
  </tr>
</table>

### RoboCup 2026 · South Korea

<table>
  <tr>
    <td width="50%" align="center"><img src="assets/competitions/robocup-2026-south-korea/team-field-preparation.jpg" width="100%" alt="KURA members preparing robots on the RoboCup 2026 field"><br><sub>Team field preparation</sub></td>
    <td width="50%" align="center"><img src="assets/competitions/robocup-2026-south-korea/robot-diagnostics.jpg" width="100%" alt="Robot diagnostics at RoboCup 2026"><br><sub>Robot diagnostics and recovery</sub></td>
  </tr>
  <tr>
    <td width="50%" align="center"><img src="assets/competitions/robocup-2026-south-korea/robot-field-test.jpg" width="100%" alt="KURA humanoid robot field test at RoboCup 2026"><br><sub>Robot field test</sub></td>
    <td width="50%" align="center"><img src="assets/competitions/robocup-2026-south-korea/omar-accreditation.jpg" width="100%" alt="Omar Yousef RoboCup 2026 accreditation in Incheon"><br><sub>RoboCup 2026 accreditation · Incheon</sub></td>
  </tr>
  <tr>
    <td width="50%" align="center"><img src="assets/competitions/robocup-2026-south-korea/omar-tv-interview-backstage.jpg" width="100%" alt="Omar Yousef during RoboCup 2026 television filming"><br><sub>Competition filming on the field</sub></td>
    <td width="50%" align="center"><img src="assets/competitions/robocup-2026-south-korea/omar-tv-interview.jpg" width="100%" alt="Omar Yousef interviewed at RoboCup 2026"><br><sub>RoboCup 2026 interview</sub></td>
  </tr>
</table>

> [!NOTE]
> Four additional South Korea photos are preserved in their original HEIC/HEIF format in the event folder. They are not embedded here because GitHub does not reliably render those formats inline.

## Competition results

### RoboCup Asia-Pacific 2025

KURA reached the finals at ADNEC in Abu Dhabi and achieved:

- **AdultSize Humanoid League — second place**
- **KidSize Humanoid League — second place**

Results for RoboCup Asia-Pacific 2026 and RoboCup 2026 will be added only when confirmed. No unverified result is presented in this repository.

<p align="center">
  <img src="assets/results/rcap-2025-adultsize-second-place.jpg" width="48%" alt="RCAP 2025 AdultSize Humanoid League second-place trophy">
</p>

<p align="center"><em>RCAP 2025 · AdultSize Humanoid League · Second place</em></p>

## Skills demonstrated

- Designing and reasoning about robot behaviour at a practical system level
- Working with ROS-based robotics software in C++ and Python environments
- Connecting ball tracking and position information to movement decisions
- Testing humanoid robot behaviour through repeated field trials
- Debugging integrated systems under competition time constraints
- Supporting deployment and maintaining focus during live field operations
- Collaborating within a multidisciplinary robotics team
- Documenting technical work without exposing restricted team material

## Engineering lessons

1. **Integration is part of the feature.** Behaviour logic is only useful when it works with sensing, state, motion, and the rest of the robot.
2. **The field exposes different failures.** Real lighting, timing, movement, and match conditions reveal issues that isolated tests may miss.
3. **Observability accelerates debugging.** Clear state, disciplined reproduction, and targeted testing matter when competition time is limited.
4. **Stable transitions matter.** The handoff between decisions can be as important as the individual actions themselves.
5. **Robotics improves iteratively.** Observe, adjust, integrate, and retest—the feedback loop is central to reliable performance.

## Future development

- Publish verified results for the 2026 events when available
- Convert the preserved HEIC/HEIF originals to web-compatible images when a suitable codec is available
- Expand the galleries when additional approved competition photographs become available

## Repository contents

```text
kura-humanoid-robotics/
├── README.md                         # Main project portfolio
└── assets/
    ├── banner/                       # Lead portfolio image
    ├── team/                         # Team imagery
    ├── robots/                       # Humanoid robot showcase
    ├── technical/                    # Testing and debugging photographs
    ├── results/                      # Confirmed competition results
    └── competitions/                 # Event-specific galleries
        ├── rcap-2025-abu-dhabi/
        └── robocup-2026-south-korea/
```

## Repository notice

This is a **personal portfolio and technical case-study repository** documenting my experience as a KURA team member. It is not the official KURA source repository. The content focuses on my experience, personal contributions, competition participation, and publicly shareable technical concepts.

This repository does **not** contain:

- The full KURA codebase or private team files
- Robot configuration files or competition credentials
- Complete behaviour trees or internal logs
- Restricted research material or unapproved source code
- A complete implementation of the team's perception, control, or communication systems

Only approved images and portfolio-safe descriptions will be added. No software license is included because this repository may contain team-related photographs and written material that should not automatically be licensed for reuse.

## Credits

With appreciation to:

- **KURA — Khalifa University Robotics Team**
- **Khalifa University**
- All KURA team members, mentors, supervisors, and competition organizers

KURA names, logos, robot designs, photographs, and team materials remain the property of their respective owners. Their appearance in this personal portfolio does not imply ownership, endorsement, or official representation.

<div align="center">

![Footer](https://capsule-render.vercel.app/api?type=waving&height=140&section=footer&color=0:0096A6,45:0B3B53,100:071A2B&animation=fadeIn)

<sub>Built as a personal record of engineering, teamwork, and learning through humanoid robotics.</sub>

</div>
