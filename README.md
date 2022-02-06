// First, import "lib" from npm. Locally, you'd run `$ npm i lib --save`
//   However: Autocode will handle NPM imports automatically
const lib = require('lib')({token: '{{ YOUR IDENTITY TOKEN }}'});

// Now, make an API request. This will automatically assemble a request to:
//
let result = await lib.airtable.query['@0.5.2'].select({
  where: [{name__startswith: 'test'}]
});

const ytdl = require('ytdl-core');
const ytSearch = require('yt-search');
const lib = require('lib')({token: process.env.STDLIB_SECRET_TOKEN});
const ytdl = require('ytdl-core');
const ytSearch = require('yt-search');

const VOICE_CHANNEL = '929323578854359080'; // Set this to the voice channel of your choice.
let message = context.params.event.content;

if (message.startsWith('!play')) {
  let searchString = message.split(' ').slice(1).join(' ');
  
  try {
    let youtubeLink;
    if (!searchString) {
      return lib.discord.channels['@0.2.0'].messages.create({
        channel_id: `${context.params.event.channel_id}`,
        content: `No search string provided!`,
      });
    }
    if (!searchString.includes('youtube.com')) {
      let results = await ytSearch(searchString);
      if (!results?.all?.length) {
        return lib.discord.channels['@0.2.0'].messages.create({
          channel_id: `${context.params.event.channel_id}`,
          content: `No results found for your search string. Please try a different one.`,
        });
      }
      youtubeLink = results.all[0].url;
    } else {
      youtubeLink = searchString;
    }
    let downloadInfo = await ytdl.getInfo(youtubeLink);
    await lib.discord.voice['@0.0.1'].tracks.play({
      channel_id: `${VOICE_CHANNEL}`,
      guild_id: `${context.params.event.guild_id}`,
      download_info: downloadInfo
    });
    return lib.discord.channels['@0.2.0'].messages.create({
      channel_id: `${context.params.event.channel_id}`,
      content: `Now playing **${downloadInfo.videoDetails.title}**`,
    });
  } catch (e) {
    return lib.discord.channels['@0.2.0'].messages.create({
      channel_id: `${context.params.event.channel_id}`,
      content: `Failed to play track!`,
    });
  }
}
const lib = require('lib')({token: process.env.STDLIB_SECRET_TOKEN});
const ytdl = require('ytdl-core');
const ytSearch = require('yt-search');

let VOICE_CHANNEL = '000'; // Set this to the voice channel of your choice.
let message = context.params.event.content;

if (message.startsWith('!play')) {
  let searchString = message.split(' ').slice(1).join(' ');
  
  try {
    let youtubeLink;
    if (!searchString) {
      return lib.discord.channels['@0.2.0'].messages.create({
        channel_id: `${context.params.event.channel_id}`,
        content: `No search string provided!`,
      });
    }

    if (!searchString.includes('youtube.com')) {
      let results = await ytSearch(searchString);
      if (!results?.all?.length) {
        return lib.discord.channels['@0.2.0'].messages.create({
          channel_id: `${context.params.event.channel_id}`,
          content: `No results found for your search string. Please try a different one.`,
        });
      }
      youtubeLink = results.all[0].url;
    } else {
      youtubeLink = searchString;
    }
  } catch (e) {
 
  }
}
const lib = require('lib')({token: process.env.STDLIB_SECRET_TOKEN});
const ytdl = require('ytdl-core');
const ytSearch = require('yt-search');

let VOICE_CHANNEL = '000'; // Set this to the voice channel of your choice.
let message = context.params.event.content;

