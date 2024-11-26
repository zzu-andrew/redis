cmake_minimum_required(VERSION 3.10)
project(Redis VERSION 6.2.6 LANGUAGES C)

# 设置编译选项
set(CMAKE_C_STANDARD 11)
set(CMAKE_C_STANDARD_REQUIRED ON)
set(CMAKE_POSITION_INDEPENDENT_CODE ON)

# 设置源文件目录
set(SOURCE_DIR ${CMAKE_SOURCE_DIR}/src)
set(BIN_DIR ${CMAKE_BINARY_DIR}/src)

# 添加源文件
file(GLOB SOURCES "${SOURCE_DIR}/*.c")

# 添加头文件目录
include_directories(${SOURCE_DIR})

# 添加库文件目录
link_directories(${BIN_DIR})

# 添加可执行文件
add_executable(redis-server ${SOURCES})

# 设置目标属性
set_target_properties(redis-server PROPERTIES RUNTIME_OUTPUT_DIRECTORY ${BIN_DIR})

# 添加链接库
target_link_libraries(redis-server pthread)

# 添加编译选项
target_compile_options(redis-server PRIVATE
        -Wall
        -W
        -Wno-missing-braces
        -Wno-missing-field-initializers
        -Wno-unused-function
        -Wno-unused-variable
        -Wno-sign-compare
        -Wno-unused-result
        -Wno-deprecated-declarations
        -Wno-format-security
        -Wno-pointer-sign
        -Wno-stringop-truncation
        -Wno-stringop-overflow
        )

