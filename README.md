# GamingBot
from openai import OpenAI 
client= OpenAI(
    api_key= "YOUR_API_KEY",
    base_url= "https://api.groq.com/openai/v1"
)

while True:
 user_input=input("you :")
 if user_input == "quit":
  print("system:Goodbye!")
  break
 response =client.chat.completions.create(
    model="llama3-70b-8192",
    messages= [
      {"role" :"system", "content": "you are a gaming bot,provide information only related to gaming"},
      {"role": "user","content":user_input}
    ]
)

print("bot:", response.choices[0].message.content)
