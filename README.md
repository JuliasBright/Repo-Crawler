Here's a basic `README.md` file for your crawler.

---
# GitHub Pull Request Crawler

This crawler fetches information about pull requests initiated, reviewed, or approved by a specific user across all repositories in a given GitHub organization.

## Prerequisites

To run this crawler, you'll need:

1. Python 3.6 or higher
2. Required Python libraries: `requests`, `json`, and `csv`. You can install these using pip:
    ```bash
    pip install requests json csv
    ```

3. A GitHub account and a [Personal Access Token](https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/creating-a-personal-access-token) (PAT) for that account. The PAT is used for authenticating with the GitHub API.

4. Jupyter notebook. If you don't have it installed, you can install it using pip:
    ```bash
    pip install jupyter
    ```

## How to Run

1. Open the `github_crawler.ipynb` file in Jupyter notebook. You can do this by navigating to the directory containing the file and typing `jupyter notebook` in your terminal, then selecting the `github_crawler.ipynb` file in the Jupyter notebook interface in your browser.

2. Replace the placeholders in the script with your actual values:

    ```python
    headers = {
        'Authorization': 'token YOUR_GITHUB_TOKEN',
        'Accept': 'application/vnd.github.v3+json',
    }
    ```

    Replace `YOUR_GITHUB_TOKEN` with your actual GitHub Personal Access Token.

    ```python
    target_user = "TARGET_USERNAME"
    org_name = "ORGANIZATION_NAME"
    ```

    Replace `TARGET_USERNAME` with the username of the person whose activity you want to track, and `ORGANIZATION_NAME` with the name of the organization you want to crawl.

3. Run all cells in the Jupyter notebook. The result will be saved in a CSV file named `github_data.csv` in the same directory.

## Output

The script saves the crawled data into a CSV file named `github_data.csv`. Each row in the CSV file corresponds to a single pull request that was either initiated, reviewed, or approved by the target user. The columns in the CSV file are as follows:

1. `PR_number`: The number of the pull request.
2. `Initiator`: The username of the person who initiated the pull request.
3. `Approver`: The username of the person who approved the pull request. If the pull request has not been approved, this field is `None`.
4. `Reviewers`: The usernames of the people who reviewed the pull request, separated by commas.
