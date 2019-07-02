---
title: サンプルの実装 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cd788fd3-b070-40d5-a3d3-ac8e5208cc47
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ca5f7a6d3561e8217a3eebca16b48644a56238da
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65377354"
---
# <a name="implementing-the-sample"></a><span data-ttu-id="1cdce-102">サンプルの実装</span><span class="sxs-lookup"><span data-stu-id="1cdce-102">Implementing the Sample</span></span>
<span data-ttu-id="1cdce-103">サンプルを実装するには、ように進めます。</span><span class="sxs-lookup"><span data-stu-id="1cdce-103">To implement the sample, proceed as follows:</span></span>  
  
1.  <span data-ttu-id="1cdce-104">SWIFT スキーマの新しいフォルダーを作成 (\<DocumentSchemaLocation\>ユーティリティの構文で)。</span><span class="sxs-lookup"><span data-stu-id="1cdce-104">Create a new folder for SWIFT schemas (\<DocumentSchemaLocation\> in the utility syntax).</span></span> <span data-ttu-id="1cdce-105">InfoPath フォームの作成/変更する予定のすべてのスキーマは、ユーティリティを実行するときに、このフォルダーに配置する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1cdce-105">All schemas for which you are going to create/modify the InfoPath forms must be located in this folder when you execute the utility.</span></span>  
  
2.  <span data-ttu-id="1cdce-106">MT メッセージの InfoPath フォームを生成している場合、コピー **SWIFT ベース Types.xsd**と **SWIFT 共通データ Types.xsd**から **\<ドライブ:\> \Program Files\Microsoft BizTalk Accelerator for SWIFT\<メッセージ パック バージョン\>メッセージ Pack\SWIFT Messages\A4SWIFT-SRG\<メッセージ パック バージョン\>\Base スキーマ**フォルダーにします。SWIFT スキーマ用に作成します。</span><span class="sxs-lookup"><span data-stu-id="1cdce-106">If you are generating InfoPath forms for MT messages then copy **SWIFT Base Types.xsd** and **SWIFT Common Data Types.xsd** from **\<drive :\> \Program Files\Microsoft BizTalk Accelerator for SWIFT \<Message Pack Version\> Message Pack\SWIFT Messages\A4SWIFT-SRG\<Message Pack Version\>\Base Schemas** into the folder that you created for SWIFT schemas.</span></span>  
  
3.  <span data-ttu-id="1cdce-107">手順 1. で SWIFT スキーマ用に作成したフォルダーに InfoPath フォームを作成する予定のすべてのスキーマをコピーします。</span><span class="sxs-lookup"><span data-stu-id="1cdce-107">Copy all schemas for which you are going to create InfoPath forms into the folder that you created for SWIFT schemas in Step 1.</span></span>  
  
4.  <span data-ttu-id="1cdce-108">作成または作成した InfoPath フォーム テンプレート ソリューション ファイルを保存するフォルダーを指定 (\<DestinationFolderPath\>ユーティリティの構文で)。</span><span class="sxs-lookup"><span data-stu-id="1cdce-108">Create or designate a folder to hold the created InfoPath form template solution files (\<DestinationFolderPath\> in the utility syntax).</span></span> <span data-ttu-id="1cdce-109">出力フォルダーを作成しない場合、ユーティリティで作成されます、同じパスと名前、コマンドラインで渡すこと。</span><span class="sxs-lookup"><span data-stu-id="1cdce-109">If you do not create the output folder, the utility will create the same with path and name that you pass on the command line.</span></span>  
  
5.  <span data-ttu-id="1cdce-110">[オプション]-テキスト ファイルを作成\<NameOfFileContainingSchemaList\> InfoPath フォームを生成するメッセージのメッセージの種類を一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="1cdce-110">[Optional]-  Create a text file \<NameOfFileContainingSchemaList\> that lists the message types for messages for which the InfoPath form is to be generated.</span></span> <span data-ttu-id="1cdce-111">例: メッセージの種類には、MT103、MT102 などを指定できます。メッセージ名は、このテキスト ファイルを作成する代わりにコマンドラインを使用して直接渡されることができます。</span><span class="sxs-lookup"><span data-stu-id="1cdce-111">For e.g. Message Type can be MT103, MT102 etc. The Message names can directly be passed through the command line instead of creating this text file.</span></span>  
  
