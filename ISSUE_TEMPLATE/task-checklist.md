name: "📝 Task with checklist"
description: "Задача с чек-листом Definition of Done (DoD)"
title: "[TASK] "
labels: [task]
assignees: []

body:
  - type: textarea
    id: description
    attributes:
      label: "📌 Description"
      description: "Опишите задачу и что нужно сделать"
      placeholder: "Опишите суть задачи..."
    validations:
      required: true

  - type: checkboxes
    id: checklist
    attributes:
      label: "✅ Checklist"
      options:
        - label: "The task is implemented according to the requirements."
          required: true
        - label: "The code is covered with unit tests."
        - label: "Static code analysis has been completed with no critical issues."
        - label: "A pull request has been created."
        - label: "The code has passed the code review."
        - label: "The pull request has been successfully merged."
