client.on('message', message => {
    if (!message.content.startsWith(prefix) || message.author.bot) return;
    const args = message.content.slice(prefix.length).trim().split(/ +/);
    const command = args.shift().toLowerCase();
if(command === 'avatar') {
      let user = message.mentions.members.first() || message.guild.members.cache.get(args[0])
        let member = message.guild.member(user)
      if(!member) return  message.channel.send(new Discord.MessageEmbed()
        .setAuthor(message.author.tag,message.author.displayAvatarURL())
        .setImage(message.author.displayAvatarURL({size: 2048,dynamic : true})))
      if(member) {
        message.channel.send(new Discord.MessageEmbed()
        .setAuthor(member.user.tag,member.user.displayAvatarURL())
        .setImage(member.user.displayAvatarURL({size: 2048,dynamic : true})))
      }
    }
});
