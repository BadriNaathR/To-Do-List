import React from "react";
import { Outlet, Link } from "react-router-dom";
import { FaBars, FaChartBar, FaInbox, FaUserCircle } from "react-icons/fa";

const Layout = () => {
  return (
    <div className="flex min-h-screen">
      {/* Sidebar */}
      <aside className="w-24 bg-blue-800 text-white flex flex-col items-center py-6 space-y-8">
        <FaBars className="text-2xl" />
        <div className="space-y-4">
          <Link to="/dashboard" className="flex flex-col items-center text-sm">
            <FaChartBar className="text-2xl" />
            <span>Dashboard</span>
          </Link>
          <Link to="/dropbox" className="flex flex-col items-center text-sm">
            <FaInbox className="text-2xl" />
            <span>Drop Box</span>
          </Link>
        </div>
        <div className="mt-auto flex flex-col items-center">
          <FaUserCircle className="text-3xl" />
          <p className="text-xs mt-1">158820</p>
        </div>
      </aside>

      {/* Main Section */}
      <div className="flex flex-col flex-1">
        {/* Header */}
        <header className="bg-blue-900 text-white px-6 py-4 flex items-center">
          <div className="flex items-center gap-4">
            <div className="leading-tight">
              <p className="font-bold text-xs">TATA CONSULTANCY SERVICES</p>
              <p className="font-bold text-2xl">tcs</p>
            </div>
            <h1 className="ml-6 text-xl font-semibold">
              TCS Service Delivery Performance Capture
            </h1>
          </div>
        </header>

        {/* Center Content */}
        <main className="flex-1 p-6 bg-gray-100">
          <Outlet />
        </main>

        {/* Footer */}
        <footer className="text-xs text-center p-4 text-gray-500">
          © 2025 Tata Consultancy Services
        </footer>
      </div>
    </div>
  );
};

export default Layout;
