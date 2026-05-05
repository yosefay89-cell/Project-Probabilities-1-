using System;
using System.Linq;
using System.Collections.Generic;

class Program
{
    static void Main()
    {
        double[] data = {
            115, 182, 191, 31, 196, 1099, 5, 172, 10, 179,
            83, 21, 20, 21, 186, 177, 195, 193, 188, 199,
            62, 109, 105, 183, 110
        };

        Array.Sort(data);
        int n = data.Length;

        // Mean
        double mean = data.Average();

        // Mode
        var groups = data.GroupBy(v => v)
                         .OrderByDescending(g => g.Count())
                         .First();
        double mode = groups.Key;

        // Median
        double median = GetPercentile(data, 50);

        // Variance
        double variance = data.Select(x => Math.Pow(x - mean, 2)).Average();

        // Standard Deviation
        double stdDev = Math.Sqrt(variance);

        // Percentiles
        double p20 = GetPercentile(data, 20);
        double p50 = GetPercentile(data, 50);

        // Quartiles
        double q1 = GetPercentile(data, 25);
        double q2 = GetPercentile(data, 50);
        double q3 = GetPercentile(data, 75);

        // Range
        double range = data.Max() - data.Min();

        // Interquartile Range
        double iqr = q3 - q1;

        // Sum of Deviations
        double sumDev = data.Sum(x => (x - mean));

        // Output
        Console.WriteLine("Mean = " + mean);
        Console.WriteLine("Mode = " + mode);
        Console.WriteLine("Median = " + median);
        Console.WriteLine("Variance = " + variance);
        Console.WriteLine("Standard Deviation = " + stdDev);
        Console.WriteLine("P20 = " + p20);
        Console.WriteLine("P50 = " + p50);
        Console.WriteLine("Q1 = " + q1);
        Console.WriteLine("Q2 = " + q2);
        Console.WriteLine("Q3 = " + q3);
        Console.WriteLine("Range = " + range);
        Console.WriteLine("Interquartile Range = " + iqr);
        Console.WriteLine("Sum of Deviations = " + sumDev);
    }

    static double GetPercentile(double[] sortedData, double percentile)
    {
        double position = (sortedData.Length + 1) * percentile / 100.0;
        int index = (int)position;
        double fraction = position - index;

        if (index <= 0) return sortedData[0];
        if (index >= sortedData.Length) return sortedData[sortedData.Length - 1];

        return sortedData[index - 1] + fraction * (sortedData[index] - sortedData[index - 1]);
    }
}
