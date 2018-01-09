Build Google gn build tools using the source repos of chromium_src-63.0.3239.132   

1 Download source package from googlesource   
2 Download googletest from https://codeload.github.com/google/googletest/zip/release-1.8.0    
3 Upzip googletest put the folder under "chromium\third_party\googletest" and rename it to src, make sure the tree look as: chromium\third_party\googletest\src\googletest    
4 Edit chromium\tools\gn\bootstrap\bootstrap.py, comment out line 764 and 770    
``` 
       #'base/synchronization/read_write_lock_win.cc',    
        'base/synchronization/waitable_event_watcher_win.cc',   
        'base/synchronization/waitable_event_win.cc',   
        'base/sys_info_win.cc',    
        'base/threading/platform_thread_win.cc',    
        'base/threading/thread_local_storage_win.cc',    
        #'base/threading/worker_pool_win.cc',      
  ````
5 Run chromium\tools\gn\bootstrap\bootstrap.py -s, donn't forget "-s" which means: no rebuild with gn itself    
 
6  Find the "gn.exe" in chromium\out\Release    
