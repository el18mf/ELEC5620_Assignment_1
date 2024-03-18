# $${\color{Turquoise}Seven \space Segment \space Display \space Driver \space Assessment}$$

Please refer to the assignment specification on Minerva for more details.

The following files are provided:

| File | Purpose |
| ---  | --- |
| `1-A-SevenSegDisplay/main.c`        | A test program which will allow you to test your solution (**do not modify**). |
| `1-A-SevenSegDisplay/DE1SoC_SevenSeg/DE1SoC_SevenSeg.h` | The header file which defines the interface for the driver (**do not modify**). |
| `1-A-SevenSegDisplay/DE1SoC_SevenSeg/DE1SoC_SevenSeg.c` | The implementation file for the driver. You need to complete this file. |

Please note you will need to create and configure the project in Arm Development Studio.

## ${\color{gold}Commit \space Notation}$

To better organise and track changes throughout the assignment, a fairly simplistic commit comment layout was employed as shown below with an example:

| Commit `Number`: | Topic Affected |  `Stage of Assignment` | `Succinct Description of Changes` |
| ---  | --- | ---  | --- |
| Commit 1 | Format | Initial Set-up of file | Revamp of Authors & Addition of myself |

## ${\color{gold}Assignment \space Steps}$
### ${\color{orange}Assignment \space Step \space Checklist}$
The assignment was comprised of the following 7 steps:

- [X] Step 1 - Create Assignment Reposity Via Minerva Link

- [x] Step 2 - Create the project in Arm Development Studio
    - [x] Project name is ${\color{green}1-A-SevenSegDisplay}$
    - [x] Location should be `C:\Users\Mathew\Workspace\ELEC5620-Assignment1-<GitHubUsername>\1-A-SevenSegDisplay` 

- [ ] Step 3 - Configure Project Settings
    - [ ] Using Unit 1.1 Notes configure the program settings properly or compiling shan't work

- [ ] Step 4 - Setting the Base Peripheral Addresses
    - [ ] The two peripheral addresses require setting in ${\color{green}DE1SoC_SevenSeg.c}$

- [ ] Step 5 - `DE1SoC_SevenSeg_SetSingle()` - Hexadecimal Single Display Decoder

- [ ] Step 6 - `DE1SoC_SevenSeg_SetDoubleHex()` – Hexadecimal Dual Display Decoder

- [ ] Step 7 - `DE1SoC_SevenSeg_SetDoubleDec()` – Decimal Dual Display Decoder

### ${\color{orange}Step \space 1 \space - \space Create \space Assignment \space Reposity \space Via \space Minerva \space Link}$ 
- [X] Creation of Assignment Repositry using the link shown on minerva, as shown by the 2 images below: 

<img src="Images/Step1/Step1_1.png" width="900" height="600">

<img src="Images/Step1/Step1_2.png" width="900" height="600">

### ${\color{orange}Step \space 2 \space - \space Create \space the \space project \space in \space Arm \space Development \space Studio}$
Create Project with:
- [x] titled: `1-A-SevenSegDisplay`
- [x] Location: `C:\Users\<username>\Workspace\ELEC5620-Assignment1-<GitHubUsername>\1-A-SevenSegDisplay`

To undertake this process, after installing and launching Arm Development Studio, the following steps must be following to properly create the project (with accompanying images):

- Select File -> New -> Project...

<img src="Images/Step2/Step2_1.png" width="750" height="500">

- Select C Project from the menu that has appeared

<img src="Images/Step2/Step2_2.png" width="600" height="500">

- As required, I change the location of the project to `C:\Users\Mathew\Workspace\ELEC5620-Assignment1-el18mf\1-A-SevenSegDisplay`, and project name to `1-A-SevenSegDisplay`

<img src="Images/Step2/Step2_3.png" width="600" height="500">

- Double check that the GitHub Repositories are in the correct location

<img src="Images/Step2/Step2_4.png" width="600" height="500">

- On the next menu titled "Select Configurations", make sure that debug is ticked while Release is not

