---
title: "このサンプルを実装する |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: cd788fd3-b070-40d5-a3d3-ac8e5208cc47
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0d2e07078f630852fc14bf8081a4bd1453a0dc7b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="implementing-the-sample"></a><span data-ttu-id="c5b57-102">このサンプルを実装します。</span><span class="sxs-lookup"><span data-stu-id="c5b57-102">Implementing the Sample</span></span>
<span data-ttu-id="c5b57-103">サンプルを実装するには、手順に従います。</span><span class="sxs-lookup"><span data-stu-id="c5b57-103">To implement the sample, proceed as follows:</span></span>  
  
1.  <span data-ttu-id="c5b57-104">SWIFT スキーマの新しいフォルダーを作成 (\<DocumentSchemaLocation > ユーティリティの構文で)。</span><span class="sxs-lookup"><span data-stu-id="c5b57-104">Create a new folder for SWIFT schemas (\<DocumentSchemaLocation> in the utility syntax).</span></span> <span data-ttu-id="c5b57-105">対象の InfoPath フォームの作成または変更することは、すべてのスキーマは、ユーティリティを実行するときに、このフォルダーに配置する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c5b57-105">All schemas for which you are going to create/modify the InfoPath forms must be located in this folder when you execute the utility.</span></span>  
  
2.  <span data-ttu-id="c5b57-106">InfoPath フォーム MT メッセージを生成する場合、コピー **SWIFT ベース Types.xsd**と**SWIFT 共通データ Types.xsd**から**\<ドライブ: > \Program Files\MicrosoftBizTalk Accelerator 用 SWIFT\<メッセージ パックのバージョン > メッセージ Pack\SWIFT Messages\A4SWIFT SRG\<メッセージ パックのバージョン > \Base スキーマ**SWIFT スキーマ用に作成したフォルダーにします。</span><span class="sxs-lookup"><span data-stu-id="c5b57-106">If you are generating InfoPath forms for MT messages then copy **SWIFT Base Types.xsd** and **SWIFT Common Data Types.xsd** from **\<drive :> \Program Files\Microsoft BizTalk Accelerator for SWIFT \<Message Pack Version> Message Pack\SWIFT Messages\A4SWIFT-SRG\<Message Pack Version>\Base Schemas** into the folder that you created for SWIFT schemas.</span></span>  
  
3.  <span data-ttu-id="c5b57-107">しようとする InfoPath フォームを作成し、手順 1. で SWIFT スキーマ用に作成したフォルダーをすべてのスキーマをコピーします。</span><span class="sxs-lookup"><span data-stu-id="c5b57-107">Copy all schemas for which you are going to create InfoPath forms into the folder that you created for SWIFT schemas in Step 1.</span></span>  
  
4.  <span data-ttu-id="c5b57-108">作成または作成した InfoPath フォーム テンプレート ソリューション ファイルを保存するフォルダーを指定 (\<DestinationFolderPath > ユーティリティの構文で)。</span><span class="sxs-lookup"><span data-stu-id="c5b57-108">Create or designate a folder to hold the created InfoPath form template solution files (\<DestinationFolderPath> in the utility syntax).</span></span> <span data-ttu-id="c5b57-109">出力フォルダーを作成しない場合、ユーティリティは作成同じパスと、コマンドラインで渡された名前を使用します。</span><span class="sxs-lookup"><span data-stu-id="c5b57-109">If you do not create the output folder, the utility will create the same with path and name that you pass on the command line.</span></span>  
  
5.  <span data-ttu-id="c5b57-110">[オプション]-テキスト ファイルを作成\<NameOfFileContainingSchemaList > InfoPath フォームを生成するメッセージのメッセージの種類を一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="c5b57-110">[Optional]-  Create a text file \<NameOfFileContainingSchemaList> that lists the message types for messages for which the InfoPath form is to be generated.</span></span> <span data-ttu-id="c5b57-111">例: メッセージの種類は MT103、MT102 などを指定できます。メッセージの名前は、このテキスト ファイルを作成する代わりにコマンドラインを使用して直接渡されます。</span><span class="sxs-lookup"><span data-stu-id="c5b57-111">For e.g. Message Type can be MT103, MT102 etc. The Message names can directly be passed through the command line instead of creating this text file.</span></span>  
  
