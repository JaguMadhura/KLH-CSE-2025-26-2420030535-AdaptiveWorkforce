# Database Design

## 1. Purpose

The database stores employee, task, scheduling, workload, and assignment
information required by the Adaptive Workforce Scheduling and Task
Allocation System.

## 2. Main Entities

### Employee

Stores employee information.

| Field | Description |
|---|---|
| employee_id | Unique employee identifier |
| name | Employee name |
| email | Employee email |
| availability | Current availability status |
| workload | Current workload |
| status | Active or inactive |

### Skill

Stores available employee skills.

| Field | Description |
|---|---|
| skill_id | Unique skill identifier |
| skill_name | Name of the skill |

### EmployeeSkill

Connects employees with their skills.

| Field | Description |
|---|---|
| employee_id | Employee identifier |
| skill_id | Skill identifier |
| proficiency | Skill proficiency level |

### Task

Stores task information.

| Field | Description |
|---|---|
| task_id | Unique task identifier |
| title | Task title |
| description | Task description |
| priority | Task priority |
| required_skill | Required skill |
| deadline | Task deadline |
| estimated_hours | Estimated effort |
| status | Task status |

### Assignment

Stores task-to-employee assignments.

| Field | Description |
|---|---|
| assignment_id | Unique assignment identifier |
| task_id | Assigned task |
| employee_id | Assigned employee |
| assigned_hours | Allocated hours |
| assignment_status | Assignment status |

### Schedule

Stores workforce schedule information.

| Field | Description |
|---|---|
| schedule_id | Unique schedule identifier |
| employee_id | Employee identifier |
| task_id | Task identifier |
| start_time | Task start time |
| end_time | Task end time |
| schedule_status | Schedule status |

### Workload

Stores workload monitoring information.

| Field | Description |
|---|---|
| workload_id | Unique workload identifier |
| employee_id | Employee identifier |
| assigned_hours | Assigned working hours |
| completed_hours | Completed working hours |
| workload_percentage | Workload percentage |
| recorded_at | Time of measurement |

## 3. Relationships

The main relationships are:

- One employee can have multiple skills.
- One skill can belong to multiple employees.
- One employee can receive multiple tasks.
- One task can be assigned to an employee.
- One employee can have multiple schedule entries.
- One employee can have multiple workload records.

## 4. Database

**Database:** MySQL

The database will be integrated with the Spring Boot backend using
appropriate database connectivity and ORM technologies.

## 5. Data Security

The system should protect employee and task information.

Database credentials must not be stored directly in the GitHub repository.
Sensitive configuration should be maintained using environment variables or
other secure configuration mechanisms.
