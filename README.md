freshSPM: README.md
==========

[SPM](http://www.fil.ion.ucl.ac.uk/spm/) is the original gangster of open source neuroimaging software (freshMRI stands by this claim despite the fact that it effectively depends on MATLAB). [SPM: A history](http://www.ncbi.nlm.nih.gov/pmc/articles/PMC3480642) is the first thing anyone who wants to learn about SPM should read. Although the neurds at freshMRI find much of John Ashburner's work absolutely riveting, [SPM: A history](http://www.ncbi.nlm.nih.gov/pmc/articles/PMC3480642) provides a shockingly down to earth explanation of many aspects of SPM that can be really confusing to new users (and perhaps a powerful antidote for any poor soul who has attempted to imbibe the heady and dangerous brew that is the official SPM manual).

freshSPM is currently a submodule of [freshMRI](http://github.com/wem3/freshMRI), and so rather than serve as a walkthrough for doing an entire analysis, freshSPM, consists primarily of handy tips and MATLAB code for carrying out various tasks that are easily accomplished in SPM. It will focus on the most recent release, [SPM12b](http://www.fil.ion.ucl.ac.uk/spm/software/spm12/), providing as much backward compatibility with SPM8 as possible. None of the freshSPM code is likely to work in older versions (though your old code may work in SPM8/SPM12b).  


SPM is far and away the easiest package to install (assuming you already have MATLAB installed). Unlike most of the other tools on freshMRI, You can probably get away with just downloading through a browser, clicking on the zipped file to extract it, and dragging it to ~/Documents/MATLAB. **This is a bad policy for several reasons** (most of them pertaining to maintaining a solid glowbox policy).  

To set up SPM freshMRI-style:
Make sure MATLAB is installed properly. The default directory lives at ~/Documents/MATLAB, but if you installed FSL, it puts a directory at ~/matlab. This is a huge pain. For now, just leave the directory that FSL installs alone, we'll correct the issue later.  

**Clean up ~/Documents/MATLAB!!!** MATLAB adds this directory to the path by default, and any loose .m files at the top level can be automatically added to the path as well. This can cause huge headaches. ~/Documents/MATLAB is **not** the place to store study specific scripts, in progress code, or really anything but directories of code that you want to add to and remove from the MATLAB path as needed. Seriously. 80% of MATLAB issues can be resolved by fixing the MATLAB path. Leaving cruft in ~/Documents/MATLAB is a great way to break it.  

Go to the [SPM12b download page](http://www.fil.ion.ucl.ac.uk/spm/software/spm12/), fill out the brief form (freshMRI will always wonder if anyone has been reading the 'one-sentence-at-a-time' story that is now approaching novella-like volume), click the link under 'You should download SPM using the following URL' (don't worry about the keyword, you won't need it), and then save spm12b.zip in ~/Documents/MATLAB: ![download_spm12b_as.png](https://github.com/wem3/freshSPM/raw/master/assets/download_spm12b_as.png "save spm12b as such")  

Fire up the Terminal.  

```bash
cd ~/Documents/MATLAB
unzip spm12b.zip
matlab &
```

Set the path in MATLAB. Advanced instructions to follow, here's how to do it through the GUI: ![SetPath_button.png](https://github.com/wem3/freshSPM/raw/master/assets/SetPath_button.png "click Set Path")  


Click 'Add Folder' (**NOT** 'Add with Subfolders' spm does this automatically through its own functions, and it can confuse MATLAB if you choose 'Add with Subfolders') ![add_spm12b_to_path.png](https://github.com/wem3/freshSPM/raw/master/assets/add_spm12b_to_path.png "add spm12b to the path")  

You can save the path with spm12b on it unless you have a reason not to (e.g., you're working in another version of spm, you're working with functions that conflict with spm's, etc.).  

In the MATLAB Command Window:  
```matlab
spm fmri
```

Kaboom!
  