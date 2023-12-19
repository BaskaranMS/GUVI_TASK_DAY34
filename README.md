# GUVI_TASK_DAY34

Hi Evaluators,
   I am Baskaran M S, B52 BATCH WEEKDAY TAMIL. I Have Created the DB Model for Guvi Zen Class as a Task for the DAY 34 ( DATABASE DAY 2 ).
   I Have attached the Model as a pdf format. and also please free to check the model also through this link https://dbdiagram.io/d/GUVI_ZEN_CLASS_DASHBOARD-6581ec7556d8064ca055faf0

   CODE: 

TABLE USER_TABLE {
  User_ID int [pk, increment]
  User_Name varchar(255)
  Email varchar(255)
  Password varchar(255)
}

TABLE COURSE_TABLE {
  CourseID int [pk, increment]
  CourseName varchar(255)
  Description varchar(255)
  Duration int 
}

TABLE LESSON_TABLE {
  LessonID int [pk, increment]
  CourseID int [ref: > COURSE_TABLE.CourseID]
  LessonTitle varchar(255)
  Content text
}

TABLE USER_COURSE_PROGRESS {
  ProgressID int [pk, increment]
  UserID int [ref: > USER_TABLE.User_ID]
  CourseID int [ref: > COURSE_TABLE.CourseID]
  CompletedLessons text
  ProgressPercentage int
}

TABLE LEADERBOARD_TABLE {
  LeaderboardID int [pk, increment]
  UserID int [ref: > USER_TABLE.User_ID]
  CourseID int [ref: > COURSE_TABLE.CourseID]
  TotalPoints int
  Rank int
}

TABLE TASK_COMPLETION_TABLE {
  TaskCompletionID int [pk, increment]
  UserID int [ref: > USER_TABLE.User_ID]
  LessonID int [ref: > LESSON_TABLE.LessonID]
  TaskTitle varchar(255)
  IsCompleted bool
}

TABLE ATTENDANCE_TABLE {
  AttendanceID int [pk, increment]
  UserID int [ref: > USER_TABLE.User_ID]
  CourseID int [ref: > COURSE_TABLE.CourseID]
  LessonID int [ref: > LESSON_TABLE.LessonID]
  AttendanceDate date
  IsPresent bool
}
