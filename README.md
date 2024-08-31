USE [master]
GO
/****** Object:  Database [ACSWebPortalDb]    Script Date: 8/31/2024 4:23:42 PM ******/
CREATE DATABASE [ACSWebPortalDb]
 CONTAINMENT = NONE
 ON  PRIMARY 
( NAME = N'ACSWebPortalDb', FILENAME = N'C:\Program Files\Microsoft SQL Server\MSSQL16.MSSQLSERVER\MSSQL\DATA\ACSWebPortalDb.mdf' , SIZE = 8192KB , MAXSIZE = UNLIMITED, FILEGROWTH = 65536KB )
 LOG ON 
( NAME = N'ACSWebPortalDb_log', FILENAME = N'C:\Program Files\Microsoft SQL Server\MSSQL16.MSSQLSERVER\MSSQL\DATA\ACSWebPortalDb_log.ldf' , SIZE = 8192KB , MAXSIZE = 2048GB , FILEGROWTH = 65536KB )
 WITH CATALOG_COLLATION = DATABASE_DEFAULT, LEDGER = OFF
GO
ALTER DATABASE [ACSWebPortalDb] SET COMPATIBILITY_LEVEL = 160
GO
IF (1 = FULLTEXTSERVICEPROPERTY('IsFullTextInstalled'))
begin
EXEC [ACSWebPortalDb].[dbo].[sp_fulltext_database] @action = 'enable'
end
GO
ALTER DATABASE [ACSWebPortalDb] SET ANSI_NULL_DEFAULT OFF 
GO
ALTER DATABASE [ACSWebPortalDb] SET ANSI_NULLS OFF 
GO
ALTER DATABASE [ACSWebPortalDb] SET ANSI_PADDING OFF 
GO
ALTER DATABASE [ACSWebPortalDb] SET ANSI_WARNINGS OFF 
GO
ALTER DATABASE [ACSWebPortalDb] SET ARITHABORT OFF 
GO
ALTER DATABASE [ACSWebPortalDb] SET AUTO_CLOSE OFF 
GO
ALTER DATABASE [ACSWebPortalDb] SET AUTO_SHRINK OFF 
GO
ALTER DATABASE [ACSWebPortalDb] SET AUTO_UPDATE_STATISTICS ON 
GO
ALTER DATABASE [ACSWebPortalDb] SET CURSOR_CLOSE_ON_COMMIT OFF 
GO
ALTER DATABASE [ACSWebPortalDb] SET CURSOR_DEFAULT  GLOBAL 
GO
ALTER DATABASE [ACSWebPortalDb] SET CONCAT_NULL_YIELDS_NULL OFF 
GO
ALTER DATABASE [ACSWebPortalDb] SET NUMERIC_ROUNDABORT OFF 
GO
ALTER DATABASE [ACSWebPortalDb] SET QUOTED_IDENTIFIER OFF 
GO
ALTER DATABASE [ACSWebPortalDb] SET RECURSIVE_TRIGGERS OFF 
GO
ALTER DATABASE [ACSWebPortalDb] SET  DISABLE_BROKER 
GO
ALTER DATABASE [ACSWebPortalDb] SET AUTO_UPDATE_STATISTICS_ASYNC OFF 
GO
ALTER DATABASE [ACSWebPortalDb] SET DATE_CORRELATION_OPTIMIZATION OFF 
GO
ALTER DATABASE [ACSWebPortalDb] SET TRUSTWORTHY OFF 
GO
ALTER DATABASE [ACSWebPortalDb] SET ALLOW_SNAPSHOT_ISOLATION OFF 
GO
ALTER DATABASE [ACSWebPortalDb] SET PARAMETERIZATION SIMPLE 
GO
ALTER DATABASE [ACSWebPortalDb] SET READ_COMMITTED_SNAPSHOT OFF 
GO
ALTER DATABASE [ACSWebPortalDb] SET HONOR_BROKER_PRIORITY OFF 
GO
ALTER DATABASE [ACSWebPortalDb] SET RECOVERY FULL 
GO
ALTER DATABASE [ACSWebPortalDb] SET  MULTI_USER 
GO
ALTER DATABASE [ACSWebPortalDb] SET PAGE_VERIFY CHECKSUM  
GO
ALTER DATABASE [ACSWebPortalDb] SET DB_CHAINING OFF 
GO
ALTER DATABASE [ACSWebPortalDb] SET FILESTREAM( NON_TRANSACTED_ACCESS = OFF ) 
GO
ALTER DATABASE [ACSWebPortalDb] SET TARGET_RECOVERY_TIME = 60 SECONDS 
GO
ALTER DATABASE [ACSWebPortalDb] SET DELAYED_DURABILITY = DISABLED 
GO
ALTER DATABASE [ACSWebPortalDb] SET ACCELERATED_DATABASE_RECOVERY = OFF  
GO
EXEC sys.sp_db_vardecimal_storage_format N'ACSWebPortalDb', N'ON'
GO
ALTER DATABASE [ACSWebPortalDb] SET QUERY_STORE = ON
GO
ALTER DATABASE [ACSWebPortalDb] SET QUERY_STORE (OPERATION_MODE = READ_WRITE, CLEANUP_POLICY = (STALE_QUERY_THRESHOLD_DAYS = 30), DATA_FLUSH_INTERVAL_SECONDS = 900, INTERVAL_LENGTH_MINUTES = 60, MAX_STORAGE_SIZE_MB = 1000, QUERY_CAPTURE_MODE = AUTO, SIZE_BASED_CLEANUP_MODE = AUTO, MAX_PLANS_PER_QUERY = 200, WAIT_STATS_CAPTURE_MODE = ON)
GO
USE [ACSWebPortalDb]
GO
/****** Object:  Table [dbo].[__EFMigrationsHistory]    Script Date: 8/31/2024 4:23:43 PM ******/
SET ANSI_NULLS ON
GO
SET QUOTED_IDENTIFIER ON
GO
CREATE TABLE [dbo].[__EFMigrationsHistory](
	[MigrationId] [nvarchar](150) NOT NULL,
	[ProductVersion] [nvarchar](32) NOT NULL,
 CONSTRAINT [PK___EFMigrationsHistory] PRIMARY KEY CLUSTERED 
(
	[MigrationId] ASC
)WITH (PAD_INDEX = OFF, STATISTICS_NORECOMPUTE = OFF, IGNORE_DUP_KEY = OFF, ALLOW_ROW_LOCKS = ON, ALLOW_PAGE_LOCKS = ON, OPTIMIZE_FOR_SEQUENTIAL_KEY = OFF) ON [PRIMARY]
) ON [PRIMARY]
GO
/****** Object:  Table [dbo].[ClientsFeedbacks]    Script Date: 8/31/2024 4:23:43 PM ******/
SET ANSI_NULLS ON
GO
SET QUOTED_IDENTIFIER ON
GO
CREATE TABLE [dbo].[ClientsFeedbacks](
	[Id] [int] IDENTITY(1,1) NOT NULL,
	[Feedback] [nvarchar](max) NOT NULL,
	[ClientName] [nvarchar](max) NOT NULL,
	[CompanyName] [nvarchar](max) NOT NULL,
	[CompanyEmail] [nvarchar](max) NOT NULL,
	[ClientImageName] [nvarchar](max) NOT NULL,
	[CreatedAt] [datetime2](7) NOT NULL,
	[UpdatedAt] [datetime2](7) NOT NULL,
 CONSTRAINT [PK_ClientsFeedbacks] PRIMARY KEY CLUSTERED 
(
	[Id] ASC
)WITH (PAD_INDEX = OFF, STATISTICS_NORECOMPUTE = OFF, IGNORE_DUP_KEY = OFF, ALLOW_ROW_LOCKS = ON, ALLOW_PAGE_LOCKS = ON, OPTIMIZE_FOR_SEQUENTIAL_KEY = OFF) ON [PRIMARY]
) ON [PRIMARY] TEXTIMAGE_ON [PRIMARY]
GO
/****** Object:  Table [dbo].[Company]    Script Date: 8/31/2024 4:23:43 PM ******/
SET ANSI_NULLS ON
GO
SET QUOTED_IDENTIFIER ON
GO
CREATE TABLE [dbo].[Company](
	[Id] [int] IDENTITY(1,1) NOT NULL,
	[CompanyName] [nvarchar](20) NOT NULL,
	[Details] [nvarchar](500) NOT NULL,
	[Address] [nvarchar](100) NOT NULL,
	[Status] [bit] NOT NULL,
	[CompanyImage] [nvarchar](20) NOT NULL,
	[CreatedAt] [datetime2](7) NOT NULL,
 CONSTRAINT [PK_Company] PRIMARY KEY CLUSTERED 
(
	[Id] ASC
)WITH (PAD_INDEX = OFF, STATISTICS_NORECOMPUTE = OFF, IGNORE_DUP_KEY = OFF, ALLOW_ROW_LOCKS = ON, ALLOW_PAGE_LOCKS = ON, OPTIMIZE_FOR_SEQUENTIAL_KEY = OFF) ON [PRIMARY]
) ON [PRIMARY]
GO
/****** Object:  Table [dbo].[JobCategories]    Script Date: 8/31/2024 4:23:43 PM ******/
SET ANSI_NULLS ON
GO
SET QUOTED_IDENTIFIER ON
GO
CREATE TABLE [dbo].[JobCategories](
	[Id] [int] IDENTITY(1,1) NOT NULL,
	[Name] [nvarchar](50) NOT NULL,
	[Description] [nvarchar](255) NULL,
	[Status] [bit] NOT NULL,
	[CreatedAt] [datetime2](7) NOT NULL,
	[CreatedOn] [datetime2](7) NOT NULL,
	[IconClass] [nvarchar](50) NULL,
 CONSTRAINT [PK_JobCategories] PRIMARY KEY CLUSTERED 
(
	[Id] ASC
)WITH (PAD_INDEX = OFF, STATISTICS_NORECOMPUTE = OFF, IGNORE_DUP_KEY = OFF, ALLOW_ROW_LOCKS = ON, ALLOW_PAGE_LOCKS = ON, OPTIMIZE_FOR_SEQUENTIAL_KEY = OFF) ON [PRIMARY]
) ON [PRIMARY]
GO
/****** Object:  Table [dbo].[JobDetails]    Script Date: 8/31/2024 4:23:43 PM ******/
SET ANSI_NULLS ON
GO
SET QUOTED_IDENTIFIER ON
GO
CREATE TABLE [dbo].[JobDetails](
	[Id] [int] IDENTITY(1,1) NOT NULL,
	[JobId] [int] NOT NULL,
	[CompanyId] [int] NOT NULL,
	[Title] [nvarchar](20) NOT NULL,
	[JobDescription] [nvarchar](1000) NOT NULL,
	[ResponsibilityDetails] [nvarchar](200) NOT NULL,
	[ResponsibilityId] [int] NOT NULL,
	[QualificationsDetails] [nvarchar](200) NOT NULL,
	[QualificationId] [int] NOT NULL,
	[Status] [bit] NOT NULL,
	[Lastdate] [datetime2](7) NOT NULL,
	[CreatedAt] [datetime2](7) NOT NULL,
	[LocationId] [int] NOT NULL,
 CONSTRAINT [PK_JobDetails] PRIMARY KEY CLUSTERED 
(
	[Id] ASC
)WITH (PAD_INDEX = OFF, STATISTICS_NORECOMPUTE = OFF, IGNORE_DUP_KEY = OFF, ALLOW_ROW_LOCKS = ON, ALLOW_PAGE_LOCKS = ON, OPTIMIZE_FOR_SEQUENTIAL_KEY = OFF) ON [PRIMARY]
) ON [PRIMARY]
GO
/****** Object:  Table [dbo].[JobLocations]    Script Date: 8/31/2024 4:23:43 PM ******/
SET ANSI_NULLS ON
GO
SET QUOTED_IDENTIFIER ON
GO
CREATE TABLE [dbo].[JobLocations](
	[Id] [int] IDENTITY(1,1) NOT NULL,
	[Name] [nvarchar](20) NOT NULL,
	[Description] [nvarchar](255) NULL,
	[Status] [bit] NOT NULL,
	[CreatedAt] [datetime2](7) NOT NULL,
	[UpdatedOn] [datetime2](7) NOT NULL,
 CONSTRAINT [PK_JobLocations] PRIMARY KEY CLUSTERED 
(
	[Id] ASC
)WITH (PAD_INDEX = OFF, STATISTICS_NORECOMPUTE = OFF, IGNORE_DUP_KEY = OFF, ALLOW_ROW_LOCKS = ON, ALLOW_PAGE_LOCKS = ON, OPTIMIZE_FOR_SEQUENTIAL_KEY = OFF) ON [PRIMARY]
) ON [PRIMARY]
GO
/****** Object:  Table [dbo].[JobTypes]    Script Date: 8/31/2024 4:23:43 PM ******/
SET ANSI_NULLS ON
GO
SET QUOTED_IDENTIFIER ON
GO
CREATE TABLE [dbo].[JobTypes](
	[Id] [int] IDENTITY(1,1) NOT NULL,
	[Title] [nvarchar](20) NOT NULL,
	[Status] [bit] NOT NULL,
	[CreatedAt] [datetime2](7) NOT NULL,
 CONSTRAINT [PK_JobTypes] PRIMARY KEY CLUSTERED 
(
	[Id] ASC
)WITH (PAD_INDEX = OFF, STATISTICS_NORECOMPUTE = OFF, IGNORE_DUP_KEY = OFF, ALLOW_ROW_LOCKS = ON, ALLOW_PAGE_LOCKS = ON, OPTIMIZE_FOR_SEQUENTIAL_KEY = OFF) ON [PRIMARY]
) ON [PRIMARY]
GO
/****** Object:  Table [dbo].[QualificationDetails]    Script Date: 8/31/2024 4:23:43 PM ******/
SET ANSI_NULLS ON
GO
SET QUOTED_IDENTIFIER ON
GO
CREATE TABLE [dbo].[QualificationDetails](
	[Id] [int] IDENTITY(1,1) NOT NULL,
	[QualificationId] [int] NOT NULL,
	[Title] [nvarchar](100) NOT NULL,
 CONSTRAINT [PK_QualificationDetails] PRIMARY KEY CLUSTERED 
(
	[Id] ASC
)WITH (PAD_INDEX = OFF, STATISTICS_NORECOMPUTE = OFF, IGNORE_DUP_KEY = OFF, ALLOW_ROW_LOCKS = ON, ALLOW_PAGE_LOCKS = ON, OPTIMIZE_FOR_SEQUENTIAL_KEY = OFF) ON [PRIMARY]
) ON [PRIMARY]
GO
/****** Object:  Table [dbo].[Qualifications]    Script Date: 8/31/2024 4:23:43 PM ******/
SET ANSI_NULLS ON
GO
SET QUOTED_IDENTIFIER ON
GO
CREATE TABLE [dbo].[Qualifications](
	[Id] [int] IDENTITY(1,1) NOT NULL,
	[Status] [bit] NOT NULL,
 CONSTRAINT [PK_Qualifications] PRIMARY KEY CLUSTERED 
(
	[Id] ASC
)WITH (PAD_INDEX = OFF, STATISTICS_NORECOMPUTE = OFF, IGNORE_DUP_KEY = OFF, ALLOW_ROW_LOCKS = ON, ALLOW_PAGE_LOCKS = ON, OPTIMIZE_FOR_SEQUENTIAL_KEY = OFF) ON [PRIMARY]
) ON [PRIMARY]
GO
/****** Object:  Table [dbo].[ResponsibilityDetails]    Script Date: 8/31/2024 4:23:43 PM ******/
SET ANSI_NULLS ON
GO
SET QUOTED_IDENTIFIER ON
GO
CREATE TABLE [dbo].[ResponsibilityDetails](
	[Id] [int] IDENTITY(1,1) NOT NULL,
	[ResponsibilityId] [int] NOT NULL,
	[Title] [nvarchar](100) NOT NULL,
 CONSTRAINT [PK_ResponsibilityDetails] PRIMARY KEY CLUSTERED 
(
	[Id] ASC
)WITH (PAD_INDEX = OFF, STATISTICS_NORECOMPUTE = OFF, IGNORE_DUP_KEY = OFF, ALLOW_ROW_LOCKS = ON, ALLOW_PAGE_LOCKS = ON, OPTIMIZE_FOR_SEQUENTIAL_KEY = OFF) ON [PRIMARY]
) ON [PRIMARY]
GO
/****** Object:  Table [dbo].[Responsibilitys]    Script Date: 8/31/2024 4:23:43 PM ******/
SET ANSI_NULLS ON
GO
SET QUOTED_IDENTIFIER ON
GO
CREATE TABLE [dbo].[Responsibilitys](
	[Id] [int] IDENTITY(1,1) NOT NULL,
	[Status] [bit] NOT NULL,
 CONSTRAINT [PK_Responsibilitys] PRIMARY KEY CLUSTERED 
(
	[Id] ASC
)WITH (PAD_INDEX = OFF, STATISTICS_NORECOMPUTE = OFF, IGNORE_DUP_KEY = OFF, ALLOW_ROW_LOCKS = ON, ALLOW_PAGE_LOCKS = ON, OPTIMIZE_FOR_SEQUENTIAL_KEY = OFF) ON [PRIMARY]
) ON [PRIMARY]
GO
INSERT [dbo].[__EFMigrationsHistory] ([MigrationId], [ProductVersion]) VALUES (N'20240728133426_efmigration', N'8.0.7')
INSERT [dbo].[__EFMigrationsHistory] ([MigrationId], [ProductVersion]) VALUES (N'20240731044329_addJobLocationTable', N'8.0.7')
INSERT [dbo].[__EFMigrationsHistory] ([MigrationId], [ProductVersion]) VALUES (N'20240731044431_addJobLocationTable1', N'8.0.7')
INSERT [dbo].[__EFMigrationsHistory] ([MigrationId], [ProductVersion]) VALUES (N'20240804105921_addClientsFeedback', N'8.0.7')
INSERT [dbo].[__EFMigrationsHistory] ([MigrationId], [ProductVersion]) VALUES (N'20240807035537_addJobs', N'8.0.7')
GO
SET IDENTITY_INSERT [dbo].[ClientsFeedbacks] ON 

