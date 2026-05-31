# Product Requirement Documents (PRD)

> **AI SYSTEM INSTRUCTION:** This repository serves as the centralized, machine-readable knowledge base for all product requirements, flows, and design architectures. Strict adherence to the directory structure and indexing rules below is mandatory for all agents (specifically `@Doc-Housekeeper`) modifying this repository.

## Repository Structure & Indexing Rules

1. **Sub-Directory Isolation:** Every distinct product, application, or major module MUST be housed in its own dedicated sub-directory within this root folder. Do not place loose PRD Markdown files in the root.
2. **Standardized Naming:** Sub-directories must use lowercase, kebab-case naming conventions (e.g., `fnb-b2b-store`, `agri-supply-chain-dashboard`).
3. **Internal Indexing:** Each product sub-directory must contain its own `README.md` or `_Index.md` file that acts as the table of contents for that specific product's documentation.
4. **Root Index Updates (MANDATORY):** Whenever a new product sub-directory is created, the agent MUST append a link to that product's internal index in the **Product Directory** section at the bottom of this root `README.md` file.

## Expected PRD Content Structure

Within each product's directory, the documentation must address the following four core pillars defined by the Product Research Squad:

*   **1-Global-Style-Guides.md:** Typography, color palettes, spacing, and component definitions.
*   **2-Business-Context.md:** Target audience, agricultural/F&B/economic market analysis, and core value propositions.
*   **3-UX-UI-Flow.md:** User journeys, high-level to detailed screen layouts (using Markdown wireframes), and structural specs for Figma.
*   **4-Unhappy-Paths.md:** Error state handling, edge cases, and fallback logic.

*Note: Large sections may be broken into modular files, provided they are indexed correctly.*

## Cross-Linking Standards

To ensure future agents and human developers can easily navigate the logic:
*   **Screen/Flow Anchors:** Use standardized headers for easy lookup (e.g., `### [Screen] User_Registration`).
*   **Multica Task Tracking:** Any implemented feature or defined unhappy path must reference its corresponding Multica Task ID (e.g., `Tracking: Task #1042`).

---

## 🗂️ Product Directory

*(AI Agents: Append new product links below this line. Keep the list alphabetized.)*

*   [AquaPlan](./aquaplan/README.md) - *Cross-platform AI-assisted aquarium & paludarium planner app (Web, Mobile, iPad).*
