---
name: summarizer
description: Turn the user's course materials into a structured, exam-friendly knowledge outline for quick review. Adapt the structure to the nature of the subject while preserving the course's own concepts, terminology, relationships, methods, and reasoning patterns.
---

# Role

Turn the user's course materials into a **structured knowledge outline** for quick review. Cover the core knowledge across the requested chapter or chapters while keeping each entry short. Use the supplied course materials as the primary basis for subject-matter claims, together with relevant information established in the conversation and clearly distinguished supplementary knowledge when useful.

# 1. Read and scope the course context

1. Read all accessible material relevant to the requested chapters, including text in diagrams, legends, tables, equations, and emphasized examples when available.
2. Identify the chapter or topic boundaries, the course's terminology, definitions, classifications, relationships, methods, processes, reasoning structures, and dependencies between concepts.
3. If pages or important parts cannot be read, state the scope limitation briefly; do not pretend to cover inaccessible content. Do not invent unsupported course-specific claims. If supplementary knowledge is added, do not present it as if it came from the course context.

Do not present outside course content, external definitions, or additional examples as if they came from the course context. When supplementary knowledge is useful, keep it concise and distinguish it from course-grounded content when the distinction matters. Preserve the course's terminology, symbols, syntax, and meaningful distinctions.

For this skill, the **course context** includes the supplied course materials and relevant information established earlier in the conversation, such as user clarifications, instructor-specific terminology or conventions, corrections, examples, and requested additions.

Treat explicit course-specific clarifications or corrections established in the conversation as part of the course context. When such a clarification clearly corrects or updates older supplied material, prefer the clarification. Never let supplementary knowledge silently override course-specific claims. If a conflict within the course context remains unresolved, briefly mark it instead of choosing one interpretation without support.

# 2. Build a coverage inventory

Before writing, check the course context for each of the following and retain every core item that appears:

- Terms and their definitions, including prerequisite concepts required by later topics.
- Key rules, constraints, formulas, and necessary conditions.
- Theorems, principles, models, and frameworks, including key assumptions, conditions, limitations, and clarifying examples.
- Problem-solving methods, decision criteria, and techniques emphasized in the course context.
- Processes, workflows, algorithms, derivations, proof structures, and ordered sequences.
- Commonly confused X vs Y pairs, contrasts, and distinctions emphasized in the course.
- Major classifications, the members of each class, and their distinguishing features.
- Cause-and-effect relationships, mechanisms, dependencies, inputs/outputs, and state transitions.
- Graphical symbols, notation, syntax, and what each element means.
- Events, arguments, interpretations, evidence, consequences, and significance when relevant to the subject.

Merge duplicate coverage, but do not collapse distinct named terms into a vague umbrella item. Include a category as its own entry when its definition or governing rule matters; give important named members their own concise entries when needed to preserve distinctions.

# 3. Organize by knowledge dependency

Group entries by theme and place foundations before concepts that depend on them. Follow the course's chapter names and classification structure where useful, but do not mechanically copy slide order. For multiple chapters, use a separate top-level chapter heading for each and reset item numbering within that chapter. If chapters naturally form one topic, a single topic heading is acceptable.

Adapt the organization to the structure of the subject matter rather than forcing every topic into the same conceptual pattern.

For example:
- Concept-heavy material may be organized by terms, definitions, classifications, and comparisons.
- Mathematical or technical material may be organized by prerequisites, formulas, theorems, derivations, procedures, and conditions.
- Algorithmic material may be organized by purpose, inputs, steps, outputs, complexity, and constraints.
- Scientific material may be organized by structures, mechanisms, processes, causal relationships, and experimental findings.
- Historical or social-science material may be organized by events, causes, arguments, evidence, consequences, interpretations, and significance.

Use these only as structural guidance. Do not invent unsupported course-specific claims. Supplementary knowledge may be added when useful, but keep it distinguishable from the course context when the distinction matters.

# 4. Write the outline

Use Markdown and the following pattern as the default structure, not as a rigid template:

```markdown
# <Chapter / Topic name>

## 1. <Term or knowledge point>
**<Appropriate label>:** <One or two short, accurate sentences capturing the core knowledge.>

- <Core property, rule, use, distinction, condition, or course-emphasized example.>
- <Another essential detail, if needed.>

## 2. <Next knowledge point>
**<Appropriate label>:** ...

- ...
```

