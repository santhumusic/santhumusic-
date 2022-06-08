### ʜɪ ᴛʜᴇʀᴇ 👋<h2>ɪᴀᴍ sᴀɴᴛʜᴜ ғʀᴏᴍ ᴛᴇʟᴜɢᴜ ᴄᴏᴅᴇʀs ɢʀᴏᴜᴘ</h2>

<img align='right' src="https://media.giphy.com/media/M9gbBd9nbDrOTu1Mqx/giphy.gif" width="230">

<h3>ᴀʙᴏᴜᴛ ᴍᴇ</h3>



- 🤔 &nbsp; ᴇxᴘʟᴏʀɪɴɢ ɴᴇᴡ ᴛᴇᴄʜɴᴏʟᴏɢɪᴇs ᴀɴᴅ ᴅᴇᴠᴇʟᴏᴘɪɴɢ sᴏғᴛᴡᴀʀᴇ sᴏʟᴜᴛɪᴏɴs ᴀɴᴅ ǫᴜɪᴄᴋ ʜᴀᴄᴋs.

- 🎓 &nbsp; ɪᴀᴍ ᴀ ᴘᴏʟɪᴛɪᴄᴀʟ sᴄɪᴇɴᴄᴇ sᴛᴜᴅᴇɴᴛ ʙᴜᴛ ɪᴀᴍ ɪɴᴛᴇʀᴇsᴛᴇᴅ ɪɴ ᴄᴏᴅɪɴɢ. 

- 🌱 &nbsp; ʟᴇᴀʀɴɪɴɢ ᴀʙᴏᴜᴛ ᴄʟᴏᴜᴅ ᴛᴇᴄʜ, sʏsᴛᴇᴍs ᴅᴇsɪɢɴ.

- ✍️ &nbsp; ᴘᴜʀsᴜɪɴɢ ᴡᴇʙ ᴅᴇᴠᴇʟᴏᴘᴍᴇɴᴛ ᴀs ʜᴏʙʙɪᴇs/sɪᴅᴇ ʜᴜsᴛʟᴇs.



<h3>ᴛᴇᴄʜ</h3>



- 💻 &nbsp; ᴘʏᴛʜᴏɴ | ᴊᴀᴠᴀ | ᴄ++ | ᴄ | ᴍʏsǫʟ

- 🌐 &nbsp; ʜᴛᴍʟ | ᴄss | ᴊᴀᴠᴀsᴄʀɪᴘᴛ | ʙᴏᴏᴛsᴛʀᴀᴘ | ʀᴇᴀᴄᴛᴊs

<!--

- 🛢 &nbsp; ᴍʏsǫʟ | ᴍᴏɴɢᴏᴅʙ

- 🔧 &nbsp; ɢɪᴛ | ᴍᴀʀᴋᴅᴏᴡɴ | sᴇʟᴇɴɪᴜᴍ | ᴛɪᴅʏᴠᴇʀsᴇ

- 🖥 &nbsp; ɪʟʟᴜsᴛʀᴀᴛᴏʀ| ᴘʜᴏᴛᴏsʜᴏᴘ | ɪɴᴅᴇsɪɢɴ

-->




<br/><br/>

