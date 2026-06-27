这个 command 在每次任务结束后运行，用于判断对话中是否出现了值得沉淀到 skills 库的经验。

执行步骤：

1. **回顾对话**：梳理这次对话中出现的做法、决策和偏好，找出候选经验。

2. **读取评估标准**：读取 `skills/meta-skill/SKILL.md`，按照其中的判断标准逐条评估候选经验是否值得沉淀。

3. **如果有值得沉淀的内容**：
   - 读取 `CLAUDE.md` 索引，检查是否已有相关 skill 目录。
   - 若已有：更新对应的 `skills/<名称>/SKILL.md`，更新 `last_updated` 字段。
   - 若没有：按 `meta-skill` 的格式规范新建 `skills/<名称>/SKILL.md`，并在 `CLAUDE.md` 索引中添加一行。
   - 创建新分支，命名格式：`skill/<简短描述>`。
   - `git add` 变更文件，`git commit`，commit message 遵循 `skill(<名称>): 一句话描述` 格式。
   - 输出 `git diff main` 供 review。
   - 等待确认后，告知是否可以 merge 到 main。

4. **如果没有值得沉淀的内容**：说明判断理由（例如：本次经验属于一次性操作、或已被现有 skill 覆盖）。
