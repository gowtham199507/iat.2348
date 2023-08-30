# iat.2348
<usermanual>
___________________________________________________________________________________________________________________	

									Age Implicit Association Test (IAT) - with pictures
___________________________________________________________________________________________________________________

Main Inquisit programming: Sean Draine (seandr@millisecond.com)
last updated:  02-23-2022 by K. Borchert (katjab@millisecond.com) for Millisecond Software, LLC

Script Copyright © 02-23-2022 Millisecond Software

___________________________________________________________________________________________________________________
BACKGROUND INFO 	
___________________________________________________________________________________________________________________

The Implicit Association Task (Greenwald, McGhee, & Schwartz, 1998) is a widely-used cognitive-behavioral paradigm
that measures the strength of automatic (implicit) associations between concepts in people’s minds relying 
on latency measures in a simple sorting task.
 
The strength of an association between concepts is measured by the standardized mean difference score of 
the 'hypothesis-inconsistent' pairings and 'hypothesis-consistent' pairings (d-score) (Greenwald, Nosek, & Banaji, 2003). 
In general, the higher the d-score the stronger is the association between the 'hypothesis-consistent' pairings 
(decided by researchers). Negative d-scores suggest a stronger association between the 'hypothesis-inconsistent' pairings.

Inquisit calculates d-scores using the improved scoring algorithm as described in Greenwald et al (2003). 
Error trials are handled by requiring respondents to correct their responses according to recommendation (p.214).

D-scores obtained with this script:
Positive d-scores: support a stronger association between 'Young-Good' and 'Old-Bad' than for the opposite pairings
Negative d-scores: support a stronger association between 'Old-Good' and 'Young-Bad' than for the opposite pairings

References:

general IAT:
Greenwald, A. G., McGhee, D. E., & Schwartz, J. K. L. (1998). Measuring individual differences in implicit cognition: 
The Implicit Association Test. Journal of Personality and Social Psychology, 74, 1464-1480.

Greenwald, A. G., Nosek, B. A., & Banaji, M. R. (2003). Understanding and Using the Implicit Association Test: 
I. An Improved Scoring Algorithm. Journal of Personality and Social Psychology, 85, 197-216.

Stimuli: This IAT is based on the generic Inquisit IAT template and uses the stimuli fromm the age IAT
from Project Implicit (Retrieved from osf.io/y9hiq)

___________________________________________________________________________________________________________________
TASK DESCRIPTION	
___________________________________________________________________________________________________________________

Participants are asked to categorize attributes (e.g. "joyful"; "tragic") and target items (e.g pictures of young and old faces) 
into predetermined categories via keystroke presses. The basic task is to press a left key (E) if an item (e.g. "joyful")
belongs to the category presented on the left (e.g. "Good") and to press the right key (I) if the word (e.g. "tragic") 
belongs to the category ("Bad") presented on the right.
For practice, participants sort items into the target categories "Youngs vs. Olds" and the attribute categories "Good vs. Bad".
For the test, participants are asked to sort categories into the paired/combined categories (e.g. 
"Young OR Good" on the left vs. "Old OR Bad" on the right). Pairings are reversed for a second test (e.g. "Old OR Good" on the left
vs. "Young OR Bad" on the right). Order is counterbalanced by groupnumber.							  

___________________________________________________________________________________________________________________	
DURATION 
___________________________________________________________________________________________________________________	
the default set-up of the script takes appr. 5.5 minutes to complete

__________________________________________________________________________________________________________________	
DATA FILE INFORMATION 
___________________________________________________________________________________________________________________	
The default data stored in the data files are:

(1) Raw data file: 'ageiat_raw*.iqdat' (a separate file for each participant)

build:							The specific Inquisit version used (the 'build') that was run
computer.platform:				the platform the script was run on (win/mac/ios/android)
date, time: 					date and time script was run 

subject, group, 				with the current subject/groupnumber
										Note: odd/even groupnumbers balance the order in which 
										hypothesis-compatible/incompatible blocks are run
										odd = compatible - incompatible
										even = incompatible - compatible
										
session:						with the current session id

blockcode, blocknum:			the name and number of the current block (built-in Inquisit variable)
trialcode, trialnum: 			the name and number of the currently recorded trial (built-in Inquisit variable)
									Note: trialnum is a built-in Inquisit variable; it counts all trials run; 
									even those that do not store data to the data file such as feedback trials
									
conditionOrder:					c-ic: consistent -> inconsistent
								ic-c: inconsistent -> consistent									
									
