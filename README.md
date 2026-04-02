Open Mic Sign Up

A lightweight open mic signup tool built for GitHub Pages.

Hosts can create an event, generate a QR code, and let performers sign themselves up from their phones. The host can then manage the lineup, reorder acts, mark performers as checked in or live, and keep the night moving without passing around a paper sheet.

Features
	•	Host sign in with Firebase Authentication
	•	Public signup page for performers
	•	QR code for easy signups at the venue
	•	Host admin page for event setup and lineup management
	•	Drag and drop lineup reordering
	•	Status controls like Checked In, Live, Done, and Waitlist
	•	Poster view for printing or tablet display
	•	CSV export of the lineup
	•	Event ownership model for host control

Live App

Hosted on GitHub Pages:

https://petesimple.github.io/openmic/

How It Works

The app uses:
	•	GitHub Pages for hosting
	•	Firebase Firestore for shared live event and signup data
	•	Firebase Authentication for host login and event ownership

Performers do not need to sign in. They just scan the QR code or open the public event link and add themselves to the list.

Default Open Mic Setup

The default event settings are built around a typical weekly open mic:
	•	Signups open at 6:00 PM
	•	Show starts at 7:00 PM
	•	Each act gets 3 songs or 15 minutes
	•	The host can adjust all of these settings per event

Firebase Setup

1. Create a Firebase project

Create a new Firebase project for the app.

2. Enable Firestore

Turn on Cloud Firestore.

3. Enable Authentication

Under Authentication, enable Google sign in.

Also add this domain under authorized domains:

petesimple.github.io

4. Add Firebase config

Paste your Firebase web app config into index.html.

Firestore Rules

Use the Firestore rules block from the current app version you are testing.

For the owner based host model, the project uses rules that allow:
	•	public read access to events and signups
	•	public creation of signups
	•	host-only editing of event data and signup management

If you later move to multi-host support, update the rules accordingly.

Local Development

This app is currently designed to be simple to host as a static site.

You can work on it locally by opening the project in a local server, for example with VS Code Live Server or another static file server.

Basic Host Flow
	1.	Sign in as host
	2.	Create or load an event
	3.	Save event settings
	4.	Copy the public link or show the QR code
	5.	Let performers sign up from their phones
	6.	Reorder and manage the lineup during the event
	7.	Export the lineup as CSV if needed

Suggested Test Flow
	•	Create a test event
	•	Open the public signup page on a phone
	•	Add several performers
	•	Reorder the lineup
	•	Mark performers as Checked In, Live, and Done
	•	Test the poster view
	•	Test CSV export

Current Status

Current pinned test baseline:

v1.3

This includes:
	•	Google host sign in
	•	owner based event control
	•	public signups
	•	poster view
	•	drag and drop lineup management

Roadmap Ideas

Planned or possible future ideas include:
	•	co-host support
	•	self-cancel or self-edit performer links
	•	event archive page
	•	better host dashboard
	•	SMS style queue tools
	•	venue presets and branding

Why This Exists

Paper signup sheets work, but they also get messy, vanish, get beer on them, and force somebody to decode handwriting under stage lights.

This app tries to make open mic signup a little cleaner, faster, and less chaotic.

License

MIT

Author

Built by Pete.
