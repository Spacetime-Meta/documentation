<center>
    <p style="font-size: xx-large">SPACETIME METAVERSE</p>
    <img src="../src/spacetime_logo.png" style="height: 200px;">
    <p style="font-size: x-large">Identity Whitepaper</p>
    <p style="font-size: large"><a>spacetimemeta.io</a></p>
</center>
<br><br>

**This document was made by [LiquidBlocks](https://twitter.com/FrdricCt15)**

---

Welcome to the Identity whitepaper part 1, This is a continuation of
previous work on the Spacetime Metaverse project and is meant to
add value to the whole Cardano Ecosystem. Due to the integration of
other projects in the metaverse identity system, this paper was split
into 2 parts. Part 1: Introduction to $handle and how we plan to
integrate them. Part 2: Building game content on top of identities

## Part 1. Intro

In the Spacetime Metaverse users can already possess parts of
the metaverse and customize them to host 3D environments or
websites. We already have examples of this like project solaris
and spawn planet. These worlds can be explored in first person
and games can be played there. Now we want a way to collect
items and rewards in these games and attach this information to
our profiles in an immutable and transparent way. Doing so will
make our progression persistent and compatible with any
environment.
In this document, we present the different moving parts of this
system and explain the reasons behind the conceptual decisions.

## Part 2. $handle

In the Cardano community, the $handle project is the dominant
project regarding identities. For this reason, we decided to not mint
our own Spacetime Metaverse Identity Token but instead build it
directly on top of the existing handle project using only transaction
metadata and multisig transactions. We first took this decision for
the benefit of the Spacetime project as it will feed our ecosystem
with 30k individual users, but we believe this choice to be beneficial
to the whole Cardano community as it will provide additional features
to one of the most recognized projects in the space.
On the technical side, using handles will take care of the uniqueness
of each profile (since all handles are unique) and will allow easy
mapping of metaverse profiles to cardano addresses, as this is the
principal utility of the handle project.

## Part 3. Types Of Profiles

There are 2 types of profiles. The profiles for individuals and the
profiles for projects and groups. All profile types are entirely based on
Cardano transaction metadata, meaning you don’t need anything
else than an $handle to create a profile.
By default, a $handle represents a user profile and will appear on the
leaderboards. To create a project profile or a group profile, creators
must fill and successfully submit a transaction containing the $handle
they want to register as project and the necessary metadata in the
right format.
In the following sections, we go over each type to describe their
utilities and basic implementations. Keep in mind this paper only
scratches the surface of what can be done with Metaverse identities.
Much more can be extrapolated from this implementation and
spacetime intends to keep developing multiple other features in the
years to come.

## Part 3.1. User profiles

On the Cardano Blockchain, Stake keys are representatives of a single
user. What we want in the Spacetime metaverse, is something to
point at profiles, so that one user can control multiple Metaverse
profiles. Just like most video games, it can be fun to create different
game characters to explore different classes and options, without
sacrificing those we already have.
This is where handles come into play, Spacetime will consider every
individual handle as individual metaverse profiles. This allows one
user to own multiple profiles and give them different attributes. Here
is a closer look to what can be done with a metaverse profile.

### **What you can do with a Spacetime Meta profile:**
1. **Set a profile picture.** Using transaction Metadata, you can link a profile picture
to appear on your profile presentation and in
leaderboards. If you don't select a picture, a default one
will appear by your name on the leaderboard.
2. **Set a profile name.** Using transaction Metadata, you can select a profile name
to appear on your profile presentation and in the
leaderboards. Note the name is different from the handle
IDs. Names are not unique.
3. **Support your favorite project.** Using transaction Metadata, it will be possible to select a
list of favorite projects to appear on your profile
presentation. This selection will also be reflected on the
projects profiles, as most supported projects will be on top
of the leaderboard.
4. **Appear in leaderboards.** Once your profile is registered in transaction metadata, it
will appear in leaderboards across Spacetime Metaverse.
being registered on a public system like the Cardano
blockchain enhances the metaverse experience by
allowing for all content creators to display your profiles
the same way.
5. **Join Groups.** You can link your profile token to multiple groups created
around existing collections.

All the metadata attached to your token will be transferred in a
transaction if you ever sell your profile to another user. Profiles with
multiple/rare success and high level skills might become valuable
game items.

Here is an example of what a valid metadata for full customization of
a profile might look like:
```
{
    77223003:{
        “handle”: “$user-handle”,
        “name”: “demo user”,
        “image”: “Qme7ss3ARVgxv6rXqVPiikMJ8u2NLgmgszg13pYrDKEoiu”,
        “projects”: [
            “$spacetimemeta”,
            “$project-handle”
        ]
    }
}
```

## Part 3.2. Project Profiles

Since the Cardano Blockchain is a public network, anyone can make a
transaction including metadata in a format that would give
themselves some illegitimate rewards. To prevent these illegitimate
rewards from being registered in the leaderboards, all the scoring and
rewarding transactions from a certain creator must be coming from
the creators registered address. Fortunately, we have $handles to
easily map project information to the address of its owner.

To be registered as a project, you need to mint a profile token with
the project tag in its metadata. This form of profile has all the basic
functionalities.

### **What you can do with a project token:**
7. **Set a project picture.** Using transaction Metadata, you can link a project picture
to appear on the presentation page of your profile and on
the profile of those who support your project. This is also
the picture for your project when it appears in
leaderboards.
8. **Set a project name.** Using transaction Metadata, you can select a project name
to appear on your project presentation and in the
leaderboards.
9. **Get support from your community.** Using transaction Metadata, your community will be able
to select projects they like and link your project to their
profile.
10. **Appear in leaderboards.** Once your profile is registered in transaction metadata, it
will appear in leaderboards across Spacetime Metaverse.
being registered on a public system like the Cardano
blockchain enhances the metaverse experience by
allowing for all content creators to display your profiles
the same way.

Here is an example of valid metadata for a project profile registration:
```
{
    77223004:{
        “handle”: “$project-handle”,
        “type”: “project”,
        “name”: “demo project”
    }
}
```
When submitting the metadata presented above, a very simple
project profile is created with the name ‘demo project’ and all other
fields empty. Using the $handle registered as a project, the creator
can now affect the users $handles by attaching metadata to a
transaction and pointing this metadata to the wanted user handles.

More information about rewards distribution in the second part of
this whitepaper or in future modifications.