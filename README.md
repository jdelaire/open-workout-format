# Open Workout Format

Open Workout Format is an AI-first, human-readable format for describing workout instructions.

The first specification is **Workout Day Markdown v0.1**, a Markdown-based format for one complete training day. It is designed to be:

- readable by coaches and athletes;
- parseable by software;
- resilient to messy real-world plans;
- broad enough for strength, hypertrophy, skill, conditioning, EMOM, AMRAP, intervals, tests, and warm-ups;
- useful as a conversion target for AI systems.

Set is the first intended consumer, but the format is not Set-specific.

## Status

Draft v0.1.

The format is stable enough to build prototypes and fixtures against, but it may change as more real programs are converted.

## Canonical Spec

- [Workout Day Markdown v0.1](spec/v0.1.md)

## Examples

- [Hypertrophy tri-set](examples/hypertrophy-tri-set.md)
- [EMOM](examples/emom.md)
- [AMRAP](examples/amrap.md)
- [Strength day](examples/strength-day.md)

### Real-World Pattern Fixtures

These examples are synthetic and rights-safe. They mirror common structures found in real training PDFs without copying source program content.

- [Tempo strength day](examples/real-world-patterns/tempo-strength-day.md)
- [Rehab calendar day](examples/real-world-patterns/rehab-calendar-day.md)
- [Compact week session](examples/real-world-patterns/compact-week-session.md)
- [Max-rep test session](examples/real-world-patterns/max-rep-test-session.md)
- [Note-heavy press day](examples/real-world-patterns/note-heavy-press-day.md)
- [AMRAP with composite item](examples/real-world-patterns/amrap-composite-item.md)

## Design Goals

1. Preserve intent over precision.
2. Keep the source readable as Markdown.
3. Mark semantic workout boundaries explicitly.
4. Normalize values only when safe.
5. Preserve unknown fields instead of dropping information.
6. Make AI conversion output auditable by humans.

## Non-Goals For v0.1

- Full multi-week program scheduling.
- Athlete profiles, equipment inventory, injuries, or readiness state.
- Logged workout history.
- A required database schema.
- A converter skill or parser package.

## Minimal Example

```md
# Lower Body

::: block id=part-1 name="Tri-set" kind=tri-set
complete: 4 rounds
rest: 1m30s-2m
rpe: 8

- Eccentric Nordic Hamstring Curl
  reps: 5
  tempo: "Slow the eccentric as much as possible"

- Leg Extension
  reps: 10/side
  tempo: 20X2

- Banded Clamshell
  reps: 10/side
:::
```

## Versioning

The spec uses explicit versioned documents under `spec/`. Draft changes should update the current draft until a version is declared stable. Breaking changes after a stable release should create a new spec version.

## License

MIT. See [LICENSE](LICENSE).
