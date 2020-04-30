# discord-markovizer
markov chains from all your discord messages

i might make a discord bot for this later, idk, right now its just a bunch of script commands to run

dependencies: python, R, Tyrrrz/DiscordChatExporter, markovify library for python

instructions: 

download whatever discord channels you want as csv and combine them to one file

(in R:)

data = read.csv("file.csv", header=TRUE)

out = data[[4]][c(dat[[2]]=="username#0000")]   #insert the username there, or just do data[[4]] if you want it to do all messages

write(paste(out, ".", sep=""), file="data.txt")  #markovify only counts the end of a sentence as wherever there is 

punctuation, not the end of a line, theres probably a better fix for this but it works for now

(in python:)

import markovify

with open("data.txt") as f:

    text = f.read()

text_model = markovify.Text(text)

all set up now, do

print(text_model.make_short_sentence(100)) #or whatever string length you want

or

print(text_model.make_sentence())

to generate text
