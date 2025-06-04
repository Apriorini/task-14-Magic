Console.Write("Введите размер квадрата: ");
int n = Convert.ToInt32(Console.ReadLine());
int[,] magicsquare = new int[n, n];
int num = 1;
int i = 0;
int j = n / 2;
while (num <= n * n)
{
    if (magicsquare[i, j] == 0)
    {
        magicsquare[i, j] = num;
        num++;
    }
    int new_i = (i - 1) % n;
    if (new_i < 0) new_i += n;
    int new_j = (j + 1) % n;
    if (magicsquare[new_i, new_j] != 0)
    {
        i += 1;
    }
    else
    {
        i = new_i;
        j = new_j;
    }
}
Console.WriteLine($"Магический квадрат n = {n}");
for (int row = 0; row < n; row++)
{
    for (int col = 0; col < n; col++)
    {
        Console.Write(magicsquare[row, col] + "\t");
    }
    Console.WriteLine();
}
// я честно не знаю как решать четные числа
