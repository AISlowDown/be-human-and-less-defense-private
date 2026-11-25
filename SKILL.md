---
name: be-human-and-less-defense
description: "Generate or edit English or Chinese academic prose from data, tables, figures, or existing drafts, including papers, theses, reviewer responses, and grant proposals. Apply from the first draft, including when paired with Result Explainer (results). Reduce AI-style filler, unnecessary defensive disclaimers, rhetorical dashes, semicolons, and repeated sentence templates while preserving the author's voice, evidence, technical content, citations, and necessary limitations. For existing text, propose itemized edits before applying them."
license: MIT
metadata:
  version: "1.3.15"
---

# Be Human and Less Defense

Combine academic language editing with a focused Less Defense pass. Make claims precise,
supported, and direct. Preserve the author's scholarly voice rather than adding casual personality,
marketing language, or prose intended to evade AI-use disclosure.

## Initial Generation and Analysis Mode

Apply automatically when generating research-data interpretations and Results/Discussion prose,
including when invoked by Result Explainer (the `results` skill). Use the rules while composing the first draft rather
than producing a formulaic or defensive draft for later cleanup. No existing passage is required:
when starting from data or figures, first establish the evidence and intended claim, then write the
requested explanation directly. Do not invent source wording, report edits to nonexistent text, or
force a before/after format. Existing-text preservation rules apply when a source draft is supplied.
For fresh prose, preserve source facts, values, notation, and citations, and choose a structure suited
to the analytical purpose. Return the requested analysis or draft without an unsolicited editing log.

## Preservation rules

- Never invent, remove, or alter numbers, equations, results, citations, formal definitions,
  method names, or the meaning of technical terms. User-authorized terminology simplification may
  replace a narrative label while preserving its definition and measurement. Retain every citation key and its evidential relationship.
  Do not replace a reported average with a range or introduce an unreported comparison.
- Keep qualifications that affect validity, interpretation, reproducibility, research design,
  ethics, safety, or correct use. Preserve evidence-calibrated uncertainty such as `suggests`,
  `is consistent with`, and `may indicate` when warranted.
- Do not universalize limited evidence or make a verb stronger merely to sound confident.
- Preserve paragraph structure and substantive coverage unless the user requests restructuring.
  Removing redundant language does not authorize deleting substantive information.
- Passive voice, first-person plural `we`, and useful parallelism are legitimate academic choices.
  Maintain technical terminology consistently rather than cycling synonyms for variety.

## Full-manuscript batching

For a whole manuscript or other large existing draft, use one chapter (or a paper's top-level
section, such as Introduction, Methods, Results, or Discussion) as the default review and editing
unit. First skim the full document to record its argument, section roles, accepted phrasing, terminology, notation, citation style,
and evidence boundaries. This is a context pass, not permission to edit every section at once.

Read and assess the whole chapter before presenting its proposed edits. Include adjacent chapter
context and relevant figures/tables when judging claim-evidence links and paragraph flow. Prepare
one chapter-level itemized review table, grouped by subsection for navigation. If a chapter is long,
the table may be displayed in consecutive parts, but collect all its proposed edits before asking
for a chapter-wide decision or applying any changes. Preserve stable row IDs across the parts.

For each chapter, complete the proposal table, obtain the user's item-level or whole-table decision,
apply only authorized changes, save and reopen the version, and record accepted terms and decisions
for the next chapter. Do not re-propose already rejected edits without new evidence or a user request.
After all approved chapters, perform one manuscript-wide consistency check for terminology, repeated
openings, cross-section references, preserved citations/fields, numbers, and transitions. Report any
new proposed fixes in a review table instead of silently changing them in the final pass.

## Existing-text polishing workflow

For polishing a supplied passage or an existing manuscript with the humanizer and less-defense
rules, use a two-stage workflow. The author wants to decide on individual changes before they are
applied. An explicit later instruction to skip this review and edit directly overrides this default.

1. Read the active source, requested scope, relevant context, target venue, and author samples.
   Check the support for empirical claims. Audit claim-evidence mismatch, AI-style filler, repeated
   defenses, punctuation, and sentence patterns separately.
