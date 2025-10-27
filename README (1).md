# GENAI Dataset: VQA Model Outputs and Noisy/Original Images

This repository contains outputs from a Visual Question Answering (VQA) experiment, as well as both original and synthetically noised images. All data is organized under the `GENAI DATASET/` folder.

---

## 📂 Dataset Structure

```
GENAI DATASET/
├── Model Output/
│   ├── vqa_results_correct_original.json
│   ├── vqa_results_correct_blurred.json
│   ├── vqa_results_correct_gaussian.json
│   ├── vqa_results_generated_original.json
│   ├── vqa_results_generated_blurred.json
│   ├── vqa_results_generated_gaussian.json
│   ├── vqa_results_wrong_original.json
│   ├── vqa_results_wrong_blurred.json
│   └── vqa_results_wrong_gaussian.json
│
├── Noisy Images/
│   ├── blur/
│   │   ├── blur_COCO_train2014_000000000009.jpg
│   │   ├── blur_COCO_train2014_000000000025.jpg
│   │   └── ...
│   └── gaussian/
│       ├── gaussian_COCO_train2014_000000000009.jpg
│       ├── gaussian_COCO_train2014_000000000025.jpg
│       └── ...
│
├── Original Images/
│   ├── COCO_train2014_000000000009.jpg
│   ├── COCO_train2014_000000000025.jpg
│   └── ...
│
└── annotations_Question_and_Answers.json
```

---

## 🔍 File Descriptions

### Model Output (`Model Output/`)
Each JSON file contains VQA results for the 20 selected images. Filenames follow this pattern:

- `vqa_results_<type>_<noise>.json`

Where:
- `<type>`  
  - `correct`: model’s answers matching the ground truth  
  - `generated`: model’s generated answers  
  - `wrong`: model’s incorrect answers  

- `<noise>`  
  - `original`: no noise applied  
  - `blurred`: Gaussian blur applied to input images  
  - `gaussian`: Gaussian noise added to input images  

**Example:**  
`vqa_results_generated_blurred.json`  
> Contains all generated answers on the blurred version of the 20 images.

---

### Noisy Images (`Noisy Images/`)
Holds two subfolders with processed images:

- `blur/`  
  - Images blurred via a Gaussian kernel  
  - Filenames: `blur_<original_filename>.jpg`

- `gaussian/`  
  - Images with additive Gaussian noise  
  - Filenames: `gaussian_<original_filename>.jpg`

---

### Original Images (`Original Images/`)
The 20 clean COCO train2014 images used in the experiment. Filenames follow the COCO convention:

```
COCO_train2014_000000000009.jpg
COCO_train2014_000000000025.jpg
...
```

---

### Annotations (`annotations_Question_and_Answers.json`)
A single JSON file linking each selected image to its VQA questions and ground-truth answers. Structure:

```json
[
  
      "image_id": 9,
      "file_name": "COCO_train2014_000000000009.jpg",
      "correct_caption": "food items",
      "wrong_caption": "pebbles",
      "questions": [
        {
          "question_id": 9000,
          "question": "How many cookies can be seen?",
          "multiple_choice_answer": "2",
          "ground_truth_answers": [
            {
              "answer": "2",
              "answer_confidence": "yes",
              "answer_id": 1
            },
            {
              "answer": "2",
              "answer_confidence": "maybe",
              "answer_id": 2
            },
            {
              "answer": "2",
              "answer_confidence": "yes",
              "answer_id": 3
            },
            {
              "answer": "2",
              "answer_confidence": "yes",
              "answer_id": 4
            },
            {
              "answer": "2",
              "answer_confidence": "yes",
              "answer_id": 5
            },
            {
              "answer": "2",
              "answer_confidence": "yes",
              "answer_id": 6
            },
            {
              "answer": "2",
              "answer_confidence": "yes",
              "answer_id": 7
            },
            {
              "answer": "2",
              "answer_confidence": "yes",
              "answer_id": 8
            },
            {
              "answer": "2",
              "answer_confidence": "yes",
              "answer_id": 9
            },
            {
              "answer": "2",
              "answer_confidence": "yes",
              "answer_id": 10
            }
          ],
          "question_type": "counting"
        },
  ...
]
```

---

## ⚙️ How to Use

1. **Download** or **clone** this repository (including the `GENAI DATASET/` folder).
2. **Inspect**:
   - Model outputs in `GENAI DATASET/Model Output/`
   - Noisy variants in `GENAI DATASET/Noisy Images/`
   - Original images in `GENAI DATASET/Original Images/`
   - Ground-truth Q&A in `annotations_Question_and_Answers.json`
3. **Load** JSON files in your preferred environment (Python, MATLAB, etc.) to analyze performance across noise types.

---

## 🛠 Dependencies

No code to run here—this folder holds data only. To reproduce or generate similar outputs, refer to the `GEN_AI.ipynb` notebook.

---

## 📜 License

 The original COCO and VQA datasets are subject to their own licenses.