response:						the response key pressed (e.g. 18=E or 23=I)										
								Note: script saves the final and -by design- correct response for each trial
										
correct:						the accuracy of the initial response
										0 = initial response was incorrect and needed to be corrected
										1 = initial response is correct
										
latency:						the latency of the final (correct) response in ms; measured from onset of stim
stimulusnumber:					the number of the current stimulus
stimulusitem:					the currently presented item


Only meaningful for the last row of data in the raw data file (upon completion of IAT):

da:								d-score of the first short blocks
db:								d-score of the second long blocks

d:								overall d-score (non-weighted mean of the 2 d-scores); main DV

								Suggested Interpretation:

											D-score <= -0.65 => "a strong" preference for hypothesis-NONconforming pairings
											D-score < -0.35 => "a moderate" preference for hypothesis-NONconforming pairings
											D-score < -0.15 => "a slight" preference for hypothesis-NONforming pairings																						
											-0.15 <= D-score <= 0.15 "little to no" preference
											D-score > 0.15 => "a slight" preference for hypothesis-conforming pairings
											D-score > 0.35 => "a moderate" preference for hypothesis-conforming pairings
											D-score >= 0.65 => "a strong" preference for hypothesis-conforming pairings

percentcorrect:      			the overall percent correct score of initial responses in test trials of D-score qualifying latencies

propRT300:						the proportion of response latencies < 300ms

excludeCriteriaMet:				1 = yes, exclusion supported per Greenwald et al (2003, p.214, Table 4):
								More than 10% of all response latencies are faster than 300ms
								0 = otherwise
									

(2) Summary data file: 'ageiat_summary*.iqdat' (a separate file for each participant)

inquisit.version: 			 	Inquisit version run
computer.platform:				the platform the script was run on (win/mac/ios/android)
startdate:						date script was run
starttime:						time script was started
subjectid:						assigned subject id number
groupid:						assigned group id number
sessionid:						assigned session id number
elapsedtime:					time it took to run script (in ms); measured from onset to offset of script
completed:						0 = script was not completed (prematurely aborted); 
								1 = script was completed (all conditions run)
								
conditionOrder:					c-ic: consistent -> inconsistent
								ic-c: inconsistent -> consistent								

da:								d-score of the first short blocks
db:								d-score of the second long blocks

d:								overall d-score (non-weighted mean of the 2 d-scores); main DV

								Suggested Interpretation:

											D-score <= -0.65 => "a strong" preference for hypothesis-NONconforming pairings
											D-score < -0.35 => "a moderate" preference for hypothesis-NONconforming pairings
											D-score < -0.15 => "a slight" preference for hypothesis-NONforming pairings																						
											-0.15 <= D-score <= 0.15 "little to no" preference
											D-score > 0.15 => "a slight" preference for hypothesis-conforming pairings
											D-score > 0.35 => "a moderate" preference for hypothesis-conforming pairings
											D-score >= 0.65 => "a strong" preference for hypothesis-conforming pairings

percentcorrect:    				the overall percent correct score of initial responses in test trials of D-score qualifying latencies

propRT300:						the proportion of response latencies < 300ms

excludeCriteriaMet:				1 = yes, exclusion supported per Greenwald et al (2003, p.214, Table 4):
								More than 10% of all response latencies are faster than 300ms
								0 = otherwise
									
___________________________________________________________________________________________________________________	
EXPERIMENTAL SET-UP 
___________________________________________________________________________________________________________________	

Hypothesis-consistent pairings vs. hypothesis-inconsistent pairings; tested within-subjects in a blocked format
=> order is counterbalanced by groupnumber assignment
odd groupnumbers run: consistent - inconconsistent pairings
even groupnumbers run: inconsistent - consistent pairings

Block Sequence:
1. Target Category sorting training
2. Attribute sorting training
3. 1. Test Block of hypothesis-consistent* pairings with 20 trials (half the participant start with inconsistent pairings)
4. 2. Test Block of hypothesis-consistent pairings with 40 trials
5. Target Category sorting training with targets switching sides
6. 1. Test Block of hypothesis-inconsistent pairings with 20 trials
7. 2. Test Block of hypothesis-inconsistent pairings with 40 trials

In all Test Blocks:
* attributes and targets alternate
* attributes as well as targets are randomly selected without replacement

Trial Sequence:
Target -> until correct response -> ISI: 250ms (default)-> Target....

___________________________________________________________________________________________________________________	
STIMULI
___________________________________________________________________________________________________________________
Stimuli can be edited under section Editable Stimuli

