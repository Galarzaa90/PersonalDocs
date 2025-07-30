# Ruff

I use Ruff in most of my Python projects to keep consistent formatting and detect possible bugs. I usually have to go and copy my ruff config from another project and adjust it.

```toml
[tool.ruff.lint]
select = [
    "E", "W293", # pycodestyle
    "F", # Pyflakes
    "N", # pep8-naming
    "D", # pydocstyle
    "UP", # pyupgrade
    "S", # flake8-bandit
    "B", # flake8-bugbear
    "COM", # flake8-commas
    "C4", # flake8-comprehensions
    "FA", # flake8-future-annotations
    "ISC", # flake8-implicit-str-concat
    "G", # flake8-logging-format
    "PIE", # flake8-pie
    "Q", # flake8-quotes
    "RET", # flake8-return
    "SIM", # flake8-simplify
    "ARG", # flake8-unused-arguments
    "PERF", # Perflint
    "RUF", # Ruff-specific rules
    "ANN", # flake8-annotations
    "DTZ", # flake8-datetimez
    "PL", # Pylint
    "FURB", # refurb
]
ignore = [
    "D105", # Missing docstring in magic method
    "D107", # Missing docstring in `__init__`
    "RUF012", # Mutable class attributes should be annotated with `typing.ClassVar`
    "RUF013", # PEP 484 prohibits implicit `Optional`
    "ANN101", # Missing type annotation for {name} in method
    "ANN102", # Missing type annotation for {name} in classmethod
    "ANN202", # Missing return type annotation for private function {name}
    "ANN204", # Missing return type annotation for special method {name}
    "ANN401", # Dynamically typed expressions ({name}) are disallowed in `other`
    "PLR0913", # Too many arguments in function definition
    "PLR2004", #  Magic value used in comparison, consider replacing `{number}` with a constant variable
    "PLW2901", #  Outer {outer_kind} variable {name} overwritten by inner {inner_kind} target
]


[tool.ruff.lint.pycodestyle]
max-line-length = 120

[tool.ruff.lint.pep8-naming]
extend-ignore-names = ["assert*"]

[tool.ruff.lint.pyupgrade]
# Preserve types, even if a file imports `from __future__ import annotations`.
keep-runtime-typing = true

[tool.ruff.lint.flake8-bugbear]
# Allow default arguments like, e.g., `data: List[str] = fastapi.Query(None)`.
extend-immutable-calls = ["fastapi.Depends", "fastapi.Query", "fastapi.Path"]

[tool.ruff.lint.flake8-type-checking]
runtime-evaluated-base-classes = ["pydantic.BaseModel"]
```