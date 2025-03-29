---
title: Best User Profile Setup
---

One of the most common questions posed by new (and even sometimes not so new) community members is about the best profile setup.

Profiles are probably one of GrapheneOS users' most commonly used and talked about features. Although the profile feature is added by AOSP, GrapheneOS has [improved them](https://grapheneos.org/features#improved-user-profiles).

The answer to the question is that there is no single "best" setup. Each individual person has their own specific needs and use their devices in their own way. It's impossible for anyone to say one profile setup is the best because it's entirely subjective.

It is important to remember that all apps on Android are sandboxed, regardless of which profile they're installed in. For most use-cases, using profiles to further isolate apps is unnecessary. However, isolating apps to different profiles does have a few advantages, some of which are listed below:

- Apps within profiles can communicate with each other via inter-process communication (IPC).
- Apps can list other installed apps within the same profile without needing special permission.
- Some apps don't allow multiple users to be logged in, so profiles can be used to get around this kind of limitation.

---

## Some Common Setups

Some of the most common setups are as follows:

### Isolated Google Apps

One of the most common profile setups discussed within the GrapheneOS community is one where the user's main profile – often the user's "Owner" profile – has only open source apps, and another profile with Sandboxed Google Play installed, along with any other apps that rely on Google Play, such as banking apps, social media apps, etc.

### Empty Owner Profile

Many GrapheneOS users choose to keep their Owner profile almost completely empty, then use a secondary profile as their main profile.

This setup has a huge advantage in that Owner can set many global or other "dangerous" settings (like enabling ADB, or adjusting USB-C settings, for example). If the Owner profile is protected by a strong password, it would be much harder or impossible for an adversary to change those settings, even if they can access a separate profile.

Another advantage to this setup is that if a personal profile needs to be deleted for any reason, it's easy to do so, either from within the specific profile itself, or from the Owner profile. No need to do a factory reset, and any other profiles that might be on the phone won't be affected.

### Owner as an app pusher

Some users who tend to use profiles a lot like to set up their Owner profile to push apps to other profiles. Some install Sandboxed Google Play in their Owner profile, but not in other profiles so they can push apps to profiles where Sandboxed Google Play is not installed. And since GrapheneOS allows users to [disable user installed apps](https://grapheneos.org/features#user-installed-apps-can-be-disabled), users can disable Google Play and Google Play Services when not in use.

You can only push apps to other profiles from the Owner profile. You can do so from the Owner profile by going to `Settings > System > Users > Profile > Install available apps`.

### No Secondary Profiles

One option that many never even consider is to not use secondary profiles at all. Using profiles can add some unnecessary annoyances for some people because of how notifications work or switching between profiles is annoying, or PINs / passwords are too long or annoying. Keep in mind that all apps are sandboxed, so for many threat models, profiles aren't even necessary. So, for some users a no profiles setup is actually the best fit. There is also the option to use the Private Space function as an alternative to using a secondary profile. Note that, currently, there's a limit of one private space and it can only be in the Owner profile. Also, the clipboard is shared between the Owner user and the Private Space, which is a significant vector for data to leak if not operated carefully.

---

## Final Thoughts

Don't worry too much about setting up user profiles perfectly the first time. Many in the community have said that they've gone through multiple setups before finally settling on what they think works for them.