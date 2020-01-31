# hello-world
Test out GitHub with a traditional Hello World! project

# RN-IABValidator-Developer-kit
## RELEASE NOTES	
##### January 2020
##### V1.0.0


RN-IABValidator-Developer-kit IABValidator Developer Kit Release Notes

**©DTS, Inc. this publication and the product are copyrighted and all rights are reserved by DTS, Inc. without the express prior written permission of DTS, Inc., no part of this publication may be reproduced, photocopied, stored on a retrieval system, translated, or transmitted in any form or by any means, electronic or otherwise.**

RN-IABValidator-Developer-kit

This document contains confidential proprietary information owned by DTS, Inc. and/or its affiliates (“DTS”), including but not limited to trade secrets, know-how, technical and business information. Not for use or disclosure except under the terms of a fully-executed written confidential disclosure agreement by and between the recipient hereof and DTS. The recipient agrees to maintain the confidential proprietary information in confidence. Unauthorized use or disclosure is a violation of state, federal, and international laws.

Use of the hardware, software, methods associated with this document and any related documentation, including this document (the “product”) is at the recipient’s sole risk. The product is provided “as is” and without warranty of any kind. DTS expressly disclaims all warranties, express or implied, including but not limited to any implied warranties of merchantability, fitness for a particular purpose (regardless of whether DTS knows or has reason to know of the user’s particular needs) and noninfringement. DTS does not warrant that the product will meet user’s requirements, or that the defects in the product will be corrected. DTS does not warrant that the operation of any hardware or software associated with the product will be uninterrupted or error-free, and under no circumstances, including but not limited to negligence, shall DTS or the directors, officers, employees, or agents of DTS, be liable to user for any incidental, indirect, special, or consequential damages (including but not limited to damages for loss of business profits, business interruption, and loss of business information) arising out of any use, misuse, or inability to use the product . Some jurisdictions do not allow the exclusion of incidental or consequential damages, or implied warranties, so these exclusions may not apply to the user.

Conformity with any standards contained herein does not constitute DTS certification. No product is certified until it has passed DTS testing and DTS has issued a certification statement. Products containing unreleased, beta or outdated software versions may not be certified by DTS.

Both the product and documentation contain proprietary information of DTS, Inc.; they are provided under a license agreement containing restrictions on use and disclosure and are also protected by intellectual property laws. Reverse engineering, disassembly or decompilation of the product is prohibited.

Product documentation is licensed for use solely to support the product and not for any other purpose.

The information contained in this document is subject to change without notice. If you encounter any problems with the documentation, please contact us. DTS does not warrant that this document is error free. Except as may be expressly permitted in your license for the product, no part of the product may be reproduced or transmitted in any form or by any means, for any purpose, without the written permission of DTS.

DTS, the Symbol, DTS and the Symbol together are either registered trademarks or trademarks of DTS, Inc. in the United States and/or other countries. All other trademarks are the property of their respective owners.
# OVERVIEW

The IABValidator Developer Kit supports parsing and validating of SMPTE Immersive Audio Bitstream files (SMPTE document, ST 2098-2). The IABValidator Developer Kit includes:

 - IAB Parser, IABValidator libraries, and validator application
 -- Sourcecode    
 -- CMake scripts for building libraries and the validator application from source
 -- Pre-builtIABlibraries,utilitylibraries,andiab-validatorapplication
 
 - Documents
 -- RN-IABValidator-Developer-Kit.pdf(thisdocument)
 -- IABValidator-Developer-Kit-QuickStartGuide.pdf
 -- ReadMe.txt

## CHANGE LOGS

V1.0.0  
- First release








# IABVALIDATOR DEVELOPER KIT QUICK START GUIDE
##### January 2020
##### V1.0.0


RN-IABValidator-Developer-kit IABValidator Developer Kit Release Notes

**©DTS, Inc. this publication and the product are copyrighted and all rights are reserved by DTS, Inc. without the express prior written permission of DTS, Inc., no part of this publication may be reproduced, photocopied, stored on a retrieval system, translated, or transmitted in any form or by any means, electronic or otherwise.**

This document contains confidential proprietary information owned by DTS, Inc. and/or its affiliates (“DTS”), including but not limited to trade secrets, know-how, technical and business information. Not for use or disclosure except under the terms of a fully-executed written confidential disclosure agreement by and between the recipient hereof and DTS. The recipient agrees to maintain the confidential proprietary information in confidence. Unauthorized use or disclosure is a violation of state, federal, and international laws.

