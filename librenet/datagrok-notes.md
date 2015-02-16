# Notes

## Questions

### Philosophy

- Q. What exactly is a "wall?"
    - What does it model? (Dorm room door whiteboards?)
    - What actions can one perform on one's own wall, and those belonging to others?
    - What are the social/cultural expectations for privacy?

- Q. What exactly is a "tweet?"
    - What is the optimum length limit?
    - Is a character limit appropriate? A sentence limit? A concept limit?
    - In an ideal world, should URLs be excluded from counting toward the limit?
    - Should usernames be excluded from counting toward the length limit?
    - Should punctuation be excluded from counting toward the length limit?

### Manifesto

- Q. Anonymity without filtering is 4chan. What do we do about douchebags?
    - Friends-only darknet loses "serendipity" feature of twitter.
    - Pseudonymity is a start, but pseudonyms must have reputation and be preemptively blockable
    - A. `PROJECT ZERO` (facebook-alike) is friends-only darknet, `PROJECT ONE` (twitter-alike) is firehose.
        - Q. What to do about douchebags in `PROJECT ONE`?
            - A. Provide a "block" tool that actually works, unlike Twitter's
            - A. Provide an API that makes it easy for third parties to develop things like @The_Block_Bot (but better).

- Q. Should a persuasive essay include terms like "evil"? To a punter who doesn't know better this is just grandstanding. Demonstrate why it's evil instead?
    - A. It's not public-facing. It's like a mission statement for members who already sorta drink the koolaid. Intended to be strongly-worded, inspiring, resonant.

- Q. Domain name. (blah)net.com, net.net, net.org sounds funny. libre.net is taken. what to do? librenetfoundation.org?
    - A. It's not permanent, just chosen because we needed a repo name. Foundation name could be something more edgy than actual social network.

- Q. What is principle #1 declaring? Seems tautology
    - A. Similar to the principle I added: Users come first. We exist, and can exist, to provide utility. We don't subscribe to the mandate of maximal-profit-at-all-costs or even profit-or-cease-to-exist.

- Q. Are we always strong copyleft? would we tolerate weak copyleft (LGPL)? Does any of the stuff we (would ever) build necessitate the asking of this question?

- Q. Don't understand "real-time addictive information overload." sometimes that's what I want. why is it bad? proscribed from all software?
    - A. Avoid "design to sell advertising"
    - A. Need not prioritize real-time updates over other features. "As slow as email" is okay.
    - A. Maybe soften the language a bit in the manifesto

- Q. Will services be centralized, federated, or distributed? We maybe should declare this in each service's design document, with rationale.

- Q. Without central access to user data, we lose the ability to form serindipitous connections with strangers or do "similar user" recommendations. Is that ok?
    - A. In the PGP-style facebook-alike discussed today: messages posted from Alice to Bob get opened to Bob's friends by Bob by his client automatically (or at his request) reencrypting the session key to his friend list.
        - Q. Does this enable Bob's friends to know that Alice posted the message?
        - Q. Does this enable Alice to connect to like-minded strangers? (Is that something we want?)

- Q. Why is client-side encryption bolted-on after-the-fact? Shouldn't it be a non-optional core mechanic?
    - A. "Let the cryptography define the core mechanic" seems to be an engaging idea, let's follow it a bit...

- Q. If the twitter-alike is a direct subset of the facebook-alike, why distinguish them?

- Q. What properties of twitter will the twitter-alike be built for? Surely not just the arbitrary line-length limit?
    - A. The arbitrary length limit does have a social effect, despite its infuriatingly arbitrariness.

- Q. Again, encryption as a follow-on step for twitter?

- Q. What distinguishes our work from e.g. diaspora, identi.ca, mediagoblin, gnunet? Why are they not good enough?
    - A. Diaspora and it's -alikes may indeed be good enough. See "Project 0"

- Q. How much of the manifesto is a core principle of all the software and services we build, and how much of it is instead a core requirement of one particular piece of software we wish to build? Distinguish these statements and move the latter into design docs for services?
    - Q. Should manifestos be short?

### Project 0

- **Q. Diaspora has greatly improved since we last looked at it. Does it meet our needs already?**
    - A. Need to investigate.
    - A. If so, see "PGP Style Social Network Idea."

- Q. Why are we adopting the core design and vocabulary of Facebook (e.g. "wall"). Should we re-examine its design? Why should each user have (exactly one) public message area? Who sees it? Who gets notified by activity there?
- Q. "The notes can be replied to in a threaded fashion" -> we're implementing a message board. Can we improve on the "message board" concept?
- Q. Friendship is only valid when bidirectional?
- Q. Should it be called "friendship"?
- Q. Should we examine the social dynamics of "friendship"? E.g. people who somehow think collecting friendships is a game that can be won, or people who are reluctant to un-friend but perfectly happy to "mute forever."
- Q. Walls are friends-only, never public? How does one meet new, interesting people?
- Q. Only one group of friends: despite G+ shittiness, I think their "circles" models friendship dynamics better than Facebook or Twitter do. I have groups of friends that sometimes overlap and sometimes conflict bitterly (so I must keep my interactions with them separate from one another.) It is easier to think of my single persona interacting with multiple "circles" of membership than to imagine a different persona for myself for each group I interact with.
- Q. Defriending can be an affront in facebook. Should we address this? "Unsubscribe" instead? Notify at all?
- Q. Why keep client-side javascript to a minimum? JS can make a static site feel dynamic. If we're doing crypto in the browser that's a shitload of client side JS already.
- Q. Why is a torrent of friend activity bad? Are we avoiding aggregation out of principle?
- Q. User search: marginalized groups may not enter as many details; may wish to be easily found by past friends but not by creepers. How to deal?
- Q. Human-readable URLs -> scarcity. How to deal with name collision?
- Q. Should the design of the interface be welded to the backend? Do we provide a robust API that allows others to create their own interfaces?

