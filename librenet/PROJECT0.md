# PROJECT 0

Project 0 is a Facebook-style social networking service.

## Features

Or, things we will implement.

### User Page

The user page will host free-form personal information, a user avatar,
and a "Wall" for leaving personal notes. The notes can be replied to
in a threaded fashion. Users can post messages to their own pages. All
entry fields support markdown.

### Friending

Users can request "Friendship" with other users. If accepted, Walls
become accessible (as opposed to completely private).

### Session Switching

Having numerous user accounts will be allowed and encouraged. Multiple
sessions will be supported with an easy interface for switching
between them.

### Defriending

Users can terminate a friendship with other users, thus blocking them
from seeing their wall until friendship is restored.

### Event Planning

As no obvious, simple third-party service exists for this, basic
RSVPable events can be shared among friends.

### Static Generation

As much as possible, HTML will be statically generated and heavily
cached. Client-side Javascript will be kept to a minimum.

### Friend Activity

Instead of a torrential stream of updates from other users, the user
will be showed a simple activity sparkline reflecting the activity
level of friends' boards.

### User Search

Users can search for other users through a opted-into facets chosen at
account creation (handle, email address).

### Static URLs

By default, users' walls are hosted at static and human-readable URLs
for easy sharing.

### Usage Statistics

For the purpose of demonstrating cost, anonymized usage statistics
will be available to all users. These statistics range from number of
recent updates to bandwidth use.

### Pleasing design

This is a highly subjective feature. The design for the Project should
be somewhere between "Hip startup" and "Unformatted HTML." Twitter
Bootstrap may prove far too heavy (especially with respect to
Javascript) but may be suitable to get started.



## Anti-Features

### Instant Messaging

See: Jabber

### Asynchronous Messaging

See: E-Mail.

### Groups

This is a premature feature development. Users will figure out how to
group themselves. At some point such a thing might be calcified.

### Real-Time Data

This "feature" serves little purpose beyond getting users addicted to
a seemingly-infinite flow of data. It encourages indefinite use of the
given service and is highly, highly cost-prohibitive to implement. We
will prioritize static rendering over real-time features.

### Newsfeed

The "Newsfeed" of Facebook marked its transition into full-on drug
pushing mode. It is an anti-feature that discourages deep engagement
with friends.

### Photo uploading

See: Imgur, et. al.

### Video Uploading

See: Youtube, Vimeo

Or, things we will not implement.
