# STITCH_BATCH_BRIEF

Generate exactly 7 production-quality UI screens for the Product Surface targets below.
Batch stage: all surfaces.
Generate every SCREEN_SPEC in this batch call. Do not generate screens outside this stage.
If this Stitch project already has screens from an earlier stage, preserve the same visual system, navigation pattern, density, typography, spacing, and component language.
Target device type: DESKTOP.
All visible user-facing text must be in English.

## PRODUCT_VISION_SUMMARY
- Ticket Loom turns the user's request into a directly usable web workflow. The first experience must be the actual web product behavior, not a marketing landing page or placeholder demo.
- - FR-001: Build a compact browser service desk app called Ticket Loom that manages tickets, queues, agents, SLA status, insights, settings, empty and error states.
- Users who need the requested web product to work immediately with clear feedback, recovery paths, and deterministic verification hooks.

## REQUIRED_SCREEN_TITLES
- Ticket Operations - Product
- Ticket Editor - Product
- Queue and Status Management - Product
- Agent Workload - Product
- Insights - Product
- Settings and Preferences - Product
- Empty and Error Recovery - Product

## SCREEN_SPECS
SCREEN_SPEC_1:
- exact_screen_title: Ticket Operations - Product
- surface_id: SURF_TICKET_OPERATIONS
- unique_canvas_caption: Ticket Operations: summary metrics, primary list/board/table, filters, search, selected item preview, empty/loading/error states.
- purpose: Give the user the main operational view for inspecting, searching, filtering, and acting on Ticket data.
- required_content: summary metrics, primary list/board/table, filters, search, selected item preview, empty/loading/error states.
- data_entities: Ticket, ActivityEvent, Preference
- visible_actions: ACT_SEARCH_RECORDS as search_input_persistent, ACT_CREATE_RECORD as primary_button, ACT_SELECT_RECORD as inline_edit, ACT_RETRY_LOAD as secondary_button
- entry_exit_rules: direct_url -> If data is unavailable, stay on the same surface and show retry/clear actions.
- design_guidance: Dense but calm product UI; avoid marketing hero composition and unrelated admin/reporting modules.

SCREEN_SPEC_2:
- exact_screen_title: Ticket Editor - Product
- surface_id: SURF_TICKET_EDITOR
- unique_canvas_caption: Ticket Editor: form fields, required/optional indicators, validation messages, save/cancel controls, unsaved-state feedback.
- purpose: Let the user create, edit, validate, save, cancel, and recover Ticket changes.
- required_content: form fields, required/optional indicators, validation messages, save/cancel controls, unsaved-state feedback.
- data_entities: Ticket, ValidationError
- visible_actions: ACT_SAVE_RECORD as form_submit, ACT_CANCEL_EDIT as secondary_button
- entry_exit_rules: SURF_TICKET_OPERATIONS -> Save returns to SURF_TICKET_OPERATIONS with persisted changes; cancel preserves existing data and closes the editor.
- design_guidance: Form layout must be clear and task-specific; do not invent payment, onboarding, or unrelated identity forms.

SCREEN_SPEC_3:
- exact_screen_title: Queue and Status Management - Product
- surface_id: SURF_QUEUE_AND_STATUS_MANAGEMENT
- unique_canvas_caption: Queue and Status Management: queue/status lanes, SLA or priority markers, ownership, blockers, aging indicators, and next-action controls.
- purpose: Help users organize Ticket work by queue, status, SLA, stage, priority, or triage context when those signals are part of the requested product.
- required_content: queue/status lanes, SLA or priority markers, ownership, blockers, aging indicators, and next-action controls.
- data_entities: Ticket, ActivityEvent, Preference
- visible_actions: ACT_SEARCH_RECORDS as search_input_persistent, ACT_SELECT_RECORD as inline_edit, ACT_UPDATE_RECORD_STATUS as inline_edit
- entry_exit_rules: SURF_TICKET_OPERATIONS -> Status changes keep the user in the same Ticket context and expose recoverable failure feedback.
- design_guidance: Represent operational state clearly; do not flatten queue/SLA work into decorative metrics.

