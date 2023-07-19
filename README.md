# Web.BlazorClient 

# Table of Contents
[Initial Configuration](#initial-configuration)

# Initial Configuration

See the [official Telerik docs - First Staps with Server-side UI for Blazor](https://docs.telerik.com/blazor-ui/getting-started/server-blazor?_ga=2.181478319.964875160.1689781067-176290671.1678829918&_gl=1*1oplufx*_ga*MTc2MjkwNjcxLjE2Nzg4Mjk5MTg.*_ga_9JSNBCSF54*MTY4OTc4Mzg4Mi4yNC4xLjE2ODk3ODM5ODMuMTkuMC4w#step-1-create-a-new-project) for more detailed steps.

## Install

Add Telerik NuGet Feed:
Tools > NuGet Package Manager > Package Manager Settings > Package Sources

Name: telerik.com

Source: https://nuget.telerik.com/v3/index.json

Install Telerik.UI.for.Blazor using package source telerik.com

## Add/Edit the following files

#### /Pages/_Layout.cshtml
```HTML
<head>
    . . .
    <script src="_content/Telerik.UI.for.Blazor/js telerik-blazor.js" defer></script>
    <link href="_content/Telerik.UI.for.Blazor/css/kendo-theme-bootstrap/all.css" rel="stylesheet" />

</head>
```

#### Program.cs
```C#
var builder = WebApplication.CreateBuilder(args);
...

builder.Services.AddTelerikBlazor();

...

var app = builder.Build()

...

app.Run()
```

#### _Imports.razor
```C#
...
@using Telerik.Blazor
@using Telerik.Blazor.Components
@using Telerik.FontIcons
@using Telerik.SvgIcons
```

#### /shared/TelerikLayout.razor
```C#
@inherits LayoutComponentBase

<TelerikRootComponent>
    @Body
</TelerikRootComponent>
```

#### /shared/MainLayout.razor
```C#
@layout TelerikLayout
@inherits LayoutComponentBase

<PageTitle>Maricopa.Web.BlazorClient</PageTitle>

<div class="page">
    <div class="sidebar">
        <NavMenu />
    </div>

    <main>
        <div class="top-row px-4">
            <a href="https://docs.microsoft.com/aspnet/" target="_blank">About</a>
        </div>

        <article class="content px-4">
            @Body
        </article>
    </main>
</div>

```