___________________________________________________________________________________________________________________	
INSTRUCTIONS 
___________________________________________________________________________________________________________________
* start instruction page is provided as an html page. It automatically adapts to different images and category labels UNLESS
the number of attributes and/or targets have been changed. In this case, changes have to be 
made to file "intro_iat.htm", so that the correct number of items are presented in the overview table.

Example: instead of 8 words for target A, only 5 should be presented:

in file "intro_iat.htm":
change:
			<td><%item.targetA.item(1)%>, <%item.targetA.item(2)%>, <%item.targetA.item(3)%>, <%item.targetA.item(4)%>, 
				<%item.targetA.item(5)%>, <%item.targetA.item(6)%>, <%item.targetA.item(7)%>, <%item.targetA.item(8)%>
			</td>

To:
			<td><%item.targetA.item(1)%>, <%item.targetA.item(2)%>, <%item.targetA.item(3)%>, <%item.targetA.item(4)%>, 
				<%item.targetA.item(5)%>
			</td>

* item.instructions under section 'Editable Instructions' contains the the trial instructions
The instructions adapt automatically if different attributes and targets are used.

___________________________________________________________________________________________________________________	
EDITABLE CODE 
___________________________________________________________________________________________________________________	
check below for (relatively) easily editable parameters, stimuli, instructions etc. 
Keep in mind that you can use this script as a template and therefore always "mess" with the entire code 
to further customize your experiment.

The parameters you can change are:

/showsummaryfeedback:		set parameter showsummaryfeedback = true to display summary feedback to participants at the end (default)
							set parameter showsummaryfeedback = false if no summary feedback should be presented to participants
							
/ISI:						interstimulus interval (in ms) (default: 250ms)

</usermanual>

**************************************************************************************************************
**************************************************************************************************************
	EDITABLE PARAMETERS: change editable parameters here
**************************************************************************************************************
**************************************************************************************************************

<parameters>
/showsummaryfeedback = true
/ISI = 250
</parameters>

**************************************************************************************************************
**************************************************************************************************************
	EDITABLE STIMULI: change editable stimuli here
**************************************************************************************************************
**************************************************************************************************************
This sample IAT can be easily adapted to different target categories 
and attributes. To change the categories, you need only change the 
stimulus items and labels immediately below this line.

***********************************************************************
<item attributeAlabel>
/1 = "Good"
</item>

<item attributeA>
/1 = "Joy"
/2 = "Love"
/3 = "Peace"
/4 = "Wonderful"
/5 = "Pleasure"
/6 = "Glorious"
/7 = "Laughter"
/8 = "Happy"
</item>

<item attributeBlabel>
/1 = "Bad"
</item>

<item attributeB>
/1 = "Agony"
/2 = "Terrible"
/3 = "Horrible"
/4 = "Nasty"
/5 = "Evil"
/6 = "Awful"
/7 = "Failure"
/8 = "Hurt"
</item>

<item targetAlabel>
/1 = "Young"
</item>

<item targetA>
/1 = "yf1.jpg"
/2 = "yf4.jpg"
/3 = "yf5.jpg"
/4 = "ym2.jpg"
/5 = "ym3.jpg"
/6 = "ym5.jpg"
</item>

<item targetBlabel>
/1 = "Old"
</item>

<item targetB>
/1 = "of1.jpg"
/2 = "of2.jpg"
/3 = "of3.jpg"
/4 = "om1.jpg"
/5 = "om2.jpg"
/6 = "om3.jpg"
</item>
**************************************************************************************************************
**************************************************************************************************************
	EDITABLE INSTRUCTIONS: change instructions here
**************************************************************************************************************
**************************************************************************************************************

<instruct>
/ navigationbuttonfontstyle = ("Arial", 3%, false, false, false, false, 5, 1)
</instruct>

<htmlpage iatintro>
/ file = "intro_pictureiat.htm"
</htmlpage>

<item instructions>
/ 1 = "Put your left finger on the 'E' response key for items that belong to the category '<%expressions.leftTarget%>'.
Put your right finger on the 'I' response key for items that belong to the category '<%expressions.rightTarget%>'.
~nItems will appear one-by-one in the middle of the screen.
~nIf you make an error, a red X will appear - to continue, press the other response key.
~nGo as fast as you can while making as few errors as possible."

