Goal of this Challenge is to find Salesperson Serving More Than Five Customers by appling Power Query  advanced Editor(M code) 

Below is my M code Solution
 let
    Source = Excel.Workbook(File.Contents("C:\Users\SAIDI\Desktop\ADI24\POWER BI RECORDINGS\MASTER EXCEL\EXCEL\01_Case 1-20241102T070904Z-001\01_Case 1\Challenge.xlsx"), null, true),
    Table = Source{[Item="Salesperson",Kind="Table"]}[Data],
    Select = Table.SelectRows(Table, each List.Count(Text.Split(_[Customer], ", "))>5),
    Result= Select[Salesperson]
in
    Result
