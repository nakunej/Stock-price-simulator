# Stock-price-simulator
Randomly generates stock prices of a stock over 10 days, determines optimal purchase and sale date for maximum profit


	using System;
	
	static class Program
	{
	    static void MaxProfit(double [] array)
	    {
	       
			double max = 0;
			int daymin = 0;
			double minCost = 0;
			int dayMax = 0;
			double maxCost = 0;
			
			
			for(int x = 0; x < array.Length; x++)
			{
				for(int y = x; y < array.Length; y++)
				{
					if(array[y] - array[x] > max)
					{
						
					max = array[y] - array[x];
					daymin = x +1;
					dayMax = y + 1;
					minCost = array[x];
					maxCost = array[y];
					
					}
				}
			}
			
			Console.WriteLine("Bought stock on day {0} for ${1:f2}", daymin, minCost);
			Console.WriteLine("Sold stock on day {0} for ${1:f2}", dayMax, maxCost);
			Console.WriteLine("Profit is ${0:f2}", max);
	   }
	   
	   static void Main( )
	   {
	       Console.WriteLine( );
			double [] stockPrices = new double [10];
			Random rgen = new Random();
			for(int i = 0; i < stockPrices.Length; i++)
			{
				stockPrices[i] = rgen.Next(100) + rgen.NextDouble();
			}
			
			 Console.WriteLine( " stock prices are:" );
			for(int x = 0; x< stockPrices.Length; x++)
			{
				Console.WriteLine("Day {0}: ${1:f2}", x+1, stockPrices[x]);
			}
		
		MaxProfit(stockPrices);
        
    }
	
}