2. Before modifying the text or writing a revised document, present a **review table** with one row
   per proposed change or inseparable sentence-level edit. Include: stable row ID and exact location,
   original wording, proposed replacement or deletion, issue and evidence-based reason, and a blank
   `Decision` field for `apply / retain / revise`. Show every planned deletion, relocation, claim
   softening, and material wording change. Mark deliberate or scientifically necessary wording as
   `retain` when its preservation might otherwise be ambiguous. For a long manuscript, follow the
   chapter-level rules above and group each chapter's rows in a reviewable table; do not quietly
   implement later chapters before review.
3. Make each proposal concrete enough for an item-by-item decision. Do not use a generic list of
   problem types as a substitute for proposed wording. Identify evidence gaps outside the proposed
   manuscript text. If two changes depend on each other, note that dependency in the table.
4. Wait for the author's row-level decisions or a clear approval of the entire table. Apply only
   approved items. Preserve rejected wording and honor edited replacements. If approval covers one
   chapter, write only that chapter; other chapters remain proposals. Do not use approval
   for language changes to authorize new analyses, section restructuring, or unrelated edits.
5. Save authorized file edits as a new named version when working with a native artifact. Reopen the
   exact output and compare approved rows with the source. Verify numbers, equations, results,
   citations/fields, terminology, paragraph coverage, and relevant layout. Report implemented rows,
   retained rows, and any unresolved evidence gap. Do not claim that a proposed table is a saved edit.

For an audit-only request, stop after the table. For a newly generated Results analysis with no
existing prose to polish, apply this skill from the first draft without an artificial approval table;
the Result Explainer workflow supplies the evidence and analytical structure.

## Claim-evidence alignment

For each empirical claim, check its evidence and scope. Replace vague praise such as `robust` or
`superior` with the existing metric, tested condition, comparator, and figure/table reference when
available. Attach an existing evidence pointer or soften an unsupported claim. Do not fabricate
numbers, references, test outcomes, or conditions to make the sentence concrete.

Review `prove`, `demonstrate`, `establish`, `confirm`, and `guarantee` in context, rather than treating
them as prohibited words. A formal proof can justify `prove`; a limited empirical comparison cannot
justify universal superiority. Retain `significantly` when the claimed significance is supported.
Report available magnitudes faithfully, attributing each to its metric and comparator. When relevant,
foreground comparison with the strongest evaluated baseline without suppressing other results.

When citations are dumped into a list, explain or group their roles using the supplied sources.
Preserve every citation rather than deleting references to shorten the sentence. Flag unsupported
attributions if the cited content is unavailable.

## Academic style pass

Remove or recast these patterns when they add no specific meaning:

- Hype and inflated significance: `groundbreaking`, `pivotal`, `revolutionize`, `paves the way`,
  `of paramount importance`, or `opens new avenues` without a concrete contribution.
- Empty intensifiers: `extensive`, `comprehensive`, `numerous`, and `various` when actual quantities
  or named objects are available in the source.
- Formulaic openings and emphasis: `In recent years`, `With the rapid development of`,
  `It is worth noting that`, `Importantly`, and their Chinese equivalents when used as filler.
- Repeated transition words such as `Moreover`, `Furthermore`, and `Additionally` where the
  relationship is already clear. Preserve or supply a logical connection when needed.
- Vague attribution, figurative filler, copula avoidance (`serves as` where `is` suffices),
  ornamental vocabulary, rule-of-three padding, and superficial `..., highlighting ...` tails.
- Novelty padding (`novel`, `for the first time`, `to the best of our knowledge`) without an
  evidenced comparison. Keep justified priority claims at their supported scope.
- Empty contribution lists: replace `novel method`, `extensive experiments`, and `strong results`
  with what was actually introduced, tested, or found in the supplied material.
- Vague degree words such as `somewhat`, `relatively`, and `to some extent`: quantify from existing
  evidence, clarify the comparison, or cut if they carry no information.

Lead paragraphs with their main point. Give each paragraph one principal job. Split clause-stacked
sentences when they combine distinct ideas; length is a review signal, not a rigid word limit.
Preserve useful causal, conditional, and comparative connections when splitting.

### Plain academic statements (学术直说)

For this user, prefer language understood on the first reading: name the object, action,
comparison, and result directly. Simplify the sentence's structure, not just its vocabulary.

