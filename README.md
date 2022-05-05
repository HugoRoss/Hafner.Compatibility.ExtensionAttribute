# Hafner.Compatibility.ExtensionAttribute
Defines the System.Runtime.CompilerServices.Extension attribute for frameworks that do not include it, namely .NET framework 2.0 and 3.0.

Usage:

    <Project Sdk="Microsoft.NET.Sdk">

      <PropertyGroup>
        <TargetFrameworks>net6.0;net5.0;netcoreapp3.1;netcoreapp3.0;netcoreapp2.2;netcoreapp2.1;netcoreapp2.0;netcoreapp1.1;netcoreapp1.0;netstandard2.1;netstandard2.0;netstandard1.6;netstandard1.5;netstandard1.4;netstandard1.3;netstandard1.2;netstandard1.1;netstandard1.0;net48;net472;net471;net47;net462;net461;net46;net452;net451;net45;net403;net40;net35;net30;net20</TargetFrameworks>
        <FrameworksLackingExtensionAttribute>|net20|net30|</FrameworksLackingExtensionAttribute>
        <ImplicitUsings>enable</ImplicitUsings>
        <LangVersion>latest</LangVersion>
        <Nullable>enable</Nullable>
      </PropertyGroup>

      <!-- Replace '#' through '$'! -->
      <ItemGroup Condition="#(FrameworksLackingExtensionAttribute.Contains('|#(TargetFramework)|'))">
        <PackageReference Include="Hafner.Compatibility.ExtensionAttribute">
          <Version>1.0.2</Version>
        </PackageReference>
      </ItemGroup>

    </Project>

Above XML is a Visual Studio 2022 C# project file (*.csproj) that targets all the frameworks from .NET 2.0 to .NET 6.0 for the .NET flavors '.NET Framework', '.NET Core' and '.NET Standard'.

**Watch out: If you copy/paste above snipet you need to replace the '#' signs through '$' signs.**

I had to check it in like this as otherwise the condition got interpreted, sorry about that.