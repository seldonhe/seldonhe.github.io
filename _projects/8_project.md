---
layout: page
title: WanderWonder - A Local-First Travel Planning Companion
description: Product Design / React / TypeScript / Local-First Architecture / AI-Assisted Development
img: assets/img/project_img/WanderWonder/card.png
importance: 1
category: work
related_publications: false
---

<div class="container-fluid mt-3 md-3">

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/project_img/WanderWonder/cover.jpg" class="img-fluid rounded z-depth-1" alt="WanderWonder travel planning interface displayed on a laptop beside maps, a camera, and a globe" caption="WanderWonder brings itinerary planning, daily schedules, maps, costs, and trip preparation into one calm workspace." %}
    </div>
</div>

<div class="mt-4">
    <a class="btn btn-primary" href="https://devpost.com/software/wanderwonder" target="_blank" rel="noopener noreferrer">View on Devpost</a>
    <a class="btn btn-outline-primary" href="https://www.youtube.com/watch?v=lnuP1M7hjrY" target="_blank" rel="noopener noreferrer">Watch the demo</a>
</div>

</div>

<div class="container-fluid mt-3 md-3">

<h2>Project Overview</h2>

<p>Travel plans rarely live in one place. Bookings sit in email, activities accumulate in notes, routes are checked in a separate map, and expenses are tracked in another spreadsheet. WanderWonder is a local-first travel planning companion designed to turn that fragmentation into one clear flow: <b>Plan, Schedule, Map, Cost, and Prepare</b>.</p>

<p>I built WanderWonder for OpenAI Build Week 2026 as an end-to-end product and engineering project. The result is a responsive React and TypeScript application that helps travelers move from early ideas to day-by-day execution without requiring an account or a cloud database.</p>

<div class="row text-center mt-4">
    <div class="col-md-4 mb-3">
        <h3>5 connected views</h3>
        <p>One continuous trip workflow</p>
    </div>
    <div class="col-md-4 mb-3">
        <h3>Local-first</h3>
        <p>Trip data stays in the browser</p>
    </div>
    <div class="col-md-4 mb-3">
        <h3>No account</h3>
        <p>Start planning without sign-up</p>
    </div>
</div>

</div>

<div class="container-fluid mt-3 md-3">

<h2>One Trip, Five Connected Views</h2>

<h4>Plan</h4>
<p>Organize flights, trains, stays, activities, and dining in a flexible itinerary. Items can be reordered, moved between days, and reviewed in focused view or edit modes.</p>

<h4>Schedule</h4>
<p>Translate the itinerary into a daily timeline with time-aware activities and the relevant transportation and accommodation context.</p>

<h4>Map</h4>
<p>See structured trip locations, coordinate-based markers, and itinerary connections together. A location-resolution workflow helps turn incomplete place information into usable map data.</p>

<h4>Cost</h4>
<p>Compare planned and actual spending across currencies, categories, and days to understand where the travel budget is changing.</p>

<h4>Prepare</h4>
<p>Bring packing, logistics, priorities, and readiness checks into the same trip workspace so important details do not disappear between planning tools.</p>

</div>

<div class="container-fluid mt-3 md-3">

<h2>Product Demo</h2>

<p>The public demo follows a fully fictional Vancouver-to-China discovery journey. All names, bookings, costs, and travel details shown are synthetic and were created specifically for demonstration.</p>

<iframe class="project-embed" height="560" title="WanderWonder product demonstration" src="https://www.youtube-nocookie.com/embed/lnuP1M7hjrY" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

</div>

<div class="container-fluid mt-3 md-3">

<h2>Designing for Calm Complexity</h2>

<p><b>Progressive disclosure.</b> Travel planning contains many objects, states, and decisions. I separated overview and editing tasks so people can scan the trip first and reveal detail only when they need it.</p>

<p><b>Connected context.</b> Rather than recreating the same information in each section, the product carries itinerary context into schedules, routes, budgets, and preparation tasks.</p>

<p><b>Resilient local data.</b> Browser-based persistence keeps the product private and fast, but makes backup and recovery essential. WanderWonder includes portable backups, import validation, recovery copies, and schema-aware state handling.</p>

<p><b>Honest scope.</b> The current version does not claim cloud sync, live flight lookup, real-world route optimization, collaborative editing, or predictive budgeting. Its focus is a dependable personal planning workflow with explicit user control.</p>

</div>

<div class="container-fluid mt-3 md-3">

<h2>Building with AI</h2>

<p>ChatGPT and Codex supported the project from product definition through implementation. I used them to challenge workflow assumptions, shape data models and backward-compatibility plans, break large React and TypeScript refactors into reviewable steps, write validation and tests, debug edge cases, and review the finished experience.</p>

<p>The working loop remained deliberate: define the user problem, choose the smallest safe change, implement and test it, review edge cases, and refine. This kept AI assistance grounded in product judgment and verification rather than treating generated code as the final answer.</p>

<p>WanderWonder was submitted to <b>OpenAI Build Week 2026</b>. The public Devpost page contains the full project story, technology list, and demonstration.</p>

</div>