# 添加预处理器定义
target_compile_definitions(redis-server PRIVATE
        HAVE_JEMALLOC=1
        USE_JEMALLOC=1
        HAVE_BACKTRACE=1
        HAVE_BACKTRACE_SYMBOLS=1
        HAVE_BACKTRACE_SYMBOLS_FD=1
        HAVE_CLOCK_GETTIME=1
        HAVE_GETDELIM=1
        HAVE_LIBEVENT=1
        HAVE_LIBRT=1
        HAVE_POSIX_MEMALIGN=1
        HAVE_STDLIB_H=1
        HAVE_SYSCALL=1
        HAVE_SYS_PRCTL_H=1
        HAVE_SYS_RESOURCE_H=1
        HAVE_SYS_STAT_H=1
        HAVE_SYS_TYPES_H=1
        HAVE_UNISTD_H=1
        HAVE_ZLIB=1
        HAVE_ZSTD=1
        HAVE_TLS=1
        HAVE_NETINET_IN_H=1
        HAVE_ARPA_INET_H=1
        HAVE_NETDB_H=1
        HAVE_PTHREAD_H=1
        HAVE_FORK=1
        HAVE_VFORK=1
        HAVE_EXECVP=1
        HAVE_SETPGID=1
        HAVE_SETSID=1
        HAVE_KILL=1
        HAVE_WAITPID=1
        HAVE_WAIT3=1
        HAVE_WAIT4=1
        HAVE_WIFEXITED=1
        HAVE_WEXITSTATUS=1
        HAVE_WIFSIGNALED=1
        HAVE_WTERMSIG=1
        HAVE_WCOREDUMP=1
        HAVE_WIFSTOPPED=1
        HAVE_WSTOPSIG=1
        HAVE_WIFCONTINUED=1
        HAVE_GETPID=1
        HAVE_GETPPID=1
        HAVE_GETUID=1
        HAVE_GETEUID=1
        HAVE_GETGID=1
        HAVE_GETEGID=1
        HAVE_GETGROUPS=1
        HAVE_GETLOGIN=1
        HAVE_GETPWUID=1
        HAVE_GETGRGID=1
        HAVE_GETPRIORITY=1
        HAVE_SETPRIORITY=1
        HAVE_GETRLIMIT=1
        HAVE_SETRLIMIT=1
        HAVE_GETRUSAGE=1
        HAVE_GETTIMEOFDAY=1
        HAVE_GETHOSTNAME=1
        HAVE_GETDOMAINNAME=1
        HAVE_GETADDRINFO=1
        HAVE_GETNAMEINFO=1
        HAVE_GETSERVBYNAME=1
        HAVE_GETSERVBYPOR=1
        HAVE_GETPROTOBYNAME=1
        HAVE_GETPROTOBYNUM=1
        HAVE_GETNETBYNAME=1
        HAVE_GETNETBYADDR=1
        HAVE_GETNETENT=1
        HAVE_GETPROTOENT=1
        HAVE_GETSERVENT=1
        HAVE_GETPWENT=1
        HAVE_GETGRENT=1
        HAVE_GETGROUPMEMBERS=1
        HAVE_GETLOGIN_R=1
        HAVE_GETPWUID_R=1
        HAVE_GETGRGID_R=1
        HAVE_GETGROUPS_R=1
        HAVE_GETPWENT_R=1
        HAVE_GETGRENT_R=1
        HAVE_GETGROUPMEMBERS_R=1
        HAVE_GETLOGIN_R_2=1
        HAVE_GETPWUID_R_2=1
        HAVE_GETGRGID_R_2=1
        HAVE_GETGROUPS_R_2=1
        HAVE_GETPWENT_R_2=1
        HAVE_GETGRENT_R_2=1
        HAVE_GETGROUPMEMBERS_R_2=1
        HAVE_GETLOGIN_R_3=1
        HAVE_GETPWUID_R_3=1
        HAVE_GETGRGID_R_3=1
        HAVE_GETGROUPS_R_3=1
        HAVE_GETPWENT_R_3=1
        HAVE_GETGRENT_R_3=1
        HAVE_GETGROUPMEMBERS_R_3=1
        HAVE_GETLOGIN_R_4=1
        HAVE_GETPWUID_R_4=1
        HAVE_GETGRGID_R_4=1
        HAVE_GETGROUPS_R_4=1
        HAVE_GETPWENT_R_4=1
        HAVE_GETGRENT_R_4=1
        HAVE_GETGROUPMEMBERS_R_4=1
        HAVE_GETLOGIN_R_5=1
        HAVE_GETPWUID_R_5=1
        HAVE_GETGRGID_R_5=1
        HAVE_GETGROUPS_R_5=1
        HAVE_GETPWENT_R_5=1
        HAVE_GETGRENT_R_5=1
        HAVE_GETGROUPMEMBERS_R_5=1
        HAVE_GETLOGIN_R_6=1
        HAVE_GETPWUID_R_6=1
        HAVE_GETGRGID_R_6=1
        HAVE_GETGROUPS_R_6=1
        HAVE_GETPWENT_R_6=1
        HAVE_GETGRENT_R_6=1
        HAVE_GETGROUPMEMBERS_R_6=1
        HAVE_GETLOGIN_R_7=1
        HAVE_GETPWUID_R_7=1
        HAVE_GETGRGID_R_7=1
        HAVE_GETGROUPS_R_7=1
        HAVE_GETPWENT_R_7=1
        HAVE_GETGRENT_R_7=1
        HAVE_GETGROUPMEMBERS_R_7=1
        HAVE_GETLOGIN_R_8=1
        HAVE_GETPWUID_R_8=1
        HAVE_GETGRGID_R_8=1
        HAVE_GETGROUPS_R_8=1
        HAVE_GETPWENT_R_8=1
        HAVE_GETGRENT_R_8=1
        HAVE_GETGROUPMEMBERS_R_8=1
        HAVE_GETLOGIN_R_9=1
        HAVE_GETPWUID_R_9=1
        HAVE_GETGRGID_R_9=1
        HAVE_GETGROUPS_R_9=1
        HAVE_GETPWENT_R_9=1
        HAVE_GETGRENT_R_9=1
        HAVE_GETGROUPMEMBERS_R_9=1
        HAVE_GETLOGIN_R_10=1
        HAVE_GETPWUID_R_10=1
        HAVE_GETGRGID_R_10=1
        HAVE_GETGROUPS_R_10=1
        HAVE_GETPWENT_R_10=1
        HAVE_GETGRENT_R_10=1
        HAVE_GETGROUPMEMBERS_R_10=1
        HAVE_GETLOGIN_R_11=1
        HAVE_GETPWUID_R_11=1
        HAVE_GETGRGID_R_11=1
        HAVE_GETGROUPS_R_11=1
        HAVE_GETPWENT_R_11=1
        HAVE_GETGRENT_R_11=1
        HAVE_GETGROUPMEMBERS_R_11=1
        HAVE_GETLOGIN_R_12=1
        HAVE_GETPWUID_R_12=1
        HAVE_GETGRGID_R_12=1
        HAVE_GETGROUPS_R_12=1
        HAVE_GETPWENT_R_12=1
        HAVE_GETGRENT_R_12=1
        HAVE_GETGROUPMEMBERS_R_12=1
        HAVE_GETLOGIN_R_13=1
        HAVE_GETPWUID_R_13=1
        HAVE_GETGRGID_R_13=1
        HAVE_GETGROUPS_R_13=1
        HAVE_GETPWENT_R_13=1
        HAVE_GETGRENT_R_13=1
        HAVE_GETGROUPMEMBERS_R_13=1
        HAVE_GETLOGIN_R_14=1
        HAVE_GETPWUID_R_14=1
        HAVE_GETGRGID_R_14=1
        HAVE_GETGROUPS_R_14=1
        HAVE_GETPWENT_R_14=1
        HAVE_GETGRENT_R_14=1
        HAVE_GETGROUPMEMBERS_R_14=1
        HAVE_GETLOGIN_R_15=1
        HAVE_GETPWUID_R_15=1
        HAVE_GETGRGID_R_15=1
        HAVE_GETGROUPS_R_15=1
        HAVE_GETPWENT_R_15=1
        HAVE_GETGRENT_R_15=1
        HAVE_GETGROUPMEMBERS_R_15=1
        HAVE_GETLOGIN_R_16=1
        HAVE_GETPWUID_R_16=1
        HAVE_GETGRGID_R_16=1
        HAVE_GETGROUPS_R_16=1
        HAVE_GETPWENT_R_16=1
        HAVE_GETGRENT_R_16=1
        HAVE_GETGROUPMEMBERS_R_16=1
        )

# 添加测试目标
#enable_testing()
#add_subdirectory(deps)
#add_subdirectory(src)
#add_subdirectory(tests)