:root {
  --primary-color: #2c3e50;
  --secondary-color: #3498db;
  --success-color: #27ae60;
  --warning-color: #f1c40f;
  --danger-color: #e74c3c;
  --light-bg: #ecf0f1;
  --dark-text: #2c3e50;
  --light-text: #ffffff;
  --border-radius: 8px;
  --box-shadow: 0 2px 5px rgba(0,0,0,0.1);
}

* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  font-family: 'Segoe UI', system-ui, sans-serif;
}

body {
  background-color: #f5f6fa;
  color: var(--dark-text);
  line-height: 1.6;
}

/* Layout */
.container {
  max-width: 1200px;
  margin: 0 auto;
  padding: 20px;
}

.flex {
  display: flex;
  gap: 20px;
}

.grid {
  display: grid;
  gap: 20px;
  grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
}

/* Cards */
.card {
  background: white;
  padding: 20px;
  border-radius: var(--border-radius);
  box-shadow: var(--box-shadow);
  margin-bottom: 20px;
}

/* Buttons */
.btn {
  padding: 8px 16px;
  border: none;
  border-radius: var(--border-radius);
  cursor: pointer;
  transition: all 0.3s ease;
}

.btn-primary {
  background-color: var(--secondary-color);
  color: var(--light-text);
}

.btn-danger {
  background-color: var(--danger-color);
  color: var(--light-text);
}

/* Forms */
.form-group {
  margin-bottom: 15px;
}

.input {
  width: 100%;
  padding: 10px;
  border: 1px solid #ddd;
  border-radius: var(--border-radius);
}

/* Task Status Indicators */
.status-indicator {
  height: 10px;
  width: 10px;
  border-radius: 50%;
  display: inline-block;
}

.status-todo { background-color: var(--warning-color); }
.status-in-progress { background-color: var(--secondary-color); }
.status-completed { background-color: var(--success-color); }

/* Progress Bar */
.progress-bar {
  height: 10px;
  background-color: #ddd;
  border-radius: var(--border-radius);
  overflow: hidden;
}

.progress-fill {
  height: 100%;
  background-color: var(--success-color);
  transition: width 0.3s ease;
}

/* Responsive Design */
@media (max-width: 768px) {
  .container {
    padding: 10px;
  }
  
  .flex {
    flex-direction: column;
  }
}
