import React, { useState } from "react";
import { Input } from "@/components/ui/input";
import { Table, TableHeader, TableRow, TableHead, TableBody, TableCell } from "@/components/ui/table";
import { Card, CardContent } from "@/components/ui/card";

const initialData = [
  { id: 1, name: "Alice", age: 25, city: "New York", email: "alice@example.com", phone: "123-456-7890", job: "Engineer", company: "TechCorp", status: "Active", score: 95 },
  { id: 2, name: "Bob", age: 30, city: "Los Angeles", email: "bob@example.com", phone: "234-567-8901", job: "Designer", company: "Creative Inc", status: "Inactive", score: 88 },
  { id: 3, name: "Charlie", age: 28, city: "Chicago", email: "charlie@example.com", phone: "345-678-9012", job: "Manager", company: "Business Ltd", status: "Active", score: 92 },
  // Add more data as needed
];

export default function DataTable() {
  const [filters, setFilters] = useState({});
  const [filteredData, setFilteredData] = useState(initialData);

  const handleFilterChange = (column, value) => {
    const newFilters = { ...filters, [column]: value };
    setFilters(newFilters);
    
    const filtered = initialData.filter((row) =>
      Object.keys(newFilters).every((key) =>
        newFilters[key] === "" ||
        row[key].toString().toLowerCase().includes(newFilters[key].toLowerCase())
      )
    );
    setFilteredData(filtered);
  };

  return (
    <div className="p-6">
      <h1 className="text-3xl font-bold text-center text-blue-600 mb-6">2025 AAD PAC Schedule</h1>
      <Card>
        <CardContent>
          <div className="overflow-x-auto">
            <div className="grid grid-cols-10 gap-2 mb-4">
              {Object.keys(initialData[0]).map((col, index) => (
                <Input
                  key={index}
                  placeholder={`Filter ${col}`}
                  value={filters[col] || ""}
                  onChange={(e) => handleFilterChange(col, e.target.value)}
                  className="p-2 border border-gray-300 rounded"
                />
              ))}
            </div>
            <Table>
              <TableHeader>
                <TableRow className="bg-gray-100">
                  {Object.keys(initialData[0]).map((col, index) => (
                    <TableHead key={index} className="text-blue-700">{col}</TableHead>
                  ))}
                </TableRow>
              </TableHeader>
              <TableBody>
                {filteredData.map((row) => (
                  <TableRow key={row.id} className="hover:bg-gray-50">
                    {Object.values(row).map((cell, index) => (
                      <TableCell key={index} className="text-gray-800">{cell}</TableCell>
                    ))}
                  </TableRow>
                ))}
              </TableBody>
            </Table>
          </div>
        </CardContent>
      </Card>
    </div>
  );
}
