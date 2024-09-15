using System;
using System.Collections.Generic;
using System.Linq;

class Student
{
    public int Id { get; set; }
    public string Name { get; set; }
    public int Age { get; set; }
}

class Program
{
    static void Main(string[] args)
    {

        Console.OutputEncoding = System.Text.Encoding.UTF8;


        List<Student> students = new List<Student>
        {
            new Student { Id = 1, Name = "An", Age = 16 },
            new Student { Id = 2, Name = "Bình", Age = 18 },
            new Student { Id = 3, Name = "Cường", Age = 15 },
            new Student { Id = 4, Name = "Dũng", Age = 19 },
            new Student { Id = 5, Name = "Anh", Age = 17 }
        };


        Console.WriteLine("Danh sách học sinh:");
        students.ForEach(s => Console.WriteLine($"Id: {s.Id}, Name: {s.Name}, Age: {s.Age}"));


        var ageRangeStudents = students.Where(s => s.Age >= 15 && s.Age <= 18).ToList();
        Console.WriteLine("\nHọc sinh có tuổi từ 15 đến 18:");
        ageRangeStudents.ForEach(s => Console.WriteLine($"Id: {s.Id}, Name: {s.Name}, Age: {s.Age}"));


        var studentsWithA = students.Where(s => s.Name.StartsWith("A")).ToList();
        Console.WriteLine("\nHọc sinh có tên bắt đầu bằng chữ 'A':");
        studentsWithA.ForEach(s => Console.WriteLine($"Id: {s.Id}, Name: {s.Name}, Age: {s.Age}"));


        var totalAge = students.Sum(s => s.Age);
        Console.WriteLine($"\nTổng tuổi của tất cả học sinh: {totalAge}");


        var oldestStudent = students.OrderByDescending(s => s.Age).FirstOrDefault();
        Console.WriteLine($"\nHọc sinh có tuổi lớn nhất: Id: {oldestStudent.Id}, Name: {oldestStudent.Name}, Age: {oldestStudent.Age}");


        var sortedStudents = students.OrderBy(s => s.Age).ToList();
        Console.WriteLine("\nDanh sách học sinh sau khi sắp xếp theo tuổi:");
        sortedStudents.ForEach(s => Console.WriteLine($"Id: {s.Id}, Name: {s.Name}, Age: {s.Age}"));
    }
}
