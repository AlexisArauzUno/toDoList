# todo List
This application is planed to rearange your chores and prioritize them so you can have a better track on your projects and everyday chores, eventually this app could grow to have a more Getting things Done oriented tool, yet this is just for having a visual tool for required chores.


# MoSCoW

## Must Have
 - Chore definition and creation
 - On project creation must include one or more Chores
 - Not all chores are Project Related
 - Can see priority on chores
 - Can see and update Status on chores
 - User can Create, update and Delete chores
 - Login and identification

## Should Have
 - Filtering by chore priority
 - User can Rearange chores on display

## Could Have
 - Description available with links and media
 - Planing tools for defining complexity on chores
 - Recurrent/Repeating Chores

## Will not Have
 - Chores to be visible to others
 - An agile oriented 

# Entity Relation Diagram
```mermaid
erDiagram
    USER }|--o{ CHORE : creates
    CHORE }|--|| START_DATE : begin
    CHORE }|--|| END_DATE : end
    CHORE }|--o| DESCRIPTION : "might have"
    CHORE }|--|| PRIORITY : "has"
    CHORE }|--|| STATUS : "has"
    USER }|--o| PROJECT : "can create"
    PROJECT }|--|{ CHORE : "has"

```
# Database definition Diagram
```mermaid
erDiagram
    USER }|--o{ CHORE : creates
    USER }|--o{ PROJECT : "can create"
    PROJECT }|--|{ CHORE : "has"
    USER {
        string name
        string mail
        string password
    }
    CHORE {
        date start_date
        date end_date
        string description
        int priority
        int status
    }
    PROJECT {
        string description
    }
```
