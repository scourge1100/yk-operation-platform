# Project Overview

This document describes the background, goals, and system context of the **Yeolhyeolgangho W Operations Platform**.

---

## Background

The Yeolhyeolgangho W Operations Platform is a web-based administration system developed to support the live operation of the MMORPG **Yeolhyeolgangho W**.

For security reasons, game servers were isolated from external networks.  
As a result, operators could not directly access the servers to perform operational tasks such as managing announcements, granting items, or querying user data.

To address this limitation, a dedicated web-based operations platform was developed to allow operators to manage the game service through a secure and controlled interface.

---

## Problem Statement

During the game launch preparation phase, there was no operational management system available for the operations team.

To operate a live game service, several essential functions were required:

- Managing in-game announcements
- Granting items to specific characters or player groups
- Managing game events
- Querying user and character data
- Tracking operational activities

Without a centralized management system, these tasks would require direct server access or manual database operations, which could introduce security risks and operational inefficiencies.

---

## Project Goals

The main objectives of the project were:

- Provide essential tools for game service operations
- Enable operators to perform operational tasks through a web-based interface
- Implement a secure communication structure with game servers
- Improve operational efficiency by reducing manual workload
- Design a flexible menu and permission structure for future operational features

---

## System Context

The operations platform was built on an **AWS-based 3-Tier Architecture**.

Game servers were isolated from external networks, and all operational requests from the admin platform were routed through an **interface server** before reaching the game servers.

This architecture allowed the system to:

- Protect game servers from external exposure
- Control communication between systems
- Minimize the impact of operational tool failures on the game service

For more details, see:

- [System Architecture](architecture.md)
