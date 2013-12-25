# iCodeSnippets

Easy to do trivial things.


## How to install?
Xcode provides an area to save snippet code for later using. Press ```Control + Option + Command + 2``` to show
Code Snippet Library (right-lower corner).

Xcode saves its snippets code at location:

```bash
~/Library/Developer/Xcode/UserData/CodeSnippets/
```
or
```bash
/Users/username/Library/Developer/Xcode/UserData/CodeSnippets
```

Therefore, we will make a git repo which also locate at that location. Do that, we can make snippets to be updated just by pulling/pushing git repo.

So, there are two ways to make your snippet go visible on git repository.

##### Method 1
```
cd ~/Library/Developer/Xcode/UserData/CodeSnippets/
git init
git remote set-url origin https://username@github.com/username/iCodeSnippets.git

// Next, pull or push, it is up to you. Recommend that PULL first if your repo is not up-to-date.
```

##### Method 2
``` 
cd ~/Library/Developer/Xcode/UserData/
cp CodeSnippets CodeSnippetsBackup				// Backup CodeSnippets folder if it is existing
rm -r CodeSnippets 								// Remove CodeSnippets folder
git clone https://username@github.com/username/iCodeSnippets.git CodeSnippets
cp CodeSnippetsBackup/* CodeSnippets/ 			// Optional, if you want to merge the exisiting snippets and snippets from repo

// Next, PUSH or PULL, it is up to you. Recommend that PUSH first if your repo is merged!
```

## TroubleShooting

Error: 
```bash
error: The requested URL returned error: 403 while accessing https://github.com/hugo53/iCodeSnippets.git/info/refs?service=git-receive-pack
fatal: HTTP request failed
```

Fix:
```
git remote set-url origin https://username@github.com/username/iCodeSnippets.git
```

May need to change ownership of the Snippets folder and its subfolders

```
chmod -R 777
```


> Warning: Besure that your code is WILLING to go PUBLIC if you use public git repository!!!


> Next task: Synchronize Bookmark Documentation.
> Bookmark is saved in ```~/Library/Preferences/com.apple.dt.Xcode.plist``` with key ```Xcode.Organizer.Documentation.Bookmarks```. Just parse this key and get all items. 
