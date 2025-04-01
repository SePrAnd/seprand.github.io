---
title: Best User Profile Setup on GrapheneOS
---

One of the most common questions posed by new (and even sometimes not so new) GrapheneOS users is about the "best" profile setup.

The User Profiles feature is probably one of GrapheneOS users' most commonly used and talked about features. Although it was added by AOSP, GrapheneOS has [made improvements](https://grapheneos.org/features#improved-user-profiles).

There are [multiple types](https://source.android.com/docs/devices/admin/multi-user#categories_of_users) of user profiles. The "system user", as Android documentation calls it, is the only profile on newly set up or factory reset devices. The default name in English for this profile is "Owner", so in this article we'll refer to it as the "owner profile". Other non-owner profiles will be referred to as "secondary user profiles".

When creating a new user profile you go through the setup wizard similar to when first setting up the device. The new user profile has the same default apps as the owner profile and no user data.

It is important to remember that all apps on Android are sandboxed, regardless of which profile they're installed in. For most use-cases, using secondary user profiles to further isolate apps is unnecessary. However, isolating apps to different profiles does have a few advantages, some of which are listed below:

- Apps within a profile can communicate with each other via inter-process communication (IPC).
- Apps can list other installed apps within the same profile without needing special permission.
- Some apps don't support multiple accounts to be logged in, so profiles can be used to get around this kind of limitation.
- Each profile has its own set of contacts, files and media directories. Apps in different profiles, which have been granted the necessary permissions, can only access data from that profile. The [Storage](https://grapheneos.org/features#storage-scopes) and [Contact](https://grapheneos.org/features#contact-scopes) Scopes features in GrapheneOS allow users to choose exactly what contacts, files and media any app can access, providing a more convenient way of achieving isolation of these data types.

In some rare cases, some apps will not work when used in a secondary user profile and will require you to use them in your owner profile.

There is no single "best" profile setup. Each individual person has their own specific needs and use their devices in their own way. It's impossible for anyone to say one setup is the best because it's entirely subjective.

## Some Common Setups

### Isolated Google Apps

One of the most common profile setups discussed within the GrapheneOS community is one where the user's main profile – often the user's owner profile – has only open source apps, and another profile with Sandboxed Google Play installed along with any other apps that rely on Google Play, such as banking apps, social media apps, etc.

### Empty Owner Profile

Many GrapheneOS users choose to keep their owner profile almost completely empty, then use a secondary user profile as their main profile.

One advantage to this setup is that if a secondary user profile needs to be deleted for any reason, it's easy to do so, either from within the specific profile itself, or from the owner profile. There's no need to do a factory reset, and any other profiles that might be on the device won't be affected.

Another advantage is that the owner profile can set many global or other "dangerous" settings (like enabling ADB, or adjusting USB-C settings, for example). By regularly using a profile other than the owner profile, these settings are harder to access. However, keep in mind that most "dangerous" settings are still protected by the owner profile's PIN or password.

### Owner as an App Pusher

Some users who tend to use profiles a lot like to set up their owner profile to push apps to other profiles. Some install Sandboxed Google Play in their owner profile, but not in other profiles so they can push apps to profiles where Sandboxed Google Play is not installed. And since GrapheneOS allows users to [disable user installed apps](https://grapheneos.org/features#user-installed-apps-can-be-disabled), users can disable Google Play and Google Play Services when not in use.

You can only push apps to other profiles from the owner profile. You can do so from `Settings > System > Users > Profile > Install available apps`.

### No Secondary User Profiles

One option that many never even consider is not using secondary user profiles at all. Using profiles can add some unnecessary annoyances for some people because of how notifications work or switching between profiles is annoying, or PINs / passwords are too long or annoying. Keep in mind that all apps are sandboxed, so for many threat models, profiles aren't even necessary. So, for some users, a no profiles setup may actually be the best fit for them.

There is also the option to use the Private Space feature as an alternative to using a secondary user profile. This is a special type of profile nested under the owner profile. Apps in the Private Space and owner profile can be accessed simultaneously. Note that, currently, there's a limit of one Private Space and it can only be in the owner profile. Also, the clipboard is shared between the owner profile and the Private Space, which is a significant vector for data to leak if not operated carefully.

## Final Thoughts

Don't worry too much about setting up user profiles perfectly the first time. Many in the GrapheneOS community have said that they've gone through multiple setups before finally settling on what they think works for them.

Our suggestion for people who are switching to GrapheneOS would be to start out without using secondary user profiles and evaluate whether their needs require their use later. As explained above, the Private Space feature is a great way to get the advantages of separate profiles without any of the inconvenience that they can come with.