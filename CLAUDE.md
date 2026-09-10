# Skill을 추가하거나 고칠 때

- 위치: `skills/<이름>/SKILL.md`. 폴더 이름과 frontmatter `name`이 같아야 한다. 영문 소문자와 하이픈만.
- frontmatter `description`에는 언제 쓰는지와 사용자가 실제로 할 말(따옴표)을 넣는다. Claude는 이것을 보고 Skill을 고른다.
- 실제 계정명, secret, 개인 PC 경로를 넣지 않는다.
- 추가하거나 고친 뒤 `.claude-plugin/plugin.json`과 `.claude-plugin/marketplace.json`의 version을 함께 올린다.
