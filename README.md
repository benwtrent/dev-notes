# dev-notes
collection of my daily notes, TILs, dev activities

I use the following function in my `.bash_profile` to make this more seamless

```
export DEV_NOTES_PATH=/path/to/my/repo/
notes() {
      local fpath=${DEV_NOTES_PATH}notes/`date +"%Y-%m-%d"`.md
      elif [ "$1" == "vim" ]; then
          vim + $fpath
      elif [ "$1" == "time" ]; then
          echo '' >> $fpath
          echo '# '`date +"%T"` >> $fpath
          echo '---------------------' >> $fpath
      elif [ "$1" == "" ]; then
          less +G $fpath
      elif [ "$1" == "publish" ]; then
        git --git-dir ${DEV_NOTES_PATH}.git --work-tree ${DEV_NOTES_PATH} pull
        git --git-dir ${DEV_NOTES_PATH}.git --work-tree ${DEV_NOTES_PATH} commit -am 'adding notes for `date +"%Y-%m-%d"`'
        git --git-dir ${DEV_NOTES_PATH}.git --work-tree ${DEV_NOTES_PATH} push
      else
          echo '' >> $fpath
          echo $@ >> $fpath
      fi
}
```