## <a name="syntax-of-command-usage-for-formgeneratorexe"></a><span data-ttu-id="c5b57-112">FormGenerator.exe のコマンドの使用法の構文</span><span class="sxs-lookup"><span data-stu-id="c5b57-112">Syntax of Command usage for FormGenerator.exe</span></span>  
  
```csharp  
FormGenerator [-b]   [-#] <TemplateFolderPath> [<TemplateFolderPath2>   
   [...<TemplateFolderPath#>]]  
 <DestinationFolderPath>     <DocumentSchemaLocation>  
   { [<SpaceSeparatedDocumentSchemaList>] |   [-f <NameOfFileContainingSchemaList>] }  
  
```  
  
 <span data-ttu-id="c5b57-113">各要素の説明は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="c5b57-113">Where:</span></span>  
  
-   <span data-ttu-id="c5b57-114">フォームを作成後にコンパイルする b: 指定した場合。</span><span class="sxs-lookup"><span data-stu-id="c5b57-114">-b: If specified, forms will be compiled after creation.</span></span>  
  
-   <span data-ttu-id="c5b57-115">InfoPath ソリューションを作成するために使用するテンプレート ファイルを含むフォルダーの TemplateFolderPath:</span><span class="sxs-lookup"><span data-stu-id="c5b57-115">TemplateFolderPath: the folder containing the template files used to create the InfoPath solution</span></span>  
  
-   <span data-ttu-id="c5b57-116">-#: 場合は、指定されたテンプレートがルックアップする複数のテンプレート パスに (できるだけ番号 # 整数として指定) と指定された順序で。</span><span class="sxs-lookup"><span data-stu-id="c5b57-116">-#: If specified, templates will be looked up in multiple template paths (as many as the integer number # specifies) and in the order specified.</span></span>  
  
-   <span data-ttu-id="c5b57-117">フォームを作成するフォルダーの DestinationFolderPath:</span><span class="sxs-lookup"><span data-stu-id="c5b57-117">DestinationFolderPath: the folder where the forms will be created</span></span>  
  
-   <span data-ttu-id="c5b57-118">スキーマ (MT メッセージの基本クラスと共通のスキーマを含む) の DocumentSchemaLocation: の場所</span><span class="sxs-lookup"><span data-stu-id="c5b57-118">DocumentSchemaLocation: location of schemas (including base and common schemas for MT messages)</span></span>  
  
-   <span data-ttu-id="c5b57-119">SpaceSeparatedDocumentSchemaList: MT103 MT300 と同様にスキーマのスペースで区切られた一覧です。</span><span class="sxs-lookup"><span data-stu-id="c5b57-119">SpaceSeparatedDocumentSchemaList: space-separated list of schemas like MT103 MT300.</span></span>  
  
-   <span data-ttu-id="c5b57-120">-f: 場合、指定されたスキーマの一覧がファイルから読み取られる必要があります。</span><span class="sxs-lookup"><span data-stu-id="c5b57-120">-f: If specified, the schema list needs to be read from a file.</span></span>  
  
-   <span data-ttu-id="c5b57-121">リストを含むファイルの名前を NameOfFileContainingSchemaList: です。</span><span class="sxs-lookup"><span data-stu-id="c5b57-121">NameOfFileContainingSchemaList: name of file containing the list.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="c5b57-122">上記のコマンドは、MT、MX、およびカテゴリ 0 ジェネリック コマンドのメッセージ。</span><span class="sxs-lookup"><span data-stu-id="c5b57-122">The above command is a generic command for MT, MX and Category 0 messages.</span></span> <span data-ttu-id="c5b57-123">この種類のフォームを生成する特定のコマンドがで指定された、以下のセクションでします。</span><span class="sxs-lookup"><span data-stu-id="c5b57-123">Specific commands to generate these types of forms are given in the below sections.</span></span>