from pathlib import Path

source = Path("/mnt/data/Pasted markdown(7).md")
readme = Path("/mnt/data/README.md")

original = source.read_text(encoding="utf-8")

badges = """<!-- Corporate README Badges -->
![Strategic Architecture](https://img.shields.io/badge/Strategic%20Architecture-Corporate%20Blueprint-0A2540)
![Operating Model](https://img.shields.io/badge/Operating%20Model-Solo%20Operator-1F4E79)
![Business Model](https://img.shields.io/badge/Business%20Model-Revenue%20Operations-2E6E65)
![Execution Roadmap](https://img.shields.io/badge/Execution%20Roadmap-90%20Days-6B7280)
![Treasury Strategy](https://img.shields.io/badge/Treasury%20Strategy-BTC%20%2B%20Dividend%20Equities-F59E0B)
![Capital Allocation](https://img.shields.io/badge/Capital%20Allocation-Disciplined-374151)

"""

# Preserve the supplied document verbatim; only prepend README badges.
readme.write_text(badges + original, encoding="utf-8")

print(f"Created: {readme}")
print(f"Original lines preserved: {len(original.splitlines())}")
print(f"README lines: {len(readme.read_text(encoding='utf-8').splitlines())}")
