import React, { useState, useEffect } from 'react';
import './styles/style.css';

function App() {
  const [projects, setProjects] = useState([]);
  const [newProject, setNewProject] = useState('');

  // Fetch projects from API
  useEffect(() => {
    fetch('/api/projects')
      .then(res => res.json())
      .then(data => setProjects(data));
  }, []);

  const handleCreateProject = () => {
    fetch('/api/projects', {
      method: 'POST',
      headers: {
        'Content-Type': 'application/json',
      },
      body: JSON.stringify({ name: newProject }),
    })
    .then(res => res.json())
    .then(project => {
      setProjects([...projects, project]);
      setNewProject('');
    });
  };

  return (
    <div className="container">
      <h1>Project Manager</h1>
      
      <div className="card">
        <h2>Create New Project</h2>
        <input
          type="text"
          className="input"
          value={newProject}
          onChange={(e) => setNewProject(e.target.value)}
          placeholder="Project name"
        />
        <button className="btn btn-primary" onClick={handleCreateProject}>
          Create Project
        </button>
      </div>

      <div className="grid">
        {projects.map(project => (
          <div key={project._id} className="card">
            <h3>{project.name}</h3>
            <p>Tasks: {project.tasks?.length || 0}</p>
            <p>Status: {project.status}</p>
          </div>
        ))}
      </div>
    </div>
  );
}

export default App;
