# BioForce / Pointeuse App

## Overview
**BioForce** is a robust **Biometric Attendance Management System** designed to bridge the gap between hardware time clocks and HR operations. It automates the collection of employee "punches" from ZKTeco and Hikvision devices, processes them into meaningful attendance data, and provides powerful administration tools.

## Key Features
*   **Hardware Integration**:
    *   **ZKTeco**: Integrated via `zfemkeeper.dll` (SDK).
    *   **Hikvision**: Integrated via `HCNetSDK`.
    *   **SyncService**: Background windows service for automated real-time data polling.
*   **Smart Attendance Processing**:
    *   Converts raw logs into structured Daily Attendance (Check-In, Break-Out, Break-In, Check-Out).
    *   **Multi-schedule support**: Dynamic lateness calculation based on assigned shifts (e.g., Morning vs. Night shift).
*   **Workforce Management**:
    *   Employee profiles with photos and enrollment IDs.
    *   Department organization.
    *   Shift/Schedule assignment.
*   **Dashboard & Reporting**:
    *   Real-time view of Present/Late/Absent/Incomplete statuses.
    *   Visual indicators for attendance anomalies.

## Technology Stack
*   **Frontend**: .NET MAUI (Multi-platform App UI) for Windows/Android.
*   **Backend**: SQL Server (`BioForceDB`) with direct `SqlClient` access.
*   **Language**: C# 10+.
*   **Architecture**: MVVM (Model-View-ViewModel) using `CommunityToolkit.Mvvm`.
![IMG_20260127_114104](https://github.com/user-attachments/assets/c7068be2-22ef-4128-8425-e28b375c1e98)

## Project Structure
*   `/Pointeuse_App`: Main MAUI application (UI, ViewModels, Repositories).
*   `/ZKTeco.SyncService`: Background worker for device communication.
*   `/HikvisionSDK`: Wrapper libraries for Hikvision device support.
*   `/Database`: SQL scripts and stored procedures (e.g., `sp_ProcessDailyAttendance`).