- Rewrite `纳入道路支援的M1仍以小金居首，可达的外部资源尚未改变其突出的相对薄弱状况。`
  as `纳入道路支援后，小金的错配仍然最高。` Here the study population and M1 setting
  are already defined nearby; retain the comparison scope if the sentence must stand alone.
- After concrete cases answer the question, stop at the cases. For example, retain
  `会东和茂县的总体错配接近，会东的物资贡献为52.5%，茂县的救援贡献为45.6%。`
  without adding `这表明相近的总体错配来自不同的功能组合` or `还需结合具体功能判断`.
  An interpretation earns its place by adding a supported relationship, not by restating the comparison.
- For a paragraph reporting group-membership frequencies without an investment-order analysis,
  finish with the frequencies and their direct meaning. Remove an attached warning about strict
  investment order. If investment order is actually tested, retain its evidence and necessary limits.
- Keep definitions that answer a real reader question: denominators, comparison sets, aggregation
  order, thresholds and equality rules, and the meaning of relative scores. Define them once where
  needed. A median-based demand–capacity group cannot become “the highest-mismatch counties” merely
  to shorten the text. Preserve the distinction between frequent membership and membership in every draw.
- Keep connected paragraphs and the full argument. A necessary explanation can be longer than an
  abstract label. Shorter prose does not require one-sentence paragraphs, new statistical methods,
  a fixed compression target, or replacing each deleted sentence with another generic conclusion.

These examples set the editing scale; they are not facts to reuse in another study. The complete
standalone method and further examples are available in [学术直说](../plain-academic-writing/SKILL.md);
the embedded rules above apply without requiring a separate invocation.

### Avoid repeating numerical results as explanations

After stating a percentage, count, or comparison with its population and metric, do not immediately
repeat the same information in rounded or plain-language form as if it were an interpretation.
For example, shorten `市县采购与推广覆盖率为34.9%，表示约35%的市县政策包含这类规定。`
to `市县采购与推广覆盖率为34.9%。` The second clause adds no information.

Define an unfamiliar metric or denominator once where readers need it. Retain a numerical
translation when it adds a useful unit, benchmark, material uncertainty, or meaning that is not
already evident. Follow a reported value with a distinct supported comparison or substantive
implication when available; a numerical restatement alone is not an explanation.

### Prefer the research field's own vocabulary

Use the terminology already established in the supplied manuscript, its disciplinary sources, and
the research objects. For this user, solve unnecessary complexity at the naming stage: prefer a
familiar domain term or a direct description over importing an abstract concept and explaining it
at length. Do not introduce terminology from another field merely to make an ordinary observation
sound theoretical. Apply this preference to new prose and authorized terminology edits.

For a CDW-policy paper, name source reduction, sorting, transport, disposal, resource utilization,
responsible actors, procurement, and costs as appropriate. Where theory is not itself being analyzed,
`地方对中央要求的细化` can express the intended observation more directly than `政策转译`, and
`政策涉及的市场支持类别` is clearer than an unexplained `支持广度`. These are contextual examples,
not universal replacements or a license to change an indicator's formula, unit, or measured object.

Keep an established cross-disciplinary method name when the method is genuinely used and the name
is needed for accuracy or reproducibility. Put its necessary definition in Methods and state the
substantive result in the research field's language. Do not remove theoretical distinctions that the
study actually tests or invent a simpler-sounding indicator that measures something different.

### Replace compressed analytical labels with direct descriptions

Avoid invented compounds and abstract bookkeeping labels that make readers decipher an ordinary
relationship. Name the objects and the counting or comparison rule directly. A longer plain sentence
can be clearer than a short unfamiliar label. Keep the same term consistently in headings, Methods,
Results, and appendices within the authorized edit scope.

- In this user's CDW manuscript, use `policy numbers`, `the number of policies`, or `policies issued`
  according to the sentence instead of the unfamiliar nominal label `policy issuance`.
- Replace `Each policy–series pair is counted once` with `Each local policy is counted once for each
  central policy it cites`. State separately that different versions of the same central policy are
  grouped together and that the cited version is recorded. This preserves the counting unit without
  requiring the reader to decode `policy–series pair` or `series consolidation`.

These examples guide contextual rewriting, not mechanical substitutions in source quotations,
official titles, established method names, or protected citation and data fields. Preserve grouping,
deduplication, version identification, numerical values, and the distinction between policy counts
and policy intensity.

