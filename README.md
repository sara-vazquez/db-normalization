# db-normalization

### Google Sheet
[Normalization chart](https://docs.google.com/spreadsheets/d/10Yw1332MEDziovvPmbA9k7eY8Vcse30_Qm9orzXNUWU/edit?gid=0#gid=0)

### Chen diagram


### Database Schema

```mermaid
%%{init: {
  'theme': 'base',
  'themeVariables': {
    'primaryTextColor': '#080808',
    'primaryBorderColor': '#D94802',
    'lineColor': '#D94802',
    'background': '#D9A702',
    'mainBkg': '#DBB38C',
    'secondBkg': '#D9A702',
    'tertiaryBkg': '#D9A702'
  }
}}%%
erDiagram

    CLASSROOM {
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
        string languages
        int classroom_id FK
    }
    
    CLASSROOM ||--o{ STUDENTS : "has"
    CLASSROOM ||--o{ COURSES : "offers"
    STUDENTS }o--o{ COURSES : "takes"
```
