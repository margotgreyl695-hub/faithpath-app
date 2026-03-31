# Database Schema Documentation

This document outlines the comprehensive database schema for the FaithPath application. It includes the various tables used in the application and their relationships.

## Tables

### 1. Users
- **Table Name**: `users`
- **Description**: Stores user information and preferences.
- **Columns**:
  - `id` (Primary Key, Integer): Unique identifier for each user.
  - `username` (String, Unique): User's chosen username.
  - `email` (String, Unique): User's email address.
  - `password_hash` (String): Hashed password for authentication.
  - `created_at` (Timestamp): Date and time when the user registered.
  - `updated_at` (Timestamp): Date and time when the user information was last updated.

### 2. Bible Verses
- **Table Name**: `bible_verses`
- **Description**: Contains Bible verses and associated metadata.
- **Columns**:
  - `id` (Primary Key, Integer): Unique identifier for the verse.
  - `book` (String): The book of the Bible.
  - `chapter` (Integer): Chapter number.
  - `verse` (Integer): Verse number.
  - `text` (Text): The content of the verse.

### 3. Emotions
- **Table Name**: `emotions`
- **Description**: Stores emojis and corresponding emotional meanings for user interaction.
- **Columns**:
  - `id` (Primary Key, Integer): Unique identifier for each emotion entry.
  - `emoji` (String): The emoji representing an emotion.
  - `description` (String): Description of the emotion.

### 4. Reading Plans
- **Table Name**: `reading_plans`
- **Description**: Facilitates users' planned Bible reading schedules.
- **Columns**:
  - `id` (Primary Key, Integer): Unique identifier for each reading plan.
  - `user_id` (Integer, Foreign Key): Reference to the user who created the plan.
  - `start_date` (Date): The date the reading plan starts.
  - `end_date` (Date): The date the reading plan ends.
  - `created_at` (Timestamp): Date and time the reading plan was created.
  - `updated_at` (Timestamp): Date and time the reading plan was last updated.

### 5. Memorization Tracking
- **Table Name**: `memorization_tracking`
- **Description**: Records verses memorized by the user and their progress.
- **Columns**:
  - `id` (Primary Key, Integer): Unique identifier for each memorization entry.
  - `user_id` (Integer, Foreign Key): Reference to the user.
  - `verse_id` (Integer, Foreign Key): Reference to the Bible verse.
  - `memorization_status` (String): Current status of the memorization (e.g., "not started", "in progress", "completed").
  - `created_at` (Timestamp): Date and time of the record creation.

### 6. Chat History
- **Table Name**: `chat_history`
- **Description**: Logs interactions in the chat feature of the application.
- **Columns**:
  - `id` (Primary Key, Integer): Unique identifier for each chat entry.
  - `user_id` (Integer, Foreign Key): Reference to the user.
  - `message` (Text): Content of the chat message.
  - `created_at` (Timestamp): Date and time the message was sent.

## Relationships
- `users` table is linked to `reading_plans`, `memorization_tracking`, and `chat_history` through the `user_id` foreign key.
- `bible_verses` table is linked to `memorization_tracking` through the `verse_id` foreign key.

This schema is designed to facilitate easy access and management of user data, Bible verses, and their interactions with the FaithPath application.