INSERT [dbo].[ClientsFeedbacks] ([Id], [Feedback], [ClientName], [CompanyName], [CompanyEmail], [ClientImageName], [CreatedAt], [UpdatedAt]) VALUES (1, N'Efficient recruitment process with high-quality candidate matches, though initial screening could be faster.', N'Anita Singh', N'HCL', N'anita@hcl.com', N'testimonial-1.jpg', CAST(N'2024-08-04T00:00:00.0000000' AS DateTime2), CAST(N'2024-08-04T00:00:00.0000000' AS DateTime2))
INSERT [dbo].[ClientsFeedbacks] ([Id], [Feedback], [ClientName], [CompanyName], [CompanyEmail], [ClientImageName], [CreatedAt], [UpdatedAt]) VALUES (2, N'Provided excellent candidates who met our requirements, but their services were on the pricier side.', N'Roopali', N'Wipro', N'roopali@wipro.com', N'testimonial-2.jpg', CAST(N'2024-08-04T00:00:00.0000000' AS DateTime2), CAST(N'2024-08-04T00:00:00.0000000' AS DateTime2))
INSERT [dbo].[ClientsFeedbacks] ([Id], [Feedback], [ClientName], [CompanyName], [CompanyEmail], [ClientImageName], [CreatedAt], [UpdatedAt]) VALUES (3, N'Outstanding communication and responsiveness, though initial consultations could be more detailed.', N'Anjali Pal', N'TCS', N'anjali@tc.com', N'testimonial-3.jpg', CAST(N'2024-08-04T00:00:00.0000000' AS DateTime2), CAST(N'2024-08-04T00:00:00.0000000' AS DateTime2))
INSERT [dbo].[ClientsFeedbacks] ([Id], [Feedback], [ClientName], [CompanyName], [CompanyEmail], [ClientImageName], [CreatedAt], [UpdatedAt]) VALUES (4, N'Customized approach suited our needs well, but the process took longer than expected.', N'Adley', N'Infosys', N'Adley@infosys.com', N'testimonial-4.jpg', CAST(N'2024-08-04T00:00:00.0000000' AS DateTime2), CAST(N'2024-08-04T00:00:00.0000000' AS DateTime2))
SET IDENTITY_INSERT [dbo].[ClientsFeedbacks] OFF
GO
SET IDENTITY_INSERT [dbo].[Company] ON 