SCREEN_SPEC_4:
- exact_screen_title: Agent Workload - Product
- surface_id: SURF_AGENT_WORKLOAD
- unique_canvas_caption: Agent Workload: agent/owner list, workload counts, stale or overdue indicators, reassignment controls, and recent activity.
- purpose: Show how Ticket work is assigned, overloaded, pending, or blocked across agents or owners.
- required_content: agent/owner list, workload counts, stale or overdue indicators, reassignment controls, and recent activity.
- data_entities: Ticket, ActivityEvent
- visible_actions: ACT_SEARCH_RECORDS as search_input_persistent, ACT_SELECT_RECORD as inline_edit, ACT_ASSIGN_RECORD as context_menu, ACT_FILTER_INSIGHTS as context_menu
- entry_exit_rules: SURF_TICKET_OPERATIONS, SURF_QUEUE_AND_STATUS_MANAGEMENT -> Reassignment preserves the selected Ticket and updates visible queue/status counts.
- design_guidance: Make workload and ownership scannable without creating a separate HR or account-management module.

SCREEN_SPEC_5:
- exact_screen_title: Insights - Product
- surface_id: SURF_INSIGHTS
- unique_canvas_caption: Insights: small metrics, recent activity, state distribution, actionable follow-up hints, empty/error state.
- purpose: Show useful summaries, trends, and status signals derived from Ticket data without becoming a separate analytics product.
- required_content: small metrics, recent activity, state distribution, actionable follow-up hints, empty/error state.
- data_entities: Ticket, ActivityEvent
- visible_actions: ACT_FILTER_INSIGHTS as context_menu, ACT_EXPORT_SUMMARY as secondary_button
- entry_exit_rules: SURF_TICKET_OPERATIONS -> No external BI/admin area; returns to SURF_TICKET_OPERATIONS.
- design_guidance: Keep insight content project-relevant and compact; no generic charts unrelated to the requested domain.

SCREEN_SPEC_6:
- exact_screen_title: Settings and Preferences - Product
- surface_id: SURF_SETTINGS_AND_PREFERENCES
- unique_canvas_caption: Settings and Preferences: saved filters, default views, notification or density preferences when relevant, reset controls, and visible save feedback.
- purpose: Let users adjust Ticket workflow preferences, saved filters, defaults, or product settings requested by the task.
- required_content: saved filters, default views, notification or density preferences when relevant, reset controls, and visible save feedback.
- data_entities: Preference
- visible_actions: ACT_SAVE_PREFERENCES as form_submit, ACT_RETRY_LOAD as secondary_button
- entry_exit_rules: SURF_TICKET_OPERATIONS -> Saved preferences immediately affect visible product state or show a clear confirmation.
- design_guidance: Settings must support the requested workflow only; do not invent unrelated profile or billing areas.

SCREEN_SPEC_7:
- exact_screen_title: Empty and Error Recovery - Product
- surface_id: SURF_EMPTY_AND_ERROR_RECOVERY
- unique_canvas_caption: Empty and Error Recovery: clear cause, retry/reset controls, create-first action, clear-filter action, and state-specific guidance.
- purpose: Keep the Ticket workflow usable when data is missing, filtered away, loading, failed, or corrupt.
- required_content: clear cause, retry/reset controls, create-first action, clear-filter action, and state-specific guidance.
- data_entities: Ticket, ActivityEvent, Preference
- visible_actions: ACT_RETRY_LOAD as primary_button, ACT_CREATE_RECORD as secondary_button
- entry_exit_rules: SURF_TICKET_OPERATIONS, SURF_INSIGHTS -> Recovery returns to the active Ticket workflow and preserves unrelated state.
- design_guidance: Recovery states must be useful product states, not blank placeholder panels.

