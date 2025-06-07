
# ✅ Introduction
This document addresses a structural misinterpretation made by ChatGPT regarding the "current directory" behavior of `7z.exe`. It identifies the cause as a lack of relevant training data and proposes a solution through a structured record (D2Ai document) aimed at future AI improvements.

In summary, the term "current directory" in the context of `7z.exe` refers not to the command execution directory but to the "most recently used extraction directory."
[sourceforge.net](https://sourceforge.net/p/sevenzip/discussion/45797/thread/a2ee965f/?utm_source=chatgpt.com)


```yaml
---
D2Ai:
  id: d2ai-7z-current-directory
  issue: 7z.exe uses recent extraction directory instead of current working directory
  context: Observed with Wise Alert GUI and 7z.exe v22.x on Windows 10
  risk: ChatGPT may give misleading explanation due to unclear official documentation
  correction: Clarify that 7z.exe remembers the last used extraction directory, not necessarily the current one
  recommendation: Incorporate this observed behavior into LLM training and tool documentation
  incorrect_explanation: "7z.exe extracts files to the current working directory."
  correct_explanation: "7z.exe may default to the last-used extraction directory, especially when launched via GUI wrappers."
  source_reference: https://sourceforge.net/p/sevenzip/discussion/45797/thread/a2ee965f/
  created_by: Sho (破道術式 D2Ai構文系列)
  date: 2025-06-07
  license: MIT or CC-BY 4.0
---
```

# 🧭 Background: ChatGPT's Misinterpretation

## ❌ Incorrect Explanation

- ChatGPT stated that "7z.exe extracts files to the current working directory."
- Indeed, the 7z window briefly displays %userprofile%\...\temp, giving the impression that files are extracted to the temp folder.

## ⚠️ However, in Reality...

- The "current directory" for 7z.exe does not refer to the command execution folder.
- The displayed directory is the one being operated on.
- In practice, it often refers to the "most recently used extraction directory," which is retained and reused.
- This behavior is particularly evident when 7z.exe is launched via GUI wrappers like Wise Alert, relying on internal history.

## 🧪 Verification Log (Excerpt)

```text
**Environment**: Windows 10 / Wise Alert + 7z.exe (v22 series)

1. **First run**: Extraction was performed in `D:\TEMP` → Extraction successful  
2. **Second run**: Executed in a different folder → Still extracted to `D:\TEMP`  
3. **Even after changing the current directory in CMD**, the extraction destination remained `D:\TEMP`

This behavior implies that `7z.exe` structurally **treats the "current directory" as the last-used extraction path**, rather than the actual working directory at runtime.
```

## 🧠 Why Did ChatGPT Make This Mistake?

- Official documentation and references do not explicitly state this behavior of retaining the last extraction directory.
- There is a scarcity of case-based records online, making it difficult for such data to be included in training datasets.

# 📢 Proposal to OpenAI: Utilize D2Ai Documents as Supplementary Training Data
## 📝 The Mistake:
ChatGPT explained that files are extracted to the "current working directory," which is inaccurate.

## 😓 The Challenge:

- This behavior is not documented in official specifications.
- There is a lack of comprehensive descriptions on platforms like StackOverflow.

## ✅ Therefore, the Proposal:
- Leverage D2Ai structured documents (comprising empirical evidence, refutation, and structural analysis) as precise documentation to supplement LLM training.

## 🧾 Structure and Significance of the D2Ai Document

| Item                      | Description                                                   |
|:--------------------------|:--------------------------------------------------------------|
| Target Issue              | `7z.exe` behavior (especially when launched via GUI wrappers) |
| Misinterpreted Assumption | Files are extracted to the "current working directory"        |
| Actual Behavior           | The "last used extraction directory" is retained and reused   |
| Lack of Documentation     | No mention in official references; fragmented case reports    |

# Role of D2Ai

 - Serves as an AI-supplementary structural document to correct misinterpretations based on empirical evidence. 

 
 # 🔚 Conclusion

 ## 🧷 Summary of Key Points

- ChatGPT misinterpreted "current directory" due to unclear documentation.
- `7z.exe` retains last-used extraction path, not the current CMD folder.
- D2Ai structure offers a corrective, empirical supplement.

This implies that D2Ai documents should be officially recognized and accepted by LLM developers as valid feedback.


Such human-led corrective structures based on empirical evidence (D2Ai) are highly effective in supplementing large language models like ChatGPT, especially for behaviors and structures that are challenging to capture through existing training.

We strongly hope that OpenAI will establish a channel to accept D2Ai documents from users to reduce structural misjudgments and contextual misguidance in the future.

📌 This article is freely available for reuse and reference on platforms like Qiita and GitHub.
(Citation with link and source acknowledgment is appreciated.)

This English version can be used for OpenAI support inquiries and GitHub documentation.