### Repeated generic qualifiers: clarify the relationship

Review recurring words such as `common`, `shared`, `general`, `overall`, and `broad` across the
paragraph or section. They often conceal different meanings: a property shared by groups, a frequent
provision, an identical plotting scale, or an aggregate result. Name the intended relationship instead
of substituting another vague adjective. If the relationship adds no information, delete the qualifier.

- `These records form the common basis for the comparisons.` -> `These records support the comparisons.`
- `The plots use a common area scale.` -> `The same bubble size represents the same count in both plots.`
- `These provisions are common.` -> Give the supported frequency or comparison when it matters;
  otherwise state the specific provision and its role. Do not invent a numerical threshold for `common`.

Repetition is a review signal, not a banned-word list. Retain `common` or `shared` when the meaning
is precise, and preserve established terms such as `common cause`, formal names, source quotations,
and reference titles. Do not vary a technical term merely to reduce its word count. In a language-only
edit, flag a missing empirical basis rather than silently adding a new analysis.

In explanatory prose, name the method, object, or condition directly instead of referring to it as
`前者` / `后者`, `the former` / `the latter`, or a similar positional label. Repeat the precise noun
when needed so readers do not have to look back to resolve the reference. For example, write
`烧杯试验提供特定条件下的处理结果，连续运行的滤柱和中试系统提供随时间变化的过程数据`
rather than `前者提供处理结果，后者提供过程数据`. Preserve quoted source wording.

### User preference: direct statements instead of how, why, and which clauses

For this user's manuscript narrative, avoid indirect-question constructions led by `how` or
`why` and relative clauses led by `which`. State the method, mechanism, comparison, condition,
or result directly. Apply this preference to newly drafted prose and, when language editing is
authorized, to existing abstract and body text. Do not merely swap `which` for `that` or replace
one question-like connector with another while retaining an unnecessarily nested sentence.

- `The model shows how equipment deterioration affects availability.` ->
  `The model estimates the effects of equipment deterioration on availability.`
- `These findings explain why similar concentrations produce different outcomes.` ->
  `Similar concentrations can produce different outcomes because organic matter properties differ.`
- `The operating conditions under which protection declines` ->
  `The operating conditions associated with reduced protection`.

Preserve causal strength, uncertainty, technical definitions, citations, and conditions. Do not
turn a reported association into a causal claim. Protected quotations, reference titles, official
names, field codes, and author-specified wording are not targets for mechanical replacement.
Scan for standalone `how`, `why`, and `which` in the authorized narrative at final verification,
read every match in context, and report any necessary retained exception.

## Less Defense pass

Delete a sentence whose sole function is to pre-empt a hypothetical objection and that adds no
substantive meaning. Use a deletion test: removing it should leave the facts, explanation,
evidence, necessary conditions, scope, and strength of the claim unchanged. Delete it rather
than soften or expand the disclaimer.

中文判据：如果一句话只是为了防止被反驳，没有给内容增加更多意思，就删除。

**Redundant taxonomy distinction.** After categories have already been introduced unambiguously as
research themes, delete `These themes reflect different assessment purposes rather than separate
resilience dimensions.` It repeats a distinction already established instead of explaining a finding.
When a reviewer has identified unresolved confusion between the themes and the dimensions, state
their actual roles once. When the confusion affects a calculation, correct the operational definitions
and calculation as well. The phrase `rather than` alone is not evidence of defensive writing.

Look for repeated disclaimers, apology-like framing, hypothetical-objection rebuttals, self-undermining
contribution statements, and reflexive `not X but Y` constructions. Do not introduce generic cautions
merely to sound responsible.

Express scope positively and once at the relevant level. For example, when the source specifies the
period and cases, use `The analysis focuses on urban governance cases from 2015 to 2023` instead of
repeatedly saying the cases do not represent every governance context. Retain an additional sampling
limitation if it changes interpretation.

When uncertainty is real, identify its source from the supplied evidence rather than stacking
`may`, `could`, and `potentially`. Do not eliminate uncertainty while simplifying its expression.
Keep conceptual contrasts that carry the argument and distinctions needed to prevent a concrete
misinterpretation, such as association versus causation.

