

# TypeScript To-Do List Mini Project 📝

This is a simple **To-Do list** application built with **TypeScript**. The app allows users to add tasks, mark them as completed, and persist the tasks using `localStorage`. 💾

## Features ✨

- **Add New Task**: Users can enter a task title and add it to the list. ➕
- **Mark Tasks as Completed**: Each task has a checkbox that users can toggle to mark the task as completed. ✅
- **Persistence with Local Storage**: All tasks are saved in `localStorage`, so they remain available even after the page is reloaded. 🔄
- **UUID for Task ID**: Each task has a unique ID generated using `uuid`. 🔑

## Tech Stack 🛠️

- **TypeScript**: TypeScript is used to enhance JavaScript with static types and modern ES features.
- **UUID**: The `uuid` library is used to generate unique IDs for each task.
- **LocalStorage**: Used for task persistence.

## Installation 🖥️

### Prerequisites 🔧

Before running this project, make sure you have the following installed:

- **Node.js**: You can download it from [here](https://nodejs.org/).
- **npm (Node Package Manager)**: It comes bundled with Node.js.

### Steps to Run the Project 🚀

1. Clone the repository:
   ```bash
   git clone <your-repository-url>
   ```
2. Install dependencies:
   ```bash
   npm install
   ```

3. Compile the TypeScript code:
   ```bash
   npx tsc
   ```

4. Open the `index.html` file in a browser to see the app in action. 🌐

## Code Explanation 📚

1. **Task Type Definition**:  
   We define a `Task` type to represent the structure of each task, which includes the task's unique `id`, `title`, `completed` status, and `createdAt` date.

   ```typescript
   type Task = {
     id: string;
     title: string;
     completed: boolean;
     createdAt: Date;
   };
   ```

2. **Task List**:  
   The tasks are stored in an array `tasks[]`, and each task is rendered as an item in the list.

3. **Adding New Tasks**:  
   When the user submits a new task through the form, a new task object is created, assigned a unique `id` using `uuidV4()`, and added to the `tasks[]` array. The task is then displayed on the page.

4. **Marking Tasks as Completed**:  
   Each task has a checkbox that can be toggled to mark the task as completed. This updates the `completed` status of the task and saves the task list to `localStorage`.

5. **Persistence**:  
   Tasks are saved in `localStorage` whenever a task is added or marked as completed, ensuring that tasks are preserved even after page reloads.

## Code Snippets 🖋️

### Adding a New Task

```typescript
form?.addEventListener("submit", function (e) {
  e.preventDefault();

  if (input?.value == "" || input?.value == null) return;

  const newTask: Task = {
    id: uuidV4(),
    title: input.value,
    completed: false,
    createdAt: new Date(),
  };

  tasks.push(newTask);
  addListItem(newTask);
  input.value = "";
});
```

### Marking a Task as Completed

```typescript
checkbox.addEventListener("change", function () {
  task.completed = checkbox.checked;
  saveTasks();
});
```

### Saving Tasks to LocalStorage

```typescript
function saveTasks() {
  localStorage.setItem("TASKS", JSON.stringify(tasks));
}
```

## Contributing 🤝

Feel free to fork this repository and contribute by creating a pull request. If you find any bugs or issues, please feel free to open an issue on GitHub.

## License 📜

This project is open-source and available under the [MIT License](LICENSE).

