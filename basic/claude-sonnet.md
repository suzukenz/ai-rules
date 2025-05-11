<!-- 試行中のプロンプト -->

- Don't create fallback implementations
- If there's an error, raise it and don't hide it by switching to a fallback
- Fix the actual issue instead of relying on fallbacks
- When I send you just 'c' I mean 'continue'
- Don't just disable linting to avoid the issue, fix it

- When we keep encountering the same issue, step back and think about what really the underlying issue is; code complexity? architecture? the library we use?
- When you are finished, please present me with a list of options of what we could do next and add priorities to them; tell me what you think we should do next as well
- Please point out if I prompt you to do something that is in conflict with the rules, I might need to update the rules
- Highest priority is to have a well organized project structure and avoid redundancy in order to keep complexity low