<img src="Images/Step2/Step2_5.png" width="600" height="500">

- The final window that appears is the summary, which should contain all the following info if the above was done correctly:

<img src="Images/Step2/Step2_6.png" width="600" height="500">


### ${\color{orange}Step \space 3 \space - \space Configure \space Project \space Settings}$
- [X] Use Unit 1.1 Notes to properly configure setting
- [X] Test program compilation to prove successful configuration upon successful completion

Configuration steps with accompanying images shown below

- To begin configuring the Arm Development studio, you right click on the project explorer (Left Side) and select properties 

<img src="Images/Step3/Step3_1.png" width="800" height="500">

- One in properties, open the drop-down list titled "C/C++ General" and select Paths and Symbols. Once on this screen, click Link Folder

<img src="Images/Step3/Step3_2.png" width="800" height="500">

- This opens a new window, in which first click the box "Link to folder in the file system", after which you can click the browse... button which opens the file explorer. In said file explorer navigate to the ELEC5620-Resources folder and select the Drivers folder within. After this is done, click ok

<img src="Images/Step3/Step3_3.png" width="800" height="500">

<img src="Images/Step3/Step3_4.png" width="800" height="500">

- Back on the same screen, click the includes button (Highlighted in red)

<img src="Images/Step3/Step3_5.png" width="800" height="500">

- Once clicked, it will open a similar but different window, now with a languages and include directories section. This will open the "Add directory path" window

<img src="Images/Step3/Step3_6.png" width="800" height="500">

- From this window, you select the "Add to all configurations", "Add to all languages", and the third option "*emoji shown in picture* Is a workspace path" boxes, after which you select workspace... opening up a Folder selection window, in which you highlight the Drivers folder and press okay

<img src="Images/Step3/Step3_7.png" width="800" height="500">

- Next is configuring the compiler. To do this, go back to properties window, but this time select "C/C++ Build" and click settings

<img src="Images/Step3/Step3_8.png" width="800" height="500">

- Once in settings, make the changes outlined in the table below, in the following sections:
    - Under All Tools Settings -> Target
    - Under Arm C Conpiler for Embedded 6 -> Miscellaneous
    - Under Arm Linker 6 -> Image Layout
        - Scatter file code: `${workspace_loc}\ELEC5620M-Resources\ScatterFiles\FPGARomRam.scat`

<img src="Images/Step3/Step3_9.png" width="800" height="500">

### ${\color{orange}Step \space 4 \space - \space Setting \space the \space Base \space Peripheral \space Addresses}$
- [ ] Base Peripheral Addresses Set

*To note here, while going through the steps, I got a tad distracted while setting up an excel sheet to display how 0-9 and A-F are shown, and what segments light up, causing me to look up some excel based commands. After this, I was cleaning up some tabs and stumbled across an extra Github page open on main.c, and I noticed that on line 25 that key_ptr had been set. I assume this is the correct format, and truthfully is what I had planned to do, but I thought it best to admit this as citing resources is important.*

Two peripheral addresses cover the six 7-segment displays, with the split being:
- HEX0, HEX1, HEX2, and HEX3 on 1
- HEX4 and Hex5 being on the other. 

The parallal I/O Port Control Registers for the 7-Segment display is shown below:

|Address| 31 | 30 ... 24 | 23 | 22 ... 16 | 15 | 14 ... 8 | 7 | 6 ... 0 | Displays Controlled |
| ---  | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| ${\color{green}0xFF200020}$  | X | HEX3<sub>6-0</sub> | X | HEX2<sub>6-0</sub> | X | HEX1<sub>6-0</sub> | X | HEX0<sub>6-0</sub> | Displays 0 to 3s |
| ${\color{green}0xFF200030}$ | X | X | X | X | X | HEX5<sub>6-0</sub> | X | HEX4<sub>6-0</sub> | Displays 4 & 5 |

***To note: The use of ${\color{red}volatile \space unsigned \space char*}$ while declaring the addresses is preferrable, due to ${\color{red}char}$ being an 8-bit type and the 7-segment displays using 8 bits of the address. Eases addressing of each 7-segment display***


