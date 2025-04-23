import React from "react";
import { FaChartBar, FaChartLine, FaChartPie, FaBars, FaSearch, FaExpand, FaHome, FaInbox, FaUserCircle } from "react-icons/fa";

const DashboardPage = () => {
  return (
    <div className="flex min-h-screen">
      {/* Sidebar */}
      <aside className="w-20 bg-blue-800 text-white flex flex-col items-center py-6 space-y-8">
        <FaBars className="text-2xl" />
        <div className="space-y-2 text-center">
          <FaChartBar className="text-2xl mx-auto" />
          <p className="text-xs">Dashboard</p>
        </div>
        <div className="space-y-2 text-center">
          <FaInbox className="text-2xl mx-auto" />
          <p className="text-xs">Drop Box</p>
        </div>
        <div className="mt-auto text-center">
          <FaUserCircle className="text-3xl mx-auto" />
          <p className="text-xs mt-1">158820</p>
        </div>
      </aside>

      {/* Main Content */}
      <main className="flex-1 bg-gray-100">
        {/* Top Navbar */}
        <header className="bg-blue-900 text-white px-6 py-4 flex items-center justify-between">
          <div className="flex items-center gap-4">
            <div className="text-sm leading-tight">
              <p className="font-bold">TATA CONSULTANCY SERVICES</p>
              <p className="text-2xl font-bold -mt-1">tcs</p>
            </div>
            <h1 className="text-xl font-semibold ml-6">
              TCS Service Delivery Performance Capture
            </h1>
          </div>
          <div className="flex items-center gap-4 text-xl">
            <FaSearch />
            <FaExpand />
          </div>
        </header>

        {/* Breadcrumb */}
        <div className="text-sm text-gray-600 px-6 py-2">Dashboard &gt;</div>

        {/* Filters */}
        <div className="bg-white mx-6 p-4 rounded shadow mb-4 grid grid-cols-6 gap-4 text-sm">
          <input className="border px-2 py-1 rounded" placeholder="Contract ID" />
          <select className="border px-2 py-1 rounded">
            <option>Select a Contract ID</option>
          </select>

          <div className="flex items-center gap-2">
            <input type="radio" name="project" />
            <span>Project ID</span>
          </div>
          <select className="border px-2 py-1 rounded col-span-1">
            <option>Select a Project ID</option>
          </select>

          <div className="flex items-center gap-2">
            <input type="radio" name="projectType" />
            <span>Project Type</span>
          </div>
          <select className="border px-2 py-1 rounded col-span-1">
            <option>Select a Project Type</option>
          </select>

          <div className="flex items-center gap-2 col-span-2">
            <input type="radio" name="groupClient" />
            <span>Group Client</span>
            <select className="border px-2 py-1 rounded ml-2">
              <option>Select a Group Client</option>
            </select>
          </div>

          <button className="bg-red-600 text-white px-4 py-1 rounded">Reset</button>
          <button className="bg-blue-600 text-white px-4 py-1 rounded">Filter</button>
        </div>

        {/* Chart Grid */}
        <div className="grid grid-cols-3 gap-4 px-6 pb-6">
          {[
            <FaChartBar />, <FaChartLine />, <FaChartBar />,
            <FaChartLine />, <FaChartPie />, <FaChartBar />
          ].map((Icon, i) => (
            <div
              key={i}
              className="bg-white p-6 rounded shadow flex flex-col items-center justify-center text-center h-40"
            >
              <Icon className="text-4xl mb-2" />
              <p className="text-sm font-semibold">Chart {i + 1}</p>
            </div>
          ))}
        </div>

        {/* Footer */}
        <footer className="text-xs text-center py-4 text-gray-500">
          Copyright © 2025 Tata Consultancy Services
        </footer>
      </main>
    </div>
  );
};

export default DashboardPage;
