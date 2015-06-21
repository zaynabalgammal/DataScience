{\rtf1\ansi\ansicpg1252\cocoartf1345\cocoasubrtf380
{\fonttbl\f0\fnil\fcharset0 HelveticaNeue;}
{\colortbl;\red255\green255\blue255;\red38\green38\blue38;\red50\green98\blue178;}
{\*\listtable{\list\listtemplateid1\listhybrid{\listlevel\levelnfc23\levelnfcn23\leveljc0\leveljcn0\levelfollow0\levelstartat1\levelspace360\levelindent0{\*\levelmarker \{disc\}}{\leveltext\leveltemplateid1\'01\uc0\u8226 ;}{\levelnumbers;}\fi-360\li720\lin720 }{\listname ;}\listid1}
{\list\listtemplateid2\listhybrid{\listlevel\levelnfc23\levelnfcn23\leveljc0\leveljcn0\levelfollow0\levelstartat1\levelspace360\levelindent0{\*\levelmarker \{disc\}}{\leveltext\leveltemplateid101\'01\uc0\u8226 ;}{\levelnumbers;}\fi-360\li720\lin720 }{\listname ;}\listid2}}
{\*\listoverridetable{\listoverride\listid1\listoverridecount0\ls1}{\listoverride\listid2\listoverridecount0\ls2}}
\paperw11900\paperh16840\margl1440\margr1440\vieww10800\viewh8400\viewkind0
\deftab720
\pard\pardeftab720

\f0\fs32 \cf2 \expnd0\expndtw0\kerning0
Run_Analysis.R R-script on Human Activity Recognition Using Smartphones Dataset\
\pard\pardeftab720

\b\fs72 \cf3 \expnd0\expndtw0\kerning0
\
\pard\pardeftab720
\cf2 \expnd0\expndtw0\kerning0
Version 1.0\
\pard\pardeftab720
\cf3 \expnd0\expndtw0\kerning0
\
\pard\pardeftab720
\cf2 \expnd0\expndtw0\kerning0
by Themos Patrikios\
\pard\pardeftab720

\b0\fs32 \cf2 \expnd0\expndtw0\kerning0
The run_analysis.R script reads data from the "Human Activity Recognition Using Smartphones Dataset Version 1.0" and produces a new - tidy - dataset which may be used for further analysis.\
The data in the "Human Activity Recognition Using Smartphones Dataset Version 1.0" have been taken from experiments carried out with a group of 30 volunteers within an age bracket of 19-48 years. Each person performed six activities (WALKING, WALKING_UPSTAIRS, WALKING_DOWNSTAIRS, SITTING, STANDING, LAYING) wearing a smartphone (Samsung Galaxy S II) on the waist. Using its embedded accelerometer and gyroscope, 3-axial linear acceleration and 3-axial angular velocity at a constant rate of 50Hz data were captured. The experiments were video-recorded to label the data manually. The obtained dataset was randomly partitioned into two sets, where 70% of the volunteers was selected for generating the training data and 30% the test data.\
\pard\pardeftab720

\b\fs72 \cf3 \expnd0\expndtw0\kerning0
\
\pard\pardeftab720
\cf2 \expnd0\expndtw0\kerning0
The original dataset included the following data files:\
\pard\tx220\tx720\pardeftab720\li720\fi-720
\ls1\ilvl0
\b0\fs32 \cf2 \kerning1\expnd0\expndtw0 {\listtext	\'95	}\expnd0\expndtw0\kerning0
'features.txt': List of all features.\
\ls1\ilvl0\kerning1\expnd0\expndtw0 {\listtext	\'95	}\expnd0\expndtw0\kerning0
'activity_labels.txt': List of class labels and their activity name.\
\ls1\ilvl0\kerning1\expnd0\expndtw0 {\listtext	\'95	}\expnd0\expndtw0\kerning0
'train/X_train.txt': Training set.\
\ls1\ilvl0\kerning1\expnd0\expndtw0 {\listtext	\'95	}\expnd0\expndtw0\kerning0
'train/y_train.txt': Training labels.\
\ls1\ilvl0\kerning1\expnd0\expndtw0 {\listtext	\'95	}\expnd0\expndtw0\kerning0
'train/subject_train.txt': ID's of subjects in the training data\
\ls1\ilvl0\kerning1\expnd0\expndtw0 {\listtext	\'95	}\expnd0\expndtw0\kerning0
'test/X_test.txt': Test set.\
\ls1\ilvl0\kerning1\expnd0\expndtw0 {\listtext	\'95	}\expnd0\expndtw0\kerning0
'test/y_test.txt': Test labels.\
\ls1\ilvl0\kerning1\expnd0\expndtw0 {\listtext	\'95	}\expnd0\expndtw0\kerning0
'test/subject_test.txt': ID's of subjects in the training data\
\pard\pardeftab720
\cf2 \expnd0\expndtw0\kerning0
For more information about the "Human Activity Recognition Using Smartphones Dataset Version 1.0" contact: {\field{\*\fldinst{HYPERLINK "mailto:activityrecognition@smartlab.ws"}}{\fldrslt \cf3 \expnd0\expndtw0\kerning0
activityrecognition@smartlab.ws}}\
\pard\pardeftab720

\b\fs72 \cf3 \expnd0\expndtw0\kerning0
\
\pard\pardeftab720
\cf2 \expnd0\expndtw0\kerning0
A brief description of the script:\
\pard\pardeftab720

\b0\fs32 \cf2 \expnd0\expndtw0\kerning0
The run_analysis.R script merges data from a number of .txt files and produces a tidy data set which may be used for further analysis.\
\pard\tx220\tx720\pardeftab720\li720\fi-720
\ls2\ilvl0\cf2 \kerning1\expnd0\expndtw0 {\listtext	\'95	}\expnd0\expndtw0\kerning0
First it checks to see if the required "reshape2" has been installed and then loads the "reshape2" package.\
\ls2\ilvl0\kerning1\expnd0\expndtw0 {\listtext	\'95	}\expnd0\expndtw0\kerning0
It then reads all required .txt files and labels the datasets\
\ls2\ilvl0\kerning1\expnd0\expndtw0 {\listtext	\'95	}\expnd0\expndtw0\kerning0
Consquently the appropriate "activity_id"'s and "subject_id"'s are appended to the "test" and the "training" data, which are then combined into one single data frame\
\ls2\ilvl0\kerning1\expnd0\expndtw0 {\listtext	\'95	}\expnd0\expndtw0\kerning0
Using the "grep" function, all the columns with mean() and std() values are extracted and then a new data frame, including only the "activity_id", the "subject_id" and the mean() and std() columns, is created \
\ls2\ilvl0\kerning1\expnd0\expndtw0 {\listtext	\'95	}\expnd0\expndtw0\kerning0
Using the "merge" function, descriptive activity names are merged with the mean/std values dataset, to get one dataset with descriptive activity names\
\ls2\ilvl0\kerning1\expnd0\expndtw0 {\listtext	\'95	}\expnd0\expndtw0\kerning0
Lastly, with the help of the "melt" and "dcast" functions of the "reshape2" package, the data is converted into a table containing mean values of all the included features, ordered by the activity name and the subject id, and the data is written to the "tidy_movement_data.txt" file.\
\pard\pardeftab720
\cf2 \expnd0\expndtw0\kerning0
A description of the "tidy_movement_data.txt" file may be found in the "CodeBook.md" file.\
\pard\pardeftab720

\b\fs72 \cf3 \expnd0\expndtw0\kerning0
\
\pard\pardeftab720
\cf2 \expnd0\expndtw0\kerning0
Acknowledgements:\
\pard\pardeftab720

\b0\fs32 \cf2 \expnd0\expndtw0\kerning0
Davide Anguita, Alessandro Ghio, Luca Oneto, Xavier Parra and Jorge L. Reyes-Ortiz. Human Activity Recognition on Smartphones using a Multiclass Hardware-Friendly Support Vector Machine. International Workshop of Ambient Assisted Living (IWAAL 2012). Vitoria-Gasteiz, Spain. Dec 2012\
\pard\pardeftab720

\b\fs72 \cf3 \expnd0\expndtw0\kerning0
\
\pard\pardeftab720
\cf2 \expnd0\expndtw0\kerning0
License:\
\pard\pardeftab720

\b0\fs32 \cf2 \expnd0\expndtw0\kerning0
Use of the Run_Analysis.R script is free for all users.\
Use of the resulting dataset "tidy_movement_data.txt" in publications must be acknowledged by referencing the following publication [1]\
[1] Davide Anguita, Alessandro Ghio, Luca Oneto, Xavier Parra and Jorge L. Reyes-Ortiz. Human Activity Recognition on Smartphones using a Multiclass Hardware-Friendly Support Vector Machine. International Workshop of Ambient Assisted Living (IWAAL 2012). Vitoria-Gasteiz, Spain. Dec 2012\
This dataset is distributed AS-IS and no responsibility implied or explicit can be addressed to the author for its use or misuse. Any commercial use is prohibited.\
\pard\pardeftab720

\b\fs72 \cf2 \expnd0\expndtw0\kerning0
\
\pard\pardeftab720

\b0\fs32 \cf2 \expnd0\expndtw0\kerning0
Themos Patrikios, April 2014}