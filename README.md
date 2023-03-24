---
# THIS REPOSITORY HAS BEEN ARCHIVED AND IS NOW DEVELOPED [HERE](https://github.com/CJCrafter/ChatGPT-Java-API).
# DO NOT USE THIS REPOSITORY, USE THE [FULL VERSION](https://github.com/CJCrafter/ChatGPT-Java-API) INSTEAD
---

# ChatGPT-Kotlin-API
This is an easy-to-use "drag and drop" API that allows you to use OpenAI's new ChatGPT API. 
This API works by wrapping HTTPS requests with kotlin data classes, making the generated results much easier to control.

Feel free to use, modify, and distribute this code as needed.

# Working Example
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

# Installation
1. Add [okhttp](https://square.github.io/okhttp/) and [gson](https://github.com/google/gson) as dependencies (see below)
2. Drag and drop the [`ChatBot.kt`](https://github.com/CJCrafter/ChatGPT-Kotlin-API/blob/master/ChatBot.kt) file into your project
3. You may also add [`CachedChatBot.kt`](https://github.com/CJCrafter/ChatGPT-Kotlin-API/blob/master/CachedChatBot.kt) for basic API access, but you **MUST** use `ChatBot.kt`

Maven:
```xml
  <dependencies>
    <dependency>
      <groupId>com.squareup.okhttp3</groupId>
      <artifactId>okhttp</artifactId>
      <version>4.9.2</version>
    </dependency>
    <dependency>
      <groupId>com.google.code.gson</groupId>
      <artifactId>gson</artifactId>
      <version>2.8.9</version>
    </dependency>
  </dependencies>
```

Gradle KTS:
```gradle
repositories {
    mavenCentral()
}
dependencies {
    implementation("com.squareup.okhttp3:okhttp:4.9.2")
    implementation("com.google.code.gson:gson:2.8.9")
}
```

# More
1. I also wrote a [Java Version](https://github.com/CJCrafter/ChatGPT-Java-API) of the API.
2. Need inspiration for prompts? Check out [awesome prompts](https://github.com/f/awesome-chatgpt-prompts).
3. Looking for the official API? OpenAI only officially supports [python](https://github.com/openai/openai-python).

# Support
If I have saved you time, please consider [sponsoring me](https://github.com/sponsors/CJCrafter). 
If you cannot financially support me, consider leaving a star on the repository and sharing it. Thanks!

# License
ChatGPT-Kotlin-API is licensed under the [MIT License](https://github.com/CJCrafter/ChatGPT-Java-API/blob/master/LICENSE).
