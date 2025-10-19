# Agile Sprint Planning Tool

An interactive tool for sprint planning, estimation, and velocity tracking.

## Purpose

This tool streamlines the agile sprint planning process by providing teams with collaborative estimation, capacity planning, and velocity tracking capabilities. It helps teams plan more accurately and deliver consistently across sprints.

## Main Features

- **Interactive Planning Poker**: Remote-friendly estimation sessions with real-time updates
- **Backlog Management**: Drag-and-drop interface for prioritizing user stories
- **Capacity Planning**: Team availability tracking and workload balancing
- **Velocity Tracking**: Historical velocity charts and predictive analytics
- **Sprint Goals**: Define and track sprint objectives and success criteria
- **Burndown Charts**: Real-time progress visualization with trend analysis
- **Team Retrospectives**: Built-in retro boards with action item tracking
- **Integration Ready**: Connect with Jira, GitHub, and Azure DevOps

## Sample Usage

```javascript
const SprintPlanner = require('agile-sprint-planning-tool');

// Initialize sprint planning session
const sprint = new SprintPlanner.Sprint({
  team: 'backend-team',
  duration: 2, // weeks
  startDate: '2025-10-20'
});

// Add team member capacity
sprint.addTeamMember({
  name: 'Alice',
  capacity: 40, // hours
  skills: ['backend', 'database']
});

// Estimate user story
const story = sprint.addStory({
  title: 'Implement user authentication',
  description: 'Add OAuth2 support',
  acceptanceCriteria: [...]
});

// Start planning poker session
const session = sprint.startEstimation(story.id);
session.submitEstimate('Alice', 8); // story points
session.submitEstimate('Bob', 13);

// Check sprint capacity
if (sprint.hasCapacity()) {
  sprint.commitStory(story.id);
}

// Generate sprint report
const report = sprint.generateReport();
console.log(`Committed: ${report.totalPoints} points`);
console.log(`Velocity: ${report.teamVelocity}`);
```

## Quick Start

1. Install: `npm install agile-sprint-planning-tool`
2. Create your team profile and add members
3. Import your backlog or create stories manually
4. Start a planning session and invite team members
5. Run estimation, check capacity, and commit stories
6. Track progress with burndown charts throughout the sprint

## Benefits for Product Management

- **Improved Predictability**: Data-driven sprint planning with historical velocity
- **Team Alignment**: Collaborative estimation ensures shared understanding
- **Capacity Awareness**: Avoid overcommitment and team burnout
- **Stakeholder Communication**: Visual reports and progress tracking