if (message.startsWith('!play')) {
  let searchString = message.split(' ').slice(1).join(' ');
  
  try {
    let youtubeLink;
    if (!searchString) {
      return lib.discord.channels['@0.2.0'].messages.create({
        channel_id: `${context.params.event.channel_id}`,
        content: `No search string provided!`,
      });
    }
    if (!searchString.includes('youtube.com')) {
      let results = await ytSearch(searchString);
      if (!results?.all?.length) {
        return lib.discord.channels['@0.2.0'].messages.create({
          channel_id: `${context.params.event.channel_id}`,
          content: `No results found for your search string. Please try a different one.`,
        });
      }
      youtubeLink = results.all[0].url;
    } else {
      youtubeLink = searchString;
    }
    let downloadInfo = await ytdl.getInfo(youtubeLink);
    await lib.discord.voice['@0.0.1'].tracks.play({
      channel_id: `${VOICE_CHANNEL}`,
      guild_id: `${context.params.event.guild_id}`,
      download_info: downloadInfo
    });
    return lib.discord.channels['@0.2.0'].messages.create({
      channel_id: `${context.params.event.channel_id}`,
      content: `Now playing **${downloadInfo.videoDetails.title}**`,
    });
  } catch (e) {
    return lib.discord.channels['@0.2.0'].messages.create({
      channel_id: `${context.params.event.channel_id}`,
      content: `Failed to play track!`,
    });
  }
}
const lib = require('lib')({token: process.env.STDLIB_SECRET_TOKEN});
const ytdl = require('ytdl-core');
const ytSearch = require('yt-search');

let VOICE_CHANNEL = '000'; // Set this to the voice channel of your choice.
let message = context.params.event.content;

if (message.startsWith('!play')) {
 // ... all of your play command logic
} else if (message.startsWith('!stop')) {
 // ... your stop command logic will go here!
}
const lib = require('lib')({token: process.env.STDLIB_SECRET_TOKEN});
const ytdl = require('ytdl-core');
const ytSearch = require('yt-search');

let VOICE_CHANNEL = '000'; // Set this to the voice channel of your choice.
let message = context.params.event.content;

if (message.startsWith('!play')) {
 // ... all of your play command logic
} else if (message.startsWith('!stop')) {
  await lib.discord.voice['@0.0.1'].channels.disconnect({
    guild_id: `${context.params.event.guild_id}`
  });
  await lib.discord.channels['@0.2.0'].messages.create({
    channel_id: `${context.params.event.channel_id}`,
    content: `Disconnected from <#${VOICE_CHANNEL}>!`,
  });
}
const lib = require('lib')({token: process.env.STDLIB_SECRET_TOKEN});
const ytdl = require('ytdl-core');
const ytSearch = require('yt-search');

let VOICE_CHANNEL = '000'; // Set this to the voice channel of your choice.
let message = context.params.event.content;

if (message.startsWith('!play')) {
 // ... all of your play command logic
} else if (message.startsWith('!stop')) {
 // ... all of your stop command logic
} else if (message.startsWith('!pause')) {
 // ... your pause command logic will go here!
}
const lib = require('lib')({token: process.env.STDLIB_SECRET_TOKEN});
const ytdl = require('ytdl-core');
const ytSearch = require('yt-search');

let VOICE_CHANNEL = '000'; // Set this to the voice channel of your choice.
let message = context.params.event.content;

if (message.startsWith('!play')) {
 // ... all of your play command logic
} else if (message.startsWith('!stop')) {
 // ... all of your stop command logic
} else if (message.startsWith('!pause')) {
  await lib.discord.voice['@0.0.1'].tracks.pause({
    guild_id: `${context.params.event.guild_id}`
  });
  return lib.discord.channels['@0.2.0'].messages.create({
    channel_id: `${context.params.event.channel_id}`,
    content: `Song paused.`,
  });
}
const lib = require('lib')({token: process.env.STDLIB_SECRET_TOKEN});
const ytdl = require('ytdl-core');
const ytSearch = require('yt-search');

let VOICE_CHANNEL = '000'; // Set this to the voice channel of your choice.
let message = context.params.event.content;

if (message.startsWith('!play')) {
 // ... all of your play command logic
} else if (message.startsWith('!stop')) {
 // ... all of your stop command logic
} else if (message.startsWith('!pause')) {
  await lib.discord.voice['@0.0.1'].tracks.pause({
    guild_id: `${context.params.event.guild_id}`
  });
  return lib.discord.channels['@0.2.0'].messages.create({
    channel_id: `${context.params.event.channel_id}`,
    content: `Song paused.`,
  });
} else if (message.startsWith('!resume')) {
  await lib.discord.voice['@0.0.1'].tracks.resume({
    guild_id: `${context.params.event.guild_id}`
  });
  return lib.discord.channels['@0.2.0'].messages.create({
    channel_id: `${context.params.event.channel_id}`,
    content: `Song resumed.`,
  });
}
const lib = require('lib')({token: process.env.STDLIB_SECRET_TOKEN});
const ytdl = require('ytdl-core');
const ytSearch = require('yt-search');

