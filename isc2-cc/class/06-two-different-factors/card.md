# Lesson 6. Two Different Factors

**Listen:** two-different-factors.mp3 (2 min)

**The idea, in three lines**
- Three kinds of factor: **something you know** (password, PIN, security answer), **something you have** (phone, token, smart card), **something you are** (fingerprint, face, voice).
- MFA means at least two **different** kinds. Two passwords, or a password plus a PIN, is one kind twice, so it is not MFA.
- Authentication proves who you are; authorization decides what you may do. For passwords, length beats forced complexity, and current NIST guidance (SP 800-63B) drops forced periodic resets unless there's a sign of compromise.

**Impact:** you can spot the fake MFA option in an exam question, and in your own account settings.

**Who says it:** 4 of the 7 pages on authentication teach the three kinds this way; none disagree. One page (isdecisions) adds two extra kinds, somewhere you are (location) and something you do (typing rhythm); the exam core is the classic three.

**Try it** · Quick Win · 10 min
Open the security settings of your main email account and list every way it lets you sign in. For each line:
> **1.** Write the method (password, text code, authenticator app, security key, fingerprint).
> **2.** Next to it, write its kind: know, have or are.
> **3.** If every line says "know", it's one factor however many steps it takes. If you'd like, turn on one method from a different kind.

**Rule to keep**
Two factors means two different kinds.

**Skip** · no cost, no catch-up. Lesson 7 is just lesson 7.

**Go deeper (optional)**
- Factor kinds, MFA, and authentication vs authorization (Duo): https://duo.com/learn/access-control-models
- The factor categories, including the extra ones (IS Decisions): https://www.isdecisions.com/en/glossary/mfa-factors
- "Two passwords are not MFA" and the NIST password note: https://open-exam-prep.com/blog/isc2-cc-certified-in-cybersecurity-guide-2026
