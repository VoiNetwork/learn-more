# Project Documentation

This repository contains the documentation for the project, built using [MkDocs](https://www.mkdocs.org/) with the [Material for MkDocs](https://squidfunk.github.io/mkdocs-material/) theme.

## Prerequisites

Ensure you have the following installed:
- Python 3.x
- `pip` (Python's package installer)

If you're running Ubuntu and haven't installed Python yet, you can install Python and pip by running:

```bash
sudo apt update
sudo apt install python3 python3-pip
```

## Local Setup

To set up and run the documentation locally, follow these steps:

1. **Clone the repository**:

    ```bash
    git clone https://github.com/your-repo-link.git
    cd your-repo-folder
    ```

2. **Create a virtual environment**:

    It's recommended to use a virtual environment to keep dependencies isolated.

    ```bash
    python -m venv venv
    ```

3. **Activate the virtual environment**:

    - On macOS/Linux:
    
      ```bash
      source venv/bin/activate
      ```

    - On Windows:
    
      ```bash
      .\venv\Scripts\activate
      ```

4. **Install dependencies**:

    Install the necessary Python packages listed in `requirements.txt`:

    ```bash
    pip install -r requirements.txt
    ```

5. **Serve the documentation locally**:

    Once the dependencies are installed, you can serve the documentation locally with:

    ```bash
    mkdocs serve
    ```

    The site will be available at `http://127.0.0.1:8000/` by default. MkDocs will automatically rebuild the site as you make changes to the documentation files.

6. **Deactivate the virtual environment** (when done):

    After finishing your work, you can deactivate the virtual environment by running:

    ```bash
    deactivate
    ```

## Building the Documentation

If you want to generate a static site, use the `mkdocs build` command. This will create a `site/` directory with the static files:

```bash
mkdocs build
```