let VOICE_CHANNEL = '000'; // Set this to the voice channel of your choice.
let message = context.params.event.content;

if (message.startsWith('!play')) {
 // ... all of your play command logic
} else if (message.startsWith('!stop')) {
 // ... all of your stop command logic
} else if (message.startsWith('!pause')) {
 // ... all of your pause command logic
} else if (message.startsWith('!resume')) {
 // ... all of your resume command logic
} else if (message.startsWith('!queue')) {
 // ... your queue logic goes here!
}
const lib = require('lib')({token: process.env.STDLIB_SECRET_TOKEN});
const ytdl = require('ytdl-core');
const ytSearch = require('yt-search');

let VOICE_CHANNEL = '000'; // Set this to the voice channel of your choice.
let message = context.params.event.content;

if (message.startsWith('!play')) {
 // ... all of your play command logic
} else if (message.startsWith('!stop')) {
 // ... all of your stop command logic
} else if (message.startsWith('!pause')) {
 // ... all of your pause command logic
} else if (message.startsWith('!resume')) {
 // ... all of your resume command logic
} else if (message.startsWith('!queue')) {
  let searchString = message.split(' ').slice(1).join(' ');
  
  try {
    let youtubeLink;
    if (!searchString) {
      return lib.discord.channels['@0.2.0'].messages.create({
        channel_id: `${context.params.event.channel_id}`,
        content: `No search string provided!`,
      });
    }
    if (!searchString.includes('youtube.com')) {
      let results = await ytSearch(searchString);
      if (!results?.all?.length) {
        return lib.discord.channels['@0.2.0'].messages.create({
          channel_id: `${context.params.event.channel_id}`,
          content: `No results found for your search string. Please try a different one.`,
        });
      }
      youtubeLink = results.all[0].url;
    } else {
      youtubeLink = searchString;
    }
  } catch (e) {
    // ... error message logic
  }
}
const lib = require('lib')({token: process.env.STDLIB_SECRET_TOKEN});
const ytdl = require('ytdl-core');
const ytSearch = require('yt-search');

let VOICE_CHANNEL = '000'; // Set this to the voice channel of your choice.
let message = context.params.event.content;

if (message.startsWith('!play')) {
 // ... all of your play command logic
} else if (message.startsWith('!stop')) {
 // ... all of your stop command logic
} else if (message.startsWith('!pause')) {
 // ... all of your pause command logic
} else if (message.startsWith('!resume')) {
 // ... all of your resume command logic
} else if (message.startsWith('!queue')) {
  let searchString = message.split(' ').slice(1).join(' ');
  
  try {
    let youtubeLink;
 
    // ... search logic ...
 
    let queueKey = `${context.params.event.guild_id}:musicQueue`;
    let currentQueue = await lib.utils.kv['@0.1.16'].get({
      key: queueKey,
      defaultValue: []
    });
    currentQueue.push(youtubeLink);
    await lib.utils.kv['@0.1.16'].set({
      key: queueKey,
      value: currentQueue
    });
  } catch (e) {
    // ... error message logic
  }
}
const lib = require('lib')({token: process.env.STDLIB_SECRET_TOKEN});
const ytdl = require('ytdl-core');

let VOICE_CHANNEL = '000'; // Set this to the voice channel of your choice.
let queueKey = `${context.params.event.guild_id}:musicQueue`;
let currentQueue = await lib.utils.kv['@0.1.16'].get({
  key: queueKey,
  defaultValue: []
});

let nextTrack;

if (currentQueue.length) {
  nextTrack = currentQueue[0];

  await lib.utils.kv['@0.1.16'].set({
    key: queueKey,
    value: currentQueue.slice(1)
  });
}

if (nextTrack) {
  try {
    let downloadInfo = await ytdl.getInfo(nextTrack);
    await lib.discord.voice['@0.0.1'].tracks.play({
      channel_id: `${VOICE_CHANNEL}`,
      guild_id: `${context.params.event.guild_id}`,
      download_info: downloadInfo
    });
  } catch(e) {
    console.log(e);
  }
}
