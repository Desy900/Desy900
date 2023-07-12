from pptx import Presentation

# Load the presentation
presentation = Presentation('/mnt/data/Waiterful Business Overview 2023 (1).pptx')

# Let's check the content of each slide
slides_text = []
for slide in presentation.slides:
    slide_content = []
    for shape in slide.shapes:
        if shape.has_text_frame:
            for paragraph in shape.text_frame.paragraphs:
                for run in paragraph.runs:
                    slide_content.append(run.text)
    slides_text.append(' '.join(slide_content))

slides_text

