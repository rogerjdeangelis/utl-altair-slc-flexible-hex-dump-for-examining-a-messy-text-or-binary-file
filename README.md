# -utl-altair-slc-flexible-hex-dump-for-examining-a-messy-text-or-binary-file
altair slc flexible hex dump for examining a messey text or binary file
    %let pgm=utl-altair-slc-flexible-hex-dump-for-examining-a-messy-text-or-binary-file;

    %stop_submission;

    altair slc flexible hex dump for examining a messey text or binary file

    Too long to post here, see github

    github
    https://github.com/rogerjdeangelis/-utl-altair-slc-flexible-hex-dump-for-examining-a-messy-text-or-binary-file

    Your file is tab delimited, this worked for me

    data want ;
      infile "d:/txt/GISDATAnew2.txt"
        dlm      = '09'x
        firstobs = 2
        ;
      input region$ type$ x1 y x2-x17;
    run;quit;

    see these files in the repo


    SAS listserve
    https://listserv.uga.edu/scripts/wa-UGA.exe?A2=SAS-L;e294b8bb.2512A&S=

    Ops question

    I am trying to read a .txt data file into SAS using infile.
    It looks like there is an issue, but I could not determine what it is.
    Any help to fix this would be greatly appreciated.

    /*                   _
    (_)_ __  _ __  _   _| |_
    | | `_ \| `_ \| | | | __|
    | | | | | |_) | |_| | |_
    |_|_| |_| .__/ \__,_|\__|
            |_|
    */

    SEE REPO FILE FOR INPUT AND HEX DUMP
    ------------------------------------

    GISDATAnew2.txt
    GISDATAnew2hex.txt

    THE FILE LOOKS LIKE
    -------------------

    region type x1 y x2 x3 ..... x15 x16 x17
    region1 type1 5.13 233.6 134 .....
    region1 type1 6.8 115.4 62.11 ..... 22.2 19.72 0.213
    region1 type1 4.17 179.2 39.27 ..... 22.2 19.72 0.257
    region1 type1 4.5 199.9 44.98 ..... 22.2 19.72 0.253
    region1 type1 6.47 231.7 132.2 ..... 22.2 19.72 0.335
    region1 type1 4.57 169.5 86.97 ..... 22.2 19.72 0.269
    region1 type1 5.19 193.5 66.07 ..... 22.2 19.72 0.321

    /*
     _ __  _ __ ___   ___ ___  ___ ___
    | `_ \| `__/ _ \ / __/ _ \/ __/ __|
    | |_) | | | (_) | (_|  __/\__ \__ \
    | .__/|_|  \___/ \___\___||___/___/
    |_|
     _                     _
    | |__   _____  __   __| |_   _ _ __ ___  _ __
    | `_ \ / _ \ \/ /  / _` | | | | `_ ` _ \| `_ \
    | | | |  __/>  <  | (_| | |_| | | | | | | |_) |
    |_| |_|\___/_/\_\  \__,_|\__,_|_| |_| |_| .__/
                                            |_|

    see github for utlrulr documentation
    https://github.com/rogerjdeangelis/utl_hex_dump_of_complex_text_file

    */

    %slc_hexdump
          (
           utitle=ASCII Flatfile Ruler & Hex
           ,uobj  =utlrulr
           ,uinflt =d:/txt/GISDATAnew2.txt
           /*--------------------------------*\
           | Control                          |
           \*--------------------------------*/
           ,uprnlen =80     /* Linesize for Dump */
           ,ulrecl  =80     /* maximum record length */
           ,urecfm   =f
           ,uobs = 3        /* number of obs to dump */
           ,uchrtyp =ascii  /* ascii or ebcdic */
           /*--------------------------------*\
           | Outputs                          |
           \*--------------------------------*/
           ,uotflt =d:/txt/GISDATAnew2hex.txt
          );

    /*           _               _
      ___  _   _| |_ _ __  _   _| |_
     / _ \| | | | __| `_ \| | | | __|
    | (_) | |_| | |_| |_) | |_| | |_
     \___/ \__,_|\__| .__/ \__,_|\__|
                    |_|
    */

    YOUR FILE IS TAB DELIMITED, SEE THE '09', TAB', DELIMITER
    ---------------------------------------------------------

    OUTPUT
    ------

    region . type . .x1 .
    1...5. . ..10 . ... 1
    766666 0 7776 0 073 0
    2579FE 9 4905 9 981 9


    ASCII Flatfile Ruler & Hex
           slc_hexdump
      d:/txt/GISDATAnew2.txt
    d:/txt/GISDATAnew2hex.txt
    09:10 Wednesday, December 3, 2025


     --- Record Number ---  1   ---  Record Length ---- 80

    region.type.x1.y.x2.x3.x4.x5.x6.x7.x8.x9.x10.x11.x12.x13.x14.x15.x16.x17..region
    1...5....10...15...20...25...30...35...40...45...50...55...60...65...70...75...8
    76666607776073070730730730730730730730730733073307330733073307330733073300766666
    2579FE949059819998298398498598698798898998109811981298139814981598169817DA2579FE


     --- Record Number ---  2   ---  Record Length ---- 80

    1.type1.5.13.233.6.134.182.3.1010.136.3.0.1203.76.24.0.0285.1070.0.0979.3319.0.6
    1...5....10...15...20...25...30...35...40...45...50...55...60...65...70...75...8
    30777630323303332303330333230333303332303233330332330323333033330323333033330323
    194905195E139233E691349182E3910109136E390E1203976E2490E02859107090E09799331990E6


     --- Record Number ---  3   ---  Record Length ---- 80

    98.399984.4882082.22.2.19.72.0.319..region1.type1.6.8.115.4.62.11.56.2.1020.33.4
    1...5....10...15...20...25...30...35...40...45...50...55...60...65...70...75...8
    33033333303333333033230332330323330076666630777630323033323033233033230333303323
    98939998494882082922E2919E7290E319DA2579FE194905196E89115E4962E11956E291020933E4

    /*
    | | ___   __ _
    | |/ _ \ / _` |
    | | (_) | (_| |
    |_|\___/ \__, |
             |___/
    */

    1                                          Altair SLC    09:10 Wednesday, December  3, 2025

    NOTE: Copyright 2002-2025 World Programming, an Altair Company
    NOTE: Altair SLC 2026 (05.26.01.00.000758)
          Licensed to Roger DeAngelis
    NOTE: This session is executing on the X64_WIN11PRO platform and is running in 64 bit mode

    NOTE: AUTOEXEC processing beginning; file is C:\wpsoto\autoexecbom.sas
    NOTE: AUTOEXEC source line
    1       +  ï»¿%let _init_= %str(
               ^
    ERROR: Expected a statement keyword : found "?"
    NOTE: Library wpshelp assigned as follows:
          Engine:        WPD
          Physical Name: C:\Program Files\Altair\SLC\2026\sashelp

    NOTE: Format num2mis output
    NOTE: Format $chr2mis output
    NOTE: Procedure format step took :
          real time : 0.016
          cpu time  : 0.000



    NOTE: The file 'c:\temp\null.txt' is:
          Filename='c:\temp\null.txt',
          Owner Name=T7610\Roger,
          File size (bytes)=0,
          Create Time=00:00:21 Jun 15 2022,
          Last Accessed=09:10:25 Dec 03 2025,
          Last Modified=09:10:25 Dec 03 2025,
          Lrecl=1, Recfm=F

    NOTE: 1 record was written to file 'c:\temp\null.txt'
    NOTE: The data step took :
          real time : 0.004
          cpu time  : 0.000



    NOTE: The data step took :
          real time : 0.000
          cpu time  : 0.000



    NOTE: The file 'c:\temp\done.txt' is:
          Filename='c:\temp\done.txt',
          Owner Name=T7610\Roger,
          File size (bytes)=0,
          Create Time=13:37:02 Dec 01 2025,
          Last Accessed=09:10:25 Dec 03 2025,
          Last Modified=09:10:25 Dec 03 2025,
          Lrecl=32767, Recfm=V


    2                                          Altair SLC    09:10 Wednesday, December  3, 2025

    NOTE: 1 record was written to file 'c:\temp\done.txt'
          The minimum record length was 4
          The maximum record length was 4
    NOTE: The data step took :
          real time : 0.000
          cpu time  : 0.000


    NOTE: AUTOEXEC processing completed

    1         %slc_hexdump
    2               (
    3                uinflt =d:/txt/GISDATAnew2.txt
    4                /*--------------------------------*\
    5                | Control                          |
    6                \*--------------------------------*/
    7                ,uprnlen =80     /* Linesize for Dump */
    8                ,ulrecl  =80     /* maximum record length */
    9                ,urecfm   =f
    10               ,uobs = 3        /* number of obs to dump */
    11               ,uchrtyp =ascii  /* ascii or ebcdic */
    12               /*--------------------------------*\
    13               | Outputs                          |
    14               \*--------------------------------*/
    15               ,uotflt =d:/txt/GISDATAnew2hex.txt
    16              );

    NOTE: The file 'd:\txt\GISDATAnew2hex.txt' is:
          Filename='d:\txt\GISDATAnew2hex.txt',
          Owner Name=BUILTIN\Administrators,
          File size (bytes)=0,
          Create Time=07:36:38 Dec 03 2025,
          Last Accessed=09:10:25 Dec 03 2025,
          Last Modified=09:10:25 Dec 03 2025,
          Lrecl=80, Recfm=V

    NOTE: 1 record was written to file 'd:\txt\GISDATAnew2hex.txt'
          The minimum record length was 0
          The maximum record length was 0
    NOTE: The data step took :
          real time : 0.001
          cpu time  : 0.000



    NOTE: The infile 'd:\txt\GISDATAnew2.txt' is:
          Filename='d:\txt\GISDATAnew2.txt',
          Owner Name=T7610\Roger,
          File size (bytes)=16546,
          Create Time=07:04:31 Dec 03 2025,
          Last Accessed=09:04:17 Dec 03 2025,
          Last Modified=07:03:32 Dec 03 2025,
          Lrecl=80, Recfm=F

    NOTE: The file 'd:\txt\GISDATAnew2hex.txt' is:
          Filename='d:\txt\GISDATAnew2hex.txt',
          Owner Name=BUILTIN\Administrators,
          File size (bytes)=318,
          Create Time=07:36:38 Dec 03 2025,
          Last Accessed=09:10:25 Dec 03 2025,
          Last Modified=09:10:25 Dec 03 2025,

    3                                  Altair SLC
                                                  09:10 Wednesday, December  3, 2025

          Lrecl=32767, Recfm=V

    NOTE: 4 records were read from file 'd:\txt\GISDATAnew2.txt'
    NOTE: 32 records were written to file 'd:\txt\GISDATAnew2hex.txt'
          The minimum record length was 0
          The maximum record length was 80
    NOTE: The data step took :
          real time : 0.016
          cpu time  : 0.015


    17
    ERROR: Error printed on page 1

    NOTE: Submitted statements took :
          real time : 0.113
          cpu time  : 0.093


    /*         _       _   _
     ___  ___ | |_   _| |_(_) ___  _ __
    / __|/ _ \| | | | | __| |/ _ \| `_ \
    \__ \ (_) | | |_| | |_| | (_) | | | |
    |___/\___/|_|\__,_|\__|_|\___/|_| |_|

    */

    data want ;
      infile "d:/txt/GISDATAnew2.txt" dlm='09'x firstobs=2;
      input region$ type$ x1 y x2-x17;
    run;quit;

    /*           _               _
      ___  _   _| |_ _ __  _   _| |_
     / _ \| | | | __| `_ \| | | | __|
    | (_) | |_| | |_| |_) | |_| | |_
     \___/ \__,_|\__| .__/ \__,_|\__|
                    |_|
    */

    Obs  REGION   TYPE    X1        Y      X2      X3        X15   X16    X17

      1  region1  type1  5.13  233.60  134.00  182.30 .... 22.2  19.72  0.319
      2  region1  type1  6.80  115.40   62.11   56.20 .... 22.2  19.72  0.213
      3  region1  type1  4.17  179.20   39.27   56.46 .... 22.2  19.72  0.257
      4  region1  type1  4.50  199.90   44.98   94.95 .... 22.2  19.72  0.253

    142  region3  type2  1.71   51.28   34.19   34.19 .... 15.9  21.53  0.298
    143  region3  type2  0.00    0.00    0.00    0.00 .... 15.9  21.53  0.326
    144  region3  type2  0.00    0.00    0.00    0.00 .... 15.9  21.53  0.368

    /*
    | | ___   __ _
    | |/ _ \ / _` |
    | | (_) | (_| |
    |_|\___/ \__, |
             |___/
    */

    1                                          Altair SLC    09:25 Wednesday, December  3, 2025

    NOTE: Copyright 2002-2025 World Programming, an Altair Company
    NOTE: Altair SLC 2026 (05.26.01.00.000758)
          Licensed to Roger DeAngelis
    NOTE: This session is executing on the X64_WIN11PRO platform and is running in 64 bit mode

    NOTE: AUTOEXEC processing beginning; file is C:\wpsoto\autoexecbom.sas
    NOTE: AUTOEXEC source line
    1       +  ï»¿%let _init_= %str(
               ^
    ERROR: Expected a statement keyword : found "?"
    NOTE: Library wpshelp assigned as follows:
          Engine:        WPD
          Physical Name: C:\Program Files\Altair\SLC\2026\sashelp

    NOTE: Format num2mis output
    NOTE: Format $chr2mis output
    NOTE: Procedure format step took :
          real time : 0.016
          cpu time  : 0.000



    NOTE: The file 'c:\temp\null.txt' is:
          Filename='c:\temp\null.txt',
          Owner Name=T7610\Roger,
          File size (bytes)=0,
          Create Time=00:00:21 Jun 15 2022,
          Last Accessed=09:25:08 Dec 03 2025,
          Last Modified=09:25:08 Dec 03 2025,
          Lrecl=1, Recfm=F

    NOTE: 1 record was written to file 'c:\temp\null.txt'
    NOTE: The data step took :
          real time : 0.004
          cpu time  : 0.000



    NOTE: The data step took :
          real time : 0.000
          cpu time  : 0.000



    NOTE: The file 'c:\temp\done.txt' is:
          Filename='c:\temp\done.txt',
          Owner Name=T7610\Roger,
          File size (bytes)=0,
          Create Time=13:37:02 Dec 01 2025,
          Last Accessed=09:25:08 Dec 03 2025,
          Last Modified=09:25:08 Dec 03 2025,
          Lrecl=32767, Recfm=V


    2                                          Altair SLC    09:25 Wednesday, December  3, 2025

    NOTE: 1 record was written to file 'c:\temp\done.txt'
          The minimum record length was 4
          The maximum record length was 4
    NOTE: The data step took :
          real time : 0.001
          cpu time  : 0.000


    NOTE: AUTOEXEC processing completed

    1         data want ;
    2           infile "d:/txt/GISDATAnew2.txt" dlm='09'x firstobs=2;
    3           input region$ type$ x1 y x2-x17;
    4         run;

    NOTE: The infile 'd:\txt\GISDATAnew2.txt' is:
          Filename='d:\txt\GISDATAnew2.txt',
          Owner Name=T7610\Roger,
          File size (bytes)=16546,
          Create Time=07:04:31 Dec 03 2025,
          Last Accessed=09:23:52 Dec 03 2025,
          Last Modified=07:03:32 Dec 03 2025,
          Lrecl=32767, Recfm=V

    NOTE: 144 records were read from file 'd:\txt\GISDATAnew2.txt'
          The minimum record length was 89
          The maximum record length was 124
    NOTE: Data set "WORK.want" has 144 observation(s) and 20 variable(s)
    NOTE: The data step took :
          real time : 0.004
          cpu time  : 0.015


    4       !     quit;
    5
    ERROR: Error printed on page 1

    NOTE: Submitted statements took :
          real time : 0.068
          cpu time  : 0.062

    /*              _
      ___ _ __   __| |
     / _ \ `_ \ / _` |
    |  __/ | | | (_| |
     \___|_| |_|\__,_|

    */
