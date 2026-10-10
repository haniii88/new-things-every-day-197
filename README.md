function dailyLog197() {
  const projects = [
    { name: "Website", progress: 85, deadlineRisk: false },
    { name: "Mobile App", progress: 45, deadlineRisk: true },
    { name: "API Service", progress: 70, deadlineRisk: false },
    { name: "Dashboard", progress: 30, deadlineRisk: true }
  ];

  const averageProgress =
    projects.reduce((sum, project) => sum + project.progress, 0) /
    projects.lengt;

  const needsAttention = projects.filter(
    project => project.deadlineRisk || project.progress < 50
  );

  const report = {
    date: new Date().toISOString().split("T")[0],
    totalProjects: projects.length,
    averageProgress: `${averageProgress.toFixed(1)}%`,
    projectsNeedingAttention: needsAttention.map(project => project.name),
    status: needsAttention.length === 0
      ? "All projects on track"
      : "Some projects need attention"
  };

  console.log("Daily Project Health Report:", report);
}

dailyLog197();