### Anti-features

- Q. Async messaging is an anti-feature, but we have threaded responses to posts left on walls?
- Q. users will figure out how to group themselves -> wat? Implications? Safety for marginalized?
- Q. example of "real-time data" on other sites that we avoid
- Q. No photo/video uploading, what about oembed them from other sites?
    - Q. Could embedded media or click-through-to-youtube subvert our privacy mechanisms?

### PGP-style Social Network Idea

- Q. Just how long does it take modest hardware to encrypt a session key to [150 friends]? What about a browser on a 2010 smartphone? What about an app on a 2010 smartphone? And a Raspberry Pi?

- Q. Should we provide for [Off The Record] communications? Does pseudonymity solve this problem for us?

- Q. When de-friending, we wish to remove access to past posts. Re-key everything?
    - Q. How long will it take for 150 friends, 2000 posts?
        - Q. If it's bad: is it necessary to re-key *everything*? Even innocuous stuff?
            - A. It's probably faster to re-key everything than to select what need not be rekeyed...
    - Q. Stalkers, attackers, crypto experts, and developers of alternate UIs (if we provide an API and a UI) won't be deterred by re-keying if they have a local cache. We accept this is okay and do it anyway?
    - Q. Will I ever lose access to words I post, the way I did with Facebook?
        - A. No.

- Q. What can someone intercepting a PGP-encrypted message (say, by examining a user's wall) learn?
    - A. **The list of those who have read access. But not who sent it.** from [rfc4880][] §5.1:

        > The body of [a public-key encrypted session key] packet consists of: ... An eight-octet number that gives the Key ID of the public key to which the session key is encrypted. ...

- Q. Can strangers post to your wall? (Strangers can encrypt data with your public key...)

[150 friends]: http://en.wikipedia.org/wiki/Dunbar's_number "Dunbar's Number"
[Off The Record]: http://en.wikipedia.org/wiki/Off-the-Record_Messaging "Wikipedia: Off-the-Record Messaging"
[rfc4880]: http://www.ietf.org/rfc/rfc4880.txt "OpenPGP Message Format"

## Sketches

### PGP messaging as the basis for Facebook-like "walls"

Assuming:

- All messages are encrypted with session key, but retrievable by anyone
- Session keys are regenerated for each message posted and stored public-key-encrypted with messages

Then:

- "Alice A posts message M on Bob B's wall" means:
    1. A generates new random symmetric data encryption key DEK.
    2. A encrypts M with DEK to get encrypted message W
    3. A encrtpts DEK with B's public key to get e(DEK,B) and optionally also some or all of A's friends' PKs to get e(DEK,AF1), e(DEK,AF2), ... e(DEK,AFi).
    4. W is stored along with E(DEK,\*) in some content-addressable data store (By the hash value of the encrypted message? Or the original? Data leakage?
    5. A pointer (or hash value, or id, or URL) is added to B's wall.
    6. When B next reads his wall (or aggregated feed?) his client obtains the session key DEK, and uses it to decrypt W and get M.
    7. Automatically(?) B encrypts DEK for all of B's friends and stores those e(DEK,BFi) encrypted keys with the message. This could be analogous to Facebook's "share."

Implications:

- When Eve E visits B's wall,
    - She can learn:
        - How many messages have been posted
        - The list of users who can read those messages - exposes Bob's friends list
        - The approximate size of the message or its image under compression
    - She can **not** trivially learn:
        - The sender of those messages

Questions:

- Could the walls (lists of pointers) themselves be encrypted?

- Idea: PGP crypto using FB language
    - "Share" means "re-encrypt existing session key for more people." Expands the list of who can see a particular message.
        - Can't reduce the list of people; that way lies DRM. But UI/app on top of API could kinda do it by re-keying old content. Would have to assume most users wouldn't have kept local copies. Would not thwart determined attackers. Could not enforce same behavior for alternative UIs.
    - A's "wall" is a serialized list of messages that A has shared. (And included herself in recipient list?)
        - Does A's wall reference *all* or only *some* of the messages A has shared? A: seems like *some* therefore walls must be a data structure; can't build A's wall simply by collecting all the messages that A can read.
    - A cannot "post to B's wall" directly, but can "share with B" and notify him that the message is "intended for his wall", and B can approve its placement (sharing the post with his friends).
    - A can share with A's friends but not notify them while notifying B. A's friends will see the activity in their news feed.
    - A can request, but not enforce, that a message not be re-shared with others.
    - A can request that posts authored by her be deleted

- Facebook, twitter are notorious for (in the past) having posts that could not be edited. Can posted messages be edited? (no, but UI could make it appear that they can, with a delete and re-post?)

### Exposing the recipient list problem

PGP-encrypting a message to a group of recipients exposes the list of recipients to any interceptor of that message; we consider this untenable. How do we deal with this?

This problem is related to (reducable to) the problem where PGP e-mail encrypted to a list of BCC recipients the list of recipients. One paper that addresses this is [Barth, A., and Boneh., D. Correcting Privacy Violations in Blind-Carbon-Copy (BCC) Encrypted Email][barth]. Reviewing this paper and those that cite and are cited by it may reveal a solution or workaround.

[barth]: http://crypto.stanford.edu/portia/papers/bb-bcc.pdf "Correcting Privacy Violations in Blind-Carbon-Copy (BCC) Encrypted Email"

# Glossary

- **PK**: public key (c.f. **SK**, "secret key")
- **SK**: secret key (c.f. **PK**, "public key")
- **DEK**: (sometimes a.k.a. "MEK") data encryption key. A random symmetric key used in PGP style encryption to encrypt data, which is then encrypted for specific recipients using assymetric encryption.
