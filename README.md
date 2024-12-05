
> **⚠️ Important Note:**  
> Mục đích của repo này là để em demo trong buổi workshop và cũng là để cho anh em luyện tập, làm quen thao tác, để hiểu được concept.  
> Chứ workflow này chưa phải là final version. Em sẽ làm 1 repo khác hoặc branch khác cho final version sau. Version đó sẽ đầy đủ và chất lượng hơn.

## Know-how

* [The correct approach to do software development with AI](https://mm.tt/app/map/3491464465?t=VSDMUwppGh)

## Toolset

* Aider: https://aider.chat/ - Hoặc anh em cũng có thể dùng Cursor Composer cũng được. (Nhưng để luyện tập hiệu quả thì em vẫn recommend dùng Aider trước)
* llm model: [Claude 3.5 Sonnet](https://www.anthropic.com/news/claude-3-5-sonnet) (highly recommended)

## Các ưu điểm

* professional workflow. Giúp development workflow chuyên nghiệp hơn, giảm thiểu được các sai sót và nâng chất lượng code.
* documenting on the go. Giúp cho repo có nhiều documents hơn.
* learn from AI. Giúp anh em dev học thêm những practices từ senior dev (aka AI)

* Workflow này không hứa hẹn sẽ giúp anh em làm việc nhanh hơn, nhưng chắc chắn là sẽ giúp anh em làm việc hiệu quả hơn và thú vị hơn. Khi anh em đã quen thao tác với AI workflow này rồi thì nó sẽ nhẹ nhàng và hiệu quả tựa như cách mà anh em đã từng làm quen với những code editor (như Vim hoặc VSCode).

## Insights

* without AI workflow

  ```mermaid
  flowchart TD
      A(requirements) -->|discuss, brainstorm| B[dev]
      B --> C{Let me think}
      C -->|implement| D[task 1]
      C -->|implement| E[task 2]
      C -->|implement| F[task 3]
  ```

  * *with just coding copilot only, that would be not enough*
  * *one-shot prompting would overwhelmed the llm, which would lead to not good result.*

* with AI workflow

  ```mermaid
  flowchart TD
      A(requirements) -->|discuss/brainstorm| B[dev]
      B -->|guide/review/approve| C["phase_1 (planer)"]
      C -->|core_requirements.md| D["phase_2 (architect/tech_stack generator)"]
      D -->|bom.md/package.json/Gemfile| E["phase_3 (stories generator)"]
      E -->|stories.md| E1[story 1]
      E -->|stories.md| E2[story 2]
      E -->|stories.md| E3[story 3]
      E1 --> F1["phase_4 (story implementor)"]
      F1 --> G1[commit_1]
      E2 --> F2["phase_4 (story implementor)"]
      F2 --> G2[commit_2]
      E3 --> F3["phase_4 (story implementor)"]
      F3 --> G3[commit_3]
  ```

  * key benefits:
    * professional workflow.
    * have AI assisting on each phase of development works
    * learn from AI
    * documenting on the go (the future you will thank you)
    * and more …
