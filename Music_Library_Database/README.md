# MelodyBase

## A comprehensive SQL database system for music collection management

---

## 🎵 Overview

MelodyBase is a robust SQL database system designed to manage and organize music collections with efficiency and precision. This project implements a sophisticated database architecture that allows users to catalog songs, artists, albums, and playlists while maintaining complex relationships between these entities.

Built with SQLite and employing advanced database concepts, MelodyBase demonstrates the practical application of relational database design in handling real-world data scenarios. While not intended as a streaming platform, it provides the essential backend infrastructure for comprehensive music library management.

---

## ✨ Key Features

- **Complete Music Metadata Management**
  - Comprehensive song, artist, and album cataloging
  - Detailed tracking of release dates, durations, and genres
  - Support for explicit content flagging

- **User-Centric Design**
  - Personal account management
  - Favorites and ratings system
  - Listening history tracking
  - Privacy controls

- **Playlist Functionality**
  - Custom playlist creation and management
  - Flexible song organization
  - Position tracking within playlists
  - Public/private visibility settings

- **Advanced Categorization**
  - Multi-genre classification
  - Artist collaboration tracking
  - Album type differentiation (LP, EP, Single, Compilation)

---

## 📊 Database Schema

### Core Entities

| Entity | Description |
|--------|-------------|
| Users | Account details, authentication data, and user preferences |
| Songs | Core music tracks with metadata and content flags |
| Artists | Performers with biographical information |
| Albums | Collections of songs with release information |
| Playlists | User-created song collections with metadata |
| Genres | Music classification categories |

### Junction Tables

| Table | Relationship |
|-------|-------------|
| song_artists | Maps the many-to-many relationship between songs and artists |
| playlist_songs | Connects songs to playlists with position tracking |
| song_genres | Associates songs with their respective genres |
| user_songs | Tracks user favorites and ratings |

---

## 🔍 Entity Details

### Users Table

```sql
CREATE TABLE users (
    user_id INTEGER PRIMARY KEY,
    username TEXT NOT NULL UNIQUE,
    email TEXT NOT NULL UNIQUE,
    password_hash TEXT NOT NULL,
    first_name TEXT NOT NULL,
    last_name TEXT NOT NULL,
    created_at DATETIME DEFAULT CURRENT_TIMESTAMP,
    last_login DATETIME
);
```

### Songs Table

```sql
CREATE TABLE songs (
    song_id INTEGER PRIMARY KEY,
    title TEXT NOT NULL,
    duration_seconds INTEGER NOT NULL CHECK(duration_seconds > 0),
    release_date DATE,
    album_id INTEGER REFERENCES albums(album_id),
    explicit BOOLEAN DEFAULT FALSE
);
```

### Artists Table

```sql
CREATE TABLE artists (
    artist_id INTEGER PRIMARY KEY,
    name TEXT NOT NULL,
    bio TEXT,
    formed_date DATE
);
```

### Albums Table

```sql
CREATE TABLE albums (
    album_id INTEGER PRIMARY KEY,
    title TEXT NOT NULL,
    release_date DATE NOT NULL,
    album_type TEXT CHECK(album_type IN ('LP', 'EP', 'Single', 'Compilation')),
    total_tracks INTEGER CHECK(total_tracks > 0)
);
```

### Playlists Table

```sql
CREATE TABLE playlists (
    playlist_id INTEGER PRIMARY KEY,
    user_id INTEGER NOT NULL REFERENCES users(user_id),
    name TEXT NOT NULL,
    description TEXT,
    created_at DATETIME DEFAULT CURRENT_TIMESTAMP,
    is_public BOOLEAN DEFAULT TRUE
);
```

### Genres Table

```sql
CREATE TABLE genres (
    genre_id INTEGER PRIMARY KEY,
    name TEXT NOT NULL UNIQUE,
    description TEXT
);
```

---

## 🔄 Relationships

![Music Library ER Diagram](https://github.com/user-attachments/assets/27dbd10f-caa9-4866-bf5a-e2e5f0535b2d)

### Key Relationships

- **User ↔ Playlists**: One-to-many (A user can create multiple playlists)
- **User ↔ Songs**: Many-to-many via user_songs (Favoriting mechanism)
- **Songs ↔ Artists**: Many-to-many via song_artists (Supports multiple artists per song)
- **Songs ↔ Albums**: Many-to-one (Songs belong to at most one album)
- **Songs ↔ Genres**: Many-to-many via song_genres (Multiple genre classification)
- **Songs ↔ Playlists**: Many-to-many via playlist_songs (Songs can appear in multiple playlists)

---

## 🚀 Implementation Details

### Performance Optimizations

#### Strategic Indexes

```sql
-- Fast search functionality
CREATE INDEX idx_song_title ON songs(title);
CREATE INDEX idx_artist_name ON artists(name);

-- Quick authentication
CREATE INDEX idx_user_email ON users(email);

-- Efficient sorting and filtering
CREATE INDEX idx_album_release ON albums(release_date);
CREATE INDEX idx_genre_name ON genres(name);
CREATE INDEX idx_playlist_created ON playlists(created_at);
```

#### Optimized Views

```sql
-- Comprehensive song details
CREATE VIEW SongDetails AS
SELECT s.song_id, s.title, s.duration_seconds, s.release_date, s.explicit,
       a.name AS artist_name, al.title AS album_title
FROM songs s
JOIN song_artists sa ON s.song_id = sa.song_id
JOIN artists a ON sa.artist_id = a.artist_id
LEFT JOIN albums al ON s.album_id = al.album_id;

-- Complete playlist contents
CREATE VIEW PlaylistContents AS
SELECT p.playlist_id, p.name AS playlist_name, s.song_id, 
       s.title AS song_title, ps.position, ps.added_at
FROM playlists p
JOIN playlist_songs ps ON p.playlist_id = ps.playlist_id
JOIN songs s ON ps.song_id = s.song_id
ORDER BY p.playlist_id, ps.position;
```

---

## 💡 Use Cases

### Personal Music Organization

- Catalog personal music collections
- Create themed playlists for different occasions
- Track favorite songs and artists
- Monitor listening preferences over time

### Music Analysis

- Analyze distribution of genres in a collection
- Track listening trends by time period
- Identify most prolific artists in specific genres
- Study album completeness in a collection

### Content Management

- Maintain clean separation between explicit and non-explicit content
- Organize music by release chronology
- Create specialized collections (e.g., holiday music, workout playlists)
- Filter content by various metadata attributes

---

## ⚠️ Limitations

### Technical Constraints

- No audio file storage capabilities
- Limited representation of artist roles (primary artist, featured artist, producer)
- Cannot handle classical music complexity (composers, conductors, orchestras)
- No version control for playlist modifications
- Limited representation of compilation relationships

### Data Model Constraints

- Simplified genre relationships
- No support for temporary/seasonal playlists
- Cannot track partial listening within tracks
- No representation for music videos or visual media
- Limited support for different versions of the same song
- No regional availability tracking

---

## 🔮 Future Development

Potential enhancements include:

- Advanced artist role classification
- Support for classical music compositions
- Version history for playlists
- Integration points for audio streaming services
- Extended metadata for musicological analysis
- User collaboration features
- Smart playlist generation based on listening patterns
- Rating system for songs and albums

---

## 📝 License

This project is licensed under the MIT License - see the LICENSE file for details.

---

*Developed as a personal project to demonstrate advanced SQL database design and implementation.*
