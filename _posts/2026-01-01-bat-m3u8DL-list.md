---
layout: default
title: bat-m3u8DL-list
date: 2026-01-01
---
    
@echo off
setlocal enabledelayedexpansion
set "input=down.txt"
set "temp=%input%.tmp"
type nul > "%temp%"
for /f "usebackq tokens=1,2 delims=$" %%a in ("%input%") do (
    echo 正在下载: %%a
    N_m3u8DL-CLI.exe "%%b" --workDir ".\Downloads" --saveName "%%a" --maxThreads "256" --minThreads "64" --retryCount "20" --timeOut "20" --enableDelAfterDone
    if errorlevel 1 (
        echo 下载失败，保留任务: %%a
        echo %%a$%%b >> "%temp%"
    ) else (
        echo 下载成功，移除任务: %%a
        rem 成功就不写入临时文件，相当于删除该行
    )
)
move /y "%temp%" "%input%" >nul