/ 2 = "Put your left finger on the 'E' response key for items that belong to the category '<%item.attributeAlabel.item(1)%>'.
Put your right finger on the 'I' response key for items that belong to the category '<%item.attributeBlabel.item(1)%>'.
~nIf you make an error, a red X will appear - to continue, press the other response key.
~nGo as fast as you can while making as few errors as possible."

/ 3 = "Press the left 'E' key for '<%item.attributeAlabel.item(1)%>' and '<%expressions.leftTarget%>'.
Press the right 'I' key for '<%item.attributeBlabel.item(1)%>' and '<%expressions.rightTarget%>'.
~nEach item belongs to only one category.
~nIf you make an error, a red X will appear - to continue, press the other response key.
~nGo as fast as you can while making as few errors as possible."

/ 4 = "This is the same task as the previous one.
~n~nPress the left 'E' key for '<%item.attributeAlabel.item(1)%>' and '<%expressions.leftTarget%>'.
Press the right 'I' key for '<%item.attributeBlabel.item(1)%>' and '<%expressions.rightTarget%>'.
~nEach item belongs to only one category.
~nGo as fast as you can while making as few errors as possible."

/ 5 = "Attention! The labels have changed sides.
~nPress the left 'E' key for '<%expressions.rightTarget%>'.
Press the right 'I' key for '<%expressions.leftTarget%>'.
~nGo as fast as you can while making as few errors as possible."

/ 6 = "Press the left 'E' key for '<%item.attributeAlabel.item(1)%>' and '<%expressions.rightTarget%>'.
Press the right 'I' key for '<%item.attributeBlabel.item(1)%>' and '<%expressions.leftTarget%>'.
~nIf you make an error, a red X will appear - to continue, press the other response key.
~nGo as fast as you can while making as few errors as possible."

/ 7 = "This is the same task as the previous one.
~nPress the left 'E' key for '<%item.attributeAlabel.item(1)%>' and '<%expressions.rightTarget%>'.
Press the right 'I' key for '<%item.attributeBlabel.item(1)%>' and '<%expressions.leftTarget%>'
~nEach item belongs to only one category.
~nGo as fast as you can while making as few errors as possible."
</item>

Note: expressions used to assign the correct label to the left and right response keys
<expressions>
/ leftTarget = if(values.conditionOrder == "c-ic"){
	item.targetAlabel.item(1);
} else {
	item.targetBlabel.item(1);
};
/ rightTarget = if (values.conditionOrder == "c-ic"){
	item.targetBlabel.item(1);
} else {
	item.targetAlabel.item(1);
};
</expressions>

<text spacebar>
/ items = ("Press the SPACE BAR to begin.")
/ position = (50%, 90%)
/ valign = bottom
</text>

<text errorReminder>
/ items = ("If you make an error, a red X will appear. Press the other key to continue.")
/ position = (50%, 95%)
/ valign = bottom
/ fontstyle = ("Arial", 3%, false, false, false, false, 5, 1)
/ txcolor = gray
/ erase = false
</text>

<text finish>
/ items = ("Thank you!")
/ fontstyle = ("Arial", 8%, true, false, false, false, 5, 1)
/ position = (50%, 50%)
/ size = (80%, 80%)
/ vjustify = center
/ valign = center
/ halign = center
</text>

<text exit>
/ items = ("<press spacebar to exit>")
/ fontstyle = ("Arial", 3%, false, false, false, false, 5, 1)
/ position = (50%, 90%)
/ size = (80%, 5%)
/ vjustify = center
/ valign = center
/ halign = center
</text>

***********************************************************************
Performance summary
***********************************************************************

<trial summary>
/ ontrialbegin = [
	values.magnitude = "little to no";
	if( abs(expressions.d) > 0.15 ) values.magnitude = "a slight";
	if( abs(expressions.d) > 0.35 ) values.magnitude = "a moderate";
	if( abs(expressions.d) >= 0.65 ) values.magnitude = "a strong";
	if (expressions.d >= 0.0) values.preferred = item.targetALabel.1;
	if (expressions.d < 0.0) values.preferred = item.targetBLabel.1;
	if (expressions.d < 0.0) values.notpreferred= item.targetALabel.1;
	if (expressions.d >= 0.0) values.notpreferred= item.targetBLabel.1;
]
/ stimulustimes = [0=summary]
/ validresponse = (" ")
/ recorddata = false
</trial>

<text summary>
/ items = ("Your IAT score (D) was <% expressions.d %>, which suggests <% values.magnitude %> automatic preference for <% values.preferred %> compared to <% values.notpreferred %>.~n~n~nPress the spacebar to complete this session.") 
/ size = (60%, 60%)
/ hjustify = left
 </text>

