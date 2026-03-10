# Easy Access

For general ease of use for this repo when it comes to things like committing changes or accessing this repo, these scripts were created. These are simple scripts that you can implement into the repo and make the overall experience easier to work with.

This helped the problem of continuously doing the same lines of text for repeating tasks like committing changes or opening my IDE. 

## Committing

    commit.sh

The following script exists to make committing more efficient. The previous set of code to achieve the same results were (in git bash):

    git add .
    git commit -m "message"
    git push origin main

To use commit.sh, simply do (in your terminal, git bash):

    chmod +x commit.sh

Now you can do:

    ./commit.sh "Your message"

If you would like to make this an easy alias that you can use in any subfolder (and any repo as a whole!) you would:

    echo "alias commit='yourrepodirectory'" >> ~/.bashrc
    source ~/.bashrc

Now, from anywhere, you can go:

    commit "your message here" DEEZ NUTS