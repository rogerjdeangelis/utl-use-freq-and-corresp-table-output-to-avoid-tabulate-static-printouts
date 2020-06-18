# utl-use-freq-and-corresp-table-output-to-avoid-tabulate-static-printouts
Use freq and corresp table output to avoid tabulate static printouts 
    Use freq and corresp table output to avoid tabulate static printouts                                                                
                                                                                                                                        
      Two Solutiions                                                                                                                    
                                                                                                                                        
          a. proc corresp                                                                                                               
          b. pr0oc freq                                                                                                                 
                                                                                                                                        
    github                                                                                                                              
    https://tinyurl.com/y7z3sdde                                                                                                        
    https://github.com/rogerjdeangelis/utl-use-freq-and-corresp-table-output-to-avoid-tabulate-static-printouts                         
                                                                                                                                        
    sas forum                                                                                                                           
    https://tinyurl.com/yak7b7w9                                                                                                        
    https://communities.sas.com/t5/SAS-Programming/proc-report-add-3-total-columns/m-p/663131                                           
                                                                                                                                        
    *_                   _                                                                                                              
    (_)_ __  _ __  _   _| |_                                                                                                            
    | | '_ \| '_ \| | | | __|                                                                                                           
    | | | | | |_) | |_| | |_                                                                                                            
    |_|_| |_| .__/ \__,_|\__|                                                                                                           
            |_|                                                                                                                         
    ;                                                                                                                                   
                                                                                                                                        
    data have;                                                                                                                          
    input ID Z1 $ Z2 $ Z3 $ Z4 $ Y;                                                                                                     
    cards4;                                                                                                                             
    1 a express Yes Long 10                                                                                                             
    2 a express Yes Long 20                                                                                                             
    3 a express No Long 30                                                                                                              
    4 a Direct No Long 40                                                                                                               
    5 a Direct Yes Long 150                                                                                                             
    6 a Direct No Long 60                                                                                                               
    7 a express Yes short 15                                                                                                            
    8 b express Yes short 25                                                                                                            
    9 b express No short 35                                                                                                             
    10 b Direct No short 45                                                                                                             
    11 b Direct Yes short 55                                                                                                            
    12 b Direct No short 65                                                                                                             
    ;;;;                                                                                                                                
    run;quit;                                                                                                                           
                                                                                                                                        
    WORK.have total obs=12                                                                                                              
                                                                                                                                        
      ID    Z1      Z2       Z3      Z4       Y                                                                                         
                                                                                                                                        
       1    a     express    Yes    Long      10                                                                                        
       2    a     express    Yes    Long      20                                                                                        
       3    a     express    No     Long      30                                                                                        
       4    a     Direct     No     Long      40                                                                                        
       5    a     Direct     Yes    Long     150                                                                                        
       6    a     Direct     No     Long      60                                                                                        
       7    a     express    Yes    short     15                                                                                        
       8    b     express    Yes    short     25                                                                                        
       9    b     express    No     short     35                                                                                        
      10    b     Direct     No     short     45                                                                                        
      11    b     Direct     Yes    short     55                                                                                        
      12    b     Direct     No     short     65                                                                                        
                                                                                                                                        
    *            _               _                                                                                                      
      ___  _   _| |_ _ __  _   _| |_                                                                                                    
     / _ \| | | | __| '_ \| | | | __|                                                                                                   
    | (_) | |_| | |_| |_) | |_| | |_                                                                                                    
     \___/ \__,_|\__| .__/ \__,_|\__|                                                                                                   
                    |_|                                                                                                                 
      __ _      ___ ___  _ __ _ __ ___  ___ _ __                                                                                        
     / _` |    / __/ _ \| '__| '__/ _ \/ __| '_ \                                                                                       
    | (_| |_  | (_| (_) | |  | | |  __/\__ \ |_) |                                                                                      
     \__,_(_)  \___\___/|_|  |_|  \___||___/ .__/                                                                                       
                                           |_|                                                                                          
    ;                                                                                                                                   
                                                                                                                                        
    WORK.WANTCOR total obs=5                                                                                                            
                                                                                                                                        
                       NO_    NO_       YES_      YES_                                                                                  
      LABEL           LONG    SHORT     LONG      SHORT    SUM                                                                          
                                                                                                                                        
      a * Direct      100        0       150        0      250                                                                          
      a * express      30        0        30       15       75                                                                          
      b * Direct        0      110         0       55      165                                                                          
      b * express       0       35         0       25       60                                                                          
                                                                                                                                        
      Sum             130      145       180       95      550                                                                          
                                                                                                                                        
    run;quit;                                                                                                                           
                                                                                                                                        
    *_         __                                                                                                                       
    | |__     / _|_ __ ___  __ _                                                                                                        
    | '_ \   | |_| '__/ _ \/ _` |                                                                                                       
    | |_) |  |  _| | |  __/ (_| |                                                                                                       
    |_.__(_) |_| |_|  \___|\__, |                                                                                                       
                              |_|                                                                                                       
    ;                                                                                                                                   
                                                                                                                                        
    WORK.WANT total obs=4                                                                                                               
                                                                                                                                        
      FREQUENCY    NOLONG    NOSHORT    YESLONG    YESSHORT    TOTAL                                                                    
                                                                                                                                        
      aDirect        100         0        150          0        250                                                                     
      aexpress        30         0         30         15         75                                                                     
      bDirect          0       110          0         55        165                                                                     
      bexpress         0        35          0         25         60                                                                     
                                                                                                                                        
    *          _       _   _                                                                                                            
     ___  ___ | |_   _| |_(_) ___  _ __  ___                                                                                            
    / __|/ _ \| | | | | __| |/ _ \| '_ \/ __|                                                                                           
    \__ \ (_) | | |_| | |_| | (_) | | | \__ \                                                                                           
    |___/\___/|_|\__,_|\__|_|\___/|_| |_|___/                                                                                           
      __ _      ___ ___  _ __ _ __ ___  ___ _ __                                                                                        
     / _` |    / __/ _ \| '__| '__/ _ \/ __| '_ \                                                                                       
    | (_| |_  | (_| (_) | |  | | |  __/\__ \ |_) |                                                                                      
     \__,_(_)  \___\___/|_|  |_|  \___||___/ .__/                                                                                       
                                           |_|                                                                                          
    ;                                                                                                                                   
                                                                                                                                        
    data havFix/view=havFix;                                                                                                            
      length z1z2 $12 z3z4 $12;                                                                                                         
      set have;                                                                                                                         
      z1z2=cats(z1,z2);                                                                                                                 
      z3z4=cats(z3,z4);                                                                                                                 
    run;quit;                                                                                                                           
                                                                                                                                        
    proc datasets lib=work nolist;                                                                                                      
     delete want;                                                                                                                       
    run;quit;                                                                                                                           
                                                                                                                                        
    %utl_odsfrq(setup);                                                                                                                 
    options ls=384;                                                                                                                     
    proc freq data=havFix;                                                                                                              
      tables z1z2*z3z4 / missing nopercent norow nocol ;                                                                                
      weight y;                                                                                                                         
    run;quit;                                                                                                                           
    %utl_odsfrq(outdsn=want);                                                                                                           
                                                                                                                                        
    proc print data=want(drop=rownam level);                                                                                            
    run;quit;                                                                                                                           
                                                                                                                                        