**************************************************************************************************************
								!!!REMAINING CODE: Customize after careful consideration only!!!
**************************************************************************************************************


**************************************************************************************************************
**************************************************************************************************************
	DEFAULTS
**************************************************************************************************************
**************************************************************************************************************
script requires Inquisit 6.5.2.0 or higher

<defaults>
/ fontstyle = ("Arial", 3.5%, false, false, false, false, 5, 1)
/ screencolor = black
/ txbgcolor = black
/ txcolor = white
/ minimumversion = "6.5.2.0"
/ canvasaspectratio = (4, 3)
/ windowSize = (95%, 95%)
</defaults>

**************************************************************************************************************
**************************************************************************************************************
	DATA
**************************************************************************************************************
**************************************************************************************************************

Note: data file explanations under User Manual Information at the top

***********************
raw data file
***********************
<data>
/ columns = (build, computer.platform, date, time, subject, group, session, blockcode, blocknum, 
trialcode, trialnum, values.conditionOrder,
response, correct, latency, 
stimulusnumber, stimulusitem, 
expressions.da, expressions.db, expressions.d, expressions.percentcorrect, 
expressions.propRT300, expressions.excludeCriteriaMet)
</data>

****************
summary data
****************

<summarydata>
/ columns = (inquisit.version, computer.platform, script.startdate, script.starttime, 
script.subjectid, script.groupid, script.sessionid, script.elapsedtime, 
script.completed, values.conditionOrder,
expressions.da, expressions.db, expressions.d, expressions.percentcorrect, 
expressions.propRT300, expressions.excludeCriteriaMet)
</summarydata>

**************************************************************************************************************
**************************************************************************************************************
	VALUES: automatically updated
**************************************************************************************************************
**************************************************************************************************************

<values>
/ magnitude = "unknown"
/ preferred = "unknown"
/ notpreferred = "unknown"
/ progresswidth = 0
/ instructionIndex = 0
/conditionOrder = ""
</values>

**************************************************************************************************************
**************************************************************************************************************
	EXPRESSIONS
**************************************************************************************************************
**************************************************************************************************************

* 1 is compatible, 2 is incompatible
* a is first block, b is second block

/ m1a:					mean latencies of correct responses in first compatible block (short block)
/ sd1a:					standard deviation of latencies of correct responses in first compatible block (short block)

/ m2a:					mean latencies of correct responses in first incompatible block (short block)
/ sd2a					standard deviation of latencies of correct responses in first incompatible block (short block)

/ m1b:					mean latencies of correct responses in second compatible block (long block)
/ sd1b:					standard deviation of latencies of correct responses in second compatible block (long block)

/ m2b:					mean latencies of correct responses in second incompatible block (long block)
/ sd2b:					standard deviation of latencies of correct responses in second incompatible block (long block)

/ sda					pooled standarddeviation of latencies in first block (short block)
/ sdb 					pooled standarddeviation of latencies in second block (long block)

/ da:					D-score for first blocks		
/ db:					D-score for second blocks

/ d:					overall D-score (non-weighted mean of the d-scores from the short and long block)

/ percentcorrect:       calculates the overall percent correct score of initial responses of test trials of D-score qualifying latencies
/ progress:				sets the length of the progress bar to %

<expressions>
/m1a = list.RT_compatible1.mean
/sd1a = list.RT_compatible1.standarddeviation
/m1b = list.RT_compatible2.mean
/sd1b = list.RT_compatible2.standarddeviation
/m2a = list.RT_incompatible1.mean
/sd2a = list.RT_incompatible1.standarddeviation
/m2b = list.RT_incompatible2.mean
/sd2b = list.RT_incompatible2.standarddeviation
/sda = list.RT_block1.standarddeviation
/sdb = list.RT_block2.standarddeviation
/ da = (expressions.m2a - expressions.m1a) / expressions.sda
/ db = (expressions.m2b - expressions.m1b) / expressions.sdb
/ d = (expressions.da + expressions.db) / 2

/percentcorrect = list.ACC.mean*100
/ progress = 1% * values.progresswidth
/ propRT300 = list.RT300.mean
/ excludeCriteriaMet = if (expressions.propRT300 > 0.1){
	1;
} else {
	0;
}
</expressions>

//stores qualifying response times from short compatible block 
<list RT_compatible1>
</list>

//stores qualifying response times from long compatible block 
<list RT_compatible2>
</list>

