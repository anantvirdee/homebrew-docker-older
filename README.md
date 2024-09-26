# Anantvirdee Docker-older

## How do I install Docker Desktop v4.22.0?

### Why do you need v4.22.0?

Docker Desktop v4.22.0 is the latest compatible version with mac OS Big Sur. It is not available for download though on the official docker desktop site as it is an older/unsupported version.

### Solution

#### Create a custom cask and tap to download v4.22.0. Detailed steps:
1. Set up a GitHub Repository for the Tap:
     Create a new GitHub repository for your Homebrew tap, like homebrew-docker-older.
      The convention for naming a Homebrew tap is `homebrew-<name>`.

2. Set up Homebrew Tap in Local Machine
    In your terminal, run the following commands: `brew tap-new <your-github-username>/docker-older`

3. Copy the Old Docker Cask:

You'll now need to find the old version of the Docker Desktop cask(Casks/docker.rb) and copy it into your new tap. Here’s how:

    Go to the official Docker cask history on GitHub: Docker Desktop Cask History
    Find the version you want (e.g., 4.22.0) in the commit history.
    Click on the commit for that version, and you’ll see the exact contents(raw) of the docker.rb file at that point in time.

3. Create the Cask in Your Tap:
    On your local machine, navigate to your Homebrew tap directory:
      `cd $(brew --repository)/Library/Taps/<your-github-username>/homebrew-docker-older`
   
    Inside this directory, create a Casks folder if it doesn’t already exist:
      `mkdir -p Casks`

   In the Casks folder, create a file called docker.rb:
      `touch Casks/docker.rb`

   Open the docker.rb file in a text editor and paste the content from the version of Docker Desktop that you want (which you found in step 3).

5. Push the Changes to GitHub:

    Now, push your local changes to your GitHub repository. Run the following commands in your terminal:

    `git add Casks/docker.rb`
    `git commit -m "Add Docker Desktop 4.22.0 cask"`
    `git push origin main`

6. Install the Old Version:

Now that you have the old version in your tap, you can install it using Homebrew:

  `brew install --cask <your-github-username>/docker-older/docker`

This will install the older version of Docker Desktop that you manually added to your Homebrew tap.
