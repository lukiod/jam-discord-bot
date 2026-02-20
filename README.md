<div align="center">

# jam bot

<img src="https://img.shields.io/badge/jam-discord%20bot-ff6b6b?style=for-the-badge&logo=discord&logoColor=white" alt="jam discord bot"/>

<br/>

[![discord](https://img.shields.io/discord/1234567890?label=join%20the%20jam&logo=discord&logoColor=white&color=5865F2&style=flat-square)](https://discord.gg/5sdGUP4pG5)
[![python](https://img.shields.io/badge/python-3.11-3776AB?style=flat-square&logo=python&logoColor=white)](https://python.org)
[![discord.py](https://img.shields.io/badge/discord.py-2.3.0+-5865F2?style=flat-square&logo=discord&logoColor=white)](https://discordpy.readthedocs.io)
[![postgres](https://img.shields.io/badge/postgresql-4169E1?style=flat-square&logo=postgresql&logoColor=white)](https://postgresql.org)
[![license](https://img.shields.io/github/license/wespreadjam/jam-discord-bot?style=flat-square&color=ff6b6b)](LICENSE)

[![github stars](https://img.shields.io/github/stars/wespreadjam/jam-discord-bot?style=flat-square&logo=github&color=ffdd57)](https://github.com/wespreadjam/jam-discord-bot)
[![last commit](https://img.shields.io/github/last-commit/wespreadjam/jam-discord-bot?style=flat-square&color=a8e6cf)](https://github.com/wespreadjam/jam-discord-bot)
[![repo size](https://img.shields.io/github/repo-size/wespreadjam/jam-discord-bot?style=flat-square&color=dcd0ff)](https://github.com/wespreadjam/jam-discord-bot)
[![code lines](https://img.shields.io/badge/lines%20of%20code-1017-f9a8d4?style=flat-square)](https://github.com/wespreadjam/jam-discord-bot)

<br/>

*a community engagement bot that turns your discord server into a jam-flavored xp machine*

[join the discord](https://discord.gg/5sdGUP4pG5) · [report a bug](https://github.com/wespreadjam/jam-discord-bot/issues) · [request a feature](https://github.com/wespreadjam/jam-discord-bot/issues)

</div>

---

## what is jam bot?

jam bot is a discord bot that gamifies your community. it tracks messages, awards xp, manages referrals, and hands out jam-themed roles as members level up. think of it as a little engine that rewards people for actually participating.

it also handles onboarding — new members have to introduce themselves and share a project before they get verified. no lurkers allowed (well, fewer lurkers).

## how it works

```
message sent → xp awarded → level up → jam role assigned → announced to the server
```

every message earns **10 xp** (with a 60-second cooldown so you can't spam your way to the top). longer messages (50+ chars) earn a **5 xp bonus**. refer a friend and get **50 xp** on top of that.

## the jam tier system

| level | role | xp needed |
|:---:|---|---:|
| 1 | strawberry jam | 100 |
| 2 | blueberry jam | 500 |
| 3 | golden jam | 1,500 |
| 4 | diamond jam | 8,000 |
| 5 | platinum jam | 15,000 |
| 6 | infinity jam | 25,000 |

## commands

| command | what it does |
|---|---|
| `/rank` | check your xp, level, referrals, and message count |
| `/mylink` | get your personal referral invite link |
| `/myreferrals` | see everyone you've referred |
| `/leaderboard` | top 10 members by xp |
| `/ref-leaderboard` | top 10 members by referrals |
| `/joined` | check when a member joined the server |
| `/bread` | receive a random bread blessing |
| `/am-i-jam` | deep philosophical question |

### admin commands

| command | what it does |
|---|---|
| `/setxp` | manually set a user's xp |
| `/setreferrals` | manually set a user's referral count |
| `/setup-welcome` | post welcome embeds to a channel |
| `/test-welcome` | dm yourself the welcome message |

## features

- **xp & leveling** — message-based xp with cooldowns, bonus xp for longer messages, automatic role assignment
- **referral tracking** — personal invite links, referral credit with xp rewards, persistent tracking via database
- **onboarding gate** — new members must post in #intros and #projects to get verified
- **thread management** — auto-archives threads in specified channels to keep things tidy
- **welcome system** — dms new members with onboarding info and their personal referral link

## setup

### prerequisites

- python 3.11+
- a postgresql database
- a discord bot token from the [developer portal](https://discord.com/developers/applications)

### install

```bash
git clone https://github.com/wespreadjam/jam-discord-bot.git
cd jam-discord-bot
pip install -r requirements.txt
```

### environment variables

```env
DISCORD_BOT_TOKEN=your_bot_token_here
DATABASE_URL=your_postgres_connection_string
```

### server setup

create these roles in your discord server:
> strawberry jam · blueberry jam · golden jam · diamond jam · platinum jam · infinity jam · verified

create these channels:
> #intros · #projects · #commands

### run

```bash
python bot.py
```

then run `/setup-welcome` in any channel to post the welcome embeds.

### deploy

the bot includes a `Procfile` for easy deployment to railway or heroku:

```
worker: python bot.py
```

on railway, the `DATABASE_URL` is set automatically when you add the postgres plugin.

## tech stack

| | |
|---|---|
| language | python |
| framework | discord.py |
| database | postgresql |
| hosting | railway / heroku |

## credits

credits to **hassan2bit bread** on discord for naming infinity jam

---

<div align="center">

**[join the jam](https://discord.gg/5sdGUP4pG5)**

made with love and preserves

</div>