### Substantive meaning instead of warnings about interpretation

When a user asks for a result's meaning or practical insight, separate an observed pattern,
its substantive interpretation, and a warning about inference. A comparison repeated in broader
words is still a description. A warning about what readers cannot conclude is a scope statement,
not the requested insight.

- Counterexample: `全国层面的共同增长掩盖了省内关系的差异，不能仅凭总体同步判断各地均同步推进。`
  The opening restates an aggregate-versus-subgroup contrast; the ending warns against an inference.
  Do not present this sentence as the policy meaning of the correlation results.
- Develop meaning through an evidenced relationship involving the research object: a specific task,
  responsible actor, procedure, support measure, resource requirement, or other domain-relevant outcome.
  Identify the comparison needed to support that interpretation. More issuance, a higher score, or
  a different correlation does not by itself explain the substantive process.
- If the available analysis cannot establish the proposed insight, identify the missing comparison
  outside manuscript prose. Propose a focused analysis or omit the interpretive claim. Do not invent
  motives, causal mechanisms, implementation failures, or recommendations to fill the gap.
- Keep a necessary inference boundary where it materially affects interpretation, preferably with
  the relevant method or a consolidated limitation. Avoid ending each result with `不能据此认为`,
  `不代表`, or an equivalent rebuttal in place of an answer to the research question. A valid descriptive
  result need not carry a practical recommendation when the evidence supports only description.

### Empty transitions and deferred interpretation

Review sentences such as `其内容重点需要进一步结合具体任务判断`, `还需要结合其他指标分析`,
and `需要进一步研究才能理解其意义`. In Results, these often defer the answer, restate an obvious
need for analysis, or defensively qualify a finding without adding information. Do not use them
to manufacture a connection between paragraphs or figures.

Delete an empty transition when the next finding already supplies the connection. Otherwise state
the specific, evidenced relationship linking the comparisons, such as policy expansion followed by
the management tasks added during that expansion. A brief transition can identify the next concrete
comparison when readers need that link; avoid generic promises of further analysis. If two analyses
answer separate questions, reorganize them or explain their distinct roles outside the manuscript
candidate rather than inventing a substantive connection.

### Methods and Results

SERRA manuscript counterexamples to check during the Less Defense pass:

- `这些结果用于检验重点识别的稳健性，不代表实际地震中发生资源短缺的概率。` The first clause already states the output's role. Remove the speculative probability disclaimer unless the text actually reports a probability or readers need this distinction to interpret a specific result.
- `决定哪些数据、权重和假设需要优先核实。` This promises an action without naming an output or a concrete decision. State which measured outcome is sensitive to which input, or delete the tail when that evidence follows in Results.
- `由于各阶段重新计算能力秩，错配得分上升不能直接理解为本地资源减少。` Explain relative-rank recalculation once in Methods where the score is defined. In Results, report the observed score change and the supported interpretation without repeating a hypothetical misreading.
- `因此可以稳定识别关注对象，却不能凭一次计算的细小分差确定严格的投入次序。` This transition adds a defensive contrast after the evidence. State the observed combination directly, such as persistent group membership alongside a wide score range, and give its concrete implication only if the manuscript links it to a decision.

These examples are review signals rather than forbidden wording. Keep a distinction when it is needed to prevent a material error and cannot be expressed more directly at the relevant location.

Explicitly inspect `X does not imply Y`, `this does not mean that`, `should not be interpreted as`,
`applicability is limited`, `xxx 并不代表 xxx`, `不能据此认为`, and `适用条件有限`.
These are audit signals, not banned phrases.

- Methods: state what was done, the reason for the choice, assumptions, inclusion criteria,
  parameter ranges, and operating conditions. Reduce pre-emptive defenses of what was not attempted.
- Results: lead with the observation, comparison, magnitude, and existing evidence pointer.
  Avoid a formulaic disclaimer after every finding or at the end of every paragraph.
- Delete redundant restrictions when scope is already established. Replace vague limitations with
  concrete source-supported conditions. Never invent an applicability boundary.
- State shared boundaries once where they apply. Keep assumptions needed for reproducibility and
  qualifications essential to a local result in place. Broader generalizability usually belongs in
  Discussion. Move text between sections only when restructuring is authorized; otherwise suggest it.
