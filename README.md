# db-normalization

### Google Sheet
[Normalization chart](https://docs.google.com/spreadsheets/d/10Yw1332MEDziovvPmbA9k7eY8Vcse30_Qm9orzXNUWU/edit?gid=0#gid=0)

### Chen diagram


### Database Schema

```mermaid
erDiagram
    CLASS {
        int classroom_id PK
        string classroom_description
    }

    STUDENTS {
        int student_id PK
        string student_name
        int classroom_id FK
    }

    COURSES {
        int course_id PK
        string lenguages
        int classroom_id FK
    }

    ENROLLMENT {
        int student_id PK,FK
        int course_id PK,FK
    }

    CLASS ||--o{ STUDENTS : "has"
    CLASS ||--o{ COURSES : "offers"
    STUDENTS }|--|{ ENROLLMENT : "enrolls in"
    COURSES }|--|{ ENROLLMENT : "is taken by"
    ```