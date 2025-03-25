# Medzudo App – Funktionsübersicht & User Flow

**Medzudo** ist eine minimalistische, Apple-inspirierte Community-App für medizinisches Fachpersonal in Deutschland. Sie ermöglicht fachübergreifenden Austausch in einer datenschutzkonformen, modernen Plattform.

## 🌐 Kerntechnologien

- **Frontend:** React Native + TypeScript, Expo + Expo Router
- **UI Framework:** React Native Paper
- **Backend:** Supabase (auth, db, storage, edge functions, realtime)
- **Multilingual:** 🇩🇪 Deutsch & 🇬🇧 Englisch via i18n
- **Deployment:** Vercel (Web), Expo (iOS/Android)
- **Hosting:** DSGVO-konform, Deutschland

## 🧠 Hauptfunktionen

1. Benutzerregistrierung & Login
2. Onboarding nach Login
3. Newsfeed mit Beiträgen & Medien
4. Interaktionen: Like, Kommentar, Teilen, Speichern
5. Explore (Trendige Beiträge, Suche, Empfehlungen Communities und User)
6. Community-Bereich mit Rollen & Sub-Communities
7. Echtzeit-Messaging & Push Notifications
8. Profilverwaltung für Individuen, Einrichtungen & Organisationen
9. Multilinguale Oberfläche (Deutsch/Englisch)

## 📲 Logischer User Flow

### 1. Splash Screen

- Anzeige des Medzudo-Logos (2s Animation)
- → Weiterleitung zu Onboarding/Login

### 2. Onboarding (Intro Slides)

- **Slide 1:** Willkommen bei Medzudo – Für medizinische Expert:innen
- **Slide 2:** Funktionen: Austausch, Communities, Newsfeed
- **Slide 3:** DSGVO-konform & Hosting in Deutschland
- **Button:** `Loslegen →` → Registrierung/Login

### 3. Registrierung / Login

**Optionen:**
- Login via E-Mail & Passwort
- Login via Magic Link (Supabase Auth)

**Registrierungsfelder:**
- Name
- E-Mail
- Passwort
- Rolle:
  - Individuum
  - Einrichtung (Krankenhaus, Praxis etc.)
  - Organisation (Verband, Unternehmen etc.)
- Sprache: Deutsch / Englisch

→ E-Mail-Verifikation zwingend erforderlich

### 4. Onboarding (nach Login)

- Auswahl von Interessensgebieten (Tag-Selector)
- Optional: Profilbild hochladen
- Erklärung der Tabs via Tooltip oder Modals

→ Danach: Weiterleitung zur Homescreen = Newsfeed

### 5. Hauptnavigation (Bottom Tab Bar)

| Tab       | Beschreibung                                 |
| --------- | -------------------------------------------- |
| 📰 Newsfeed | Beiträge von Nutzer:innen & Communities       |
| 🔍 Explore | Trends, Tags, Empfehlungen, Suche             |
| 👥 Community | Beitritt & Verwaltung von Communities        |
| 👤 Profil   | Verwaltung des eigenen Profils & Settings    |

In Webapp (Desktopview) die Hauptnavigation als Sidebar

## 🧾 Detaillierter Screen-by-Screen Flow

### 📰 Newsfeed Tab