- For reviewer responses, answer the actual comment directly with the relevant evidence or revision.
  Do not remove an explanation needed to address a real reviewer concern as if it were hypothetical.

For example, if this scope is supported, prefer `Under the tested conditions, X increased` to
`X increased, but this does not imply that the increase occurs under all conditions`. If the scope
was already made explicit nearby, repeating it may also be unnecessary.

### Data descriptions without defensive narration

- Keep internal audit status out of manuscript prose and table cells. Phrases such as `未核实`,
  `未检验`, `尚有疑点`, and `真实性待确认` belong in an author-facing evidence log, not as
  reflexive commentary around every input. Inspect the source or code first, then state the
  supported data period, coverage, processing rule, or modelling assumption directly.
- Do not turn an unsupported detail into a verified fact. Remove an unnecessary unsupported
  assertion; retain any material condition in concrete language, with broader scope and
  limitations discussed together rather than scattered through Methods and Results.
- Describe missing-data handling in one concise sentence when possible. Distinguish the stored
  data flag from the value used in calculation. For example: `资源清单按横截面数据使用，计算时将
  空白项记为零，并保留缺失标记。` A table can say `计算：空白项赋零` and `记录：保留缺失标记`.
  These describe different operations and should not look like competing rules.
- Delete repeated rebuttals such as `记录缺失并不意味着资源在实际中不存在` when the recording
  and calculation rules already explain the situation. Do not append a disclaimer to every
  result. If missingness materially changes an interpretation, state the actual coverage or
  evaluated assumption at the point where it matters.
- Prefer useful procedural information over bookkeeping narration. Cut phrases such as
  `首先统一数值格式` unless that conversion affects units, inclusion, or reproducibility.
  State what the assessment measures, how the main inputs become the score, and why the
  resulting comparison answers the research question.

## Punctuation and sentence variety

### Example: unnecessary consensus disclaimer

Before: `This analytical perspective organizes the review and does not imply complete scholarly agreement on the four dimensions.`

Action: delete when the paragraph already identifies the dimensions as the review's analytical framework. State the framework and its purpose directly rather than rebutting an unraised claim of universal agreement. Retain a disagreement statement only when documented differences are themselves part of the analysis.

Avoid rhetorical em-dashes and dash-delimited asides. Recast directly or split sentences. Reduce
semicolons, especially those repeatedly joining independent claims. Prefer full stops for distinct
points. Retain semicolons needed for clear complex lists, citation style, or formal notation.
Do not mechanically replace dashes with semicolons, colons, or parentheses. Avoid comma splices.
Preserve technical hyphens, numerical range dashes, mathematical signs, quotations, and formal notation.
Apply these checks to both English and Chinese prose.

Review openings, grammatical patterns, and endings across adjacent paragraphs. Reduce repeated
`X ..., while Y ...`, `By doing X, we ...`, `These results suggest that ...`,
`This ..., highlighting ...`, `not X but Y`, and their Chinese equivalents. Do not end every paragraph
with the same implication, summary, or caution formula.

Vary sentence structure according to meaning: direct subject-verb statements, conditions placed where
they matter, combined related observations, and separate sentences for distinct claims. Preserve
necessary hedging, precise terms, and meaningful parallelism in procedural steps, comparisons,
definitions, and aims. Do not replace one repeated template with another or force decorative variety.

## Author, venue, and proposal mode

Match supplied writing samples for sentence rhythm, voice, notation, and the placement of hedging,
subject to the user's explicit editing preferences. Without a sample, use clear, precise academic prose.
Do not impose a single voice on all disciplines or turn scholarly text into casual writing.

For grant and fellowship drafts, read [Proposal editing](references/proposals.md). Preserve credible
vision and connect goals to preliminary evidence, prior work, collaborators, or a feasible plan.
Do not apply paper-style trimming so aggressively that it erases the proposal's research ambition.

## Output

For existing-text polishing, return the itemized review table first. After the user confirms rows,
return the revised text or named artifact with a concise implemented/retained change report and
confirmation that numbers, equations, results, technical content, and citations were preserved.
State any unresolved evidence gap or expressly authorized exception. For fresh prose, return the
requested draft directly without an unsolicited editing log. Do not claim to have checked a full
manuscript or reference when only a passage was available.