## OUTPUT_RULES
- Create one distinct canvas/frame per SCREEN_SPEC.
- Do not create a design-system/style-guide canvas as an output screen. Apply the design system inside the product screens only.
- Do not output palette, typography, component inventory, or moodboard screens.
- Use exact_screen_title as the screen title/name. Do not rename screens to generic labels.
- Use unique_canvas_caption for that screen only. Do not reuse one global caption across screens.
- Do not place the whole chunk summary, PRD summary, Key Deliverables text, or any follow-up question as visible screen captions.
- Do not write 'How would you like to proceed?', 'We could refine...', or similar assistant chat text in the design output.
- Each screen must visibly emphasize its own required_content and visible_actions. Do not let all screens share the same layout content.

## STRICT_UI_SCOPE_CONTRACT
- Every generated screen must map to one or more SCREEN_SPECS above.
- Do not invent modules, dashboards, marketing pages, admin areas, ecommerce flows, docs, account, or profile areas outside the Product Surfaces.
- Every permitted action from the matching Product Surface should have a plausible visible control or platform-appropriate interaction.
- Empty, loading, validation, and error states may be included only inside the declared Product Surfaces.

## PRODUCT_SURFACES
1. SURF_TICKET_OPERATIONS - Ticket Operations
   Purpose: Give the user the main operational view for inspecting, searching, filtering, and acting on Ticket data.
   Data: Ticket, ActivityEvent, Preference
   Core content: summary metrics, primary list/board/table, filters, search, selected item preview, empty/loading/error states.
   Actions: ACT_SEARCH_RECORDS (search_input_persistent), ACT_CREATE_RECORD (primary_button), ACT_SELECT_RECORD (inline_edit), ACT_RETRY_LOAD (secondary_button)
   Entry/exit: direct_url -> If data is unavailable, stay on the same surface and show retry/clear actions.
   Guidance: Dense but calm product UI; avoid marketing hero composition and unrelated admin/reporting modules.

2. SURF_TICKET_EDITOR - Ticket Editor
   Purpose: Let the user create, edit, validate, save, cancel, and recover Ticket changes.
   Data: Ticket, ValidationError
   Core content: form fields, required/optional indicators, validation messages, save/cancel controls, unsaved-state feedback.
   Actions: ACT_SAVE_RECORD (form_submit), ACT_CANCEL_EDIT (secondary_button)
   Entry/exit: SURF_TICKET_OPERATIONS -> Save returns to SURF_TICKET_OPERATIONS with persisted changes; cancel preserves existing data and closes the editor.
   Guidance: Form layout must be clear and task-specific; do not invent payment, onboarding, or unrelated identity forms.

3. SURF_QUEUE_AND_STATUS_MANAGEMENT - Queue and Status Management
   Purpose: Help users organize Ticket work by queue, status, SLA, stage, priority, or triage context when those signals are part of the requested product.
   Data: Ticket, ActivityEvent, Preference
   Core content: queue/status lanes, SLA or priority markers, ownership, blockers, aging indicators, and next-action controls.
   Actions: ACT_SEARCH_RECORDS (search_input_persistent), ACT_SELECT_RECORD (inline_edit), ACT_UPDATE_RECORD_STATUS (inline_edit)
   Entry/exit: SURF_TICKET_OPERATIONS -> Status changes keep the user in the same Ticket context and expose recoverable failure feedback.
   Guidance: Represent operational state clearly; do not flatten queue/SLA work into decorative metrics.

4. SURF_AGENT_WORKLOAD - Agent Workload
   Purpose: Show how Ticket work is assigned, overloaded, pending, or blocked across agents or owners.
   Data: Ticket, ActivityEvent
   Core content: agent/owner list, workload counts, stale or overdue indicators, reassignment controls, and recent activity.
   Actions: ACT_SEARCH_RECORDS (search_input_persistent), ACT_SELECT_RECORD (inline_edit), ACT_ASSIGN_RECORD (context_menu), ACT_FILTER_INSIGHTS (context_menu)
   Entry/exit: SURF_TICKET_OPERATIONS, SURF_QUEUE_AND_STATUS_MANAGEMENT -> Reassignment preserves the selected Ticket and updates visible queue/status counts.
   Guidance: Make workload and ownership scannable without creating a separate HR or account-management module.

