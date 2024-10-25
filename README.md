import {
  LineChart,
  Line,
  XAxis,
  YAxis,
  CartesianGrid,
  Tooltip,
  Legend,
  ResponsiveContainer
} from 'recharts';
const NetworkAvailabilityChart = () => {
  const data = [
    { month: 'Jan', preImplementation: 92.1, postImplementation: 99.8 },
    { month: 'Feb', preImplementation: 91.8, postImplementation: 99.7 },
    { month: 'Mar', preImplementation: 92.5, postImplementation: 99.9 },
    { month: 'Apr', preImplementation: 91.9, postImplementation: 99.6 },
    { month: 'May', preImplementation: 92.8, postImplementation: 99.8 },
    { month: 'Jun', preImplementation: 92.4, postImplementation: 99.7 }
  ];
  return (
    <div className="w-full max-w-4xl p-4 bg-white rounded-lg shadow-lg">
      <h2 className="text-xl font-bold mb-4 text-center">
        Figure 1: Network Availability Comparison
      </h2>
      <div className="h-96">
        <ResponsiveContainer width="100%" height="100%">
          <LineChart
            data={data}
            margin={{ top: 5, right: 30, left: 20, bottom: 5 }}
          >
            <CartesianGrid strokeDasharray="3 3" />
            <XAxis 
              dataKey="month" 
              label={{ 
                value: 'Month', 
                position: 'insideBottom', 
                offset: -5 
              }}
            />
            <YAxis
              domain={[90, 100]}
              label={{ 
                value: 'Availability (%)', 
                angle: -90, 
                position: 'insideLeft',
                offset: 10
              }}
            />
            <Tooltip />
            <Legend verticalAlign="top" height={36} />
            <Line
              type="monotone"
              dataKey="preImplementation"
              name="Pre-Implementation"
              stroke="#ff7300"
              strokeWidth={2}
              dot={{ r: 4 }}
            />
            <Line
              type="monotone"
              dataKey="postImplementation"
              name="Post-Implementation"
              stroke="#0088fe"
              strokeWidth={2}
              dot={{ r: 4 }}
            />
          </LineChart>
        </ResponsiveContainer>
      </div>
      <div className="mt-4 text-sm text-gray-600 text-center">
        Six-month comparison of network availability before and after microwave redundancy implementation
      </div>
    </div>
  );
};
export default NetworkAvailabilityChart;