- Dynamisch generierter Feed (Global & Community-bezogen)
- Beiträge enthalten:
  - Text, Bilder, PDFs, Videos
  - Tags (#Dermatologie, #Pflege, #KI etc.)
- Aktionen:
  - ❤️ Liken
  - 💬 Kommentieren
  - 🔗 Teilen (Link oder in Community)
  - 📌 Speichern

### 🔍 Explore Tab

- **Empfohlene Inhalte**:
  - Trending Beiträge
  - Empfohlene Communities
  - Empfohlene Nutzer:innen

- **Suche mit Filteroptionen**:
  - Tags
  - Themenbereiche
  - Nutzer:innen
  - Beiträge
  - Communities

### 👥 Community Tab

- Darstellung in Grid oder List View
- Filter: Kategorien 
- Beitreten zu Gruppen (Join Requests bei privaten Gruppen)

#### Community-Subtabs:

| Tab        | Inhalt                                                 |
| ---------- | ------------------------------------------------------ |
| 📰 Feed     | Beiträge innerhalb der Community                       |
| 📁 Medien   | Ordnerstruktur: Bilder, PDFs, Videos                   |
| 📅 Meetup   | Events (online/offline), Kalender, Video-Meeting-Link (mit Whereby oder anderen WebRTC) |
| 👤 Members  | Mitgliederliste    
| Sub Community | Liste der Verlinkten Sub Communities
| ℹ️ Info     | Beschreibung, Weblinks, Sponsoren, Rollen              |

**Community-Rollen:**
- Admin, Moderator, Member
- Erstellung von Sub-Communities möglich
- Community Typen: Öffentlich / Privat / Versteckt
  - Öffentlich (jeder user kann beitreten)
  - Privat (Anfrage an den Community Admin)
  - Versteckt (Community wird nich im Explorer Angezeigt, nur Admin, und bereits member können die Community sehen)

### 💬 Messaging

- 1:1 Chats & Gruppenchats
- Supabase Realtime + Edge Functions
- Medienanhänge:
  - Fotos, Videos, PDFs
- Push Notifications bei neuen Nachrichten

### 👤 Profil

#### Für Individuen:

- Profilbild & Coverbild
- Position, Headline
- Standort
- Berufserfahrung
- Ausbildung
- Zertifikate
- Publikationen
- Links (Website, Social Media)
- Eigene Beiträge & gespeicherte Beiträge

#### Für Einrichtungen:

- Typ: Krankenhaus, Praxis, MVZ etc.
- Beschreibung, Fachbereiche
- Weiterbildungsermächtigungen
- Ausstattung
- Standort & Kontakt

#### Für Organisationen:

- Typ: Verband, Verein, Organisation, Unternehmen etc.
- Mission, Tätigkeitsfelder, Unternehmenform (GmbH, AG, e.V., etc.)
- Standort & Kontakt

#### Einstellungen:

- Profile bearbeiten (Profil bild, Cover Bild, Profil Infos, Link, etc.)
- Sprache wechseln
- Zertifizierung hochladen (Dokument)
- Nachricht an den Support
- Account löschen
- Datenschutzeinstellungen

## 🛠 Zusätzliche Features

- **Mehrsprachigkeit**: 🇩🇪 ↔ 🇬🇧 jederzeit umschaltbar
- **Rechtemanagement**:
  - Experten-Badges für validierte Profile
  - Community-Rollensteuerung (Admin, Moderator, Member)
  - User Profile (Individum, Einrichtung, Organisation)
- App Admin Dashboard (Statistik, User list, Community List, Support Meldungen, Einstellungen (Wartunsmodus, etc.))

## 🗄 Datenbankstruktur

### Users & Authentication
```sql
-- Users Table
CREATE TABLE users (
  id UUID PRIMARY KEY DEFAULT uuid_generate_v4(),
  email TEXT UNIQUE NOT NULL,
  encrypted_password TEXT NOT NULL,
  role TEXT NOT NULL DEFAULT 'user',
  language TEXT DEFAULT 'de',
  is_verified BOOLEAN DEFAULT false,
  created_at TIMESTAMP WITH TIME ZONE DEFAULT NOW(),
  updated_at TIMESTAMP WITH TIME ZONE DEFAULT NOW()
);

-- User Profiles
CREATE TABLE user_profiles (
  id UUID PRIMARY KEY REFERENCES users(id),
  first_name TEXT,
  last_name TEXT,
  title TEXT,
  specialty TEXT,
  bio TEXT,
  avatar_url TEXT,
  cover_url TEXT,
  location TEXT,
  website TEXT,
  languages TEXT[],
  created_at TIMESTAMP WITH TIME ZONE DEFAULT NOW(),
  updated_at TIMESTAMP WITH TIME ZONE DEFAULT NOW()
);

-- User Settings
CREATE TABLE user_settings (
  user_id UUID PRIMARY KEY REFERENCES users(id),
  notifications_enabled BOOLEAN DEFAULT true,
  email_notifications BOOLEAN DEFAULT true,
  theme TEXT DEFAULT 'system',
  created_at TIMESTAMP WITH TIME ZONE DEFAULT NOW(),
  updated_at TIMESTAMP WITH TIME ZONE DEFAULT NOW()
);

-- Professional Experience
CREATE TABLE professional_experience (
  id UUID PRIMARY KEY DEFAULT uuid_generate_v4(),
  user_id UUID REFERENCES users(id),
  title TEXT NOT NULL,
  organization TEXT NOT NULL,
  start_date DATE NOT NULL,
  end_date DATE,
  description TEXT,
  created_at TIMESTAMP WITH TIME ZONE DEFAULT NOW(),
  updated_at TIMESTAMP WITH TIME ZONE DEFAULT NOW()
);

-- Education
CREATE TABLE education (
  id UUID PRIMARY KEY DEFAULT uuid_generate_v4(),
  user_id UUID REFERENCES users(id),
  degree TEXT NOT NULL,
  institution TEXT NOT NULL,
  start_date DATE NOT NULL,
  end_date DATE,
  description TEXT,
  created_at TIMESTAMP WITH TIME ZONE DEFAULT NOW(),
  updated_at TIMESTAMP WITH TIME ZONE DEFAULT NOW()
);

-- Certifications
CREATE TABLE certifications (
  id UUID PRIMARY KEY DEFAULT uuid_generate_v4(),
  user_id UUID REFERENCES users(id),
  name TEXT NOT NULL,
  issuer TEXT NOT NULL,
  issue_date DATE NOT NULL,
  expiry_date DATE,
  document_url TEXT,
  created_at TIMESTAMP WITH TIME ZONE DEFAULT NOW(),
  updated_at TIMESTAMP WITH TIME ZONE DEFAULT NOW()
);
```

### Content & Posts
```sql
-- Posts
CREATE TABLE posts (
  id UUID PRIMARY KEY DEFAULT uuid_generate_v4(),
  user_id UUID REFERENCES users(id),
  community_id UUID REFERENCES communities(id),
  title TEXT,
  content TEXT NOT NULL,
  visibility TEXT DEFAULT 'public',
  created_at TIMESTAMP WITH TIME ZONE DEFAULT NOW(),
  updated_at TIMESTAMP WITH TIME ZONE DEFAULT NOW()
);

-- Post Media
CREATE TABLE post_media (
  id UUID PRIMARY KEY DEFAULT uuid_generate_v4(),
  post_id UUID REFERENCES posts(id),
  media_type TEXT NOT NULL,
  url TEXT NOT NULL,
  created_at TIMESTAMP WITH TIME ZONE DEFAULT NOW()
);

-- Comments
CREATE TABLE comments (
  id UUID PRIMARY KEY DEFAULT uuid_generate_v4(),
  post_id UUID REFERENCES posts(id),
  user_id UUID REFERENCES users(id),
  content TEXT NOT NULL,
  created_at TIMESTAMP WITH TIME ZONE DEFAULT NOW(),
  updated_at TIMESTAMP WITH TIME ZONE DEFAULT NOW()
);

-- Likes
CREATE TABLE likes (
  id UUID PRIMARY KEY DEFAULT uuid_generate_v4(),
  user_id UUID REFERENCES users(id),
  post_id UUID REFERENCES posts(id),
  created_at TIMESTAMP WITH TIME ZONE DEFAULT NOW(),
  UNIQUE(user_id, post_id)
);

-- Saved Posts
CREATE TABLE saved_posts (
  user_id UUID REFERENCES users(id),
  post_id UUID REFERENCES posts(id),
  created_at TIMESTAMP WITH TIME ZONE DEFAULT NOW(),
  PRIMARY KEY (user_id, post_id)
);
```

### Communities
```sql
-- Communities
CREATE TABLE communities (
  id UUID PRIMARY KEY DEFAULT uuid_generate_v4(),
  name TEXT NOT NULL,
  description TEXT,
  avatar_url TEXT,
  cover_url TEXT,
  specialty TEXT,
  visibility TEXT DEFAULT 'public',
  created_by UUID REFERENCES users(id),
  created_at TIMESTAMP WITH TIME ZONE DEFAULT NOW(),
  updated_at TIMESTAMP WITH TIME ZONE DEFAULT NOW()
);

-- Community Members
CREATE TABLE community_members (
  community_id UUID REFERENCES communities(id),
  user_id UUID REFERENCES users(id),
  role TEXT DEFAULT 'member',
  joined_at TIMESTAMP WITH TIME ZONE DEFAULT NOW(),
  PRIMARY KEY (community_id, user_id)
);

-- Community Media
CREATE TABLE community_media (
  id UUID PRIMARY KEY DEFAULT uuid_generate_v4(),
  community_id UUID REFERENCES communities(id),
  media_type TEXT NOT NULL,
  url TEXT NOT NULL,
  created_at TIMESTAMP WITH TIME ZONE DEFAULT NOW()
);

-- Events
CREATE TABLE events (
  id UUID PRIMARY KEY DEFAULT uuid_generate_v4(),
  community_id UUID REFERENCES communities(id),
  title TEXT NOT NULL,
  description TEXT,
  start_time TIMESTAMP WITH TIME ZONE NOT NULL,
  end_time TIMESTAMP WITH TIME ZONE,
  location TEXT,
  virtual_link TEXT,
  created_at TIMESTAMP WITH TIME ZONE DEFAULT NOW(),
  updated_at TIMESTAMP WITH TIME ZONE DEFAULT NOW()
);

-- Event Participants
CREATE TABLE event_participants (
  event_id UUID REFERENCES events(id),
  user_id UUID REFERENCES users(id),
  status TEXT DEFAULT 'pending',
  created_at TIMESTAMP WITH TIME ZONE DEFAULT NOW(),
  PRIMARY KEY (event_id, user_id)
);
```

### Messaging
```sql
-- Conversations
CREATE TABLE conversations (
  id UUID PRIMARY KEY DEFAULT uuid_generate_v4(),
  type TEXT NOT NULL,
  created_at TIMESTAMP WITH TIME ZONE DEFAULT NOW(),
  updated_at TIMESTAMP WITH TIME ZONE DEFAULT NOW()
);

-- Conversation Participants
CREATE TABLE conversation_participants (
  conversation_id UUID REFERENCES conversations(id),
  user_id UUID REFERENCES users(id),
  joined_at TIMESTAMP WITH TIME ZONE DEFAULT NOW(),
  PRIMARY KEY (conversation_id, user_id)
);

-- Messages
CREATE TABLE messages (
  id UUID PRIMARY KEY DEFAULT uuid_generate_v4(),
  conversation_id UUID REFERENCES conversations(id),
  sender_id UUID REFERENCES users(id),
  content TEXT NOT NULL,
  created_at TIMESTAMP WITH TIME ZONE DEFAULT NOW(),
  updated_at TIMESTAMP WITH TIME ZONE DEFAULT NOW()
);

-- Message Media
CREATE TABLE message_media (
  id UUID PRIMARY KEY DEFAULT uuid_generate_v4(),
  message_id UUID REFERENCES messages(id),
  media_type TEXT NOT NULL,
  url TEXT NOT NULL,
  created_at TIMESTAMP WITH TIME ZONE DEFAULT NOW()
);
```

### Notifications
```sql
-- Notifications
CREATE TABLE notifications (
  id UUID PRIMARY KEY DEFAULT uuid_generate_v4(),
  user_id UUID REFERENCES users(id),
  type TEXT NOT NULL,
  content TEXT NOT NULL,
  reference_id UUID,
  read BOOLEAN DEFAULT false,
  created_at TIMESTAMP WITH TIME ZONE DEFAULT NOW()
);
```

## 📁 Optimale Ordnerstruktur

```
medzudo-app/
├── app/                      # Expo Router App Directory
│   ├── (auth)/              # Auth Screens
│   │   ├── login.tsx
│   │   ├── register.tsx
│   │   └── forgot-password.tsx
│   ├── (tabs)/              # Main App Tabs
│   │   ├── newsfeed.tsx
│   │   ├── explore.tsx
│   │   ├── community.tsx
│   │   └── profile.tsx
│   ├── _layout.tsx          # Root Layout
│   └── index.tsx            # Entry Point
├── src/                     # Source Code
│   ├── components/          # Reusable Components
│   │   ├── common/         # Shared Components
│   │   ├── forms/          # Form Components
│   │   ├── layout/         # Layout Components
│   │   └── ui/             # UI Components
│   ├── hooks/              # Custom React Hooks
│   ├── services/           # API & External Services
│   │   ├── supabase/      # Supabase Client & Queries
│   │   └── api/           # API Integration
│   ├── store/             # State Management
│   │   ├── slices/        # Zustand Slices
│   │   └── index.ts       # Store Configuration
│   ├── types/             # TypeScript Types
│   ├── utils/             # Utility Functions
│   └── constants/         # App Constants
├── assets/                # Static Assets
│   ├── images/
│   ├── fonts/
│   └── icons/
├── docs/                  # Documentation
│   ├── CONTEXT.md
│   └── API.md
├── tests/                # Test Files
│   ├── unit/
│   ├── integration/
│   └── e2e/
├── .env.example          # Environment Variables Example
├── app.json              # Expo Config
├── babel.config.js       # Babel Config
├── package.json          # Dependencies
├── tsconfig.json         # TypeScript Config
└── README.md            # Project Documentation
```

## ✅ Nächste Schritte für Developer

1. Figma/Design in Cursor importieren & responsiv anpassen
2. Supabase-Projekt aufsetzen (Schema siehe oben)
3. Authentifizierung via Supabase implementieren
4. UI-Komponenten mit Tailwind + shadcn/ui bauen
5. Logik Schritt für Schritt modular implementieren (Tabs, Datenbindung)
6. Supabase-Edge Functions & Realtime Channels einrichten
7. Lokalisierung (i18n) konfigurieren
8. QA-Tests für Web, iOS, Android
9. Deployment via Expo (App Store + Play Store) & Vercel (Web)

## 📌 Hinweise für die Entwicklung

- Fokus auf DSGVO, Performance
- Optimierung für Web, iOS und Android (responsive Design)
- Skalierbar auf 20.000+ Nutzer
- Bereit für spätere API-Integrationen (z. B. KBV, ZBMED) 