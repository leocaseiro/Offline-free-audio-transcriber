# Audio Transcribe offilne with Sphinx

* [CMU Sphinx](http://cmusphinx.sourceforge.net/wiki/) (works offline)
* [MacOS pocketsphinx-python](https://github.com/bambocher/pocketsphinx-python)


## You should have git, python3 and swig

```
brew install swig
```

## Install pocketshinx and SpeechRecognition via pip

```
pip3 install pocketsphinx
pip3 install SpeechRecognition
```


### Throubleshooting

> Using legacy 'setup.py install' for pocketsphinx, since package 'wheel' is not installed.

*Make sure we have up-to-date versions of pip, setuptools and wheel*

```
python -m pip install --upgrade pip setuptools wheel
pip install --upgrade pocketsphinx
```


> clang -Wno-unused-result -Wsign-compare -Wunreachable-code -DNDEBUG -g -fwrapv -O3 -Wall -I/Applications/Xcode.app/Contents/Developer/Platforms/MacOSX.platform/Developer/SDKs/MacOSX.sdk/usr/include -I/Applications/Xcode.app/Contents/Developer/Platforms/MacOSX.platform/Developer/SDKs/MacOSX.sdk/usr/include -DSPHINXBASE_EXPORTS -DPOCKETSPHINX_EXPORTS -DSPHINX_DLL -DHAVE_CONFIG_H -Ideps/sphinxbase/include -Ideps/sphinxbase/include/sphinxbase -Ideps/sphinxbase/include/android -I/System/Library/Frameworks/OpenAL.framework/Versions/A/Headers -I/Users/leocaseiro/.pyenv/versions/3.7.5/include/python3.7m -c deps/sphinxbase/src/libsphinxad/ad_openal.c -o build/temp.macosx-10.15-x86_64-3.7/deps/sphinxbase/src/libsphinxad/ad_openal.o -Wno-macro-redefined -Wno-sign-compare -Wno-logical-op-parentheses
>  deps/sphinxbase/src/libsphinxad/ad_openal.c:43:10: fatal error: 'al.h' file not found
>  #include <al.h>
>           ^~~~~~
>  1 error generated.
>  error: command 'clang' failed with exit status 1
>  ----------------------------------------
>  ERROR: Failed building wheel for pocketsphinx

https://github.com/bambocher/pocketsphinx-python/issues/28#issuecomment-597794252
```
brew install openal-soft
cd /usr/local/include
ln -s /usr/local/Cellar/openal-soft/1.20.1/include/AL/* .
pip3 install pocketsphinx
```
