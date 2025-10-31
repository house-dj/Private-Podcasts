## **Private Podcast Publisher Setup**

This guide explains how to use the podcast\_publisher.py script to automate the publishing of new audio files to your private podcast feed on GitHub Pages.

### **Prerequisites**

1. **Python 3:** Ensure you have Python installed on your PC.  
2. **Git:** Ensure you have the Git command-line tool installed and configured on your PC.  
3. **Local Repository:** You must have a local clone of your repository (Private-Podcasts) where you will run this script.  
4. **Initial feed.xml:** You must have an initial feed.xml file in the root of your repository, even if it's just the channel header (see the script comments for the required structure).

### **Step 1: Install Required Library**

The script uses the mutagen library to accurately read the duration of the MP3 files.

Open your terminal or command prompt in the root of your Private-Podcasts directory and run:

pip install mutagen

### **Step 2: Create the Audio Directory**

Create a new directory named \_new\_uploads (or whatever you configure NEW\_AUDIO\_DIR to be) in the root of your local repository.

* This is where you will place all the new MP3 files you want to upload.

### **Step 3: Run the Script**

1. Place your new MP3 files inside the \_new\_uploads directory.  
2. Run the script from the root of your repository:

python podcast\_publisher.py

The script will:

1. Read metadata from all files in \_new\_uploads.  
2. Update the feed.xml file with new \<item\> entries.  
3. Move the processed MP3 files to the repository root.  
4. Run git add ., git commit, and git push to upload everything to GitHub.