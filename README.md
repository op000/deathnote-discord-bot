# deathnote-discord-bot
from time import *
import discord
from discord.ext import commands
from discord.utils import get
client = commands.Bot(command_prefix="dn.")

@client.event
async def on_ready():
    print("bot ready")




@client.command()
@commands.has_permissions(administrator = True)
async def c(ctx,amount=2):
    await ctx.channel.purge(limit = amount)

@client.command()
@commands.has_permissions(kick_members = True)
async def killwr(ctx,member : discord.Member,*,reason= "heart attack"):
    sleep(40)
    await ctx.send(member.name + " died by "+reason)
    await ctx.send(reason= reason)
    
@client.command()
@commands.has_permissions(kick_members = True)
async def kill(ctx,member : discord.Member):
    sleep(40)
    await ctx.send(member.name + " died by a heart attack")

@client.command()
async def rules(ctx):
    await ctx.send("The human whose name is written in this note shall die.\n This note will not take effect unless the writer has the person's face in their mind when writing his/her name. Therefore, people sharing the same name will not be affected.\n If the cause of death is written within the next 40 seconds of writing the person's name, it will happen.\n If the cause of death is not specified, the person will simply die of a heart attack.")


client.run("ODU0Mjc4MzI0MjA4OTI2NzIx.YMhmsA.gVThbndAQCfjESBlXamEcpbiVTo")
