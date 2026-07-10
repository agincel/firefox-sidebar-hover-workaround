# Firefox Vertical Tab Sidebar Expand-on-Hover Workaround
This tweak fixes [an issue impacting Linux users of Firefox](https://bugzilla.mozilla.org/show_bug.cgi?id=1985692), where the Sidebar expands as the cursor leaves the window (such as when using multiple monitors), and does not retract until the cursor returns.

<img src="/media/issue.gif" alt="The issue" width="450" />

It accomplishes this by disabling the broken built-in behavior, and applying CSS to approximate the same behavior. Which is probably not ideal, but it beats losing 10% of the screen every time your cursor leaves off the left side.
Feel free to PR with any further tweaks if this helps you.

<img src="/media/workaround.gif" alt="The solution" width="450" />

>*The below elements of this README.md were largely taken from [ENDE25](https://github.com/ENDE25/FIREFOX-tabs-hover-expand). 😃*

---

>*To make this modification work, a small configuration in the browser is required, as described below:*

## Always Expand Sidebar
This fix conflicts with the built-in sidebar expansion behavior. Open up `about:config` and set:
`sidebar.visibility: always-show`


## Enable Legacy Toolkit and Set Up the `chrome` Folder  

To apply this style in Firefox, follow these steps:  

### 1. Enable `userChrome.css` Support  
1. Open Firefox and type in the address bar:  
`about:config`
2. Accept the warning message if it appears.  
3. Search for the preference:  
`toolkit.legacyUserProfileCustomizations.stylesheets`
4. Double-click it to set its value to `true`.  

### 2. Find the User Profile Folder  
1. Type in the address bar:  
`about:support`
2. Look for the **"Profile Folder"** section and click **"Open Folder"**.  
3. Inside the profile folder, locate (or create if it doesn't exist) a folder named `chrome`.  

### 3. Apply the Style  
1. Copy the `userChrome.css` file into the `chrome` folder.  
2. Restart Firefox for the changes to take effect.  

That's it! Now your vertical tabs should now behave closer to expected, if this issue was impacting you.

---