//stores qualifying response times from short incompatible block 
<list RT_incompatible1>
</list>

//stores qualifying response times from long incompatible block 
<list RT_incompatible2>
</list>

//stores qualifying response times from short block (pooled)
<list RT_block1>
</list>

//stores qualifying response times from long block (pooled)
<list RT_block2>
</list>

//stores accuracy of D-score qualifying responses
<list ACC>
</list>

**************************************************************************************************************
**************************************************************************************************************
	INSTRUCTIONS
**************************************************************************************************************
**************************************************************************************************************

<text instructions>
/ items = instructions
/ position = (10%, 25%)
/ halign = left
/ valign = top
/ hjustify = left
/ vjustify = center
/ size = (80%, 50%)
/ select = values.instructionIndex
</text>

<trial instructions>
/ ontrialbegin = [
	values.progresswidth += 10;
	values.instructionIndex += 1;
]
/ stimulustimes = [1=instructions, spacebar, progressbar, progressbar_fill]
/ correctresponse = (" ")
/ errormessage = false
/ recorddata = false
/ showmousecursor = true
</trial>

<trial finish>
/ recorddata = true
/ stimulusframes = [1 = finish, exit]
/ validresponse = (" ")
</trial>

**************************************************************************************************************
**************************************************************************************************************
	STIMULI
**************************************************************************************************************
**************************************************************************************************************

<shape progressbar>
/shape = rectangle
/ size = (70%, 2%)
/ color = gray
/ position = (15%, 95%)
/ halign = left
/ valign = top
</shape>

<shape progressbar_fill>
/shape = rectangle
/ size = (expressions.progress, 2%)
/ color = green
/ position = (15%, 95%)
/ halign = left
/ valign = top
</shape>

<text attributeA>
/ items = attributeA
/ fontstyle = ("Arial", 5%)
/ txcolor = green
</text>

<text attributeB>
/ items = attributeB
/ fontstyle = ("Arial", 5%)
/ txcolor = green
</text>

<picture targetB>
/ items = targetB
/ size = (20%, 20%)
</picture>

<picture targetA>
/ items = targetA
/ size = (20%, 20%)
</picture>

<text error>
/ position = (50%, 75%)
/ items = ("X")
/ color = red
/ fontstyle = ("Arial", 10%, true)
</text>

<text attributeAleft>
/ items = attributeAlabel
/ valign = top
/ halign = left
/ position = (5%, 5%)
/ txcolor = green
/ fontstyle = ("Arial", 5%)
</text>

<text attributeBright>
/ items = attributeBlabel
/ valign = top
/ halign = right
/ position = (95%, 5%)
/ txcolor = green
/ fontstyle = ("Arial", 5%)
</text>

<text targetBleft>
/ items = targetBlabel
/ valign = top
/ halign = left	
/ position = (5%, 5%)
/ fontstyle = ("Arial", 5%)
</text>

<text targetBright>
/ items = targetBlabel
/ valign = top
/ halign = right
/ position = (95%, 5%)
/ fontstyle = ("Arial", 5%)
</text>

<text targetBleftmixed>
/ items = targetBlabel
/ valign = top
/ halign = left
/ position = (5%, 19%)
/ fontstyle = ("Arial", 5%)
</text>

<text targetBrightmixed>
/ items = targetBlabel
/ valign = top
/ halign = right
/ position = (95%, 19%)
/ fontstyle = ("Arial", 5%)
</text>

<text targetAleft>
/ items = targetAlabel
/ valign = top
/ halign = left
/ position = (5%, 5%)
/ fontstyle = ("Arial", 5%)
</text>

<text targetAright>
/ items = targetAlabel
/ valign = top
/ halign = right
/ position = (95%, 5%)
/ fontstyle = ("Arial", 5%)
</text>

<text targetAleftmixed>
/ items = targetAlabel
/ valign = top
/ halign = left
/ position = (5%, 19%)
/ fontstyle = ("Arial", 5%)
</text>

<text targetArightmixed>
/ items = targetAlabel
/ valign = top
/ halign = right
/ position = (95%, 19%)
/ fontstyle = ("Arial", 5%)
</text><text orleft>
/ items = ("or")
/ valign = top
/ halign = left
/ position = (5%, 12%)
/ fontstyle = ("Arial", 5%)
</text>

<text orright>
/ items = ("or")
/ valign = top
/ halign = right
/ position = (95%, 12%)
/ fontstyle = ("Arial", 5%)
</text>

**************************************************************************************************************
**************************************************************************************************************
	LISTS	