Use of the hardware, software, methods associated with this document and any related documentation, including this document (the “product”) is at the recipient’s sole risk. The product is provided “as is” and without warranty of any kind. DTS expressly disclaims all warranties, express or implied, including but not limited to any implied warranties of merchantability, fitness for a particular purpose (regardless of whether DTS knows or has reason to know of the user’s particular needs) and noninfringement. DTS does not warrant that the product will meet user’s requirements, or that the defects in the product will be corrected. DTS does not warrant that the operation of any hardware or software associated with the product will be uninterrupted or error-free, and under no circumstances, including but not limited to negligence, shall DTS or the directors, officers, employees, or agents of DTS, be liable to user for any incidental, indirect, special, or consequential damages (including but not limited to damages for loss of business profits, business interruption, and loss of business information) arising out of any use, misuse, or inability to use the product . Some jurisdictions do not allow the exclusion of incidental or consequential damages, or implied warranties, so these exclusions may not apply to the user.

Conformity with any standards contained herein does not constitute DTS certification. No product is certified until it has passed DTS testing and DTS has issued a certification statement. Products containing unreleased, beta or outdated software versions may not be certified by DTS.

Both the product and documentation contain proprietary information of DTS, Inc.; they are provided under a license agreement containing restrictions on use and disclosure and are also protected by intellectual property laws. Reverse engineering, disassembly or decompilation of the product is prohibited.

Product documentation is licensed for use solely to support the product and not for any other purpose.

The information contained in this document is subject to change without notice. If you encounter any problems with the documentation, please contact us. DTS does not warrant that this document is error free. Except as may be expressly permitted in your license for the product, no part of the product may be reproduced or transmitted in any form or by any means, for any purpose, without the written permission of DTS.

DTS, the Symbol, DTS and the Symbol together are either registered trademarks or trademarks of DTS, Inc. in the United States and/or other countries. All other trademarks are the property of their respective owners.
# VERSION HISTORY

# CHAPTER 1 : GETTING STARTED

SMPTE’s IAB standard (SMPTE Immersive Audio Bitstream, based on ST 2098-2:2018 and ST 2098- 2:2019) is an interoperable, channel & object based audio distribution format that is used to deliver immersive audio content for Digital Cinema or IMF applications.

The IABValidator Developer Kit (the Kit) allows developers to build a validator application which parses Immersive Audio Bitstreams and validates them against the following parameter profiles or constraint sets*, as defined in published standards and additional guideline documents:

1.  For Digital Cinema applications:
    
    1.  ST2098-2:2018
        
    2.  ST429-18:2019
        
    3.  Dolby CP850 and Dolby IMS3000 Immersive Audio Bitstream Guidelines Issue 3, 01-13- 2020
        
2.  For IMF applications:
    
    1.  ST2098-2-revision:2019
        
    2.  ST2067-201:2019
        
    3.  IMF IAB Interoperability Guidelines 07-08-2019
        

This document describes the Kit package and provides instructions to build the validator application from source code.

* Note: The terms of validation “profile” and “constraint set” are used interchangeably to refer to a set of parameters for validation.

IABValidator-Developer-Kit-QuickStartGuide

1.1 SYSTEM REQUIREMENTS FOR BUILDING THE VALIDATOR

The following describes requirements to build the libraries and the included validator application from source.

-   C++ compiler must be installed on the target machine
    
-   CMake v3.1.0 or newer
    
    For steps to build from source, see Chapter 4 below.
    
    1.2 INCLUDED PRE-BUILT BINARIES  
    Pre-built libraries and validator binaries for the following platforms/compilers have been included in
    
    package.

*It is noted that platforms and/or compilers included in this section and sub-sections, have been QA tested and qualified.*

*LINUX:*

-   Operating System: CentOS 6.9 o Compiler:GCC-4.4.7
    
*MAC:*
    
-   Operating System: OSX 10.14 o Compiler:Xcode7.3.1
    
 *WINDOWS:*
    

• Operating System: Windows 10  
o Compiler:VisualStudio2015

## CHAPTER 2 : IABVALIDATOR DEVELOPER KIT STRUCTURE

IABValidator Kit top level folder structure:

-   app: contains validator application source code and 64-bit pre-built binaries.
    
-   cmake: contains CMake configuration files.
    
-   docs: contains the Kit documentation.
    
-   include: contains validator application version header file.
    
-   module/common-stream: contains bitstream low level processing utility source code used by parser.
    
-   module/iabcore/lib: contains IAB Parser and IAB Validator 64-bit pre-built libraries.
    
-   module/iabcore/src/codec: contains source files for Dolby Lossless Codec (DLC) to decode IAB
    
    audio essence data.
    
-   module/iabcore/src/common: contains IAB Parser and IAB Validator common files.
    
-   module/iabcore/src/parser: contains IAB Parser private header and source files. The Parser library allows the application to parse IAB bitstreams.
    
-   module/iabcore/src/validator: contains IAB Validator private header and source files. The library allows the application developer to validate parsed IAB frames.
    
