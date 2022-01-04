<script>
  const commandList = [
    {
      name: "Moderation",
      commands: [
        {
          name: "Kick",
          description:
            "Remove a member from the server. The member can join the server again if they have an invite.",
          usage: "kick {@mention/ID/username/nickname} [reason]",
          requiredPerms: "Kick members",
        },
        {
          name: "Ban",
          description:
            "Remove a member from the server, but they cannot rejoin even if they have an invite unless they are unbanned.",
          usage: "ban {@mention/ID/username/nickname} [reason]",
          requiredPerms: "Ban members",
        },
        {
          name: "Unban",
          description:
            "Unbans a banned member so they can join again. You'll need to provide the exact username and tag.",
          usage: "unban {username#tag}",
          requiredPerms: "Ban members",
        },
        {
          name: "Mute",
          description:
            "Removes the permissions for a member to send messages in the server or talk in Voice Channels.",
          usage: "mute {@mention/ID/username/nickname} [reason]",
          requiredPerms: "Manage messages",
        },
        {
          name: "Tempmute",
          description:
            "Mutes a member, but temporarily. You'll need to provide how long to mute the member for.",
          usage: "tempmute {@mention/ID/username/nickname} [duration] [reason]",
          aliases: "tmute",
          requiredPerms: "Manage messages",
        },
        {
          name: "Unmute",
          description: "Unmutes a muted member.",
          usage: "unmute {@mention/ID/username/nickname}",
          requiredPerms: "Manage messages",
        },
        {
          name: "Warn",
          description:
            "Sends a warning to the member's DMs with the provided reason and logs it in a database. This command also sends you a Warning ID which you can use to delete the warning from the member later.",
          usage: "warn {@mention/ID/username/nickname} [reason]",
          requiredPerms: "View audit log",
        },
        {
          name: "Delwarn",
          description:
            "Deletes a warning from the member with the Warning ID, which you can get with the 'warnings' command or the message sent by 1Bot when a member is warned.",
          usage: "delwarn [Warning ID] {@mention/ID/username/nickname}",
          aliases: "unwarn",
          requiredPerms: "View audit log",
        },
        {
          name: "Warnings",
          description: "Shows the last 15 warnings for a member.",
          usage: "warnings {@mention/ID/username/nickname}",
          aliases: "warns",
        },
        {
          name: "Clearwarns",
          description: "Deletes all warnings for a member.",
          usage: "clearwarns {@mention/ID/username/nickname}",
          requiredPerms: "View audit log",
        },
        {
          name: "Nickname",
          description:
            "Changes the nickname of a member. If you leave the [nickname] option blank, the nickname will be reset to their username.",
          usage: "nickname {@mention/ID/username/nickname} [nickname]",
          requiredPerms: "Manage nicknames",
          aliases: "nick",
        },
        {
          name: "Slowmode",
          description:
            "Sets the slowmode for the current channel. The duration can be absolutely anything from 0s to 6h.",
          usage: "slowmode [duration]",
          aliases: "sm",
          requiredPerms: "Manage channels",
        },
        {
          name: "Role create",
          description: "A subcommand of 'role' to create a new role.",
          usage: "role create {name}",
          aliases: "role c",
          requiredPerms: "Manage roles",
        },
        {
          name: "Role delete",
          description: "A subcommand of 'role' to delete a role.",
          usage: "role delete {@mention/ID/role name}",
          aliases: "role d",
          requiredPerms: "Manage roles",
        },
        {
          name: "Role add",
          description: "A subcommand of 'role' to add a role to a member.",
          usage:
            "role add {@mention/ID/username/nickname} {@role mention/ID/role name}",
          aliases: "role a, role give",
          requiredPerms: "Manage roles",
        },
        {
          name: "Role remove",
          description: "A subcommand of 'role' to remove a role from a member.",
          usage:
            "role remove {@mention/ID/username/nickname} {@role mention/ID/role name}",
          aliases: "role r, role take",
          requiredPerms: "Manage roles",
        },
        {
          name: "Clear",
          description:
            "Deletes the last {amount} messages in the current channel at once.",
          usage: "clear {amount}",
          aliases: "purge",
          requiredPerms: "Manage messages",
        },
        {
          name: "Nuke",
          description:
            "Deletes all messages the specified current channel. If you don't provide a channel, it will clear the current channel.",
          usage: "nuke [#channel/ID/name]",
          aliases: "clearchannel",
          requiredPerms: "Manage messages",
        },
        {
          name: "Lockdown",
          description:
            "Disables permissions for members to talk in a channel. If no channel is provided, 1Bot will lock the current channel.",
          usage: "lockdown [#channel/ID/name]",
          aliases: "lock",
          requiredPerms: "Manage channels",
        },
        {
          name: "Unlock",
          description: "Undo the lockdown command.",
          usage: "unlock [#channel/ID/name]",
          requiredPerms: "Manage channels",
        },
        {
          name: "Snipe",
          description:
            "Shows the last deleted message in a channel. The channel defaults to the current channel.",
          usage: "snipe [#channel/ID/name]",
        },
        {
          name: "Edit snipe",
          description:
            "Shows the last edited message in a channel. The channel defaults to the current channel.",
          usage: "editsnipe [#channel/ID/name]",
          aliases: "esnipe",
        },
      ],
    },
    {
      name: "Utility",
      commands: [
        {
          name: "Calc",
          description:
            "Runs a simple math operation with two numbers. You will have to separate the numbers and operation by spaces.",
          usage: "calc {1st number} {operation} {2nd number}",
          aliases: "calculate",
        },
        {
          name: "Emoji",
          description:
            "Creates a custom emoji with the given name. Attach a valid image with the command OR provide a valid image URL.",
          usage: "emoji {name} [url]",
          aliases: "addemoji, createemoji, emote",
          requiredPerms: "Manage emojis and stickers",
        },
        {
          name: "Raw text",
          description:
            "You can reply to a message with this command and 1Bot will send the raw, unformatted text of the message you replied to. You can also use a Message ID instead of replying.",
          usage: "raw [message ID]",
          aliases: "rawtext",
        },
        {
          name: "Weather",
          description:
            "Gets weather information for a city. The city name is required, optionally add a state code and country code separated by commas.",
          usage: "weather {city}[state code,country code]",
        },
        {
          name: "GitHub",
          description:
            "Search for GitHub repositories right inside Discord. Enter a search query and 1Bot will send you the first result.",
          usage: "github {query}",
          aliases: "githubsearch, searchrepo",
        },
        {
          name: "Embed",
          description:
            "Starts a process to create an embed in the current channel. The messages sent in the process will be cleared.",
          usage: "embed",
          aliases: "makeembed, createembed",
        },
        {
          name: "Poll",
          description:
            "Creates a poll for members to vote with reactions. The title/question for the poll should be in double quotes and the options should be separated by slashes.",
          usage: 'poll "{question}" {options/separated by/slashes}',
        },
        {
          name: "NPM",
          description:
            "Get information about the specified NPM package. This is not a search command, so you will need to provide the exact name of the package.",
          usage: "npm {package name}",
        },
        {
          name: "PyPi",
          description:
            "Get information about the specified PyPi module. This is not a search command, so you will need to provide the exact name of the module.",
          usage: "pypi {module name}",
        },
        {
          name: "Base64 encode",
          description:
            "A subcommand of Base64. Encodes the given string to Base64.",
          usage: "base64 encode {string}",
          aliases: "b64 e",
        },
        {
          name: "Base64 decode",
          description:
            "A subcommand of Base64. Decodes the given string to normal text.",
          usage: "base64 decode {code}",
          aliases: "b64 d",
        },
        {
          name: "Lyrics",
          description:
            "Gets lyrics for the specified song. The song name is required. If the lyrics are too long, you will get reaction buttons to switch between pages of the lyrics so that you can view all the lyrics without 1Bot flooding your channel.",
          usage: "lyrics {query}",
          aliases: "ly",
        },
        {
          name: "Fahrenheit to Celsius",
          description: "Converts a temperature from Fahrenheit to Celsius.",
          usage: "fahrenheittocelsius {temperature}",
          aliases: "ftoc, f2c",
        },
        {
          name: "Celsius to Fahrenheit",
          description: "Converts a temperature from Celsius to Fahrenheit.",
          usage: "celsiustofahrenheit {temperature}",
          aliases: "ctof, c2f",
        },
      ],
    },
    {
      name: "Fun",
      commands: [
        {
          name: "Discord Together",
          description:
            "You will need to be inside a voice channel for this to work. This command starts a Discord Together game inside the current voice channel. A list of all supported games can be found by running /discord-together or 1help discordtogether.",
          usage: "discordtogether {game}",
          aliases: "dtogether",
        },
        {
          name: "Dog",
          description: "Get a random dog image.",
          usage: "dog",
          aliases: "doggo",
        },
        {
          name: "Cat",
          description: "Get a random Cat image.",
          usage: "cat",
          aliases: "kitty",
        },
        {
          name: "Bored",
          description: "Gives you something to do if you're bored.",
          usage: "bored",
        },
        {
          name: "Reddit",
          description:
            "Get a random post from the specified subreddit. If no subreddit is provided, it will default to a few meme subreddits.",
          usage: "reddit [subreddit]",
          aliases: "meme",
        },
        {
          name: "GIF",
          description:
            "Searches for GIFs on Tenor with your query and sends you the first result.",
          usage: "gif {query}",
          aliases: "tenor",
        },
        {
          name: "8Ball",
          description: "Ask the magic 8Ball a yes-or-no question.",
          usage: "8ball {question}",
          aliases: "eightball",
        },
        {
          name: "Dad joke",
          description: "Get a random dad joke.",
          usage: "dadjoke",
        },
        {
          name: "Coin flip",
          description:
            "Flip a coin. You have a 50-50 chance of getting heads or tails.",
          usage: "flip",
          aliases: "coinflip, flipcoin",
        },
        {
          name: "Mock",
          description:
            "Sends the text back in alternating case. For example, 'Hello World!' becomes 'hElLo wOrLd!'",
          usage: "mock {text}",
        },
        {
          name: "Bean",
          description:
            "A fake ban command that can be used by anyone. This does not actually ban the member, it is meant to confuse them.",
          usage: "bean {member} [reason]",
        },
        {
          name: "Warm",
          description:
            "A fake warn command that can be used by anyone. This does not actually warn the member, it is meant to confuse them.",
          usage: "warm {member} {reason}",
        },
      ],
    },
    {
      name: "Image Manipulation",
      commands: [
        {
          name: "Amogus",
          description:
            "Amogus, but with the member's avatar. You can also attach an image to use instead of a member's avatar.",
          usage: "amogus [member]",
          aliases: "sus, amongus",
        },
        {
          name: "YouTube Comment",
          description:
            "Generate an image that looks like a YouTube comment by you, with whatever you provide in the text option.",
          usage: "youtubecomment {text}",
          aliases: "ytcomment, comment",
        },
        {
          name: "Wasted",
          description:
            "Adds a \"wasted\" overlay to the member's avatar. You can also attach an image to use instead of a member's avatar.",
          usage: "wasted [member]",
        },
        {
          name: "Tweet",
          description:
            "Generate an image that looks like a Tweet by you, with whatever you provide in the text option.",
          usage: "tweet {text}",
        },
        {
          name: "Blurple",
          description:
            "Applies a filter with Discord's blurple colour on the member's avatar. You can also attach an image to use instead of the member's avatar.",
          usage: "blurple [member]",
          aliases: "blurplify",
        },
        {
          name: "Triggered",
          description: "Creates a triggered GIF with the member's avatar.",
          usage: "triggered [member]",
        },
        {
          name: "Oogway Quote",
          description: "Generate an image of a quote by Oogway with your text.",
          usage: "oogwayquote {text}",
          aliases: "oogway",
        },
        {
          name: "Greyscale",
          description: "Applies a greyscale filter on a member's avatar.",
          usage: "greyscale [member]",
          aliases: "grayscale, blackandwhite",
        },
        {
          name: "Woosh",
          description: "Creates an image of a joke going over someone's head.",
          usage: "woosh [member]",
          aliases: "whoosh, jokeoverhead",
        },
      ],
    },
  ];
</script>

<svelte:head>
  <title>1Bot - Commands</title>
</svelte:head>

<h1 class="config">1Bot Commands</h1>
<p>Important things to remember:</p>
<ul>
  <li>
    Prefix: 1<br />
    You can add a space after the 1 (optional).
  </li>
  <br />
  <li>
    Full Slash Command support<br />
    You can use Discord's Slash Commands with 1Bot - Slash Commands can be much easier
    to use than the message commands sometimes.
  </li>
</ul>

{#each commandList as category}
  <h2>{category.name} commands</h2>
  <ul class="command-list">
    {#each category.commands as command}
      <li>
        <p>
          <span class="command">{command.name}</span><br />
          <span class="light-text">
            {command.description}<br />
          </span>
        </p>

        <p>
          Usage<br />
          <span class="light-text">{command.usage}</span>
        </p>

        {#if command.aliases}
          <p>
            Aliases<br />
            <span class="light-text">{command.aliases}</span>
          </p>
        {/if}
        {#if command.requiredPerms}
          <p>
            Required Permissions<br />
            <span class="light-text">{command.requiredPerms}</span>
          </p>
        {/if}
      </li>
    {/each}
  </ul>
{/each}
