


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

with gr.Blocks() as demo:
    text = gr.Textbox()
    output = gr.Textbox()
    button = gr.Button("Run")

    button.click(fn=predict, inputs=text, outputs=output)
