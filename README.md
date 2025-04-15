# CBT577
Converted to GitHub via [cbt2git](https://github.com/wizardofzos/cbt2git)

This is still a work in progress. 
Due to amazing work by Alison Zhang and Jake Choi repos are no longer deleted.

```
//***FILE 577 is from Pergentino Arias, and contains REXX execs,    *   FILE 577
//*           panels, and Assembler programs that may be of use.    *   FILE 577
//*           Some programs are commented in Spanish.               *   FILE 577
//*                                                                 *   FILE 577
//*           I find these programs to be very interesting, and     *   FILE 577
//*           nicely done (SG - 05/02)                              *   FILE 577
//*                                                                 *   FILE 577
//*           email:  pergen@mixmail.com                            *   FILE 577
//*                                                                 *   FILE 577
//*   To make installation easier, I have included a load library   *   FILE 577
//*   in TSO XMIT format, as member $LOADLIB in this pds (SG-05/02) *   FILE 577
//*                                                                 *   FILE 577
//*   Short description of this file's contents:                    *   FILE 577
//*                                                                 *   FILE 577
//*     CASIO :    THIS IS A CALCULATOR                             *   FILE 577
//*                                                                 *   FILE 577
//*     CASIO :    THIS IS THE REXX WE MUST INVOKE                  *   FILE 577
//*     PCASIO:    IS THE PRINCIPAL PANEL                           *   FILE 577
//*     PCASIOH:   IS A HELP PANEL                                  *   FILE 577
//*     CASI01:    ARE THE ISPF MESSAGES                            *   FILE 577
//*     =======================================================     *   FILE 577
//*     SPACE :    WITH THE LRECL AND THE NUMBERS OF REGISTERS,     *   FILE 577
//*                IT GIVES THE TRKS                                *   FILE 577
//*                                                                 *   FILE 577
//*     SPACE  :  THIS IS THE REXX WE MUST INVOKE                   *   FILE 577
//*     PSPACE1:  PANEL                                             *   FILE 577
//*     PSPACE2:  PANEL                                             *   FILE 577
//*     INF10:    ARE THE ISPF MESSAGES                             *   FILE 577
//*     =======================================================     *   FILE 577
//*     EUCLIDES : THIS IS A REXX THAT USE THE EUCLID'S             *   FILE 577
//*                ALGORITHM - Calculate Greatest Common            *   FILE 577
//*                Denominator and Least Common Multiple of         *   FILE 577
//*                two given integers.                              *   FILE 577
//*     =======================================================     *   FILE 577
//*     LISTA :    THIS IS A REXX THAT GIVES A FORMATTED "TSO       *   FILE 577
//*                LISTA"                                           *   FILE 577
//*     =======================================================     *   FILE 577
//*     EASTER :   THIS IS A REXX THAT BY THE GAUSS FORMULA,        *   FILE 577
//*                GIVES US THE EASTER                              *   FILE 577
//*     =======================================================     *   FILE 577
//*     EXPCLEAN:                                                   *   FILE 577
//*                                                                 *   FILE 577
//*     EXPCLEAN:  IS AN ASSEMBLER PROGRAM THAT ALLOCATE FILES      *   FILE 577
//*                WHOSE DDNAME IN THE JCL BEGIN BY @@ AT           *   FILE 577
//*                DIFFERENCE THAN THE IEFBR14, IT OPENS AND        *   FILE 577
//*                CLOSE THE FILE (USEFUL IF AFTER THAT IT WILL     *   FILE 577
//*                BE USE BY A COBOL PROGRAM) IF THE FILE EXIST,    *   FILE 577
//*                IT CLEANS THE CONTENT.                           *   FILE 577
//*     JEXPCL :   JCL IN WHICH WE USE THE EXPCLEAN                 *   FILE 577
//*     =======================================================     *   FILE 577
//*     WAITING :  PROGRAM THAT WAITS THE TIME WE GIVE BY           *   FILE 577
//*                PARAMETER                                        *   FILE 577
//*                                                                 *   FILE 577
//*     WAITING :  IS AN ASSEMBLER PROGRAM THAT WAITS               *   FILE 577
//*     JWAIT  :   JCL THAT CALL WAITING PROGRAM                    *   FILE 577
//*     RWAIT  :   REXX THAT CALL WAITING PROGRAM                   *   FILE 577
//*     =======================================================     *   FILE 577
//*     EMPTY :                                                     *   FILE 577
//*                                                                 *   FILE 577
//*     EMPTY :    IS AN ASSEMBLER PROGRAM THAT GIVES US A RC=00    *   FILE 577
//*                IF THE SEQUENTIAL FILE ALLOCATED AS DDINPUT      *   FILE 577
//*                IS EMPTY; OTHERWISE, IT GIVES RC=12 OR THE       *   FILE 577
//*                RETURN CODE WE PASS IN HEX. BY PARM WE CAN       *   FILE 577
//*                CONCATENATE FILES                                *   FILE 577
//*     JEMPTY :   JCL TO INVOKE THE EMPTY PROGRAM                  *   FILE 577
//*     =======================================================     *   FILE 577
//*     MNF:                                                        *   FILE 577
//*                                                                 *   FILE 577
//*     MNF  :     IS AN EDIT MACRO THAT GIVES US THE NUMBER OF     *   FILE 577
//*                RECORDS IN A FILE.  IT COULD BE INVOKED IN       *   FILE 577
//*                EDIT, AS AN EDIT MACRO, OR IN THE 3.4 OPTION,    *   FILE 577
//*                BEING RUN AGAINST A SEQUENTIAL FILE-NOT A PDS.   *   FILE 577
//*                IF MNF IS INVOKED AS AN EDIT MACRO, WE MUST      *   FILE 577
//*                PUT THE CURSOR ON THE FIRST LETTER OF THE        *   FILE 577
//*                FILE NAME.                                       *   FILE 577
//*                                                                 *   FILE 577
//*     MN   :     AN ENGLISH-LANGUAGE VERSION OF MNF.              *   FILE 577
//*                                                                 *   FILE 577
//*     FFF  :     SUBROUTINE REXX                                  *   FILE 577
//*     FGF  :     SUBROUTINE REXX                                  *   FILE 577
//*     IRXNREG:   PROGRAM IN ASSEMBLER THAT IS THE ONE THAT        *   FILE 577
//*                COUNTS THE RECORDS                               *   FILE 577
//*                                                                 *   FILE 577
//*                YOU MUST CHANGE THE LINE IN THE MNF PROGRAM :    *   FILE 577
//*                "CALL LOAD.LIBRARIE(IRXNREG) "                   *   FILE 577
//*                PUTTING YOUR LIBRARIE                            *   FILE 577
//*                                                                 *   FILE 577
//*     EXAMPLE IN EDIT:                                            *   FILE 577
//*     ---------------                                             *   FILE 577
//*      EDIT       SISSHR.SIST19.JCL(LIBSEDIT) - 01.17             *   FILE 577
//*      COMMAND ===>MN                                             *   FILE 577
//*      ******  ***************************** TOP OF DATA ******** *   FILE 577
//*      000001  //SIST19A   JOB MSGCLASS=C,CLASS=C,NOTIFY=&SYSUID  *   FILE 577
//*      000002  //*----------------------------------------------- *   FILE 577
//*      000003  //PASO01   EXEC PGM=IDCAMS,COND=(0,NE)             *   FILE 577
//*      000004  //SYSPRINT DD SYSOUT=*                             *   FILE 577
//*      000005//SYSIN    DD *                                      *   FILE 577
//*      000006  DELETE   SISTSO.SIST19.PRUEBA                      *   FILE 577
//*      ==MSG> SISTSO.SIST19.PRUEBA                                *   FILE 577
//*      ==MSG> NUMBER OF RECORDS:                 52               *   FILE 577
//*      000007  SET MAXCC  = 0                                     *   FILE 577
//*                                                                 *   FILE 577
//*     EXAMPLE IN 3.4:                                             *   FILE 577
//*     --------------                                              *   FILE 577
//*                                                                 *   FILE 577
//*      DSLIST - DATA SETS MATCHING SIS*.SIST19                    *   FILE 577
//*      COMMAND ===>                                               *   FILE 577
//*                                                                 *   FILE 577
//*      COMMAND - ENTER "/" TO SELECT ACTION           VOLUME      *   FILE 577
//*      ------------------------------------------ ... ------      *   FILE 577
//*               SISTSO.SIST19.MORRAYA                 TST71B      *   FILE 577
//*      MN       SISTSO.SIST19.PRUEBA                  EXP104      *   FILE 577
//*               SISTSO.SIST19.RF                      SIST17      *   FILE 577
//*               SISTSO.SIST19.SHA1.L64                238928      *   FILE 577
//*      ******************* END OF DATA **********************     *   FILE 577
//*                                                                 *   FILE 577
//*     'SISTSO.SIST19.PRUEBA'                                      *   FILE 577
//*     NUMBER OF RECORDS:                 52                       *   FILE 577
//*                                                                 *   FILE 577
//*         ***                                                     *   FILE 577
//*                                                                 *   FILE 577
```
