---
title: Profanity filtering - Translator
titleSuffix: Azure Cognitive Services
description: Use Translator profanity filtering to determine the level of profanity translated in your text.
services: cognitive-services
author: laujan
manager: nitinme
ms.service: cognitive-services
ms.subservice: translator-text
ms.topic: conceptual
ms.date: 04/26/2022
ms.author: lajanuar
---

# Add profanity filtering with the Translator

Normally the Translator service retains profanity that is present in the source in the translation. The degree of profanity and the context that makes words profane differ between cultures. As a result, the degree of profanity in the target language may be amplified or reduced.

If you want to avoid seeing profanity in the translation, even if profanity is present in the source text, use the profanity filtering option available in the Translate() method. This option allows you to choose whether you want the profanity deleted, marked with appropriate tags, or no action taken.

The Translate method takes the "options" parameter, which contains the new element "ProfanityAction". The accepted values of ProfanityAction are "NoAction", "Marked" and "Deleted."

## Accepted values of ProfanityAction and examples
|ProfanityAction value | Action | Example: Source - Japanese | Example: Target - English|
| :---|:---|:---|:---|
| NoAction | Default. Same as not setting the option. Profanity passes from source to target. | 彼は変態です。 | He's a jerk. |
| Marked | Profane words are surrounded by XML tags \<profanity> ... \</profanity>. | 彼は変態です。 | He's a \<profanity>jerk\</profanity>. |
| Deleted | Profane words are removed from the output without replacement. | 彼は。 | He's a\. |

## Next steps
> [!div class="nextstepaction"]
> [Apply profanity filtering with your Translator call](reference/v3-0-translate.md)
