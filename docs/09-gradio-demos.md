


```markdown
# Gradio Demos

## Interface

High-level API for simple applications.

```python
gr.Interface(
    fn=predict,
    inputs="text",
    outputs="text"
).launch()
