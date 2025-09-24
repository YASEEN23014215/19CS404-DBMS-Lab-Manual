# ER Diagram Workshop – Submission Template

## Objective
To understand and apply ER modeling concepts by creating ER diagrams for real-world applications.

## Purpose
Gain hands-on experience in designing ER diagrams that represent database structure including entities, relationships, attributes, and constraints.

---

# Scenario A: City Fitness Club Management

**Business Context:**  
FlexiFit Gym wants a database to manage its members, trainers, and fitness programs.

**Requirements:**  
- Members register with name, membership type, and start date.  
- Each member can join multiple programs (Yoga, Zumba, Weight Training).  
- Trainers assigned to programs; a program may have multiple trainers.  
- Members may book personal training sessions with trainers.  
- Attendance recorded for each session.  
- Payments tracked for memberships and sessions.

### ER Diagram:
 

<img width="791" height="865" alt="Screenshot 2025-08-29 225250" src="https://github.com/user-attachments/assets/b684b060-f82e-4d63-b975-962d4dbb1c56" />


### Entities and Attributes

| Entity | Attributes (PK, FK) | Notes |
|--------|--------------------|-------|
|    Member    |        MemberID ,Membership          |  Store member details     |
|      Trainer  |      TrainerID,Name,Email,PhoneNumber              |     Store Trainer details  |
|  Program      |      ProgramID,Cost              |  Programs like Zumbz/yoga     |
|    Session    |       SessionID,SessionDate             |    Tracks attendance   |
|    Payment    |          PaymentID,Amount          |   Tracks payments by members    |


### Relationships and Constraints

| Relationship | Cardinality | Participation | Notes |
|--------------|------------|---------------|-------|
|       Member-Program       |     M:N       |      Optional(Member),Mandatory(Enrollment)         | Member may or may not join programs      |
|          Trainer-Program    |      M:N      |            Optional(Trainer),Mandatory(Assignment)   |  Trainer may or may not run Programs     |
|       Member–Trainer       |     1:N       |        Mandatory (Session), Optional (Member/Trainer)       |    Session must have a member & trainer   |

### Assumptions
- Program = recurring class; Session = specific instance.
- Payments cover both memberships and sessions.
- A Session links one Member and one Trainer.

---

## RESULT
Successfully designed an ER diagram for the flexifit gym with entities, relationships, constraints, and billing-extension using the Payment entity to support real.





---

