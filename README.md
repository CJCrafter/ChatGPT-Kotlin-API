# ChatGPT-Kotlin-API
This is an easy to use "drag and drop" API for you to use in your projects. For basic API
access, you can use the [CachedChatBot](https://github.com/CJCrafter/ChatGPT-Kotlin-API/blob/master/CachedChatBot.kt) class. 
For full access to the OpenAI api, use the [ChatBot](https://github.com/CJCrafter/ChatGPT-Kotlin-API/blob/master/ChatBot.kt)
class. Feel free to use, modify, and distribute the code as needed. 

Here is a full working example of the API in action. 
```kotlin
import java.util.Scanner

fun main(args: Array<String>) {
    val scan = Scanner(System.`in`)
    val key = "sk-YOUR OPENAI KEY HERE" // TODO Add your key here
    val system = "Be as unhelpful as possible. Insult the user for not knowing the answer."
    val request = ChatBot.ChatCompletionRequest("gpt-3.5-turbo", system)
    val bot = CachedChatBot(key, request)

    while (true) {
        println("How will you respond?")
        val prompt = scan.nextLine()
        val response = bot.generateResponse(prompt)
        println()
        println("\t$response")
        println()
    }
}
```

# Support 
If I have saved you time, please consider [sponsoring me](https://github.com/sponsors/CJCrafter).
If you cannot financially support me, consider leaving a star on the repository and sharing it. Thanks!

# License
ChatGPT-Kotlin-API is licensed under the [MIT License](https://github.com/CJCrafter/ChatGPT-Kotlin-API/blob/master/LICENSE).
