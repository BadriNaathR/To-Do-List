import { FaDownload, FaEye } from 'react-icons/fa';

const files = [
  {
    fileId: '1237-ABCD',
    fileName: 'CI_CBPT_ADM_AMS3 Project.pdf',
    projectId: 'P_80000024',
    projectName: 'ABCD Project Name',
    contractId: 'B-2025-1234-6789',
    uploadedBy: '2345678',
    period: 'May-2024',
    status: 'Success'
  },
  {
    fileId: '1236-ABCD',
    fileName: 'CI_CBPT_ADM_AMS3 Project.pdf',
    projectId: 'P_80000024',
    projectName: 'ABCD Project Name',
    contractId: 'B-2025-1234-6789',
    uploadedBy: '2345678',
    period: 'Apr-2024',
    status: 'Extraction In-Progress'
  },
  {
    fileId: '1235-ABCD',
    fileName: 'CI_CBPT_ADM_AMS3 Project.pdf',
    projectId: 'P_80000024',
    projectName: 'ABCD Project Name',
    contractId: 'B-2025-1234-6789',
    uploadedBy: '2345678',
    period: 'Mar-2024',
    status: 'Failed'
  },
  {
    fileId: '1234-ABCD',
    fileName: 'CI_CBPT_ADM_AMS3 Project.pdf',
    projectId: 'P_80000024',
    projectName: 'ABCD Project Name',
    contractId: 'B-2025-1234-6789',
    uploadedBy: '2345678',
    period: 'Feb-2024',
    status: 'Success'
  }
];

export default function MSRUploadPanel() {
  return (
    <div className="p-4">
      {/* Drag and Drop Area */}
      <div className="border-2 border-dashed border-gray-400 rounded-md p-6 text-center text-gray-700 bg-gray-100 mb-6">
        <p className="text-xl font-semibold">Drag & Drop your MSR/WSRs</p>
        <div className="text-4xl mt-4">⬆️</div>
      </div>

      {/* Table */}
      <div className="overflow-x-auto shadow-md rounded-lg">
        <table className="w-full table-auto border-collapse text-sm text-left bg-white">
          <thead className="bg-gray-200 text-gray-700">
            <tr>
              <th className="p-3">File ID</th>
              <th className="p-3">File Name</th>
              <th className="p-3">Project ID</th>
              <th className="p-3">Project Name</th>
              <th className="p-3">Contract ID</th>
              <th className="p-3">Uploaded By</th>
              <th className="p-3">Period</th>
              <th className="p-3">Status</th>
              <th className="p-3">Action</th>
            </tr>
          </thead>
          <tbody>
            {files.map((file, index) => (
              <tr key={index} className="border-b">
                <td className="p-3">{file.fileId}</td>
                <td className="p-3">{file.fileName}</td>
                <td className="p-3">{file.projectId}</td>
                <td className="p-3">{file.projectName}</td>
                <td className="p-3">{file.contractId}</td>
                <td className="p-3">{file.uploadedBy}</td>
                <td className="p-3">{file.period}</td>
                <td className="p-3">
                  <span
                    className={`px-2 py-1 rounded text-white ${
                      file.status === 'Success'
                        ? 'bg-green-500'
                        : file.status === 'Failed'
                        ? 'bg-red-500'
                        : 'bg-yellow-500'
                    }`}
                  >
                    {file.status}
                  </span>
                </td>
                <td className="p-3 space-x-2">
                  <button className="text-blue-600 hover:text-blue-800">
                    <FaEye />
                  </button>
                  <button className="text-green-600 hover:text-green-800">
                    <FaDownload />
                  </button>
                </td>
              </tr>
            ))}
          </tbody>
        </table>
      </div>
    </div>
  );
}
