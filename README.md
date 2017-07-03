# android-folder-picker-library

Русский язык по умолчанию.


# Example Uses
- To let users choose folder for saving files
- To let users choose backup folder
- To let users pick files to upload
etc...

# Screenshots

|![Preview](https://github.com/kashifo/android-folder-picker-library/raw/master/screenshots/folderpicker-scr1.png) | ![Preview](https://github.com/kashifo/android-folder-picker-library/raw/master/screenshots/folderpicker-scr2.png) | ![Preview](https://github.com/kashifo/android-folder-picker-library/raw/master/screenshots/folderpicker-scr3.png) |
|:-------------------:|:------------------------:|:-----------------:|
| Выбор папки | Создание папки | Выбор файла |


# Подключение

```
//Add it in your root build.gradle at the end of repositories:
allprojects {
		repositories {
			...
			maven { url 'https://jitpack.io' }
		}
	}
```


```
dependencies {
	        compile 'com.github.Svoka:android-folder-picker-library:-SNAPSHOT'
	}
```
  
# Использование

**To pick folder**

Just start FolderPicker activity from your app
```java
        Intent intent = new Intent(this, FolderPicker.class);
        startActivityForResult(intent, FOLDERPICKER_CODE);        
```

If the user selects folder/file, the name of folder/file will be returned to you on onActivityResult method with the variable name 'data'.

```java
        
        protected void onActivityResult(int requestCode, int resultCode, Intent intent) {
          if (requestCode == FOLDERPICKER_CODE && resultCode == Activity.RESULT_OK) {

              String folderLocation = intent.getExtras().getString("data");
              Log.i( "folderLocation", folderLocation );
            
          }
        }
        
 ```

**Options**

Customization options can be passed as extras to FolderPicker activity.

 ```java
 
        //To show a custom title
        intent.putExtra("title", "Select file to upload");
        
        //To begin from a selected folder instead of sd card's root folder. Example : Pictures directory
        intent.putExtra("location", Environment.getExternalStoragePublicDirectory(Environment.DIRECTORY_PICTURES).getAbsolutePath());
        
        //To pick files
        intent.putExtra("pickFiles", true);
        
  ```
  

## License

    Copyright 2017 Kashif Anwaar.

    Licensed under the Apache License, Version 2.0 (the "License");
    you may not use this file except in compliance with the License.
    You may obtain a copy of the License at

       http://www.apache.org/licenses/LICENSE-2.0

    Unless required by applicable law or agreed to in writing, software
    distributed under the License is distributed on an "AS IS" BASIS,
    WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
    See the License for the specific language governing permissions and
    limitations under the License.

