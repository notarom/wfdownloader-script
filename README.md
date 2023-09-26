# wfdownloader-script

This is a collection of real-world sample WFDownloader scripts in order to show how to program the WFDownloader software. The software supports scripting as a means to enable you support new websites on it. **Note that some of the scripts may already be outdated by the time you view them. It is not a goal to keep the scripts up-to-date.**

To program or write a script in the software read this [introduction tutorial](https://www.wfdownloader.xyz/blog/how-to-program-wfdownloader-app-introduction). Alternatively, you can watch this [video introduction](https://www.youtube.com/watch?v=-i1UNWATLvs).

The sample scripts can be found in this [folder](https://github.com/notarom/wfdownloader-script/tree/main/sample_scripts) and have been used on real websites as you can see from their names. Some are simple and just 2-3 lines of code while others could be 50 or more. It depends on the complexity of the site. In order to try any of the scripts

 1. Open the script for a particular site
 2. Copy the script and paste it into the editor in the software.
 3. Test it against real links of that site to see how it works or modify it to do what you want.

## A few samples
This is an image from the intro tutorial that shows the basic syntax of wfdownloader script.
![A few sample codes](https://www.wfdownloader.xyz/blog_images/sample_codes_annotated.png)

### Site example 1: cyberdrop.me found [here](https://github.com/notarom/wfdownloader-script/blob/main/sample_scripts/cyberdrop.me.txt)

    goto 'a.image' fetch .attribute_href customsubfolder pagetitle;

### Site example 2: imagetwist.com found [here](https://github.com/notarom/wfdownloader-script/blob/main/sample_scripts/imagetwist.com.txt)

    @label[id=2, label="gallery page", urlregex=#/p/#]
    goto '.gallery' fetch a_href indirectly, nextpage location '.paging' followNextPagesOfNextPages {via label 1};
    or
    @label[id=1, label="image page", urlregex=#://[^/]+/(?!p/)\w+#]
    goto 'img.pic' fetch .attribute_src;

### Site example 3: acidimg.cc found [here](https://github.com/notarom/wfdownloader-script/blob/main/sample_scripts/acidimg.cc.txt)

    goto 'img.centred' fetch .attribute_src 
    else goto 'form' submit htmlform {
        goto 'img.centred' fetch .attribute_src
    };

### Site example 4: streamable.com found [here](https://github.com/notarom/wfdownloader-script/blob/main/sample_scripts/streamable.com.txt)

    fetch all video_src;

You can find over a hundred of the above sample scripts [here](https://github.com/notarom/wfdownloader-script/tree/main/sample_scripts).
