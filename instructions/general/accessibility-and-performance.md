# Accessibility And Performance

## Accessibility

When a project has a user interface:

- Use semantic elements before accessibility attributes and preserve keyboard access.
- Provide labels, visible focus, meaningful alternatives for non-text content, and useful error
  messages.
- Do not communicate state, validation, or meaning through color alone.
- Check the real interaction path with keyboard and assistive-technology-friendly semantics.

## Performance

- Measure before optimizing and use the repository's existing profiling or monitoring tools.
- Prevent obvious request waterfalls and unnecessary work at boundaries.
- Avoid speculative memoization, caching, virtualization, batching, and background work.
- Prefer the platform's native behavior before adding a custom implementation.
- Keep performance changes focused on a measured bottleneck and preserve correctness and accessibility.