**************************************************************************************************************
**************************************************************************************************************

*************************************************
Data Lists: used for descriptive statistics
store correct latencies/accuracy data
fill up during runtime
*************************************************

Note: list stores 1 for latencies < 300ms (0 otherwise)
<list RT300>
</list>

**************************************************************************************************************
**************************************************************************************************************
	TRIALS 	
**************************************************************************************************************
**************************************************************************************************************

<trial attributeA>
/ validresponse = ("E", "I")
/ correctresponse = ("E")
/ stimulusframes = [1 = attributeA, errorReminder]
/ posttrialpause = parameters.ISI
</trial>

<trial attributeB>
/ validresponse = ("E", "I")
/ correctresponse = ("I")
/ stimulusframes = [1 = attributeB, errorReminder]
/ posttrialpause = parameters.ISI
</trial>

<trial targetBleft>
/ validresponse = ("E", "I")
/ correctresponse = ("E")
/ stimulusframes = [1 = targetB, errorReminder]
/ posttrialpause = parameters.ISI
</trial>

<trial targetBright>
/ validresponse = ("E", "I")
/ correctresponse = ("I")
/ stimulusframes = [1 = targetB, errorReminder]
/ posttrialpause = parameters.ISI
</trial>

<trial targetAleft>
/ validresponse = ("E", "I")
/ correctresponse = ("E")
/ stimulusframes = [1 = targetA, errorReminder]
/ posttrialpause = parameters.ISI
</trial>

<trial targetAright>
/ validresponse = ("E", "I")
/ correctresponse = ("I")
/ stimulusframes = [1 = targetA, errorReminder]
/ posttrialpause = parameters.ISI
</trial>

**************************************************************************************************************
**************************************************************************************************************
	BLOCKS
**************************************************************************************************************
**************************************************************************************************************

<block attributepractice>
/ bgstim = (attributeAleft, attributeBright)
/ trials = [
	1=instructions;
	2-21 = random(attributeA, attributeB);
]
/ errormessage = true(error,200)
/ response = correct
</block>

<block targetcompatiblepractice>
/ bgstim = (targetAleft, targetBright)
/ trials = [
	1=instructions;
	2-21 = random(targetAleft, targetBright);
]
/ errormessage = true(error,200)
/ response = correct
</block>

<block targetincompatiblepractice>
/ bgstim = (targetAright, targetBleft)
/ trials = [
	1=instructions;
	2-21 = random(targetAright, targetBleft);
]
/ errormessage = true(error,200)
/ response = correct
</block>

<block targetcompatiblepracticeswitch>
/ bgstim = (targetAleft, targetBright)
/ trials = [
	1=instructions;
	2-41 = random(targetAleft, targetBright);
]
/ errormessage = true(error,200)
/ response = correct
</block>

<block targetincompatiblepracticeswitch>
/ bgstim = (targetAright, targetBleft)
/ trials = [
	1=instructions;
	2-41 = random(targetAright, targetBleft);
]
/ errormessage = true(error,200)
/ response = correct
</block>

<block compatibletest1>
/ bgstim = (targetAleftmixed, orleft, attributeAleft, targetBrightmixed, orright, attributeBright)
/ trials = [
	1=instructions;
	3,5,7,9,11,13,15,17,19,21= random(targetAleft, targetBright);
	2,4,6,8,10,12,14,16,18,20 = random(attributeA, attributeB)]
/ errormessage = true(error,200)
/ response = correct
/ ontrialend = [
	if (block.compatibletest1.latency  <= 10000 && block.compatibletest1.currenttrialnumber != 1 ) {		
		list.RT_compatible1.appenditem(block.compatibletest1.latency);
		list.RT_block1.appenditem(block.compatibletest1.latency);
		list.ACC.appenditem(block.compatibletest1.correct);

	};
	if (block.compatibletest1.latency < 300) {
		list.RT300.appenditem(1);
	} else {
		list.RT300.appenditem(0);
	};
]
</block>

<block compatibletest2>
/ bgstim = (targetAleftmixed, orleft, attributeAleft, targetBrightmixed, orright, attributeBright)
/ trials = [
  2,4,6,8,10,12,14,16,18,20,22,24,26,28,30,32,34,36,38,40 = random(targetAleft, targetBright);
  1,3,5,7,9,11,13,15,17,19,21,23,25,27,29,31,33,35,37,39 = random(attributeA, attributeB)]