## <a name="syntax-of-command-usage-for-formgeneratorexe"></a><span data-ttu-id="1cdce-112">FormGenerator.exe のコマンドの使用法の構文</span><span class="sxs-lookup"><span data-stu-id="1cdce-112">Syntax of Command usage for FormGenerator.exe</span></span>  
  
```csharp  
FormGenerator [-b]   [-#] <TemplateFolderPath> [<TemplateFolderPath2>   
   [...<TemplateFolderPath#>]]  
 <DestinationFolderPath>     <DocumentSchemaLocation>  
   { [<SpaceSeparatedDocumentSchemaList>] |   [-f <NameOfFileContainingSchemaList>] }  
  
```  
  
 <span data-ttu-id="1cdce-113">各要素の説明は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="1cdce-113">Where:</span></span>  
  
-   <span data-ttu-id="1cdce-114">-b: です。指定した場合は、作成後にフォームがコンパイルされます。</span><span class="sxs-lookup"><span data-stu-id="1cdce-114">-b: If specified, forms will be compiled after creation.</span></span>  
  
-   <span data-ttu-id="1cdce-115">InfoPath ソリューションを作成するために使用するテンプレート ファイルを含むフォルダーの TemplateFolderPath:</span><span class="sxs-lookup"><span data-stu-id="1cdce-115">TemplateFolderPath: the folder containing the template files used to create the InfoPath solution</span></span>  
  
-   <span data-ttu-id="1cdce-116">-#:場合は、指定されたテンプレートを検索する複数のテンプレートのパス (多くの整数として # の番号を指定します) と指定された順序で。</span><span class="sxs-lookup"><span data-stu-id="1cdce-116">-#: If specified, templates will be looked up in multiple template paths (as many as the integer number # specifies) and in the order specified.</span></span>  
  
-   <span data-ttu-id="1cdce-117">フォームを作成するフォルダーの DestinationFolderPath:</span><span class="sxs-lookup"><span data-stu-id="1cdce-117">DestinationFolderPath: the folder where the forms will be created</span></span>  
  
-   <span data-ttu-id="1cdce-118">スキーマ (MT メッセージの基本クラスと共通のスキーマを含む) の DocumentSchemaLocation: の場所</span><span class="sxs-lookup"><span data-stu-id="1cdce-118">DocumentSchemaLocation: location of schemas (including base and common schemas for MT messages)</span></span>  
  
-   <span data-ttu-id="1cdce-119">SpaceSeparatedDocumentSchemaList: MT103 MT300 などのスキーマのスペースで区切られた一覧。</span><span class="sxs-lookup"><span data-stu-id="1cdce-119">SpaceSeparatedDocumentSchemaList: space-separated list of schemas like MT103 MT300.</span></span>  
  
-   <span data-ttu-id="1cdce-120">-f: を割り当てます。指定した場合、スキーマの一覧をファイルから読み取る必要があります。</span><span class="sxs-lookup"><span data-stu-id="1cdce-120">-f: If specified, the schema list needs to be read from a file.</span></span>  
  
-   <span data-ttu-id="1cdce-121">リストを含むファイルの名前を NameOfFileContainingSchemaList: です。</span><span class="sxs-lookup"><span data-stu-id="1cdce-121">NameOfFileContainingSchemaList: name of file containing the list.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="1cdce-122">上記のコマンドは、MT、MX、およびカテゴリ 0 の汎用コマンド メッセージ。</span><span class="sxs-lookup"><span data-stu-id="1cdce-122">The above command is a generic command for MT, MX and Category 0 messages.</span></span> <span data-ttu-id="1cdce-123">この種類のフォームを生成する特定のコマンドがで指定された、以下のセクションでします。</span><span class="sxs-lookup"><span data-stu-id="1cdce-123">Specific commands to generate these types of forms are given in the below sections.</span></span>