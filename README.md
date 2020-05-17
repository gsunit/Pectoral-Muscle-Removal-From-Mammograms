# Pectoral Muscle Removal from Mammograms
<figure>
  <img src="https://github.com/gsunit/Pectoral-Muscle-Removal-From-Mammograms/blob/master/algorithm-screenshot.png" alt="algorithm-screenshot"/>
  <figcaption>Screenshot of the image processing algorithm from the Jupyter Notebook</figcaption>
</figure>

## Glossary
### Mammograms
A mammogram is an X-ray picture of the breast. Doctors use a mammogram to look for early signs of breast cancer.

## Algorithm
```mermaid
graph LR

A(Start)

A --> B{Is it right-oriented?}
B --> |Yes| D(Canny edge detection)
B --> |No| E(Flip image)
E --> D
D --> F(Obtain Hough transform lines)
F --> G(Shortlist lines)
G --> H{If more than one line shortlisted}
H --> |Yes| I(Choose one with least area removed)
H --> |No| J(Darken pixels of area segmented by selected line)
I --> J
