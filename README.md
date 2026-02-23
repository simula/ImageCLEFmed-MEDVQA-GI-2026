# ImageCLEFmed-MEDVQA-GI-2026

[**Registration**](https://www.imageclef.org/2026#registration)

The [**ImageCLEFmed-MEDVQA-GI**](https://www.imageclef.org/2026/medical/vqa) challenge (4th edition for ImageCLEFmedical) focuses on advancing **Visual Question Answering (VQA)** for **gastrointestinal (GI) endoscopy** with a strong emphasis on **clinical relevance**, **explainability**, and **safety**.

Building on insights and outcomes from previous editions, this year's challenge shifts focus from data generation toward **trustworthy multimodal reasoning** in realistic clinical settings. Models must not only answer clinically relevant questions from GI endoscopy images, but also justify their answers in a manner aligned with medical reasoning while adhering to clinical safety principles. The challenge explicitly addresses emerging concerns related to **overconfidence**, **hallucinations**, and **misleading explanations** in medical AI systems.

By integrating behavioral safety evaluation and retrieval-augmented reasoning, the challenge aims to promote the development of reliable, interpretable, and clinically robust VQA systems for endoscopy.

---

## Task Descriptions

### Subtask 1: Clinically Relevant Visual Question Answering

This subtask asks participants to develop algorithms that accurately answer clinically relevant questions based on gastrointestinal (GI) endoscopy images. Models must correctly interpret visual findings and question intent to produce concise and medically sound answers. The focus is on diagnostic and descriptive questions commonly encountered in clinical practice.

---

### Subtask 2: Multimodal Explainability and Safety-Aware Reasoning

This subtask extends standard VQA by requiring participants to generate coherent multimodal justifications that combine textual explanations with visual evidence from the image. Explanations should reflect established medical reasoning and remain factual, consistent, and clinically safe.

A dedicated safety layer evaluates whether models exhibit undesirable behaviors such as unwarranted overconfidence, misleading explanations, or deviations from medical best practices.

---

## Data

The data used for this year's challenge is based on an expanded version of the [Kvasir-VQA](https://datasets.simula.no/kvasir-vqa/) dataset, comprising more than 150,000 question-answer pairs derived from GI endoscopy images. The dataset supports both answer prediction and explainability evaluation.

To facilitate retrieval-augmented generation approaches, participants are also provided with a curated collection of verified endoscopy-related clinical resources that may be used during inference.

Datasets will be made available on our GitHub:
https://github.com/simula/ImageCLEFmed-MEDVQA-GI-2026

---

## Evaluation Methodology

The evaluation will differ for each subtask and will include a combination of objective and expert-based assessments.

**Subtask 1** is evaluated using automatic metrics assessing answer correctness and language quality.

**Subtask 2** combines automatic measures with expert-based assessment of explanation quality, interpretability, clinical plausibility, and safety.

A dedicated **behavioral safety evaluation** examines whether generated answers and explanations exhibit problematic behaviors such as hallucination, overconfidence, or unsafe clinical recommendations. We will host an online leaderboard for rapid evaluation feedback to nurture a competitive environment.

---

## Submission System

[View Registered Submissions](https://simulamet-medvqa.hf.space)

We use the [`medvqa`](https://pypi.org/project/medvqa/) Python package to validate and submit models to the official system. The model that needs to be submitted is expected to be in a HuggingFace repository.

### Installation
```bash
pip install -U medvqa
```
> The library is under active development. Always ensure you are using the latest version.

Your HuggingFace repo **must include** a standalone script named:
- `submission_task1.py` for Task 1
- `submission_task2.py` for Task 2

Use the provided template script, and make sure to:
- Modify all `TODO` sections
- Add required information directly in the script

### Validate Before Submitting
First make sure your submission script works in your working environment and that it loads the model correctly from your submission repo and generates outputs in the required format.

```bash
python submission_task1.py
```

#### Additional Dependencies
If your code requires extra packages, you must include a `requirements.txt` in the root of the repo. The system will install these automatically during validation/submission.

Next, you can validate the script to work independently. The `.py` script should be in the root of the same HuggingFace repo as your model. You can try this in a new venv:
```bash
medvqa validate --competition=gi-2026 --task=1/2 --repo_id=<your_repo_id>
```
- `--competition`: Set to `gi-2026`
- `--task`: Use `1` for Task 1 or `2` for Task 2
- `--repo_id`: Your HuggingFace model repo ID (e.g., `SushantGautam/XXModelCheckpoint`)

### Submission Command
If validation passes, you can run:
```bash
medvqa validate_and_submit --competition=gi-2026 --task=1/2 --repo_id=<your_repo_id>
```
This will create a submission and your username, along with the task and time, should be visible on [the portal](https://simulamet-medvqa.hf.space) for it to be considered officially submitted.

The submission library will make your Hugging Face repository public but gated, granting the organizers access to your repo. It must remain unchanged at least until the results of the competition are announced. However, you are free to make your model fully public (non-gated).

If you encounter any issues with submission, don't hesitate to contact us.

---

## Participant Registration

Please refer to the general [ImageCLEF registration instructions](https://www.imageclef.org/2026#registration).

Please also email steven@simula.no to register your interest.

**Note:** This task does not use the Ai4Media benchmarking platform for evaluation. Creating an account on the platform for this task is not required. Completing the registration form is still required, similar to the other tasks.

---

## Preliminary Schedule

- **26 January 2026:** Registration opens for all ImageCLEF tasks
- **01 March 2026:** Development dataset released
- **15 March 2026:** Test dataset released
- **23 April 2026:** Registration closes for all ImageCLEF tasks
- **07 May 2026:** Deadline for submitting participant runs
- **14 May 2026:** Release of processed results by the task organizers
- **28 May 2026:** Submission of participant papers [CEUR-WS]
- **30 June 2026:** Notification of acceptance
- **21 September 2026:** CLEF 2026, Jena, Germany

---

## Results

TBA

---

## CEUR Working Notes

For detailed instructions, please refer to the CEUR-WS guidelines. A summary of the most important points:

- All participating teams with at least one graded submission, regardless of the score, should submit a CEUR working notes paper.
- Teams who participated in both subtasks should generally submit only one report.

---

## Organizers

For any queries, feel free to reach out to our team:

- **Steven A. Hicks** - [steven@simula.no](mailto:steven@simula.no), SimulaMet, Norway
- **Sushant Gautam** - [sushant@simula.no](mailto:sushant@simula.no), SimulaMet, Norway
- **Michael A. Riegler** - [michael@simula.no](mailto:michael@simula.no), SimulaMet, Norway
- **Vajira Thambawita** - [vajira@simula.no](mailto:vajira@simula.no), SimulaMet, Norway
- **Pal Halvorsen** - [paalh@simula.no](mailto:paalh@simula.no), SimulaMet, Norway

---

## For More Details & Registration

Visit: [imageclef.org/2026#registration](https://www.imageclef.org/2026#registration)

View Registered Submissions: [simulamet-medvqa.hf.space](https://simulamet-medvqa.hf.space)