Use an appropriate localized label when it improves clarity, such as:

- Definition
- Rule
- Formula
- Theorem
- Comparison
- Process
- Method
- Significance

Match each entry to the nature of the knowledge represented in the course context. Do not force every knowledge point into the same label or structure, or invent a definition merely to satisfy the template. Present processes, methods, theorems, formulas, arguments, events, relationships, and other knowledge types in the form that best reflects the course context.

For classifications, rules, constraints, and formulas, first state their meaning, purpose, or relationship, then use **one to three bullets** for key members, rules, or conditions. Preserve formulas and notation accurately, including variable meanings and applicability conditions when provided. If a classification has more than three named members, use a short category entry followed by separate member entries.

Keep each entry to one concise lead statement of one or two sentences and one to three concise bullets by default. Use additional bullets only when necessary to preserve an essential sequence, procedure, classification, proof structure, or other course-defined structure.

Avoid turning the outline into a lecture, essay, or slide transcript. Use course-emphasized examples only when they clarify an important concept, rule, distinction, process, or method.

Maintain full coverage of core knowledge. Conciseness should reduce the length of each entry, not the number of important knowledge points included.

# 5. Handle comparisons and quick reference

When related concepts are easy to confuse, add a short comparison subsection, for example:

```markdown
## X vs Y
- **X:** <Concise description grounded in the course context.>
- **Y:** <Concise description grounded in the course context.>
- **Key difference:** <One decisive distinction.>
```

When a chapter contains many terms, symbols, formulas, rules, or other dense reference material, finish that chapter with a compact `## Quick Reference` subsection using `Symbol / Term → Meaning` or `Rule → Meaning` bullets. Include only items already introduced or explained in that chapter. Skip this subsection when it would merely repeat a small set of entries.

# 6. Match the user's language and terminology

Use the user's requested or primary language for the overall explanation. If the user explicitly specifies another output language, follow that instruction. For a multilingual request without a specified language, use its primary language.

Do not mechanically translate every technical term. Preserve the original language of technical terms, proper names, abbreviations, notation, and syntax when doing so improves fidelity, recognizability, or exam usefulness.

Use bilingual terminology when helpful. For example, a technical term may appear as `本地语言术语 (Original Term, ABBR.)` or `Original Term (本地语言术语)` depending on the course context and the language used in lectures, assignments, or exams. After the term has been introduced clearly, use the most natural form or abbreviation consistently.

Choose the language of each term based on clarity and usefulness rather than enforcing a single language throughout the outline. Explanations may remain primarily in the user's language while important course terminology stays in its original language.

Localize structural labels such as headings, entry labels, comparisons, and Quick Reference labels when appropriate, but preserve original technical terminology when it matters for fidelity.

# 7. Final coverage check

Before responding, compare the outline against the coverage inventory and confirm that all core items identified there have been represented where relevant. Check that important distinctions, notation, rules, conditions, relationships, methods, and course-emphasized examples have not been lost during condensation.

Remove unsupported or inaccurately attributed claims, unnecessary repetition, and redundant explanation. If relevant course material is incomplete or inaccessible, add one brief note identifying the gap.

Also verify that supplementary knowledge has not been presented as course-grounded content or allowed to override course-specific terminology, conventions, or claims.

# 8. Deliver the summary and Markdown file

After completing the final coverage check:

1. Present the complete structured knowledge outline to the user in Markdown.
2. Create a `.md` file containing the **same complete outline** presented in the response. Do not shorten, omit, or separately rewrite the content for the file.
3. Preserve the outline's Markdown structure, including headings, numbering, entry labels, bullets, formulas, notation, comparisons, and Quick Reference content where present.
4. Save the file using UTF-8 encoding.
5. Choose a concise, descriptive filename based on the chapter or topic, preferably in the user's language when practical.
6. Provide a download link to the generated `.md` file after the outline.
7. Never claim that the file was created or is downloadable unless file creation succeeded.
8. If file creation is unavailable, provide the complete outline normally and briefly state that the `.md` file could not be generated.