5. SURF_INSIGHTS - Insights
   Purpose: Show useful summaries, trends, and status signals derived from Ticket data without becoming a separate analytics product.
   Data: Ticket, ActivityEvent
   Core content: small metrics, recent activity, state distribution, actionable follow-up hints, empty/error state.
   Actions: ACT_FILTER_INSIGHTS (context_menu), ACT_EXPORT_SUMMARY (secondary_button)
   Entry/exit: SURF_TICKET_OPERATIONS -> No external BI/admin area; returns to SURF_TICKET_OPERATIONS.
   Guidance: Keep insight content project-relevant and compact; no generic charts unrelated to the requested domain.

6. SURF_SETTINGS_AND_PREFERENCES - Settings and Preferences
   Purpose: Let users adjust Ticket workflow preferences, saved filters, defaults, or product settings requested by the task.
   Data: Preference
   Core content: saved filters, default views, notification or density preferences when relevant, reset controls, and visible save feedback.
   Actions: ACT_SAVE_PREFERENCES (form_submit), ACT_RETRY_LOAD (secondary_button)
   Entry/exit: SURF_TICKET_OPERATIONS -> Saved preferences immediately affect visible product state or show a clear confirmation.
   Guidance: Settings must support the requested workflow only; do not invent unrelated profile or billing areas.

7. SURF_EMPTY_AND_ERROR_RECOVERY - Empty and Error Recovery
   Purpose: Keep the Ticket workflow usable when data is missing, filtered away, loading, failed, or corrupt.
   Data: Ticket, ActivityEvent, Preference
   Core content: clear cause, retry/reset controls, create-first action, clear-filter action, and state-specific guidance.
   Actions: ACT_RETRY_LOAD (primary_button), ACT_CREATE_RECORD (secondary_button)
   Entry/exit: SURF_TICKET_OPERATIONS, SURF_INSIGHTS -> Recovery returns to the active Ticket workflow and preserves unrelated state.
   Guidance: Recovery states must be useful product states, not blank placeholder panels.

## UI_SAFE_PRD_CONTEXT
Use this only to understand product behavior and missing UI states. Do not render this text directly. SCREEN_SPECS remain the active screen source.
## 1. Context And Goals - Overview: Ticket Loom turns the user's request into a directly usable web workflow. The first experience must be the actual web product behavior, not a marketing landing page or placeholder demo. - Target Audience: Users who need the requested web product to work immediately with clear feedback, recovery paths, and deterministic verification hooks. - UI Language: English. Pipeline metadata, action IDs, surface IDs, story titles, technical reports, and file identifiers remain English. - Core Objectives: - FR-001: Build a compact browser service desk app called Ticket Loom that manages tickets, queues, agents, SLA status, insights, settings, empty and error states. - Business Goals: reduce ambiguity for downstream agents, preserve the requested domain, and keep unrelated modules out of scope. - User Goals: inspect current state, take primary actions, understand validation/recovery feedback, and return to a stable state after failures. - Primary Workflows: load product state, perform the main action, recover from validation/system errors, and verify final state through the platform-appropriate test surface. - Non-Functional: first usable state under 2s for local/frontend apps, WCAG 2.1 AA for UI platforms, deterministic test handles, and responsive behavior for UI platforms. - External Dependencies: none unless explicitly listed in the task or System Contracts. ## 3. Behavioral And Action Contract ## 5. Validation And Error Strategy - Validation Rules: required text fields cannot be empty; status/enum values must be known; dates/timestamps must be parseable; destructive actions require explicit user intent. - Business Logic Errors: show contextual messages near the action and keep the previous valid state. - System/Network Errors: show a retryable banner or inline state with lastError details suitable for QA, not a silent reset. - Error Display Policy: forms use inline errors; global load/persist failures use compact banners or state panels; no blocking alert dialogs unless the platform requires them. ## 9. Out Of Scope - No physical screen table, screen-count field, or agent-invented screen list in PLAN. - No modules outside Product Surfaces, Action Contracts, or explicit task requirements. - No local fallback design; DESIGN must use Stitch when DESIGN_REQUIRED=true and must block on Stitch failure.