INSERT [dbo].[Company] ([Id], [CompanyName], [Details], [Address], [Status], [CompanyImage], [CreatedAt]) VALUES (1, N'TechCom', N'TechCom is an Indian multinational information technology (IT) services and consulting company headquartered in Mumbai. It is a part of the Tata Group and operates in 150 locations across 46 countries. In March 2024', N'C 21, Patel Nagar Ghaziabad U.P', 1, N'com-logo-1.jpg', CAST(N'2024-08-07T00:00:00.0000000' AS DateTime2))
INSERT [dbo].[Company] ([Id], [CompanyName], [Details], [Address], [Status], [CompanyImage], [CreatedAt]) VALUES (3, N'International Hearts', N'International Hearts is an Indian multinational information technology (IT) services and consulting company headquartered in Mumbai. It is a part of the Tata Group and operates in 150 locations across 46 countries. In March 2024', N'A 58, Rajnagar Ghaziabad U.P', 1, N'com-logo-2.jpg', CAST(N'2024-08-07T00:00:00.0000000' AS DateTime2))
INSERT [dbo].[Company] ([Id], [CompanyName], [Details], [Address], [Status], [CompanyImage], [CreatedAt]) VALUES (4, N'DataExchange', N'DataExchange is an Indian multinational information technology (IT) services and consulting company headquartered in Mumbai. It is a part of the Tata Group and operates in 150 locations across 46 countries. In March 2024', N' Mumbai, India', 1, N'com-logo-3.jpg', CAST(N'2024-08-07T00:00:00.0000000' AS DateTime2))
INSERT [dbo].[Company] ([Id], [CompanyName], [Details], [Address], [Status], [CompanyImage], [CreatedAt]) VALUES (5, N'Fuzion', N'Fuzion is an Indian multinational information technology (IT) services and consulting company headquartered in Mumbai. It is a part of the Tata Group and operates in 150 locations across 46 countries. In March 2024', N'Mumbai, India', 1, N'com-logo-4.jpg', CAST(N'2024-08-07T00:00:00.0000000' AS DateTime2))
INSERT [dbo].[Company] ([Id], [CompanyName], [Details], [Address], [Status], [CompanyImage], [CreatedAt]) VALUES (6, N'BluePhale', N'BluePhale is an Indian multinational information technology (IT) services and consulting company headquartered in Mumbai. It is a part of the Tata Group and operates in 150 locations across 46 countries. In March 2024', N'Mumbai, India', 1, N'com-logo-5.jpg', CAST(N'2024-08-07T00:00:00.0000000' AS DateTime2))
SET IDENTITY_INSERT [dbo].[Company] OFF
GO
SET IDENTITY_INSERT [dbo].[JobCategories] ON 