### ${\color{orange}Step \space 5 \space - \space DE1SoC_SevenSeg_SetSingle() \space - \space Hexadecimal \space Single \space Display \space Decoder}$

*Function Prototype on line 38 of [DE1SoC_SevenSeg.h](1-A-SevenSegDisplay/DE1SoC_SevenSeg/DE1SoC_SevenSeg.h)*

- [ ] For values 0-9 and A-F, work out which bits need to be set to illuminate the correct sections of the seven-segment display, so that the number is shown on the display. Refer to Figure 1 for the bit to segment mapping, and Figure 2 to figure out which segments are needed for each symbol. 
    - *For example, if 1 is passed in, bits 1 and 2 are high, or if 0xC is passed in, bits 0, 3, 4, and 5 should be set high.*
- [ ] Write the function, where you first translate ${\color{red}unsigned \space int}$ value to the relevant bit-mapping value, and call DE1SoC_SevenSeg_Write() with this value. If a value that is out of range is passed in
    - i.e. greater than 0xF (16 or higher), you should set the display to show a dash (segment 6 only).
- [ ] It is possible to test this feature by pressing the button KEY0. This button has been configured in the control program to increment the value of HEX0 every time you press it. Press the button enough times to move from 0-9 then A-F. After you pass F, the display should just show a dash. You can press KEY3 to reset the value to 0 

### ${\color{orange}Step \space 6 \space - \space DE1SoC_SevenSeg_SetDoubleHex() \space - \space Hexadecimal \space Dual \space Display \space Decoder}$
*Function Prototype on line 49 of [DE1SoC_SevenSeg.h](1-A-SevenSegDisplay/E1SoC_SevenSeg/DE1SoC_SevenSeg.h)*

- [ ] This function should take an input number in the range 0x00 - 0xFF and display it on a pair of displays. Use the display given in ${\color{red}unsigned \space int}$ display for the lower digit and display+1 for the higher digit.
    - [ ] Out of range inputs should show a dash on both displays.
    - [ ] This function will need to call DE1SoC_SevenSeg_SetSingle() twice.


### ${\color{orange}Step \space 7 \space – \space DE1SoC_SevenSeg_SetDoubleDec() \space – \space Decimal \space Dual \space Display \space Decoder}$
*Function Prototype on line 60 of [DE1SoC_SevenSeg.h](1-A-SevenSegDisplay/DE1SoC_SevenSeg/DE1SoC_SevenSeg.h)*

- [ ] This function should take an input number in the range 0 - 99 and display it on a pair of displays. Use the display given in unsigned int display for the lower digit and display+1 for the higher digit.
    - [ ] If a value of 9 is passed in, the next value should be 10, 1 on the first display, 0 on the second, **NOT a value of A**.
    - [ ] Out of range inputs should show a dash on both displays.
    - [ ] This function will need to call DE1SoC_SevenSeg_SetSingle() twice.

***Provided Hint: Investigation of the C modulo (%) operator would be beneficial***

## ${\color{gold}Resources}$
Here is a list of resources created and used during the process of this Assignment:
- Excel Sheet created to allow visualisation of 7-Segment Display for 0-9 and A-F - [7-Segment Excel](https://leeds365-my.sharepoint.com/:x:/g/personal/el18mf_leeds_ac_uk/Edg4A6v9ZDZDtbDtA-TnmbwB0QYruoaQz7MNOmsCEc4idA?e=MDMCSj)
- For step 4, use of [main.c](1-A-SevenSegDisplay\main.c)
- Resource that taught me how to implement colour text within this readme: [stackoverflow](https://stackoverflow.com/questions/11509830/how-to-add-color-to-githubs-readme-md-file#:~:text=You%20can%20however%20add%20color,or%20%22code%22%20tags%20needed.)
After realising how big the images appeared as, I looked into resizing images and found out an alternative method to embedded images here: [Github comment chain](https://gist.github.com/uupaa/f77d2bcf4dc7a294d109)