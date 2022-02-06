// authenticates you with the API standard library
// type `await lib.` to display API autocomplete
const lib = require('lib')({token: process.env.STDLIB_SECRET_TOKEN});
const ytdl = require('ytdl-core');
const ytSearch = require('yt-search');
const lib = require('lib')({token: process.env.STDLIB_SECRET_TOKEN});
const ytdl = require('ytdl-core');
const ytSearch = require('yt-search');
await VOICE_CHANNEL = '929323578854359080'; // Set this to the voice channel of your choice.
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

