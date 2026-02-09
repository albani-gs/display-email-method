# Display e-mail method
Display email using a method in C#

```csharp
string[,] corporate =
{
    {"Robert", "Bavin"}, {"Simon", "Bright"},
    {"Kim", "Sinclair"}, {"Aashrita", "Kamath"},
    {"Sarah", "Delucchi"}, {"Sinan", "Ali"}
};

string[,] external =
{
    {"Vinnie", "Ashton"}, {"Cody", "Dysart"},
    {"Shay", "Lawrence"}, {"Daren", "Valdes"}
};

string externalDomain = "hayworth.com";

for (int i = 0; i < corporate.GetLength(0); i++)
{
    // display internal email addresses
    DisplayEmail(employee: i, externalClient: false);
}

for (int i = 0; i < external.GetLength(0); i++)
{
    // display external email addresses
    DisplayEmail(employee: i, domain: externalDomain, externalClient: true);
}

void DisplayEmail(int employee, string domain = "contoso.com", bool externalClient = true)
{
    if (externalClient)
    {
        string email = external[employee, 0].ToLower().Substring(0, 2);
        email += external[employee, 1].ToLower();
        email = $"{email}@{externalDomain}";
        Console.WriteLine(email);
    }
    else
    {
        string email = corporate[employee, 0].ToLower().Substring(0, 2);
        email += corporate[employee, 1].ToLower();
        email = $"{email}@{domain}";
        Console.WriteLine(email);
    }
}
```
