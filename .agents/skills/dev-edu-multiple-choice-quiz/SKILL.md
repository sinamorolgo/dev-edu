---
name: dev-edu-multiple-choice-quiz
description: Use in the dev-edu repo whenever creating or editing quizzes, glossary quizzes, review questions, or application exercises for educational HTML pages. Ensures every quiz is multiple-choice with clear options, answers, and explanations for non-developer learners.
---

# Dev Edu Multiple-Choice Quiz

Use this skill for every quiz in `/Users/nok/Documents/dev-edu`.

## Rules

1. Every quiz must be multiple-choice.
   - Applies to concept checks, practice quizzes, glossary quizzes, review questions, and application tasks.
   - Default to four choices labeled A-D.
   - If the user asks for a different number of choices, keep the quiz multiple-choice.

2. Use one best answer unless the question explicitly says "모두 고르세요".
   - Avoid ambiguous pairs of correct answers.
   - Do not use joke choices or obviously impossible distractors.

3. Build difficulty deliberately.
   - Easy: definition, core parts, nearby concept distinction.
   - Medium: short work scenario requiring tool/process selection.
   - Hard: design, critique, or improvement under constraints.
   - Default full quiz: easy 5, medium 5, hard 5.
   - Default glossary quiz: about 10 items.

4. Each question needs feedback.
   - Show all choices before the learner answers.
   - The learner should click/tap a choice to reveal whether it is correct.
   - Show the correct answer.
   - Explain why it is correct.
   - Explain why a close wrong answer is insufficient when useful.
   - Connect the explanation back to the page concept.

5. Keep wording learner-friendly.
   - Use everyday Korean first.
   - Use technical terms only after the page has introduced them.
   - Prefer concrete situations over abstract trick questions.

## HTML Pattern

Use visible choices with click-to-reveal feedback when the page uses HTML. The card may use `<details open>` for styling, but choices must be visible from the start:

```html
<details class="quiz-card" open>
  <summary>1. question text <span>보기를 선택하세요</span></summary>
  <div class="quiz-body">
    <ol class="choices" type="A">
      <li>choice</li>
      <li>choice</li>
      <li>choice</li>
      <li>choice</li>
    </ol>
    <div class="choice-result" aria-live="polite"></div>
    <div class="answer">
      <span class="answer-mark">B</span>
      <div><strong>정답: B</strong><br>Explanation.</div>
    </div>
  </div>
</details>
```

Required behavior:
- The answer/explanation is hidden at first.
- Clicking a choice marks correct/wrong.
- After a choice is selected, show the correct answer and explanation.
- Support keyboard selection with Enter/Space when implementing custom clickable choices.
