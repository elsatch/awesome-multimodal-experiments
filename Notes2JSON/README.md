# Notes2JSON experiments

This experiment aims to use vision models to extract the handwritten text and other features from color notes (like post-its) to structured text in JSON format.

## Summary of current work

Our current goal is being able to extract the number of notes in an image, handwritten text, position and color for each of them using Open source tools and models.

Interim discoveries and results: TBD

### List of experiments (in the notebooks folder)

#### Qwen-VL

For these experiments we will be using the Qwen-VL model (7B) quantized as INT4. Qwen-VL is a family of vision and language models that is able to extract the text in English, Chinese and probably other languages. Check for the feasibility of few-shot learning in the corresponding notebooks.

- [20240304-Query_Qwen_VL_Chat_INT4](./notebooks/20240304-Query_Qwen_VL_Chat_INT4.ipynb): This notebook uses the Qwen-VL model to extract the handwritten text from a picture with one or more notes. The model is able to extract the text from the notes and it's not required to format the output in any particular format. The model is able to extract the text in English, but doesn't keep the capitalization on the texts.
- [20240304-Few-Shot_Qwen_VL_Chat_INT4](./notebooks/20240304-Few-Shot_Qwen_VL_Chat_INT4.ipynb): This notebook uses the Qwen-VL model to extract the handwritten text from a picture with one or more notes. The model is able to extract the text from the notes and keep a basic formating, derived from a few example provided. It reinterprets the output format, but keeps it consistant from the first examples to the final output.
- [20240304-Few-Shot_Qwen_VL_Chat_INT4 JSON](./notebooks/20240304-Few-Shot_Qwen_VL_Chat_INT4%20JSON.ipynb): This notebook uses the Qwen-VL model to extract the handwritten text from a picture with one or more notes. The model is able to extract the text from the notes but it doesn't keep the JSON consistent in the first iteration, but produces a somewhat decent work on the final output.

## N2J Benchmark (Future work)

This benchmark will be used to compare the performance of different models and approaches to extract the handwritten text and other features from color notes (like post-its) as well their performance answering questions about the pictures themselves.

Possible metrics include:

- Zero, one-shot, and few-shot learning performance in regards to text extraction
- Zero, one-shot, and few-shot learning performance in regards to question answering
- Time to process the images in each of the zero, one-shot, and few-shot learning scenarios
- Memory usage in each of the zero, one-shot, and few-shot learning scenarios
- Context usage in regards of the few-shot learning scenarios, comparing the performance when adding new examples to the context

Initial questions to be asked about the pictures:

- How many notes are in the picture?
- What is the color of the notes?
- What is the color of the text in the notes?
- How many different shapes are the notes?
- What is the text in the notes?
- What is the position of the notes in the picture in natural language (center, top-left, bottom-right, etc)?
- What are the coordinates of the centroid of the notes?
