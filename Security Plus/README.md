
what is the difference between GET and POST on wireshark HTTP
In Wireshark's HTTP analysis, GET and POST are different HTTP request methods that show up in the packet details, and they differ primarily in how data is sent and their purpose:

Key Differences in Wireshark HTTP Packets
Aspect	GET	POST
Purpose	Requests data/content without modifying server state 
Sends data to server to create/update resources or trigger processing 
Data Location	Query string in the URL (visible as ?name=value pairs) 
Data in the request body (separated from headers by Wireshark) 
Wireshark Visibility	Parameters visible directly in the URL line	POST data appears under "Hypertext Transfer Protocol" → POST data field 
Data Length	Limited (~2048 characters max URL length) 
No restrictions 
Security	Less secure (data visible in URL, server logs, browser history) 
More secure (parameters not in browser history or URL) 
Caching	Can be cached, bookmarked, remain in history 
Never cached, not bookmarked, not in history 
How to Filter in Wireshark
See both GET and POST: http.request

Only GET requests: http.request.method == "GET"

Only POST requests: http.request.method == "POST"

When you expand an HTTP packet in Wireshark, you'll see the request method at the top (e.g., GET /index.html HTTP/1.1 or POST /submit.php HTTP/1.1), and POST data will be clearly separated from the headers for easy analysis.

okay what does this line represents: 7199 3232.462007 10.2.28.88 199.232.210.172 HTTP 336 GET /msdownload/update/v3/static/trustedr/en/authrootstl.cab?238f51c2ab526be6 HTTP/1.1
This Wireshark line represents a single HTTP GET request packet. Here's what each field means:

Field	Value	What it represents
Packet #	7199	This is packet number 7199 in your capture
Timestamp	3232.462007	Time elapsed since capture started (≈54 minutes, 32 seconds) 
Source IP	10.2.28.88	Your local machine (private IP) making the request
Destination IP	199.232.210.172	Windows Update server hosting the file
Protocol	HTTP	The packet uses HTTP protocol
Length	336	Packet size in bytes
Request	GET /msdownload/update/v3/static/trustedr/en/authrootstl.cab?238f51c2ab526be6 HTTP/1.1	The actual HTTP request being made
What This Request Is Actually Doing
The client is downloading authrootstl.cab from Microsoft's Windows Update — this is a Certificate Trust List (CTL) file containing fingerprints of trusted root certification authorities. Specifically:

Purpose: Windows automatically updates its list of trusted third-party root certificates

File type: CAB (compressed archive) containing authroot.stl (Certificate Trust List)

Query parameter (?238f51c2ab526be6): A hash/token used for cache validation or version tracking

This is normal Windows behavior — your system periodically syncs with Windows Update to maintain an up-to-date list of trusted root certificates for SSL/TLS verification.

what is a common malware port
Malware doesn't have a single "common port" — instead, attackers use various ports depending on their goals. Here are the most important ones to know:

Most Common Malware Ports (Modern Attacks)
Port	Protocol	Why Malware Uses It	Common Malware Types
443	HTTPS	Encrypted traffic, hard to inspect 
C2 communication, ransomware
80	HTTP	Looks like normal web traffic 
Reverse shells, botnets
53	DNS	DNS tunneling for covert channels 
Data exfiltration, C2
4444	TCP	Metasploit default for reverse shells 
Reverse shells, exploit frameworks
3389	RDP	Ransomware entry point via brute force 
Ransomware (lockbit, contii)
445	SMB	Worms like WannaCry spread here 
ransomware, worms
6667	IRC	Botnet command & control 
IRC botnets
Classic Trojan Ports (Historical)
Port	Trojan Name
31337	Back Orifice ("bo facil") 
12345	NetBus trojan 
6776	Sub7/SubSeven 
1243	SubSeven server 
Key Takeaway for Your Wireshark Work
Modern malware blends in with legitimate traffic by using ports 80/443/53. The most suspicious port to watch for in Wireshark is 4444 (Metasploit), as it's rarely used legitimately. For ransomware detection, monitor 3389 (RDP) and 445 (SMB) heavily.

