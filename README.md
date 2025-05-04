<BrowserRouter>
  <Routes>
    <Route path="/" element={<Layout />}>
      <Route index element={<Navigate to="/dashboard" />} />
      <Route path="dashboard" element={<Dashboard />} />
      <Route path="about" element={<About />} />
      <Route path="login" element={<Login />} />
      <Route path="*" element={<Navigate to="/" />} />
    </Route>
  </Routes>

  <footer className="bg-black text-white text-sm flex justify-center">
    Copyright © 2025 Tata Consultancy Service
  </footer>
</BrowserRouter>