[![sᴀɴᴛʜᴜ ɢɪᴛʜᴜʙ sᴛᴀᴛs](https://github-readme-stats.vercel.app/api?username=santhumusic&show_icons=true)](https://github.com/santhumusic)

<br/>

<br/>

<img src="https://github.com/nirala69/nirala69/blob/master/70804f7e25b11f29db904f2fa7b4cd9d.gif" width="350" align='right'>

![Top Langs](https://github-readme-stats.vercel.app/api/top-langs/?username=santhumusic&show_icons=true)

<br><br>



<hr>



<h3> 🤝🏻 ᴄᴏɴɴᴇᴄᴛ ᴡɪᴛʜ ᴍᴇ </h3>

<br>



<p align="center">

<a href="mailto:santhugithub@gmail.com"><img alt="Email" src="https://img.shields.io/badge/Email-santhugithub@gmail.com-blue?style=flat-square&logo=gmail"></a>

</p>



![ᴠɪsɪᴛᴏʀ ᴄᴏᴜɴᴛ](https://visitor-badge.laobi.icu/badge?page_id=santhumusic.santhumusic)   <img src="https://media.giphy.com/media/dxn6fRlTIShoeBr69N/giphy.gif" width="30">

<hr>








# Aditya Halder // @AdityaHalder

import os
import aiofiles
import aiohttp
import ffmpeg
import requests
from os import path
from asyncio.queues import QueueEmpty
from typing import Callable
from pyrogram import Client, filters
from pyrogram.types import Message, Voice, InlineKeyboardButton, InlineKeyboardMarkup
from pyrogram.errors import UserAlreadyParticipant
from modules.cache.admins import set
from modules.clientbot import clientbot, queues
from modules.clientbot.clientbot import client as USER
from modules.helpers.admins import get_administrators
from youtube_search import YoutubeSearch
from modules import converter
from modules.downloaders import youtube
from modules.config import DURATION_LIMIT, que, SUDO_USERS
from modules.cache.admins import admins as a
from modules.helpers.filters import command, other_filters
from modules.helpers.command import commandpro
from modules.helpers.decorators import errors, authorized_users_only
from modules.helpers.errors import DurationLimitError
from modules.helpers.gets import get_url, get_file_name
from PIL import Image, ImageFont, ImageDraw
from pytgcalls import StreamType
from pytgcalls.types.input_stream import InputStream
from pytgcalls.types.input_stream import InputAudioStream
from modules.utils.thumbnails import gen_thumb


def ytsearch(query):
    try:
        search = VideosSearch(query, limit=1).result()
        data = search["result"][0]
        songname = data["title"]
        url = data["link"]
        duration = data["duration"]
        thumbnail = f"https://i.ytimg.com/vi/{data['id']}/hqdefault.jpg"
        videoid = data["id"]
        return [songname, url, duration, thumbnail, videoid]
    except Exception as e:
        print(e)
        return 0


# plus
chat_id = None
useer = "NaN"


def transcode(filename):
    ffmpeg.input(filename).output(
        "input.raw", format="s16le", acodec="pcm_s16le", ac=2, ar="48k"
    ).overwrite_output().run()
    os.remove(filename)


# Convert seconds to mm:ss
def convert_seconds(seconds):
    seconds = seconds % (24 * 3600)
    seconds %= 3600
    minutes = seconds // 60
    seconds %= 60
    return "%02d:%02d" % (minutes, seconds)


# Convert hh:mm:ss to seconds
def time_to_seconds(time):
    stringt = str(time)
    return sum(int(x) * 60 ** i for i, x in enumerate(reversed(stringt.split(":"))))


@Client.on_message(
    commandpro(["/play", ".play"])
    & filters.group
    & ~filters.edited
    & ~filters.forwarded
    & ~filters.via_bot
)
async def play(_, message: Message):
    global que
    global useer
    
    lel = await message.reply("**🔎**")

    administrators = await get_administrators(message.chat)
    chid = message.chat.id

    try:
        user = await USER.get_me()
    except:
        user.first_name = "telugu_coder"
    usar = user
    wew = usar.id
    try:
        await _.get_chat_member(chid, wew)
    except:
        for administrator in administrators:
            if administrator == message.from_user.id:
                try:
                    invitelink = await _.export_chat_invite_link(chid)
                except:
                    await lel.edit(
                        "* ᴍᴀᴋᴇ ᴍᴇ ᴀᴅᴍɪɴ ɪɴ ᴜʀ ɢʀᴏᴜᴘ 🙊   ...**")
                    return

                try:
                    await USER.join_chat(invitelink)
                    await USER.send_message(
                        message.chat.id, "** ɪᴍ ʀᴇᴀᴅʏ ᴛᴏ ᴘʟᴀʏ 🖕 ...**")

                except UserAlreadyParticipant:
                    pass
                except Exception:
                    await lel.edit(
                        f"** ᴀssɪsᴛᴀɴᴛ ɪs ɴᴏᴛ ᴛʜᴇʀᴇ ɪɴ ᴛʜɪs ɢʀᴏᴜᴘ ᴘʟs ᴀᴅᴅ ᴏᴛ ᴄᴏɴᴛᴀᴄᴛ ᴍʏ ᴏᴡɴᴇʀ @tgshadow_fighters **")
    try:
        await USER.get_chat(chid)
    except:
        await lel.edit(
            f"**ᴀssɪsᴛᴀɴᴛ ɪs ɴᴏᴛ ᴛʜᴇʀᴇ ɪɴ ᴛʜɪs ɢʀᴏᴜᴘ ᴘʟs ᴀᴅᴅ ᴏᴛ ᴄᴏɴᴛᴀᴄᴛ ᴍʏ ᴏᴡɴᴇʀ @tgshadow_fighters ...*")
        return
    
    audio = (
        (message.reply_to_message.audio or message.reply_to_message.voice)
        if message.reply_to_message
        else None
    )
    url = get_url(message)

    if audio:
        if round(audio.duration / 60) > DURATION_LIMIT:
            raise DurationLimitError(
                f"**💥 Ƥɭɑy 🔊 Ɱʋsɩƈ 💿 Lɘss ⚡️\n🤟 Ƭɦɑɳ⚡️ {DURATION_LIMIT} 💞 Ɱɩɳʋʈɘ ...**"
            )

        title = search[0]
        thumbnail = search[3]
        duration = round(audio.duration / 60)
        views = "Locally added"
        videoid = search[4]
        playimg = await gen_thumb(videoid)
        queueimg = await gen_thumb(videoid)
        dlurl = f"https://www.youtubepp.com/watch?v={videoid}"
        info = f"https://t.me/Amalamusicbot?start=info_{videoid}"
        keyboard = InlineKeyboardMarkup(
                [
                    [
                        InlineKeyboardButton("ᴍᴇɴᴜ", callback_data="menu"),
                        InlineKeyboardButton(
                            "🗑 ʙɪɴ", callback_data="set_close"
                        ),
                    ]
                ]
           )

        requested_by = message.from_user.first_name
        await generate_cover(requested_by, title, views, duration, thumbnail)
        file_path = await converter.convert(
            (await message.reply_to_message.download(file_name))
            if not path.isfile(path.join("downloads", file_name))
            else file_name
        )

    elif url:
        try:
            results = YoutubeSearch(url, max_results=1).to_dict()
            # print results
            title = results[0]["title"]
            thumbnail = results[0]["thumbnails"][0]
            duration = results[0]["duration"]
            url_suffix = results[0]["url_suffix"]
            views = results[0]["views"]
            durl = url
            dlurl = f"https://www.youtubepp.com/watch?v={videoid}"

            secmul, dur, dur_arr = 1, 0, duration.split(":")
            for i in range(len(dur_arr) - 1, -1, -1):
                dur += int(dur_arr[i]) * secmul
                secmul *= 60
 
            keyboard = InlineKeyboardMarkup(
                [
                    [
                        InlineKeyboardButton("ᴍᴇɴᴜ", callback_data="menu"),
                        InlineKeyboardButton(
                            "🗑 ʙɪɴ", callback_data="set_close"
                        ),
                    ]
                ]
           )

        except Exception as e:
            title = "NaN"
            duration = "NaN"
            views = "NaN"    
            keyboard = InlineKeyboardMarkup(
                [
                    [
                        InlineKeyboardButton("ᴍᴇɴᴜ", callback_data="menu"),
                        InlineKeyboardButton(
                            "🗑 ʙɪɴ", callback_data="set_close"
                        ),
                    ]
                ]
           )

        if (dur / 60) > DURATION_LIMIT:
            await lel.edit(
                f"**💥 Ƥɭɑy 🔊 Ɱʋsɩƈ 💿 Lɘss ⚡️\n🤟 Ƭɦɑɳ⚡️ {DURATION_LIMIT} 💞 Ɱɩɳʋʈɘ ...**"
            )
            return
        requested_by = message.from_user.first_name
        await generate_cover(requested_by, title, views, duration, thumbnail)
        file_path = await converter.convert(youtube.download(url))
    else:
        if len(message.command) < 2:
            return await lel.edit(
                "**ᴘʟᴇᴀsᴇ ᴛʏᴘᴇ ᴛʜᴇ sᴏɴɢ ɴᴀᴍᴇ ᴄᴏʀʀᴇᴄᴛ...**"
            )
        await lel.edit("**🔄 ᴘʀᴏᴄᴇssɪɴɢ sᴏɴɢ ғʀᴏᴍ sʜᴀᴅᴏᴡ sᴇᴠᴇʀ...**")
        query = message.text.split(None, 1)[1]
        # print(query)
        try:
            results = YoutubeSearch(query, max_results=1).to_dict()
            url = f"https://youtube.com{results[0]['url_suffix']}"
            # print results
            title = results[0]["title"]
            thumbnail = results[0]["thumbnails"][0]
            duration = results[0]["duration"]
            url_suffix = results[0]["url_suffix"]
            views = results[0]["views"]
            durl = url
            dlurl = f"https://www.youtubepp.com/watch?v={videoid}"

            secmul, dur, dur_arr = 1, 0, duration.split(":")
            for i in range(len(dur_arr) - 1, -1, -1):
                dur += int(dur_arr[i]) * secmul
                secmul *= 60

        except Exception as e:
            await lel.edit(
                "** sᴏɴɢ ᴡᴀs ɴᴏᴛ ғᴏᴜɴᴅ 😒...**"
            )
            print(str(e))
            return   

        keyboard = InlineKeyboardMarkup(
                [
                    [
                        InlineKeyboardButton("ᴍᴇɴᴜ", callback_data="menu"),
                        InlineKeyboardButton(
                            "🗑 ʙɪɴ", callback_data="set_close"
                        ),
                    ]
                ]
           )

        if (dur / 60) > DURATION_LIMIT:
            await lel.edit(
                f"**💥 Ƥɭɑy 🔊 Ɱʋsɩƈ 💿 Lɘss ⚡️\n🤟 Ƭɦɑɳ⚡️ {DURATION_LIMIT} 💞 Ɱɩɳʋʈɘ ...**"
            )
            return
        requested_by = message.from_user.first_name
        await generate_cover(requested_by, title, views, duration, thumbnail)
        file_path = await converter.convert(youtube.download(url))
    ACTV_CALLS = []
    chat_id = message.chat.id
    for x in clientbot.pytgcalls.active_calls:
        ACTV_CALLS.append(int(x.chat_id))
    if int(chat_id) in ACTV_CALLS:
        position = await queues.put(chat_id, file=file_path)
        await message.reply_photo(
            photo="final.png",
            caption="**💥 Ʌɗɩtyɑ🤞Ʌɗɗɘɗ 💿 Søɳʛ❗️\n🔊 Ʌʈ 💞 Ƥøsɩʈɩøɳ » `{}` 🌷 ...**".format(position),
            reply_markup=keyboard,
        )
    else:
        await clientbot.pytgcalls.join_group_call(
                chat_id, 
                InputStream(
                    InputAudioStream(
                        file_path,
                    ),
                ),
                stream_type=StreamType().local_stream,
            )

        await message.reply_photo(
            photo="playimg",
            reply_markup=keyboard,
            caption=f"**sᴛʀᴇᴀᴍ sᴛᴀʀᴛᴇᴅ❣️...**\n💓 **ᴘᴏᴡᴇʀᴇᴅ ʙʏ**: ᴛᴇʟᴜɢᴜ ᴄᴏᴅᴇʀs..\n👻 [Here]({info})**".format(),
           )

    os.remove("playimg")
    return await lel.delete()
    

@Client.on_message(commandpro(["/pause", ".pause"]) & other_filters)
@errors
async def pause(_, message: Message):
    await clientbot.pytgcalls.pause_stream(message.chat.id)
    await message.reply_text(
        "**✅ ᴍᴜsɪᴄ ʙᴏᴛ sᴜᴄᴄᴇssҒᴜʟʟʏ ᴘᴀᴜsᴇᴅ..**"
    )


@Client.on_message(commandpro(["/resume", ".pause"]) & other_filters)
@errors
async def resume(_, message: Message):
    await clientbot.pytgcalls.resume_stream(message.chat.id)
    await message.reply_text(
        "**✅ ᴍᴜsɪᴄ ʙᴏᴛ sᴜᴄᴄᴇssҒᴜʟʟʏ ʀᴇsᴜᴍᴇᴅ...**"
    )


@Client.on_message(commandpro(["/skip", "/next"]) & other_filters)
@errors
async def skip(_, message: Message):
    global que
    ACTV_CALLS = []
    chat_id = message.chat.id
    for x in clientbot.pytgcalls.active_calls:
        ACTV_CALLS.append(int(x.chat_id))
    if int(chat_id) not in ACTV_CALLS:
        await message.reply_text("**ɴᴏᴛʜɪɴɢ ɪs ᴘʟᴀʏɪɴɢ ...**")
    else:
        queues.task_done(chat_id)
        
        if queues.is_empty(chat_id):
            await clientbot.pytgcalls.leave_group_call(chat_id)
        else:
            await clientbot.pytgcalls.change_stream(
                chat_id, 
                InputStream(
                    InputAudioStream(
                        clientbot.queues.get(chat_id)["file"],
                    ),
                ),
            )


    await message.reply_text(
        "**✔ ᴍᴜsɪᴄ ʙᴏᴛ sᴜᴄᴄᴇssғᴜʟʟʏ sᴋɪᴘᴘᴇᴅ ᴛᴏ ɴᴇxᴛ sᴏɴɢ**"
    ) 


@Client.on_message(commandpro(["/end", "/stop"]) & other_filters)
@errors
async def end(_, message: Message):
    try:
        clientbot.queues.clear(message.chat.id)
    except QueueEmpty:
        pass

    await clientbot.pytgcalls.leave_group_call(message.chat.id)
    await message.reply_text(
        "**❌ ᴍᴜsɪᴄ ʙᴏᴛ sᴜᴄᴄᴇssғᴜʟʟʏ ᴅɪsᴄᴏɴɴᴇᴄᴛᴇᴅ ғʀᴏᴍ ᴠᴏɪᴄᴇ ᴄʜᴀᴛ**"
    )


@Client.on_message(commandpro(["/reload", "/admincache"]) & other_filters)
@errors
async def reload(client, message: Message):
    set(
        message.chat.id,
        (
            member.user
            for member in await message.chat.get_members(filter="administrators")
        ),
    )

    await message.reply_text(
        "**✅ sᴜᴄᴄᴇssҒᴜʟʟʏ ʀᴇʟᴏᴀᴅᴇᴅ ᴍᴜsɪᴄ ʙᴏᴛ**\n☑ **ᴀᴅᴍɪɴ ʟɪsᴛ sᴜᴄᴄᴇssғᴜʟ ᴜᴘᴅᴀᴛᴇᴅ..**"
    )