okay i have deleted that repositiry, start fresh
Perfect — starting fresh is a clean solution. Here's how to set up your Cyber-Prep repository again from scratch:

Step 1: Create a new local folder
bash
mkdir Cyber-Prep
cd Cyber-Prep
Step 2: Initialize the repository
bash
git init
Step 3: Create your first file and commit
bash
# Create a README (optional but good practice)
echo "# Cyber-Prep" > README.md
echo "Cybersecurity preparation notes" >> README.md

# Create your Domain 1 notes file
mkdir -p "Security Plus"
echo "Domain 1 Notes" > "Security Plus/Domain_1.md"

# Add and commit
git add .
git commit -m "Initial commit: Domain 1 notes"
Step 4: Connect to GitHub
On GitHub, create a new repository named Cyber-Prep (don't initialize it with README).

Then add it as your remote:

bash
git remote add origin https://github.com/Malaika1712137/Cyber-Prep.git
Step 5: Push to GitHub
bash
git push -u origin master
Future workflow (clean pattern)
Every time you make changes:

bash
# 1. Make changes to files
# 2. Stage them
git add .

# 3. Commit
git commit -m "Your commit message"

# 4. Pull first (to avoid conflicts)
git pull origin master

# 5. Push
git push origin master
Key rule: Always git pull before git push to keep your local branch in sync with the remote.

Let me know if you'd like me to walk through any step or if you want to add more files initially!

get rid of this rebase, what is thisL (|REBASE)
The (|REBASE) in your terminal means you're stuck in a corrupted rebase state. Since git rebase --abort didn't work (because the rebase files are missing), you need to manually delete the broken state:

Get rid of the REBASE indicator:
bash
rm -rf .git/rebase-merge
rm -rf .git/rebase-applied
Then check your status:

bash
git status
The (|REBASE) should disappear.

What is REBASE?
Rebase is a Git operation that moves your commits onto a newer version of a branch. It happens when you run:

git pull --rebase

git rebase master

During rebase, Git temporarily stores your commits and applies them one by one. If a conflict occurs, rebase pauses and waits for you to resolve it. The (|REBASE) indicator shows you're in this paused state 
.

In your case, the rebase got corrupted (the temporary files were deleted), leaving you stuck. Manually deleting .git/rebase-merge cleans it up.

After running the rm commands above, you'll be back to normal and can start fresh.

give me a readme
Completed 2 steps
README
Cyber-Prep
A personal cybersecurity study repository for organizing notes, labs, and preparation materials.

Contents
Security+ notes

Domain-based study materials

Lab practice and walkthroughs

Git/GitHub tracked coursework

Structure
text
Cyber-Prep/
├── README.md
└── Security Plus/
    └── Domain_1.md
Usage
Use this repository to keep cybersecurity notes organized by certification domain or topic.

Git workflow
bash
git add .
git commit -m "Update notes"
git pull origin master
git push origin master
Notes
Keep commits small and descriptive so it is easier to track study progress over time.


Currently open
I made a clean README you can use for your fresh Cyber-Prep repository.

README


# Cyber-Prep

A personal cybersecurity study repository for organizing notes, labs, and preparation materials.

## Contents

- Security+ notes
- Domain-based study materials
- Lab practice and walkthroughs
- Git/GitHub tracked coursework

## Structure

```text
Cyber-Prep/
├── README.md
└── Security Plus/
    └── Domain_1.md
```

## Usage

Use this repository to keep cybersecurity notes organized by certification domain or topic.

## Git workflow

```bash
git add .
git commit -m "Update notes"
git pull origin master
git push origin master
```

## Notes

Keep commits small and descriptive so it is easier to track study progress over time.