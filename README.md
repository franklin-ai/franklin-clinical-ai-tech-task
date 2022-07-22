# Technical Assessment task for franklin.ai

This is a technical assessment task for the role of [Clinical AI Associate](
https://jobs.lever.co/franklinai/2fdeaa3f-e35a-462d-ada8-c95a1b2e15b0) at [franklin.ai](https://franklin.ai/).

Your task is to write a script or jupyter notebook that assigns each image in a dataset to either a training, validation or test set. You may implement the solution using your choice of:

* Python
* Jupyter Notebook
* R

You are welcome to use external open-source libraries if desired.

Your solution to this task will form the starting point for a 60-minute technical interview,
during which we'll collaboratively review the code, discuss your design choices, and investigate
potential future enhancements or possible oversights.

## Task Expectations

You should take a copy of this repo, implement the requirements described below, and push them to GitHub
for discussion in the scheduled technical interview. You're welcome to use a private repository, as
long as it is visible to `@SamMaksoud8`

You will be given the email address of a member of the team, and should email this person with a link to your
solution at least 24 hours before the scheduled technical interview. You're also encouraged to email them with
questions at any time while working on this task.

**Please don't spend more than a few hours on this task**.

We are not expecting anything too elaborate. It's a small self-contained exercise to
help us get to know you through your code - how you explore the dataset to determine the distribution of images in each split, how you structure your code, and how you
communicate about it with your potential future team-mates.

We'll be looking for a clear and well justified solution that ensures the dataset splits produced are suitable for model training and validation.
We will *not* be looking for micro-optimisations or for every single detail to be carefully polished.

## Task Requirements

This technical assesment is an exploratory data analysis and dataset curation task. It will asses your ability to prepare datasets for computer vision applications in the medical domain. In this generic medical task, each patient contains one or more medical images, and each image contains one more class labels. 

Given a file (dataset.json) containing patients, images and their corrosponding labels* like the following:

```json
{
    "Patient 1": {
        "Image 1": [
            "Class 1",
            "Class 2",
            "Class 3"
        ],
         "Image 8": [
            "Class 1",
            "Class 2"
        ]
    },
    
    "Patient 2": {
        "Image 3": [
            "Class 1",
            "Class 2",
            "Class 3"
        ]
    },
  
    "Patient 3": {
        "Image 6": [
            "Class 1",
            "Class 2",
            "Class 3"
        ]
    }
}
```

Write a script that generates the following output:

```json
{
    "Training Set": ["Image 1", "Image 8"],
    "Test Set": ["Image 3","Image 6"]
}
```


In addition to the json output above, you must also report descriptive information about the dataset such as: number of patients, number of images, number of classes, and any other information that you feel is relevant to the downstream processes of model training. Providing visual analysis of the distributions of classes in each set is highly encouraged. This functionality may be implemented using your choice of **Python**,  **Jupyter Notebook** or **R** and may use external open-source libraries if desired. 

*Note - listing a class in the json under an image means that it is positive for that class.
