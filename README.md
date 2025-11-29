# HK-DTUFENTS-DUTY-HOURS-SYSTEM-
from datetime import datetime

print("=== Student Time Tracking System ===")

# Input student ID
student_id = input("Enter Student ID: ")

# Record time in
input("Press Enter to record TIME IN...")
time_in = datetime.now()
print("Time In:", time_in)

# Record time out
input("Press Enter to record TIME OUT...")
time_out = datetime.now()
print("Time Out:", time_out)

# Calculate hours
total_hours = (time_out - time_in).total_seconds() / 3600

# Display summary
print("\n=== SUMMARY ===")
print("Student ID :", student_id)
print("Time In    :", time_in)
print("Time Out   :", time_out)
print("Total Hours:", round(total_hours, 2))

# Save to file
with open("attendance_records.txt", "a") as f:
    f.write(
        f"{student_id}, {time_in}, {time_out}, {round(total_hours, 2)} hours\n"
    )

print("\nRecord saved successfully!")