INSERT [dbo].[JobCategories] ([Id], [Name], [Description], [Status], [CreatedAt], [CreatedOn], [IconClass]) VALUES (3, N'IT and Software Development', N'Software Engineer,
Web Developer,
Data Scientist,
Network Administrator', 1, CAST(N'2024-07-29T00:00:00.0000000' AS DateTime2), CAST(N'2024-07-29T00:00:00.0000000' AS DateTime2), N'fa-laptop-code')
INSERT [dbo].[JobCategories] ([Id], [Name], [Description], [Status], [CreatedAt], [CreatedOn], [IconClass]) VALUES (4, N'Sales and Marketing', N'Sales Manager,
Digital Marketing Specialist,
Brand Manager,
Business Development Executive', 1, CAST(N'2024-07-29T00:00:00.0000000' AS DateTime2), CAST(N'2024-07-29T00:00:00.0000000' AS DateTime2), N'fa-mail-bulk        ')
INSERT [dbo].[JobCategories] ([Id], [Name], [Description], [Status], [CreatedAt], [CreatedOn], [IconClass]) VALUES (5, N'Finance and Accounting', N'Accountant,
Financial Analyst,
Tax Consultant,
Internal Auditor', 1, CAST(N'2024-07-29T00:00:00.0000000' AS DateTime2), CAST(N'2024-07-29T00:00:00.0000000' AS DateTime2), N'fa-dollar-sign      ')
INSERT [dbo].[JobCategories] ([Id], [Name], [Description], [Status], [CreatedAt], [CreatedOn], [IconClass]) VALUES (6, N'Human Resources', N'HR Manager,
Recruiter,
Training and Development Manager,
Compensation and Benefits Specialist', 1, CAST(N'2024-07-29T00:00:00.0000000' AS DateTime2), CAST(N'2024-07-29T00:00:00.0000000' AS DateTime2), N'fa-user-tie         ')
INSERT [dbo].[JobCategories] ([Id], [Name], [Description], [Status], [CreatedAt], [CreatedOn], [IconClass]) VALUES (7, N'Customer Service', N'Customer Support Executive,
Call Center Agent,
Technical Support Specialist,
Client Relationship Manager', 1, CAST(N'2024-07-29T00:00:00.0000000' AS DateTime2), CAST(N'2024-07-29T00:00:00.0000000' AS DateTime2), N'fa-headset          ')
INSERT [dbo].[JobCategories] ([Id], [Name], [Description], [Status], [CreatedAt], [CreatedOn], [IconClass]) VALUES (9, N'Engineering and Manufacturing', N'Mechanical Engineer,
Electrical Engineer,
Civil Engineer, 
Computer Science Engineer', 1, CAST(N'2024-07-29T00:00:00.0000000' AS DateTime2), CAST(N'2024-07-29T00:00:00.0000000' AS DateTime2), N'fa-industry         ')
INSERT [dbo].[JobCategories] ([Id], [Name], [Description], [Status], [CreatedAt], [CreatedOn], [IconClass]) VALUES (10, N'Construction and Real Estate', NULL, 1, CAST(N'2024-07-29T00:00:00.0000000' AS DateTime2), CAST(N'2024-07-29T00:00:00.0000000' AS DateTime2), N'fa-hard-hat         ')
INSERT [dbo].[JobCategories] ([Id], [Name], [Description], [Status], [CreatedAt], [CreatedOn], [IconClass]) VALUES (11, N'Retail and Merchandising', NULL, 1, CAST(N'2024-07-29T00:00:00.0000000' AS DateTime2), CAST(N'2024-07-29T00:00:00.0000000' AS DateTime2), N'fa-hands-helping    ')
INSERT [dbo].[JobCategories] ([Id], [Name], [Description], [Status], [CreatedAt], [CreatedOn], [IconClass]) VALUES (12, N'Banking and Financial Services', NULL, 1, CAST(N'2024-07-29T00:00:00.0000000' AS DateTime2), CAST(N'2024-07-29T00:00:00.0000000' AS DateTime2), N'fa-tasks            ')
INSERT [dbo].[JobCategories] ([Id], [Name], [Description], [Status], [CreatedAt], [CreatedOn], [IconClass]) VALUES (13, N'Healthcare', NULL, 1, CAST(N'2024-07-29T00:00:00.0000000' AS DateTime2), CAST(N'2024-07-29T00:00:00.0000000' AS DateTime2), N'fa-heartbeat        ')
INSERT [dbo].[JobCategories] ([Id], [Name], [Description], [Status], [CreatedAt], [CreatedOn], [IconClass]) VALUES (14, N'Education and Training', NULL, 1, CAST(N'2024-07-29T00:00:00.0000000' AS DateTime2), CAST(N'2024-07-29T00:00:00.0000000' AS DateTime2), N'fa-book-reader      ')
INSERT [dbo].[JobCategories] ([Id], [Name], [Description], [Status], [CreatedAt], [CreatedOn], [IconClass]) VALUES (16, N'Hospitality and Travel', NULL, 1, CAST(N'2024-07-29T00:00:00.0000000' AS DateTime2), CAST(N'2024-07-29T00:00:00.0000000' AS DateTime2), N'fa-hotel            ')
INSERT [dbo].[JobCategories] ([Id], [Name], [Description], [Status], [CreatedAt], [CreatedOn], [IconClass]) VALUES (17, N'Legal', NULL, 1, CAST(N'2024-07-29T00:00:00.0000000' AS DateTime2), CAST(N'2024-07-29T00:00:00.0000000' AS DateTime2), N'fa-gavel            ')
INSERT [dbo].[JobCategories] ([Id], [Name], [Description], [Status], [CreatedAt], [CreatedOn], [IconClass]) VALUES (18, N'Media and Entertainment', NULL, 1, CAST(N'2024-07-29T00:00:00.0000000' AS DateTime2), CAST(N'2024-07-29T00:00:00.0000000' AS DateTime2), N'fa-camera           ')
INSERT [dbo].[JobCategories] ([Id], [Name], [Description], [Status], [CreatedAt], [CreatedOn], [IconClass]) VALUES (19, N'Administration', NULL, 1, CAST(N'2024-07-29T00:00:00.0000000' AS DateTime2), CAST(N'2024-07-29T00:00:00.0000000' AS DateTime2), N'fa-chart-line       ')
INSERT [dbo].[JobCategories] ([Id], [Name], [Description], [Status], [CreatedAt], [CreatedOn], [IconClass]) VALUES (20, N'Design & Creative', NULL, 1, CAST(N'2024-07-29T00:00:00.0000000' AS DateTime2), CAST(N'2024-07-29T00:00:00.0000000' AS DateTime2), N'fa-drafting-compass ')
INSERT [dbo].[JobCategories] ([Id], [Name], [Description], [Status], [CreatedAt], [CreatedOn], [IconClass]) VALUES (21, N'Others', NULL, 1, CAST(N'2024-07-29T00:00:00.0000000' AS DateTime2), CAST(N'2024-07-29T00:00:00.0000000' AS DateTime2), N'fa-lightbulb        ')
SET IDENTITY_INSERT [dbo].[JobCategories] OFF
GO
SET IDENTITY_INSERT [dbo].[JobDetails] ON 

INSERT [dbo].[JobDetails] ([Id], [JobId], [CompanyId], [Title], [JobDescription], [ResponsibilityDetails], [ResponsibilityId], [QualificationsDetails], [QualificationId], [Status], [Lastdate], [CreatedAt], [LocationId]) VALUES (1, 1, 1, N'Data Entry Operator', N'Data Entry Operator


Typing Speed : 50 Words/Minute.', N'Required good communication skills

Should identify errors if any and correct them.', 1, N'An Urgent Requirement For graduates

Locals from Noida / Ghaziabad / East Delhi are only preferred', 1, 1, CAST(N'2024-07-30T00:00:00.0000000' AS DateTime2), CAST(N'2024-07-08T00:00:00.0000000' AS DateTime2), 1)
INSERT [dbo].[JobDetails] ([Id], [JobId], [CompanyId], [Title], [JobDescription], [ResponsibilityDetails], [ResponsibilityId], [QualificationsDetails], [QualificationId], [Status], [Lastdate], [CreatedAt], [LocationId]) VALUES (2, 2, 2, N'Marketing Manager', N'Dolor justo tempor duo ipsum accusam rebum gubergren erat. Elitr stet dolor vero clita labore gubergren. Kasd sed ipsum elitr clita rebum ut sea diam tempor. Sadipscing nonumy vero labore invidunt dolor sed, eirmod dolore amet aliquyam consetetur lorem, amet elitr clita et sed consetetur dolore accusam. Vero kasd nonumy justo rebum stet. Ipsum amet sed lorem sea magna. Rebum vero dolores dolores elitr vero dolores magna, stet sea sadipscing stet et. Est voluptua et sanctus at sanctus erat vero sed sed, amet duo no diam clita rebum duo, accusam tempor takimata clita stet nonumy rebum est invidunt stet, dolor.', N'Magna et elitr diam sed lorem. Diam diam stet erat no est est. Accusam sed lorem stet voluptua sit sit at stet consetetur, takimata at diam kasd gubergren elitr dolor', 1, N'Magna et elitr diam sed lorem. Diam diam stet erat no est est. Accusam sed lorem stet voluptua sit sit at stet consetetur, takimata at diam kasd gubergren elitr dolor', 1, 1, CAST(N'2024-07-30T00:00:00.0000000' AS DateTime2), CAST(N'2024-07-08T00:00:00.0000000' AS DateTime2), 2)
INSERT [dbo].[JobDetails] ([Id], [JobId], [CompanyId], [Title], [JobDescription], [ResponsibilityDetails], [ResponsibilityId], [QualificationsDetails], [QualificationId], [Status], [Lastdate], [CreatedAt], [LocationId]) VALUES (3, 3, 3, N'Software Engineer', N'Dolor justo tempor duo ipsum accusam rebum gubergren erat. Elitr stet dolor vero clita labore gubergren. Kasd sed ipsum elitr clita rebum ut sea diam tempor. Sadipscing nonumy vero labore invidunt dolor sed, eirmod dolore amet aliquyam consetetur lorem, amet elitr clita et sed consetetur dolore accusam. Vero kasd nonumy justo rebum stet. Ipsum amet sed lorem sea magna. Rebum vero dolores dolores elitr vero dolores magna, stet sea sadipscing stet et. Est voluptua et sanctus at sanctus erat vero sed sed, amet duo no diam clita rebum duo, accusam tempor takimata clita stet nonumy rebum est invidunt stet, dolor.', N'Magna et elitr diam sed lorem. Diam diam stet erat no est est. Accusam sed lorem stet voluptua sit sit at stet consetetur, takimata at diam kasd gubergren elitr dolor', 1, N'Magna et elitr diam sed lorem. Diam diam stet erat no est est. Accusam sed lorem stet voluptua sit sit at stet consetetur, takimata at diam kasd gubergren elitr dolor', 1, 1, CAST(N'2024-07-30T00:00:00.0000000' AS DateTime2), CAST(N'2024-07-08T00:00:00.0000000' AS DateTime2), 3)
INSERT [dbo].[JobDetails] ([Id], [JobId], [CompanyId], [Title], [JobDescription], [ResponsibilityDetails], [ResponsibilityId], [QualificationsDetails], [QualificationId], [Status], [Lastdate], [CreatedAt], [LocationId]) VALUES (4, 4, 2, N'Product Designer', N'Dolor justo tempor duo ipsum accusam rebum gubergren erat. Elitr stet dolor vero clita labore gubergren. Kasd sed ipsum elitr clita rebum ut sea diam tempor. Sadipscing nonumy vero labore invidunt dolor sed, eirmod dolore amet aliquyam consetetur lorem, amet elitr clita et sed consetetur dolore accusam. Vero kasd nonumy justo rebum stet. Ipsum amet sed lorem sea magna. Rebum vero dolores dolores elitr vero dolores magna, stet sea sadipscing stet et. Est voluptua et sanctus at sanctus erat vero sed sed, amet duo no diam clita rebum duo, accusam tempor takimata clita stet nonumy rebum est invidunt stet, dolor.', N'Magna et elitr diam sed lorem. Diam diam stet erat no est est. Accusam sed lorem stet voluptua sit sit at stet consetetur, takimata at diam kasd gubergren elitr dolor', 1, N'Magna et elitr diam sed lorem. Diam diam stet erat no est est. Accusam sed lorem stet voluptua sit sit at stet consetetur, takimata at diam kasd gubergren elitr dolor', 1, 1, CAST(N'2024-07-30T00:00:00.0000000' AS DateTime2), CAST(N'2024-07-08T00:00:00.0000000' AS DateTime2), 4)
INSERT [dbo].[JobDetails] ([Id], [JobId], [CompanyId], [Title], [JobDescription], [ResponsibilityDetails], [ResponsibilityId], [QualificationsDetails], [QualificationId], [Status], [Lastdate], [CreatedAt], [LocationId]) VALUES (5, 5, 4, N'Creative Director', N'Dolor justo tempor duo ipsum accusam rebum gubergren erat. Elitr stet dolor vero clita labore gubergren. Kasd sed ipsum elitr clita rebum ut sea diam tempor. Sadipscing nonumy vero labore invidunt dolor sed, eirmod dolore amet aliquyam consetetur lorem, amet elitr clita et sed consetetur dolore accusam. Vero kasd nonumy justo rebum stet. Ipsum amet sed lorem sea magna. Rebum vero dolores dolores elitr vero dolores magna, stet sea sadipscing stet et. Est voluptua et sanctus at sanctus erat vero sed sed, amet duo no diam clita rebum duo, accusam tempor takimata clita stet nonumy rebum est invidunt stet, dolor.', N'Magna et elitr diam sed lorem. Diam diam stet erat no est est. Accusam sed lorem stet voluptua sit sit at stet consetetur, takimata at diam kasd gubergren elitr dolor', 1, N'Magna et elitr diam sed lorem. Diam diam stet erat no est est. Accusam sed lorem stet voluptua sit sit at stet consetetur, takimata at diam kasd gubergren elitr dolor', 1, 1, CAST(N'2024-07-30T00:00:00.0000000' AS DateTime2), CAST(N'2024-07-30T00:00:00.0000000' AS DateTime2), 3)
INSERT [dbo].[JobDetails] ([Id], [JobId], [CompanyId], [Title], [JobDescription], [ResponsibilityDetails], [ResponsibilityId], [QualificationsDetails], [QualificationId], [Status], [Lastdate], [CreatedAt], [LocationId]) VALUES (6, 6, 3, N'Wordpress Developer', N'Dolor justo tempor duo ipsum accusam rebum gubergren erat. Elitr stet dolor vero clita labore gubergren. Kasd sed ipsum elitr clita rebum ut sea diam tempor. Sadipscing nonumy vero labore invidunt dolor sed, eirmod dolore amet aliquyam consetetur lorem, amet elitr clita et sed consetetur dolore accusam. Vero kasd nonumy justo rebum stet. Ipsum amet sed lorem sea magna. Rebum vero dolores dolores elitr vero dolores magna, stet sea sadipscing stet et. Est voluptua et sanctus at sanctus erat vero sed sed, amet duo no diam clita rebum duo, accusam tempor takimata clita stet nonumy rebum est invidunt stet, dolor.', N'Magna et elitr diam sed lorem. Diam diam stet erat no est est. Accusam sed lorem stet voluptua sit sit at stet consetetur, takimata at diam kasd gubergren elitr dolor', 1, N'Magna et elitr diam sed lorem. Diam diam stet erat no est est. Accusam sed lorem stet voluptua sit sit at stet consetetur, takimata at diam kasd gubergren elitr dolor', 1, 1, CAST(N'2024-07-30T00:00:00.0000000' AS DateTime2), CAST(N'2024-07-30T00:00:00.0000000' AS DateTime2), 2)
SET IDENTITY_INSERT [dbo].[JobDetails] OFF
GO
SET IDENTITY_INSERT [dbo].[JobLocations] ON 

INSERT [dbo].[JobLocations] ([Id], [Name], [Description], [Status], [CreatedAt], [UpdatedOn]) VALUES (1, N'Noida', N'UP', 1, CAST(N'2024-07-31T00:00:00.0000000' AS DateTime2), CAST(N'2024-07-31T00:00:00.0000000' AS DateTime2))
INSERT [dbo].[JobLocations] ([Id], [Name], [Description], [Status], [CreatedAt], [UpdatedOn]) VALUES (2, N'Greater Noida', N'UP', 1, CAST(N'2024-07-31T00:00:00.0000000' AS DateTime2), CAST(N'2024-07-31T00:00:00.0000000' AS DateTime2))
INSERT [dbo].[JobLocations] ([Id], [Name], [Description], [Status], [CreatedAt], [UpdatedOn]) VALUES (3, N'Ghaziabad', N'UP', 1, CAST(N'2024-07-31T00:00:00.0000000' AS DateTime2), CAST(N'2024-07-31T00:00:00.0000000' AS DateTime2))
INSERT [dbo].[JobLocations] ([Id], [Name], [Description], [Status], [CreatedAt], [UpdatedOn]) VALUES (4, N'Delhi', N'Delhi', 1, CAST(N'2024-07-31T00:00:00.0000000' AS DateTime2), CAST(N'2024-07-31T00:00:00.0000000' AS DateTime2))
SET IDENTITY_INSERT [dbo].[JobLocations] OFF
GO
SET IDENTITY_INSERT [dbo].[JobTypes] ON 

INSERT [dbo].[JobTypes] ([Id], [Title], [Status], [CreatedAt]) VALUES (1, N'Full Time', 1, CAST(N'2024-08-07T00:00:00.0000000' AS DateTime2))
INSERT [dbo].[JobTypes] ([Id], [Title], [Status], [CreatedAt]) VALUES (2, N'Part Time', 1, CAST(N'2024-08-07T00:00:00.0000000' AS DateTime2))
SET IDENTITY_INSERT [dbo].[JobTypes] OFF
GO
SET IDENTITY_INSERT [dbo].[QualificationDetails] ON 

INSERT [dbo].[QualificationDetails] ([Id], [QualificationId], [Title]) VALUES (1, 1, N'UG: Any Graduate')
INSERT [dbo].[QualificationDetails] ([Id], [QualificationId], [Title]) VALUES (2, 1, N'PG: Any Postgraduate')
SET IDENTITY_INSERT [dbo].[QualificationDetails] OFF
GO
SET IDENTITY_INSERT [dbo].[Qualifications] ON 

INSERT [dbo].[Qualifications] ([Id], [Status]) VALUES (1, 1)
INSERT [dbo].[Qualifications] ([Id], [Status]) VALUES (2, 1)
INSERT [dbo].[Qualifications] ([Id], [Status]) VALUES (3, 1)
SET IDENTITY_INSERT [dbo].[Qualifications] OFF
GO
SET IDENTITY_INSERT [dbo].[ResponsibilityDetails] ON 

INSERT [dbo].[ResponsibilityDetails] ([Id], [ResponsibilityId], [Title]) VALUES (1, 1, N'Content, Editorial & Journalism')
INSERT [dbo].[ResponsibilityDetails] ([Id], [ResponsibilityId], [Title]) VALUES (2, 1, N'Editing (Print / Online / Electronic)')
INSERT [dbo].[ResponsibilityDetails] ([Id], [ResponsibilityId], [Title]) VALUES (3, 1, N'Printing & Publishing')
INSERT [dbo].[ResponsibilityDetails] ([Id], [ResponsibilityId], [Title]) VALUES (4, 1, N'Editing (Print / Online / Electronic)')
SET IDENTITY_INSERT [dbo].[ResponsibilityDetails] OFF
GO
SET IDENTITY_INSERT [dbo].[Responsibilitys] ON 

INSERT [dbo].[Responsibilitys] ([Id], [Status]) VALUES (1, 1)
INSERT [dbo].[Responsibilitys] ([Id], [Status]) VALUES (2, 1)
INSERT [dbo].[Responsibilitys] ([Id], [Status]) VALUES (3, 1)
SET IDENTITY_INSERT [dbo].[Responsibilitys] OFF
GO
USE [master]
GO
ALTER DATABASE [ACSWebPortalDb] SET  READ_WRITE 
GO