-   CMakeLists.txt: CMake script to build IAB libraries and validator application from source. CMakeLists.txt file also exists in some sub-folders as necessary for library and application build.
    
-   ReadMe.md: provides general information about the IABValidator Kit and build instructions.

## CHAPTER 3 : DOCUMENTATION

-  PACKAGE DOCUMENTATION

   The Kit contains the following documentation in the package:

 1.  IABValidator-Developer-Kit-QuickStartGuide.pdf (this document)
    
 2.  RN-IABValidator-Developer-Kit.pdf (release notes)
    
 3.  ReadMe.txt (see this file for detailed build instructions)
    
-   IAB LIBRARY API DOCUMENTATION

IAB libraries API (Application Programming Interface) information can be found in the following header

files:

- **module/iabcore/include/IABParserAPI.h** 
- **module/iabcore/include/IABValidatorAPI.h**
- **module/iabcore/include/IABElementsAPI.h**

The validator application included in this package implements a utility class **ValidateIABStream** that uses these APIs to parse and validate IAB bitstreams. After successfully processing the parsed IAB frames, the utility class passes back validation results to the application for reporting to the user.

*Developer note:*

*Header files IABPackerAPI.h or IABRendererAPI are included in the package simply for the purposes of maintaining IAB library integrity as there are no packer or renderer modules within the developer kit, APIs within these header files should not be used. Using these APIs will result in errors.*

## CHAPTER 4 : BUILD INSTRUCTIONS

Note that the prebuilt **iab-validator** command-line application for selected Linux, Mac, and Windows platforms can be found inside the **/app/bin** folder.

For steps to build from source, see the **README.md**

## CHAPTER 5: IABVALIDATOR APPLICATION

### 5.1 IABVALIDATOR APPLICATION

A command line application named iab-validator is included in the IABValidator Developer Kit.

This command line application parses the IAB bitstream file and writes validation results to a report in JSON format. To see how the application can be used, type the application name with -h or --help option to display the usage information. See Section 5.2 for selected usage examples.

Pre-built iab-validator for supported Linux, Mac, and Windows platforms can be found inside the /app/bin folder.

### 5.2 SELECTED COMMAND-LINE APPLICATION USAGE EXAMPLES


| Applications                   | Command-line Validation Option | Validation Profile 
|--------------------------------|--------------------------------|---------------- |
| Digital Cinema applications    | -c1                            | ST-2098-2-2018	|
|                                | -c2                            | ST-429-18:2019  |
|                                |  -c3                           | DbyCinema (Dolby CP850 and Dolby IMS3000 Immersive Audio Bitstream Guidelines Issue 3, 01-13- 2020) |
| IMF applications               | -c4                            | ST-2098-2-revision:2019 |
|                                |-c5	                          | ST-2067-201-2019 |
|                                |-c6                             |DbyIMF (IMF IAB Interoperability Guidelines 07-08- 2019)|
| Above both applications        |-cA                             | All profiles 1-6 |



Usage example 1: Validate an IAB bitstream against ST-2098-2:2018. In this case, all IAB frames of the bitstream are contained in a single file named “iabStream_1.iab”:

**iab-validator iabStream_1.iab -c1 -s -r**

Usage example 2: Validate an IAB bitstream against all supported validation profiles. In this case, all IAB frames of the bitstream are contained in a single file named “iabStream_2.iab”:

**iab-validator iabStream_2.iab -cA -s -r**

Usage example 3: Validate an IAB bitstream against ST-2098-2-revision:2019. In this case, the IAB bitstream is split into a frame sequence, in that, each IAB frame is contained in a separate file, all inside a folder named “IABStream_folder”.

The individual files have a naming convention in this format: “iabStream_3_xxxxxx.iab” where xxxxxx is the 6-digit suffix identifying the IAB frame index in the sequence.

**iab-validator ./IABStream_folder/iabStream_3_.iab -c4 -r**

### 5.3  VALIDATION PROFILE HIERARCHY AND DEPENDANCY

As outlined in Section 1, IAB validation profiles can be separated into two groups.

-   Group 1: 3 validation profiles (levels) for Digital Cinema applications
	-  ST-2098-2:2018
	- ST-429-18:2019
	- DbyCinema

    
-   Group 2: 3 validation profiles (levels) for IMF applications

	- ST-2098-2-revision:2019
	- ST-2067-201:2019
	- DbyIMF
    
    The two groups are independent of each other. However, within each group, validation parameters defined in the respective 3 profiles are related to each other as subset-superset.
    
    The set relationship among the 3 profiles for Digital Cinema applications is illustrated in Figure 1. Profile ST-2098-2:2018 forms the base set for digital cinema applications. Set for profile “DbyCinema” is a superset of “ST-429-18:2019”, which in turn is a superset of base set “ST-2098-2:2018”.

