Hi 👋, I'm Sohel Banadar
Full-Stack AI Engineer | IoT | Open Source Contributor

Code is just the medium. I'm here to build things that push the world a little further ahead.


👨‍💻 ABOUT ME
Hey, I'm Sohel — an engineer passionate about building tools that simplify complex workflows. I work at the intersection of AI, LLMs, and backend infrastructure.

🚀 Currently building DefBot, an AI Text Humanizer, and scaling AI-driven web apps.

🧠 Obsessed with turning ideas into products and understanding systems from first principles.

🛠️ Experienced in building GPU-accelerated infrastructure simulators and VC Outreach CRMs.

💻 TECH STACK
Languages


Frameworks & Libraries


Cloud, Databases & AI


📊 GITHUB STATS



### Step 3: How to add the 3D Contribution Graph (Like in the first image)
The first image features a cool 3D block graph. This requires setting up a GitHub Action because it has to automatically regenerate the image every day. Here is how to do it once you save your `README.md`:

1. In your new `sohel305` repository, click on the **Actions** tab.
2. Click **New workflow** -> **set up a workflow yourself**.
3. Name the file `build.yml` and paste the following code:
```yaml
name: GitHub-Profile-3D-Contrib

on:
  schedule: # 03:00 JST == 18:00 UTC
    - cron: "0 18 * * *"
  workflow_dispatch:

jobs:
  build:
    runs-on: ubuntu-latest
    name: generate-github-profile-3d-contrib
    steps:
      - uses: actions/checkout@v3
      - uses: yoshi389111/github-profile-3d-contrib@0.7.1
        env:
          GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
          USERNAME: ${{ github.repository_owner }}
      - name: Commit & Push
        run: |
          git config user.name github-actions
          git config user.email github-actions@github.com
          git add -A .
          git commit -m "generated"
          git push
Commit this file. Go back to the Actions tab, click on the workflow you just made on the left, and click Run workflow.

Once it finishes running, it will generate a folder of images. You can then add this line to your README.md to display the green 3D graph:
`

`