/ errormessage = true(error,200)
/ response = correct
/ ontrialend = [
	if (block.compatibletest2.latency  <= 10000) {
		list.RT_compatible2.appenditem(block.compatibletest2.latency);
		list.RT_block2.appenditem(block.compatibletest2.latency);
		list.ACC.appenditem(block.compatibletest2.correct);		

	};
	if (block.compatibletest2.latency  < 300) {
		list.RT300.appenditem(1);
	} else {
		list.RT300.appenditem(0);
	};
]
</block>

<block incompatibletest1>
/ bgstim = (targetBleftmixed, orleft, attributeAleft, targetArightmixed, orright, attributeBright)
/ trials = [
	1=instructions;
	3,5,7,9,11,13,15,17,19,21 = random(targetBleft, targetAright);
	2,4,6,8,10,12,14,16,18,20 = random(attributeA, attributeB)]
/ errormessage = true(error,200)
/ response = correct
/ ontrialend = [
	if (block.incompatibletest1.latency  <= 10000 && block.incompatibletest1.currenttrialnumber != 1) {		
		list.RT_incompatible1.appenditem(block.incompatibletest1.latency);
		list.RT_block1.appenditem(block.incompatibletest1.latency);
		list.ACC.appenditem(block.incompatibletest1.correct);		

	};
	if (block.incompatibletest1.latency  < 300) {
		list.RT300.appenditem(1);
	} else {
		list.RT300.appenditem(0);
	};
]
</block>

<block incompatibletest2>
/ bgstim = (targetBleftmixed, orleft, attributeAleft, targetArightmixed, orright, attributeBright)
/ trials = [
  2,4,6,8,10,12,14,16,18,20,22,24,26,28,30,32,34,36,38,40 = random(targetBleft, targetAright);
  1,3,5,7,9,11,13,15,17,19,21,23,25,27,29,31,33,35,37,39 = random(attributeA, attributeB)]
/ errormessage = true(error,200)
/ response = correct
/ ontrialend = [
	if (block.incompatibletest2.latency  <= 10000) {		
		list.RT_incompatible2.appenditem(block.incompatibletest2.latency);
		list.RT_block2.appenditem(block.incompatibletest2.latency);
		list.ACC.appenditem(block.incompatibletest2.correct);			

	};
	if (block.incompatibletest2.latency  < 300) {
		list.RT300.appenditem(1);
	} else {
		list.RT300.appenditem(0);
	};
]
</block>

<block compatibletestinstructions>
/ bgstim = (targetAleftmixed, orleft, attributeAleft, targetBrightmixed, orright, attributeBright)
/ trials = [1=instructions]
/ recorddata = false
</block>

<block incompatibletestinstructions>
/ bgstim = (targetBleftmixed, orleft, attributeAleft, targetArightmixed, orright, attributeBright)
/ trials = [1=instructions]
/ recorddata = false
</block>

<block summary>
/ skip = [parameters.showsummaryfeedback == false]
/ trials = [1=summary]
/ recorddata = false
</block>

<block end>
/ trials = [1 = finish]
</block>


**************************************************************************************************************
**************************************************************************************************************
	EXPERIMENT 
**************************************************************************************************************
**************************************************************************************************************
Groupassignment is done by groupnumber

<expt a>
/ onexptbegin = [
	values.conditionOrder = "c-ic"
]
/ preinstructions = (iatintro)
/ groups = (1 of 2)
/ blocks = [
	1=targetcompatiblepractice; 
	2=attributepractice; 
	3=compatibletest1; 
	4=compatibletestinstructions;
	5=compatibletest2; 
	6=targetincompatiblepractice; 
	7=incompatibletest1; 
	8=incompatibletestinstructions;
	9=incompatibletest2; 
	10=summary;
	11 = end;
]
</expt>

<expt b>
/ onexptbegin = [
	values.conditionOrder = "ic-c"
]
/ preinstructions = (iatintro)
/ groups = (2 of 2)
/ blocks = [
	1=targetincompatiblepractice; 
	2=attributepractice; 
	3=incompatibletest1; 
	4=incompatibletestinstructions;
	5=incompatibletest2; 
	6=targetcompatiblepractice; 
	7=compatibletest1; 
	8=compatibletestinstructions; 
	9=compatibletest2; 
	10=summary;
	11 = end;
]
</expt>

***********************************************************************
Test Monkey
***********************************************************************
<monkey>
/ latencydistribution = normal(500, 100)
/ percentcorrect = 90
</monkey>


**************************************************************************************************************
												End of File
**************************************************************************************************************
